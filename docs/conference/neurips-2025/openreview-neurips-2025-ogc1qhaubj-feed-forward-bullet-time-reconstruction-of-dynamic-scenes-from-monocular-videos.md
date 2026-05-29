---
title: Feed-Forward Bullet-Time Reconstruction of Dynamic Scenes from Monocular Videos
title_zh: 前馈式子弹时间动态场景单目视频重建
authors: "Hanxue Liang, Jiawei Ren, Ashkan Mirzaei, Antonio Torralba, Ziwei Liu, Igor Gilitschenski, Sanja Fidler, Cengiz Oztireli, Huan Ling, Zan Gojcic, Jiahui Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=oGc1qHAUBJ"
tags: ["query:gs-slam"]
score: 8.0
evidence: 前馈式三维高斯散点实现动态场景实时新视角合成
tldr: 该论文提出了首个运动感知的前馈模型BTimer，用于从单目视频中实时重建动态场景的三维高斯散点表示。通过聚合上下文帧信息，在指定时刻（子弹时间）重建完整场景，并利用静态和动态数据集实现扩展性和泛化性。实验证明该方法能高效生成高质量的新视角合成结果，为动态场景重建提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 731, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1227, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 734, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 712, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 552, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 553, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1449, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1408, \"height\": 1016, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ogc1qhaubj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1413, \"height\": 560, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 627, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 679, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 712, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 625, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 603, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 592, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 422, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1083, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 493, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 428, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ogc1qhaubj/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1401, \"height\": 390, \"label\": \"Table\"}]"
motivation: 现有静态前馈重建模型难以泛化到动态场景，无法有效处理动态内容。
method: 提出运动感知的前馈模型BTimer，在目标时刻聚合多帧信息，以三维高斯散点重建动态场景。
result: 实现了实时动态场景重建与新视角合成，具有良好的泛化能力。
conclusion: BTimer首次将前馈模型用于动态场景重建，提升了效率与通用性。
---

## Abstract
Recent advancements in static feed-forward scene reconstruction have demonstrated significant progress in high-quality novel view synthesis. However, these models often struggle with generalizability across diverse environments and fail to effectively handle dynamic content. We present BTimer (short for Bullet Timer), the first motion-aware feed-forward model for real-time reconstruction and novel view synthesis of dynamic scenes. Our approach reconstructs the full scene in a 3D Gaussian Splatting representation at a given target (‘bullet’) timestamp by aggregating information from all the context frames. Such a formulation allows BTimer to gain scalability and generalization by leveraging both static and dynamic scene datasets. Given a casual monocular dynamic video, BTimer reconstructs a bullet-time scene within 150ms while reaching state-of-the-art performance on both static and dynamic scene datasets, even compared with optimization-based approaches.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究问题**：如何构建一个能够**有效处理动态场景**的前馈式三维重建模型？
*   **研究背景与动机**：
    *   **静态重建的局限**：现有静态场景的前馈重建模型（如PixelSplat, GS-LRM）虽然在新视角合成上取得进展，但难以直接扩展到动态场景。
    *   **动态重建的挑战**：
        *   **优化-based方法**：如HyperNeRF、RoDynRF等，通过引入深度、光流等先验来约束问题，但**逐场景优化耗时极长**（数小时至数天），难以规模化。
        *   **前馈-based方法**：此前几乎无前馈模型能处理动态场景。唯一的尝试（如L4GM）仅限于合成物体、固定视角，无法泛化到真实世界场景。
    *   **核心困难**：动态场景建模的复杂性和**缺乏4D监督数据**。
*   **整体含义**：论文提出了**BTimer**，这是**首个能实时重建和渲染动态场景的前馈式模型**，旨在以极快的速度（数百毫秒）和较低的成本，从随意拍摄的单目视频中重建出高质量的、可自由选择视角和时间的动态场景（即“子弹时间”效果）。

### 2. 论文提出的方法论

*   **核心思想 (子弹时间公式)**：
    *   模型接收一组**上下文帧**（RGB + 相机位姿 + 时间戳）和指定的**子弹（目标）时间戳**。
    *   模型的目标是直接从这些输入预测出在子弹时间戳下、以**3D高斯溅射（3D Gaussian Splatting, 3DGS）** 表示的完整场景。
