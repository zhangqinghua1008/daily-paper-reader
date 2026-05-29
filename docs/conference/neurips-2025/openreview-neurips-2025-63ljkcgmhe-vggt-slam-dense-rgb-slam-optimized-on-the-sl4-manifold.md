---
title: "VGGT-SLAM: Dense RGB SLAM Optimized on the SL(4) Manifold"
title_zh: "VGGT-SLAM: 在SL(4)流形上优化的稠密RGB SLAM"
authors: "Dominic Rosario Maggio, Hyungtae Lim, Luca Carlone"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=63ljkCGMhE"
tags: ["query:gs-slam"]
score: 9.0
evidence: 使用未标定单目相机的稠密RGB SLAM系统
tldr: VGGT-SLAM利用前馈场景重建方法VGGT产出的子图，在SL(4)流形上全局对齐，解决了未标定单目相机下15自由度投影模糊问题，构建了稠密RGB SLAM系统，不需三维高斯表示，直接实现相机跟踪和地图构建。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1207, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 967, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 971, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1429, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1424, \"height\": 952, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1420, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 857, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1350, \"height\": 1363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-63ljkcgmhe/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1431, \"height\": 1120, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1395, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1474, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 739, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1028, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 738, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1394, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1473, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1158, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1379, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-63ljkcgmhe/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 636, \"height\": 208, \"label\": \"Table\"}]"
motivation: 未标定单目相机下相似变换对齐不足以处理投影模糊。
method: 基于VGGT前馈重建子图，通过SL(4)流形上的优化恢复一致场景。
result: 实现了未标定单目相机下的稠密RGB SLAM系统。
conclusion: 利用投影几何和流形优化克服了未标定相机的SLAM挑战。
---

## Abstract
We present VGGT-SLAM, a dense RGB SLAM system constructed by incrementally and globally aligning submaps created from the feed-forward scene reconstruction approach VGGT using only uncalibrated monocular cameras. While related works align submaps using similarity transforms (i.e., translation, rotation, and scale), we show that such approaches are inadequate in the case of uncalibrated cameras. In particular,  we revisit the idea of reconstruction ambiguity, where given a set of uncalibrated cameras with no assumption on the camera motion or scene structure, the scene can only be reconstructed up to a 15-degrees-of-freedom projective transformation of the true geometry. This inspires us to recover a consistent scene reconstruction across submaps by optimizing over the SL(4) manifold, thus estimating 15-degrees-of-freedom homography transforms between sequential submaps while accounting for potential loop closure constraints. As verified by extensive experiments, we demonstrate that VGGT-SLAM achieves improved map quality using long video sequences that are infeasible for VGGT due to its high GPU requirements. Our code is available at https://github.com/MIT-SPARK/VGGT-SLAM.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化中文总结。

### 1. 论文的核心问题与整体含义

-   **核心问题**：如何利用视觉几何基础变换器（VGGT）这一先进的前馈式场景重建模型，构建一个能够处理长视频序列的稠密同时定位与建图（SLAM）系统。
-   **研究动机**：
    -   VGGT虽能直接从未标定的单目RGB图像中输出高质量的场景重建（点云、相机位姿），但因受到GPU显存的限制，单次推理只能处理有限数量的图像（例如约60张），无法直接应用于大规模场景。
    -   一个直观的解决方案是将长序列拆分成多个有重叠图像的子图，然后用相似变换（Sim(3)）进行对齐。
-   **关键挑战**：论文指出，在使用未标定相机且场景先验不可靠时，VGGT重建出的子图与真实场景之间存在**投影模糊**，即它们可能相差一个高达15自由度的射影变换（单应矩阵），而不仅仅是7自由度的相似变换。因此，传统的Sim(3)对齐方法从根本上讲是不充分的。
-   **整体含义**：论文旨在提出一种新的SLAM框架，通过在SL(4)流形上进行全局优化，对齐VGGT生成的子图，从而解决该投影模糊问题，构建一个一致、精确的大规模场景重建。

### 2. 论文提出的方法论

