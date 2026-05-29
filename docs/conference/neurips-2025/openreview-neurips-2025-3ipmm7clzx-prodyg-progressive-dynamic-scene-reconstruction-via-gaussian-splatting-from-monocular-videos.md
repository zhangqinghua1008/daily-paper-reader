---
title: "ProDyG: Progressive Dynamic Scene Reconstruction via Gaussian Splatting from Monocular Videos"
title_zh: "ProDyG: 基于单目视频的渐进式动态场景高斯泼溅重建"
authors: "Shi Chen, Erik Sandström, Sandro Lombardi, Siyuan Li, Martin R. Oswald"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3iPmM7cLzx"
tags: ["query:gs-slam"]
score: 10.0
evidence: 用于动态场景的单目3DGS SLAM系统，包含位姿跟踪
tldr: ProDyG提出了一种基于单目视频的在线动态场景重建方法，通过在SLAM系统中解耦静态和动态部分实现。该方法采用新颖的运动掩码策略鲁棒地跟踪相机位姿，并利用渐进式适应重建动态部分，同时支持RGB和RGB-D输入，显著提升了动态环境下的建图与定位能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ipmm7clzx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ipmm7clzx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ipmm7clzx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ipmm7clzx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 795, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ipmm7clzx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 760, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ipmm7clzx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 395, \"label\": \"Table\"}]"
motivation: 现有SLAM方法大多仅去除动态物体或需要RGB-D输入，缺乏在线全局一致性和精细外观建模。
method: 提出ProDyG，在SLAM系统中解耦静态与动态部分，利用运动掩码进行鲁棒位姿跟踪和渐进式动态重建。
result: 实现了从单目视频的在线动态场景重建，位姿跟踪稳定，动态物体外观建模精细。
conclusion: ProDyG为单目动态场景SLAM提供了一种有效方案，推动了实时三维重建的实用性。
---

## Abstract
Achieving truly practical dynamic 3D reconstruction requires online operation, global pose and map consistency, detailed appearance modeling, and the flexibility to handle both RGB and RGB-D inputs. However, existing SLAM methods typically merely remove the dynamic parts or require RGB-D input, while offline methods are not scalable to long video sequences, and current transformer-based feedforward methods lack global consistency and appearance details. To this end, we achieve online dynamic scene reconstruction by disentangling the static and dynamic parts within a SLAM system. The poses are tracked robustly with a novel motion masking strategy, and dynamic parts are reconstructed leveraging a progressive adaptation of a Motion Scaffolds graph. Our method yields novel view renderings competitive to offline methods and achieves on-par tracking with state-of-the-art dynamic SLAM methods.

---

## 论文详细总结（自动生成）

好的，请查收基于所提供论文的详细中文总结。

---

### **1. 论文的核心问题与整体含义**

*   **核心问题**：现有方法难以同时满足实用化动态3D场景重建的四个关键需求：
    *   **在线操作**：需紧密耦合位姿估计与地图重建，以支持长视频的可扩展处理。
    *   **全局一致性**：保证长时序下的相机位姿和地图模型不发生漂移。
    *   **精细外观建模**：使用3D高斯泼溅等表达力强的表示，实现照片级渲染。
    *   **输入灵活性**：兼容纯RGB和RGB-D两种输入模式。
    *   **现有方案不足**：
        *   动态SLAM方法大多忽略或仅剔除动态物体，不进行重建。
        *   离线重建方法计算成本高，无法扩展至长视频。
        *   Transformer前馈方法缺乏全局一致性，仅生成点云。
*   **整体含义**：本文旨在提出一个能同时满足上述四大需求的统一框架，实现从单目视频中稳健、高质量、在线的动态场景重建，这是推动3D计算机视觉走向实际应用（如机器人、AR/VR）的关键一步。

### **2. 论文提出的方法论**

ProDyG的核心思想是在一个SLAM系统中解耦并分别重建静态背景和动态前景，主要由三部分构成：运动无关的在线跟踪、场景解耦表示、渐进式动态场景重建。

*   **核心思想**
    *   **解耦重建**：在一个SLAM框架内，将场景显式分离为静态高斯和随时间变化的动态高斯，由独立的管线进行处理和优化。
    *   **由粗到精的运动掩码**：利用光流残差生成粗运动掩码，用于鲁棒位姿估计；再结合语义分割模型（SAM2）提炼出精细掩码，用于准确分离动静区域。

*   **关键技术细节**
    *   **运动掩码预测与鲁棒跟踪（第3.1节）**
        *   **粗掩码生成**：基于光流残差 `rij` 计算每个像素的归一化平均运动幅度 `ri(x, y)`，通过阈值化（如前20%）生成粗掩码 `Ci`，在相机位姿优化（DBA）时抑制动态区域权重。
        *   **精细掩码优化**：以粗掩码连通域的重心作为点提示，输入SAM2模型生成物体级的精细动态掩码 `Mi`。该掩码在后续DBA优化中取代粗掩码，提供更精准的动态像素剔除，提升跟踪鲁棒性。掩码阈值可随场景自适应调整。
    *   **静态与动态解耦表示（第3.2节）**
        *   **静态高斯 (G_s)**：世界坐标系下固定不变的一组3D高斯。
        *   **动态高斯 (G_d(t))**：表达为时间的函数。每个动态高斯被定义为相对于一个参考时间戳的状态，并通过一个运动场变形到查询时间戳。
    *   **渐进式动态场景重建（第3.3节）**
        *   **非关键帧处理**：为获取密集时域监督，通过构建局部因子图优化得到非关键帧的相机位姿，并通过融合关键帧深度重投影和单目深度估计，为它们生成对齐的深度图。
        *   **动态表示（MoSca）**：采用“运动支架”图 `(V_d, E_d)` 表示底层运动。每个节点 `v(m)` 为一个随时间变化的刚体变换序列。动态高斯通过定义在每个节点上的双重四元数混合（DQB）蒙皮函数驱动。
        *   **渐进式构建与更新**：
            1.  **初始化**：对关键帧窗口内的精细动态掩码区域，利用点跟踪器生成2D轨迹并提升到3D，初始化Motion Scaffolds节点和动态高斯。随后交替进行几何正则化优化（ARAP等损失）和光度优化（RGB、深度、轨迹、掩码损失）。
            2.  **增量扩展**：新帧到来时，识别并扩展已有轨迹，对新见区域补充点跟踪，实现Motion Scaffolds和动态高斯的时域增长，并在扩展窗口内联合优化。
            3.  **关键损失函数**：除常规损失外，引入新颖的**运动掩码损失 `L_mask`**，惩罚动态高斯在静态像素上渲染出的不透明度，确保动静区域的清晰分离。

