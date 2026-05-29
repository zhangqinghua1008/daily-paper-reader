---
title: "VTGaussian-SLAM: RGBD SLAM for Large Scale Scenes with Splatting View-Tied 3D Gaussians"
title_zh: VTGaussian-SLAM：基于视图绑定三维高斯泼溅的大规模场景RGB-D SLAM
authors: "Pengchong Hu, Zhizhong Han"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vkmi3jZtYG"
tags: ["query:gs-slam"]
score: 9.0
evidence: 提出使用视图绑定三维高斯和泼溅技术的大规模场景RGB-D SLAM方法
tldr: VTGaussian-SLAM针对现有基于3D高斯泼溅的RGB-D SLAM方法难以扩展至大规模场景的问题，提出视图绑定的3D高斯表示及相应的跟踪与建图策略。该方法通过只优化与当前视图相关的局部高斯集，避免在有限GPU内存中维护全部高斯的几何与颜色一致性，从而显著提升可扩展性。实验结果表明，该方法在大规模室内场景中实现了高质量的渲染与准确的相机跟踪，为实际应用中的大场景实时SLAM提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1783, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 554, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1776, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 863, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 862, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1776, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1775, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1757, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1766, \"height\": 980, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1761, \"height\": 982, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1779, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 859, \"height\": 1141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 866, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 862, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vkmi3jztyg/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 866, \"height\": 827, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1797, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1772, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1599, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1248, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1771, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1424, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1773, \"height\": 798, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1425, \"height\": 689, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1424, \"height\": 1334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1424, \"height\": 601, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1427, \"height\": 1251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1424, \"height\": 534, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1424, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1423, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1770, \"height\": 1909, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1777, \"height\": 1171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 995, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1166, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vkmi3jztyg/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1768, \"height\": 221, \"label\": \"Table\"}]"
motivation: 现有基于3D高斯的RGB-D SLAM方法因需优化全部高斯而无法扩展至大规模场景，受限于GPU内存和一致性维护。
method: 提出视图绑定的3D高斯表示，并设计局部跟踪与建图策略，仅优化与当前视图相关的局部高斯集，以支持大场景。
result: 在大规模场景中，该方法实现了高效的渲染质量与准确的相机姿态估计，优于现有不可扩展的方法。
conclusion: 通过视图绑定高斯和局部优化，解决了3D高斯SLAM的可扩展性瓶颈，为实际大规模环境下的实时稠密建图奠定基础。
---

## Abstract
Jointly estimating camera poses and mapping scenes from RGBD images is a fundamental task in simultaneous localization and mapping (SLAM). State-of-the-art methods employ 3D Gaussians to represent a scene, and render these Gaussians through splatting 
for higher efficiency and better rendering. However, these methods cannot scale up to extremely large scenes, due to the inefficient tracking and mapping strategies that need to optimize all 3D Gaussians in the limited GPU memories throughout the training to maintain the geometry and color consistency to previous RGBD observations. To resolve this issue, we propose novel tracking and mapping strategies to work with a novel 3D representation, dubbed view-tied 3D Gaussians, for RGBD SLAM systems. View-tied 3D Gaussians is a kind of simplified Gaussians, which is tied to depth pixels, without needing to learn locations, rotations, and multi-dimensional variances. Tying Gaussians to views not only significantly saves storage but also allows us to employ many more Gaussians to represent local details in the limited GPU memory. Moreover, our strategies remove the need of maintaining all Gaussians learnable throughout the training, while improving rendering quality, and tracking accuracy. We justify the effectiveness of these designs, and report better performance over the latest methods on the widely used benchmarks in terms of rendering and tracking accuracy and scalability. Please see our project page for code and videos at https://machineperceptionlab.github.io/VTGaussian-SLAM-Project.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