-   **整体框架**：VGGT-SLAM并非直接在SLAM中进行逐帧的位姿和深度估计，而是将VGGT视为一个“子图生成器”，然后作为一个后端优化问题来对齐所有子图。
-   **关键技术细节**：
    -   **增量式子图构建**：
        1.  通过计算光流估计帧间视差，当视差超过阈值选为关键帧。
        2.  每当最新关键帧列表长度达到预设值 `w` 时，构建一个新的图像集。该图像集包含：来自前一子图的一帧、当前的关键帧列表以及为闭环检测而添加的少量图像。
        3.  将该图像集送入VGGT，得到一个包含稠密点云、相机位姿和深度的局部子图。
    -   **投影模糊的建模与局部对齐**。
        -   认识到子图间的点云对齐不应是SE(3)或Sim(3)变换，而应是一个15自由度、行列式为1的单应矩阵 `H`，它属于特殊线性群SL(4)。
        -   基于子图间共享图像的稠密对应关系，通过求解一个齐次线性系统并使用5点RANSAC算法来鲁棒地估计相邻子图间的相对单应矩阵 `Hij`。
    -   **闭环检测**：
        -   使用SALAD模型为每个关键帧计算图像描述子。
        -   在构建新子图时，检索过去子图中与当前关键帧最相似的图像，并作为闭环候选帧添加到当前子图的图像集中。
        -   同样利用共享帧的稠密对应关系，直接计算当前子图与历史子图之间的相对单应矩阵，作为闭环约束。
    -   **SL(4)流形上的后端优化**：
        -   将所有估计得到的子图间相对单应矩阵（里程计和闭环约束）作为因子，图节点为各子图在全局坐标系下的绝对单应矩阵 `Hi`。
        -   在SL(4)李群流形上构建基于最大后验估计的非线性最小二乘因子图优化问题，代价函数用于最小化相对测量误差。
        -   利用李代数`sl(4)`进行参数化，并通过Levenberg-Marquardt优化器迭代求解，最终得到将所有子图变换到一致全局坐标系下的绝对单应矩阵。

### 3. 实验设计

-   **数据集**:
    -   7-Scenes：用于评估相机位姿估计和稠密重建质量。
    -   TUM RGB-D：用于评估相机位姿估计。
-   **评估基准与指标**:
    -   **位姿估计**：绝对轨迹误差的均方根误差。
    -   **重建质量**：在7-Scenes上，评估重建点云的精度、完整度、Chamfer距离。
-   **对比方法**:
    -   **主流学习型SLAM**：MASt3R-SLAM、DROID-SLAM (含标定和未标定版本)。
    -   **经典/其他方法**：ORB-SLAM3、GO-SLAM、NICER-SLAM等（多使用标定相机）。
    -   **前馈重建方法**：Spann3R（仅用于重建评估）。
    -   **自身变体**：基于Sim(3)对齐的VGGT-SLAM，用于消融研究以证明SL(4)优化的必要性。

### 4. 资源与算力

-   **硬件配置**：所有实验在一台配备**一张NVIDIA GeForce RTX 4090 (24GB显存) GPU** 和AMD Ryzen Threadripper 7960X CPU的计算机上进行。
-   **计算资源分析**：文中明确给出了各主要模块的耗时分析（表4），其中VGGT推理耗时约662毫秒，是主要瓶颈，而SL(4)后端优化非常快（约0.5毫秒）。SL(4)方法相对Sim(3)的额外计算开销主要在于用RANSAC估计单应矩阵（增加约17毫秒），占总时间比例很小。
-   **训练耗时**：未提及，因该方法无需额外训练。

### 5. 实验数量与充分性

-   **实验组数**：论文进行了相当充分的实验。
    -   **主实验**：在两个标准数据集（7-Scenes, TUM RGB-D）上，与多种最先进方法进行位姿估计和稠密重建的定量对比。
    -   **消融研究**：
        1.  探究了多种子图大小（`w=1,8,16,32`）对性能的影响。
        2.  消融了闭环检测（有无）对轨迹误差的影响，并用t检验验证了其统计显著性。
        3.  分析了点云置信度过滤阈值（`τconf`）对ATE和重建指标的影响。
    -   **定性分析**：展示了在标准数据集和更长的室外场景（55米长走廊）的重建效果，以及SL(4)和Sim(3)方法在特定挑战性场景下的对齐差异。
