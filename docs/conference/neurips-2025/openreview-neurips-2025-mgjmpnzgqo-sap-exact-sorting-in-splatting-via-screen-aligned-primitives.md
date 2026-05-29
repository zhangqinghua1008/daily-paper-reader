---
title: "SAP: Exact Sorting in Splatting via Screen-Aligned Primitives"
title_zh: "SAP: 屏幕对齐基元实现泼溅中的精确排序"
authors: "Zhanke Wang, Zhiyan Wang, Kaiqiang Xiong, Jiahao Wu, Yang Deng, Ronggang Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=mGjmPnzGQo"
tags: ["query:gs-slam"]
score: 7.0
evidence: 通过屏幕对齐基元改善三维高斯泼溅的新视角合成渲染效果
tldr: 针对3DGS因忽略高斯原语厚度和重叠交互导致的排序不准和伪影问题，SAP提出屏幕对齐的各向异性核，为每个视图生成与像平面平行的基元，实现实时的逐像素精确排序，提升了渲染质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 721, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 1175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1116, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1421, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mgjmpnzgqo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1425, \"height\": 399, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 482, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1427, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1423, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1161, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1158, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mgjmpnzgqo/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1155, \"height\": 432, \"label\": \"Table\"}]"
motivation: 3DGS优化中忽略厚度和重叠导致排序不准，产生跳动伪影。
method: 采用屏幕对齐各向异性核生成平行基元，单次全局排序即可正确深度顺序。
result: 实现了实时逐像素正确排序，消除了渲染伪影。
conclusion: 屏幕对齐基元有效解决了3DGS的排序精度问题。
---

## Abstract
Recently, 3D Gaussian Splatting (3DGS) has achieved state-of-the-art rendering results. However, its efficiency relies on simplifications that disregard the thickness of Gaussian primitives and their overlapping interactions. These simplifications can lead to popping artifacts due to inaccurate sorting, thereby affecting the rendering quality. In this paper, we propose Screen-Aligned Primitives (SAP), an anisotropic kernel that generates primitives parallel to the image plane for each view. Our rasterization pipeline enables full per-pixel ordering in real time. Since the primitives are parallel for a given viewpoint, a single global sorting operation suffices for correct per-pixel depth ordering. We formulate 3D reconstruction as a combination of a 3D-consistent decoder and 2D view-specific primitives, and further propose a highly efficient decoder to ensure 3D consistency.  Moreover, within our framework, the primitive function values remain consistent between view space and screen space, allowing arbitrary radial basis functions (RBFs) to represent the scene without introducing projection errors. Experiments on diverse datasets demonstrate that our method achieves state-of-the-art rendering quality while maintaining real-time performance.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将基于您提供的论文内容，以中文、Markdown 格式，对《SAP: Exact Sorting in Splatting via Screen-Aligned Primitives》这篇论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究背景与动机**:
    *   3D 高斯泼溅 (3DGS) 虽然实现了最先进的渲染效果与实时性能，但其效率依赖于简化假设，即忽略高斯基元（Gaussian primitives）的厚度和它们之间的重叠相互作用。
    *   该简化导致了严重的“跳动伪影”（popping artifacts），其根源在于不精确的深度排序。3DGS 仅基于基元中心点进行全局深度排序，当各向异性的椭球体重叠时，这种排序对于某些像素是错误的，导致不正确的透明度混合。
*   **核心问题**:
    *   如何在保持实时渲染效率的前提下，解决 3DGS 中因不精确排序导致的渲染伪影问题，实现精确的逐像素（per-pixel）深度排序。
*   **整体含义**:
    *   论文提出通过改变场景的表征方式——从自由定向的3D椭球体转变为与屏幕对齐的2D平面基元，从根本上消除了基元重叠和排序歧义，从而在不增加计算开销的情况下提升渲染质量。

### 2. 论文提出的方法论

*   **核心思想: 3D一致解码器 + 2D视图特定基元**
    *   论文将3D重建过程分解为一个**3D一致解码器**和一个基于**2D基元的渲染器**。解码器负责生成视图特异性的基元属性，而渲染器则处理这些简单的2D基元。
*   **关键技术细节**:
    *   **3D一致解码器 (3D-Consistent Decoder)**:
        *   基于 **FiLM (Feature-wise Linear Modulation)** 架构，这是一个常用于可控图像生成的网络。
        *   **方向编码**: 使用观测方向作为条件信号。实验发现，使用**球谐函数 (Spherical Harmonics, SH)** 对方向进行编码效果最佳。
        *   **流程**: 解码器输入锚点特征和SH编码后的视图方向，通过FiLM层用方向信号调制特征，最终输出基元的2D旋转角度 (`θ`) 和各向异性缩放因子 (`s`) 等属性。
    *   **屏幕对齐基元 (SAP)**:
        *   **表征**: 每个基元被约束为与当前视图的图像平面平行。这通过在视图空间内构建一个2D的协方差矩阵 (`Σv`) 来实现，该矩阵仅包含2D旋转和缩放：
            `Σv = Rv Sv STv RTv`
        *   **精确排序**: 由于所有基元对于一个特定视点都是平行的，它们**永远不会相交**。因此，只需根据基元中心点的视图空间z坐标进行一次全局排序，即可保证所有像素的深度顺序都是正确的，这从根源上消除了排序错误。
    *   **无偏投影 (Unbiased Projection)**:
        *   因为平行基元内部没有深度变化，其从视图空间到屏幕空间的投影简化为一个以基元深度 `t` 为中心的简单几何缩放：
            `P = [fx/t, 0; 0, fy/t]`
        *   这避免了3DGS中使用雅可比矩阵进行仿射近似引入的投影误差。论文证明了在此框架下，视图空间和屏幕空间的马氏距离等价，因此两者的函数分布完全等价。该特性允许使用**任何任意的径向基函数 (RBF)** 来表示场景，例如广义高斯核，而不会引入投影误差。