-   **研究动机**：同时定位与建图是计算机视觉与机器人领域的核心任务。目前最先进的方法使用三维高斯泼溅（3DGS）来表示场景，虽然渲染效率高、质量好，但在处理大规模场景时遇到瓶颈。
-   **核心问题**：现有基于三维高斯泼溅的SLAM方法（如SplaTAM、Gaussian-SLAM）需要在整个训练过程中，于有限的GPU内存里，持续优化场景中的所有高斯球，以维持几何与颜色一致性。这种全局优化策略限制了可用的高斯球数量，导致它们难以扩展到超大规模场景。
-   **整体含义**：本文旨在解决三维高斯泼溅SLAM的可扩展性问题。通过提出一种新型场景表示和配套的跟踪、建图策略，实现在不牺牲、甚至提升渲染和跟踪精度的前提下，将三维高斯泼溅SLAM应用于更大规模的场景。

### 2. 论文提出的方法论

-   **核心思想：视图绑定的三维高斯**
    -   将三维高斯简化并与深度像素绑定。每个高斯球仅由**颜色**、**半径**（方差）和**不透明度**三个属性组成，移除了原始三维高斯中的位置、旋转和协方差矩阵。
    -   高斯球的**位置完全由其对应的深度值和相机位姿决定**，无需单独学习或存储。这节省了**约64.3%的存储空间**，允许在有限内存中放置更多高斯球来表示局部细节。

-   **关键技术细节**
    -   **分段（Section）管理**：将连续`N`帧的视图绑定高斯组织成一个“段（Section）”。段内第一帧为“头帧（Head）”，其余为“常规帧”。这种组织方式有助于高效访问、补充缺失深度，并实现仅优化局部高斯球的策略。
    -   **跟踪策略**：
        -   **常规帧跟踪**：渲染并优化当前所在段的固定高斯球，最小化与当前帧的RGB和深度渲染误差。
        -   **头帧跟踪**：为解决仅用当前段跟踪导致的累积误差，系统会选择一个与当前视角重叠度高的**前方已完成段**（而非最近段）进行渲染和位姿优化。选择基于可见性检查、深度投影计数和预跟踪的最小渲染误差。
    -   **建图策略**：
        -   **头帧初始化**：在头帧的所有有效深度像素上初始化高斯球。
        -   **常规帧补全**：只利用当前段高斯球的渲染，在未被覆盖的区域补充初始化新的高斯球。
        -   **局部优化**：在建图优化高斯属性时，仅优化**当前段内部的可学习高斯球**，而保持其他段的高斯球冻结。通过渲染当前段、上一段和重叠段来维持局部的时空一致性。
    -   **捆绑调整（Bundle Adjustment）**：仅在处理每个段的头帧时进行局部捆绑调整，联合优化相机位姿和高斯属性，以平衡精度和稳定性。

-   **算法流程概览**
    1.  **输入**：当前帧的RGB-D图像。
    2.  **跟踪**：根据当前帧是头帧还是常规帧，选择对应的策略，渲染固定的高斯球来优化相机位姿。
    3.  **建图**：若为头帧，全面初始化高斯；若为常规帧，补全未被覆盖区域的高斯。然后，冻结大部分高斯，仅优化当前段内的高斯属性，使其与段内及附近帧保持一致。

### 3. 实验设计

-   **数据集与场景**：在多个广泛使用的基准数据集上进行了评估。
    -   **Replica**：合成室内数据集，8个场景，高保真重建。
    -   **TUM-RGBD**：真实世界数据集，3个常见场景，包含运动模糊。
    -   **ScanNet**：真实世界大规模室内数据集，6个场景。
    -   **ScanNet++**：高保真真实世界数据集，5个场景，序列中可能有突然大运动。
-   **基准与对比方法**：
    -   **NeRF-based 方法**：NICE-SLAM, Vox-Fusion, ESLAM, Point-SLAM等。
    -   **3DGS-based 方法**：SplaTAM, MonoGS, GS-SLAM, Gaussian-SLAM等。
    -   **含回环检测的方法**：Loopy-SLAM, LoopSplat, CG-SLAM（这些依赖预训练先验，属于不公平比较）。
-   **评估指标**：
    -   **跟踪精度**：ATE RMSE（绝对轨迹误差的均方根，单位：cm）。
    -   **渲染质量**：PSNR， SSIM， LPIPS。
    -   **重建质量**：深度L1误差，F1分数。

### 4. 资源与算力