-   **实验充分性与公平性**：实验设计较为充分和客观。通过多数据集、多指标、多组消融以及与自身Sim(3)变体和当前最优方法的全面对比，有力支撑了其核心论点。为处理随机性（RANSAC），所有结果均为5次运行的平均值。

### 6. 论文的主要结论与发现

-   **主要结论**：成功构建了首个利用VGGT前馈重建能力、并在SL(4)流形上进行全局优化的SLAM系统（VGGT-SLAM），能够处理长视频序列。
-   **核心发现**：
    1.  **投影模糊的存在**：通过理论和实验证明，基于前馈式模型的场景重建在未标定条件下存在投影模糊，仅用Sim(3)对齐是不够的，尤其在VGGT无法可靠估计场景先验时。
    2.  **SL(4)优化的有效性**：提出的SL(4)流形上的因子图优化能够处理该15自由度的模糊性，实现更一致的子图对齐。即使在Sim(3)方法也表现良好的大部分场景中，SL(4)方法也能保持竞争力的性能。
    3.  **性能提升**：VGGT-SLAM在多个基准测试上表现出与最先进的、无需标定的学习方法（如MASt3R-SLAM）相当甚至更优的性能，同时能构建出高质量的稠密地图。

### 7. 优点

-   **理论洞察力强**：能从几何本质出发，将先进的深度学习方法与经典的投影重建理论相结合，准确地指出了Sim(3)对齐方案的局限性，并给出了严谨的解决方案。
-   **问题定义清晰**：明确地将子图对齐问题建模为SL(4)流形上的姿态图优化，这是SLAM领域中的一种新颖范式。
-   **框架干净高效**：利用VGGT的稠密输出，天然解决了数据关联问题，无需特征匹配。其后端优化因子图规模小，求解速度快。
-   **实验验证全面**：通过充分的定量、定性和消融实验，清晰地展示了方法的优势、适用场景和局限性。

### 8. 不足与局限

-   **平面场景退化**：在平面场景中，估计15自由度单应矩阵是病态问题，会导致求解不稳定，如TUM的floor序列所示。
-   **对深度异常值敏感**：虽然使用了RANSAC，但VGGT输出的点云存在局部一致性较强的错误深度，可能导致单应矩阵估计失败。MASt3R-SLAM中的射线匹配可能对此更鲁棒。
-   **漂移风险增加**：15自由度带来了更大的场景漂移潜力（不仅是尺度、旋转、平移漂移，还包括透视失真）。虽然闭环检测能部分缓解，但长间隔无闭环或不准确的相对估计可能导致严重问题。
-   **应用前提**：假设输入图像已经去畸变，因为射影变换不校正镜头畸变。

### 9. 总结与展望

-   **工作意义**：VGGT‑SLAM 将前馈式场景重建模型的力量与经典的多视图几何中对投影模糊的深刻理解相结合，构建了一种新颖的、无需相机标定的 SLAM 框架。它在不牺牲性能的前提下，展示了在 SL(4)流形上进行图优化以处理长序列的可行性和优势。
-   **未来方向**：
    -   **鲁棒性增强**：可进一步研究利用深度学习预测点云的不确定性，以加权的方式融入单应矩阵估计与全局优化中，缓解因局部错误深度而导致的估计失败。
    -   **退化场景处理**：针对平面或近似平面场景，可设计自适应策略，在检测到退化时自动降级为 Sim(3) 或更简化的变换模型，避免 15 自由度求解的病态问题。
    -   **融合外部约束**：集成 IMU、重力方向等绝对尺度信息，或者引入更紧的几何一致性检验，有望约束 SL(4) 优化中可能出现的透视漂移。
    -   **效率提升**：当前系统的主要瓶颈仍在于 VGGT 的推理时间，未来可通过模型轻量化、专用推理优化或并行处理来满足实时性要求。

（完）