*   **优化与训练**:
    *   **改进的致密化策略**: 针对各向异性表示在大视角变化下可能失败的问题，提出使用**最大位置梯度**作为锚点增长的判据。将平均梯度和最大梯度相结合，有助于在从特定视角重建不佳的区域（如空洞）增加点密度，提升重建质量。
    *   **损失函数**: 沿用3DGS的L1损失和SSIM损失的组合。

### 3. 实验设计

*   **数据集/场景**:
    *   **Mip-NeRF360**: 9个场景（包含无界室外和室内环境）。
    *   **Tanks&Temples**: 2个场景。
    *   **Deep Blending**: 2个场景。
    *   这些数据集覆盖了从室内有界到室外无界的多种环境，提供了全面的评估。
*   **Benchmark与对比方法**:
    *   **评价指标**: 标准的PSNR、SSIM、LPIPS。
    *   **对比方法**: 与多种最先进技术进行比较，包括 **Mip-NeRF360**、**3DGS**、**2DGS**、**Scaffold-GS**、**StopThePop**、**DisC-GS** 和 **3DGS-MCMC**。对比非常全面，涵盖了基于NeRF、传统3DGS、改进排序、改进致密化等多个方向。

### 4. 资源与算力

*   **论文明确指出**: 所有实验均在**单个NVIDIA L40S GPU**上完成。
*   **训练时长**: 消融实验部分（Table 5）提供了一个具体场景的例子。在Tanks&Temples的"Train"场景上，使用带有最大梯度致密化的SAP方法训练耗时**32分钟**，而无此策略时为26分钟。作为对比，基线Scaffold-GS的相应训练时间分别为29分钟和24分钟。
*   **推理帧率**: 在同一场景下，SAP的渲染帧率为**75 FPS**，Scaffold-GS为79 FPS，两者性能相当。

### 5. 实验数量与充分性

*   **实验数量**: 论文进行了约十余组主要实验。
    *   **主实验**: 在3个主要数据集上的定量评估（Table 1）和定性可视化（Fig. 3）。
    *   **消融实验**: 非常详尽，至少包括5组，用于验证所提各个组件的有效性：
        1.  SAP各组件（3D基元 vs SAP、FiLM解码器、SH编码、最大梯度）的贡献（Table 2）。
        2.  不同方向编码方式的对比（Table 3）。
        3.  不同核函数的对比（Table 4）。
        4.  致密化策略的可视化对比（Fig. 4）。
        5.  广义高斯核不同参数的对比（Appendix Table 6）以及计算资源对比（Appendix Table 5）。
*   **充分性与客观性**:
    *   **充分性**: 实验设计是充分的。消融研究系统地隔离并验证了每个提出的新组件（SAP、FiLM+SH编码、致密化策略）的有效性。与多种最新方法的对比也证明了其整体优越性。
    *   **客观公平性**: 对比是公平的。论文明确指出其实现基于Scaffold-GS框架，并保留了其大部分参数设置，确保了与基线的公平比较。同时，也指出来由于数据预处理（下采样）方式不同，可能与其他方法（如3DGS-MCMC）的结果存在细微差异，体现了严谨性。

### 6. 论文的主要结论与发现

*   **核心结论**: 提出的屏幕对齐基元（SAP）框架是一种有效的3D表征方式，它通过构建与视图平面平行的基元，实现了对基元的**精确逐像素排序**，从根本上解决了3DGS中的排序伪影问题。
*   **主要发现**:
    1.  **质量与效率兼得**: SAP在多个数据集上取得了**最先进的渲染质量**（PSNR/SSIM最高），同时**维持了实时渲染性能**，甚至在恒定时间内比基准略快。
    2.  **无偏投影的优势**: 平行基元的设计实现了**无偏的精确投影**，为在框架内使用更灵活、更具表达力的核函数（如广义高斯核）铺平了道路。
    3.  **组件有效性**: FiLM架构结合球谐函数编码作为3D一致解码器，以及基于最大位置梯度的致密化策略，都对渲染质量的提升起到了关键作用。

### 7. 优点

*   **方法创新且优雅**: 通过将基元约束为与屏幕平行这一简单但强大的思想，从根本上解决了复杂的排序问题，概念清晰，实现巧妙。
*   **理论扎实**: 框架保证了逐像素精确排序和无偏投影，并给出了严谨的数学证明，这为未来的研究（如探索新核函数）提供了坚实的基础。
*   **性能优异**: 在不牺牲渲染速度的前提下，显著提升了渲染质量，在主要数据集上超越了对比的多种SOTA方法，包括一些专门解决排序问题的方法（如StopThePop）。
*   **实验完备**: 消融实验设计精细，清晰地展示了每个提出组件的独立贡献，增强了结论的说服力。

### 8. 不足与局限

*   **核函数探索有限**: 论文承认，虽然框架支持任意基函数，但目前仅探索了径向基函数（高斯、广义高斯）。对于非对称核等更多样化核函数的潜力尚未挖掘。
*   **几何重建能力缺失**: 方法专注于提升渲染质量，但未考虑表面法线，这可能导致在需要从模型提取网格的应用（如表面重建）中面临挑战。这是相对于2DGS等方法的一个功能局限。
*   **广义高斯核的性能**: 实验发现，作为高斯核超集的广义高斯核（SAP-Ges）渲染质量反而不如标准高斯核（SAP-Gaussian）。论文推测这是由于优化复杂度增加，尚未找到最佳学习参数。这表明核函数的灵活性并不总能直接带来性能提升。
*   **计算资源**: 虽然在单GPU上完成实验，但未提及系统内存等其他资源的具体消耗。

（完）