-   **硬件平台**：所有实验在一张**NVIDIA RTX4090 GPU**上运行。
-   **运行时间**：在Replica数据集上，平均每帧跟踪时间为**1.92秒**，每帧建图时间为**2.43秒**。该速度与其他基于三维高斯泼溅的方法（SplaTAM, Gaussian-SLAM）相当。
-   **内存消耗**：论文强调了其方法在内存效率上的巨大优势。虽然未给出全局的峰值显存占用，但通过表格对比了可使用的总高斯球数量。其方法在整个场景中可初始化**97823K个高斯球**，远超SplaTAM（5832K）和Gaussian-SLAM（32592K），表明其在有限内存内的扩展能力极强。
-   **训练时长**：论文未明确提及离线预训练或总训练时长，因为SLAM任务通常是增量在线的。

### 5. 实验数量与充分性

-   **实验数量充足**：论文在**4个主流数据集、超过20个独立场景序列**上进行了详细的评估，覆盖合成、真实、小规模、大规模等多种环境，实验具有深度和广度。
-   **实验全面且公平**：
    -   **性能对比**：与NeRF-based和3DGS-based两大类、超过10种最先进方法进行了全面比较，并明确指出依赖“预训练先验”的方法（如LoopSplat）是不公平的比较，体现了客观性。
    -   **消融实验**：设计了多组消融实验，验证了**视图绑定高斯表示**（vs. 非绑定、各向异性）、**段长度**、**重叠段选择策略**和**可见性掩码**等核心设计的有效性，论证充分。
    -   **额外分析**：分析了深度噪声鲁棒性、位姿累积误差抑制效果、渲染与优化过程可视化等，增强了方法的可解释性。

### 6. 论文的主要结论与发现

-   **视图绑定的简化高斯表示**在SLAM任务中是高效的，能在节省大量存储的同时允许使用更多高斯球表达细节，显著提升渲染质量。
-   提出的**分段式局部跟踪与建图策略**，通过在不同时机选择不同段进行渲染和优化，成功移除了维持全局一致性的需求，有效缓解了位姿累积误差。
-   该方法在多个基准数据集上，在**渲染质量（PSNR、SSIM、LPIPS）** 和**跟踪精度（ATE）** 方面达到了当时最好的性能，尤其在大规模场景的渲染和可扩展性上优势明显。

### 7. 优点

-   **高存储效率与强可扩展性**：简化高斯表示及分段管理是推动三维高斯泼溅SLAM走向大规模场景应用的关键创新。
-   **巧妙的跟踪策略**：通过选择“既重叠又靠前”的段进行跟踪，而非仅依赖最近帧或最近关键帧，在利用高质量渲染的同时有效抑制了累积误差，是一种很好的权衡。
-   **实验扎实全面**：从合成到真实、从小房间到整层楼甚至室外（KITTI），与大量基线方法在多个维度上进行比较，并有详尽的消融和可视化分析，论证严谨。
-   **优越的性能表现**：在渲染质量上取得了极具竞争力的提升，特别是在有挑战的真实数据集（TUM-RGBD, ScanNet）上，PSNR等指标远超其他方法。

### 8. 不足与局限

-   **对深度图的强依赖性**：高斯的位置完全由深度图决定。虽然论文证明了其对深度噪声具有一定鲁棒性，但深度图的质量（空洞、噪声）会直接影响初始化质量。对于纯视觉（无深度）场景不适用。
-   **静止场景假设**：方法的核心是基于静态场景的建图，未考虑动态物体，这限制了其在真实动态环境（如KITTI实验中需要避开有动态物体的片段）中的直接应用。
-   **非完整SLAM系统**：与LoopSplat等方法相比，该方法未集成全局回环检测与位姿图优化模块，在超长距离轨迹上仍可能存在无法消除的全局累积漂移。
-   **固定半径初始化**：高斯半径基于一个简化的启发式规则（深度/焦距）初始化，可能在纹理稀少或重复纹理区域不够灵活，影响初始收敛。
-   **运行效率尚有提升空间**：虽然存储效率极高，但秒级别的每帧处理速度（~2s）距离实时应用（>30fps）仍有较大差距，后续可探索工程优化或加速渲染技术。

（完）