### **3. 实验设计**

*   **数据集与场景**
    *   **相机跟踪评估**：Bonn RGB-D Dynamic Dataset 和 TUM RGB-D Dataset 中的4个代表性动态序列。
    *   **新视角合成评估**：iPhone Dataset 中的5个动态序列。
*   **基准方法**
    *   **跟踪任务**：对比了多种RGB-D SLAM和纯RGB SLAM方法，包括静态重建、鲁棒性方法和动态重建方法，如 ORB-SLAM2， DynaSLAM, DROID-SLAM, MegaSaM, WildGS-SLAM, DynaMoN 等。主基线为其基础的Splat-SLAM。
    *   **渲染任务**：对比了SOTA离线动态重建方法 Shape of Motion， MoSca， Gaussian Marbles，以及在线方法 DynOMo。
*   **评估指标**
    *   **跟踪**：ATE RMSE [cm]。
    *   **渲染**：PSNR, SSIM, LPIPS。

### **4. 资源与算力**

*   文中在“4.1 实验设置”中提到：所有实验在一台配备 **AMD EPYC 7H12 或 7742 CPU** 和 **一块NVIDIA A6000 GPU** 的集群上运行。
*   **未明确说明**：论文没有报告完整重建单个序列的总时长、GPU显存占用等详细算力消耗情况。

### **5. 实验数量与充分性**

*   **实验组数**：
    *   **跟踪实验**：在2个数据集上，与超过15种基准方法进行了性能比较。
    *   **渲染实验**：在1个数据集上，与4种SOTA方法进行了定量和定性比较。还区分了是否在线重建、在线跟踪、纯RGB输入等多种细分设置，增强了分析的维度。
*   **充分性与公平性**：
    *   实验设计覆盖了方法的主要贡献点（跟踪和重建），对比既有经典SLAM又有最新的动态场景重建工作，较为全面。
    *   公平性上，论文区分了不同方法的输入模态和操作模式，并使用标准的评估协议，基本确保了对比的客观性。
    *   缺点方面，跟踪实验仅选取了数据集中的4个序列，样本量相对较小，且未包含任何消融实验来验证各组件（如精细掩码、运动掩码损失）的独立贡献，这是一个显著不足。

### **6. 论文的主要结论与发现**

*   ProDyG是首个能够完全在线、从单目RGB视频中实现高质量动态场景新视角合成的框架。
*   该方法的相机跟踪性能与最先进的动态SLAM方法相当，同时还能显式重建完整的动态模型。
*   其新视角合成的质量，即便在更难的在在线设定下，也超越了离线方法Shape of Motion，并可与顶级离线方法MoSca比肩。
*   一种有效的策略是在SLAM后端通过抑制动态区域进行鲁棒跟踪，同时通过独立的管线负责动态部分的完整重建。

### **7. 优点**

*   **问题导向与实用性**：准确识别并针对实际动态3D重建的四大核心需求提出一站式解决方案。
*   **技术创新性**：提出的由粗到精的运动掩码策略，将传统几何方法与SAM2的优势互补，有效兼顾了跟踪鲁棒性和重建精度。新颖的运动掩码损失有助于动静态的精确分离。
*   **方法先进性与灵活性**：是首个支持纯RGB在线输入的高质量动态重建方法，填补了领域空白。实验结果展示了令人瞩目的在线渲染质量。
*   **系统完备性**：构建了一个从跟踪、掩码预测、静态建图到动态重建的完整、复杂系统，解决了各环节间的耦合问题。

### **8. 不足与局限**

*   **实验覆盖不足**：
    *   **缺少消融实验**：未能定量验证各核心组件（如SAM2精细掩码、运动掩码损失）的独立贡献。
    *   **跟踪评估序列少**：每个数据集仅测试了4个序列，结果的统计稳健性有限。
    *   **缺乏实时性数据**：虽为“在线”方法，但未报告处理帧率，其计算成本可能离实际落地尚有距离。
*   **计算复杂度**：方法集成了Splat-SLAM、SAM2、CoTracker3等多个大型模型，计算开销巨大，对硬件要求高。
*   **应用限制**：
    *   **视野外物体处理**：难以处理移出视野再重新出现的动态物体，容易导致重建变形。
    *   **大视角变化受限**：无法合成信息缺失严重的大视角新视图。
    *   **需要逐场景优化**：与多数动态视图合成方法一样，无法泛化到新场景，部署到新环境需进行测试时优化。

（完）