*   **关键模块与技术细节**：
    *   **BTimer 重建模型**：
        *   **架构**：基于ViT的Transformer网络，包含24层自注意力模块。
        *   **输入处理**：将上下文帧切割为图块，与**Plücker相机嵌入**和**时间嵌入**（包括上下文帧时间嵌入和子弹时间嵌入）相加作为输入Token。
        *   **3DGS解码**：Transformer输出的Token通过一个线性层解码为12维的3D高斯参数（颜色、尺度、旋转四元数、不透明度、射线距离）。
        *   **像素对齐投影**：利用相机参数将预测的射线距离和方向转换为3D高斯的位置。
        *   **监督损失**：仅使用RGB空间的MSE和LPIPS损失进行监督，无需任何3D真值。
        *   **关键训练策略**：
            *   **上下文内监督**：监督时间戳随机选自上下文帧，迫使模型准确定位并重建这些已知时刻。
            *   **插值监督**：监督时间戳位于两个相邻上下文帧之间，强制模型对动态区域进行插值，避免高斯点“作弊”式地藏在相机近处。
    *   **新颖时间增强器（Novel Time Enhancer, NTE）**：
        *   **动机**：当子弹时间戳`t_b`不在原视频时间戳集合`T`中时，直接预测效果不佳，尤其在快速运动时。
        *   **设计**：一个**无3D**的ViT模型，输入上下文帧及其时间戳，并加上指定的**目标时间戳和目标相机位姿**Token，直接预测在该位姿和时间下的**RGB图像**。
        *   **集成**：先使用NTE生成子弹时间戳下的插值帧，再将该帧作为上下文输入主BTimer模型进行3D重建，从而消除拖影（ghosting）伪影。
*   **课程训练策略（Curriculum Training）**：
    *   **阶段一：低分到高分的静态预训练**：在**Objaverse、RE10K、MVImgNet、DL3DV**等大规模静态数据集上，先以128分辨率、4视图训练，再逐步微调到256和512分辨率，以获得泛化的3D先验。
    *   **阶段二：动态场景联合训练**：在阶段一基础上，加入**Kubric、PointOdyssey、DynamicReplica、Spring、PANDA-70M**等动态数据集进行微调，同时保留静态数据进行联合训练以稳定训练过程。
    *   **阶段三：长上下文窗口微调**：将输入上下文视图数从4增加到12，以适应更长的视频。

### 3. 实验设计

*   **评估数据集与Benchmark**：
    *   **动态场景**：
        *   **DyCheck iPhone数据集**：包含7个场景，3个同步相机，遵循其评估协议。
        *   **NVIDIA Dynamic Scene数据集**：包含9个场景，12个前向相机，采用DynNeRF中的循环时间+固定视角评估协议。
    *   **静态场景**：
        *   **RealEstate10K (RE10K) 基准**：用于评估对静态场景的向后兼容性。
        *   **Tanks & Temples 基准**：用于评估模型在未见数据集上的泛化能力。
    *   **定性评估**：在真实世界的**DAVIS数据集**上展示泛化效果。
*   **对比方法**：
    *   **优化-based方法**：TiNeuVox, NSFF, T-NeRF, Nerfies, **HyperNeRF**, DynNeRF, **RoDynRF**, 4D-GS, Casual-FVS, PGDVS等。
    *   **前馈式方法**：GPNR, PixelSplat, MVSplat, **GS-LRM**等（主要在静态任务上对比）。

### 4. 资源与算力

*   **训练资源**：
    *   **GPU**：训练在**32块NVIDIA A100 GPU**上进行。
    *   **训练时长**：BTimer的全流程训练耗时**约4天**。论文将其与LRM (384 GPU-days) 和 GS-LRM (192 GPU-days) 的训练成本进行了对比，认为其可接受。
    *   **批处理大小**：论文指出使用32块GPU是为了实现大batch size，因为其训练受益于大批量。
*   **推理资源与速度**：
    *   **GPU**：在**单个NVIDIA A100 GPU**上进行推理测试。
    *   **速度**：
        *   12视图，256分辨率重建：**150毫秒**。
        *   4视图，256分辨率重建：20毫秒。
        *   12视图，512分辨率重建：1.55秒。
        *   显存占用：均**小于10GB**。
    *   **渲染帧率**：输出的3DGS模型可以**115 FPS**实时渲染。

### 5. 实验数量与充分性

*   **实验数量与分组**：
    *   **主实验/对比实验**：在两个主要动态数据集（DyCheck, NVIDIA）和一个静态基准（RE10K）上，与十余种优化式和前馈式方法进行了定量对比，涵盖PSNR、SSIM、LPIPS等指标。
    *   **消融研究**：系统地消融了核心设计选择：
        1.  **课程训练策略**：包括是否进行3D静态预训练、是否仅用单一数据集（RE10K）预训练、动态训练阶段是否联合训练静态数据。
        2.  **插值监督**：评估有无该监督对重建质量（白边伪影）的影响。
        3.  **新颖时间增强器**：展示了NTE对处理快速/复杂运动后消除拖影的效果。
        4.  **上下文帧数量**：展示了增加帧数如何逐步补全场景。
*   **实验的充分性与公平性**：
    *   **充分性**：实验覆盖了动态和静态任务，包含了定量与定性结果，消融实验针对核心创新点设计，较为全面。
    *   **公平性**：在动态任务上，该方法与需要数小时优化的方法进行性能对比，明确标注了重建时间和GPU资源，对比是公平的。在静态任务上，与同为前馈式的SOTA模型进行了标准Benchmark对比，确保了可比性。对于因代码未公开而无法复现的Baseline，论文也明确注明为自行复现结果。

### 6. 论文的主要结论与发现

*   **核心结论**：BTimer验证了前馈式模型能够有效处理动态场景的重建和新视角合成任务。
*   **关键发现**：
    *   **子弹时间公式**是简单且有效的，它统一了静态和动态重建，使得模型能够从大规模动、静态数据中学习。
    *   **课程训练策略**至关重要。静态场景预训练提供了强大的3D先验，而动态联合训练则赋予了模型处理运动的能力。混合多数据集训练对泛化到未见场景至关重要。
    *   **插值监督**是缓解“作弊”伪影、提升重建质量的关键训练技巧。
    *   **新颖时间增强器**能有效处理快速运动，补偿像素对齐预测的归纳偏置。

### 7. 优点

*   **技术创新**：首创性地提出了适用于动态场景的前馈式实时重建模型，打破了此前前馈模型仅限于静态场景的限制。
*   **高效快速**：将动态场景重建速度从**数小时缩短到毫秒级**，推理和渲染速度极快，效率优势显著。
*   **统一框架**：“子弹时间”公式优雅地统一了静态和动态场景的重建，使模型具备向后兼容性，能够处理任意视频长度和帧率。
*   **训练策略**：精心设计的课程训练策略，充分挖掘了静态和动态数据集的潜力，克服了4D数据稀缺的难题。
*   **性能优秀**：在多个Benchmark上取得与耗时优化方法相媲美甚至更优的表现，展现了前馈模型的巨大潜力。

### 8. 不足与局限

*   **几何精度不足**：像素对齐的3D高斯表征导致重建的几何（深度图）不够精确，不如一些优化式方法。
*   **显式形变缺失**：模型隐式地建模运动对应关系，无法显式地表示场景中物体的时间形变和运动轨迹。文章在附录中展示了学习形变的可能性，但并非最终模型的核心能力。
*   **依赖准确位姿**：作为像素对齐方法，其对准确的相机位姿有刚性需求。虽然论文使用了SLAM系统来标注互联网视频，但位姿精度依然是影响最终重建质量的一个瓶颈。
*   **泛化性边界**：尽管在多个数据集上表现出色，但其在极端光照、反射或高度复杂的相机/物体运动下的鲁棒性未做深入探讨。
*   **输出非完整4D**：其输出是特定时刻的3D高斯序列，不是一个紧凑的、内含时间维度的完整4D表示。

（完）
