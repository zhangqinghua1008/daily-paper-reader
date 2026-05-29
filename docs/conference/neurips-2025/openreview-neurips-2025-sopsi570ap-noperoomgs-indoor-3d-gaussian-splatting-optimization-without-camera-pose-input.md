---
title: "NopeRoomGS: Indoor 3D Gaussian Splatting Optimization without Camera Pose Input"
title_zh: "NopeRoomGS: 无相机位姿输入的室内3D高斯泼溅优化"
authors: "Wenbo Li, Yan Xu, Mingde Yao, Fengjie Liang, Jiankai Sun, Menglu Wang, Guofeng Zhang, Linjiang Huang, Hongsheng Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SoPSI570Ap"
tags: ["query:gs-slam"]
score: 9.0
evidence: 联合优化3D高斯泼溅和相机位姿以进行室内新视角合成
tldr: 针对室内纹理缺失和相机运动突变环境下，基于3D高斯泼溅（3DGS）的新视角合成严重依赖可靠的相机位姿估计的问题，提出Nope-RoomGS框架。该框架无需输入相机位姿，通过从局部到全局的优化范式，联合优化3DGS和相机位姿，有效应对纹理缺失和运动突变，实现高质量室内重建与相机追踪。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sopsi570ap/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sopsi570ap/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 717, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sopsi570ap/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sopsi570ap/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1430, \"height\": 915, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sopsi570ap/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 727, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sopsi570ap/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 597, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sopsi570ap/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sopsi570ap/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sopsi570ap/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 729, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sopsi570ap/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 727, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sopsi570ap/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 727, \"height\": 192, \"label\": \"Table\"}]"
motivation: 室内环境中SfM估计的相机位姿不可靠，现有无位姿方法在突变运动下易失败。
method: 提出Nope-RoomGS，采用局部到全局的优化范式，联合优化3D高斯场和相机位姿，无需外部位姿输入。
result: 在纹理缺失和突变运动场景中，该方法实现了鲁棒的新视角合成和稳定的相机位姿恢复。
conclusion: Nope-RoomGS消除了对预计算位姿的依赖，为室内3DGS重建提供了一种灵活高效的方法。
---

## Abstract
Recent advances in 3D Gaussian Splatting (3DGS) have enabled real-time, high-fidelity view synthesis, but remain critically dependent on camera poses estimated by Structure-from-Motion (SfM), which is notoriously unreliable in textureless indoor environments. To eliminate this dependency, recent pose-free variants have been proposed, yet they often fail under abrupt camera motion due to unstable initialization and purely photometric objectives. 
In this work, we introduce **Nope-RoomGS**, an optimization framework with no need for camera pose inputs, which effectively addresses the textureless regions and abrupt camera motion in indoor room environments through a local-to-global optimization paradigm for 3DGS reconstruction. In the local stage, we propose a lightweight local neural geometric representation to bootstrap a set of reliable local 3D Gaussians for separated short video clips, regularized by multi-frame tracking constraints and foundation model depth priors. This enables reliable initialization even in textureless regions or under abrupt camera motions. 
In the global stage, we fuse local 3D Gaussians into a unified 3DGS representation through an alternating optimization strategy that jointly refines camera poses and Gaussian parameters, effectively mitigating gradient interference between them. Furthermore, we decompose camera pose optimization based on a piecewise planarity assumption, further enhancing robustness under abrupt camera motion. Extensive experiments on Replica, ScanNet and Tanks & Temples demonstrate the state-of-the-art performance of our method in both camera pose estimation and novel view synthesis.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **核心问题**：当前高质量的视图合成技术（如3D高斯泼溅，3DGS）严重依赖通过运动恢复结构（SfM）预先计算出的精确相机位姿。
*   **问题的严峻性**：在室内环境，尤其是存在大面积无纹理区域（如白墙）或相机快速、突变运动的场景下，SfM极易失效，导致无法估计出可靠的相机位姿，进而使3DGS重建失败。
*   **整体含义**：论文提出**Nope-RoomGS**框架，旨在**完全无需输入相机位姿**的情况下，针对上述具有挑战性的室内环境，同时鲁棒地恢复出准确的相机位姿和高质量的3DGS场景表示，从而将3DGS的应用拓展到SfM不可靠的真实世界场景。

### 2. 论文提出的方法论
论文的核心方法是一个“**从局部到全局**”的优化范式，分为两个关键阶段：

*   **局部阶段：建立稳健初始化**
    *   **核心思想**：将长视频序列分割为多个短片段，对每个短片段独立进行联合优化，以获取可靠的局部几何和位姿。
    *   **关键技术**：
        1.  **轻量级局部神经几何表示($F_θ$)**：用一个轻量网络为短片段内的每一帧预测尺度一致的深度图 ($D_{θ,i}$)。
        2.  **联合优化深度与位姿**：通过梯度下降同时优化网络参数 $θ$（影响深度）和短片段内的相机位姿 $T$。
        3.  **多帧追踪约束**：利用现成的点追踪器（CoTracker）提供的跨帧像素对应关系，构建重投影损失 ($L_{proj}$)，对深度和位姿进行几何一致性监督。
        4.  **基础模型深度先验**：引入一个强大但耗时的单目深度基础模型（Marigold）的预测结果，通过尺度位移不变损失 ($L_{ssi}$) 对 $F_θ$ 的深度预测进行正则化，防止其在无纹理区域偏离真实解。
    *   **产出**：每个短片段的精确深度图和相机位姿，用于初始化一组可靠的局部3D高斯球。

*   **全局阶段：渐进式融合与全局优化**
    *   **核心思想**：将所有局部3D高斯球融合到一个统一的全局3DGS表示中，并采用交替优化策略来精炼全局模型和所有帧的位姿。
    *   **关键技术**：
        1.  **目标函数**：优化全局3DGS $G$ 和全局相机位姿 $T$ 时，使用组合损失：
            *   **光度损失 ($L_{rgb}$)**：标准的3DGS图像重建损失。
            *   **深度对齐损失 ($L_{depth}$)**：约束全局模型渲染的深度与局部阶段优化出的深度保持一致，以增强在无纹理区域的鲁棒性。
            *   **基于分段平面假设的位姿约束 ($L_{plane}$)**：将场景局部视为微小平面，约束相邻帧之间的平面参数（法向量 $n$ 和偏移量 $δ$）在变换后保持一致性。该约束将监督信号分解为旋转（法向量对齐）和平移（偏移量一致性）分量，增强了对突变运动的鲁棒性。
        2.  **交替优化策略**：为解决联合优化中位姿和高斯参数（$T$ 和 $G$）梯度相互干扰的问题，采用交替更新的方式，即固定一方，优化另一方，以增强收敛稳定性。

### 3. 实验设计
*   **使用数据集**：
    *   **Replica**：高保真合成室内数据集，包含精确的真值位姿。
    *   **ScanNet**：真实世界RGB-D室内扫描数据集，存在传感器噪声和运动模糊。
    *   **Tanks & Temples**：包含纹理丰富场景的真实数据集，用于测试泛化能力。
*   **评估基准**：
    *   **位姿估计**：绝对轨迹误差（ATE）和相对位姿误差（RPEt, RPEr）。
    *   **新视角合成**：峰值信噪比（PSNR）、结构相似性指数（SSIM）和感知图像块相似度（LPIPS）。
*   **对比方法**：与多个无位姿或联合优化位姿的最先进方法进行了全面比较，包括基于NeRF的（BARF, Nope-NeRF, NeRFmm）和基于3DGS的（CF-3DGS, NoPoSplat, SelfSplat）方法。

### 4. 资源与算力
论文中**未明确提及**训练或推理所使用GPU的型号、数量以及具体的训练耗时。

### 5. 实验数量与充分性
*   **实验组数**：
    *   **主实验**：在3个不同规模、不同特点的数据集（Replica， ScanNet， Tanks & Temples）上进行了全面的定量和定性评估。
    *   **消融实验**：在Replica数据集上进行了系统的消融研究，以验证4个关键组件（局部神经几何表示、分段平面假设、交替优化策略、深度对齐损失）的有效性。
*   **实验充分性与公平性**：
    *   **充分性**：实验覆盖了合成与真实、室内与室外、纹理丰富与缺失等多种场景，并通过详细消融实验证明了每个提出模块的贡献，实验设计是充分的。
    *   **公平性**：实验比较了广泛的最先进方法，并遵循了标准评估协议（如Procrustes分析对齐位姿），确保比较是客观、公平的。

### 6. 论文的主要结论与发现
*   NopeRoomGS在Replica和ScanNet等具有挑战性的室内数据集上，实现了最先进的位姿估计和新视角合成质量，显著优于现有方法。
*   在Tanks & Temples等通用数据集上，该方法同样展现出极具竞争力的性能。
*   通过“局部到全局”的范式，特别是局部阶段的神经几何表示，可以有效解决室内无纹理和运动突变环境下的初始化难题。
*   全局阶段的交替优化和分段平面约束对于稳定全局重建、提升位姿估计精度至关重要。

### 7. 优点
*   **创新性强**：提出的“局部到全局”框架和轻量级神经几何表示，为解决无位姿3DGS重建问题提供了新思路。
*   **鲁棒性高**：针对室内环境的两大难点（无纹理和突变运动）设计了专门的解决模块，并取得了显著成效。
*   **实验扎实**：在多个数据上进行了充分验证，并通过详尽的消融实验清晰地证明了每个模块的价值。

### 8. 不足与局限
*   **计算开销**：局部阶段的引入相比原始3DGS增加了额外的计算量。
*   **极端情况失效风险**：论文承认，在极其快速的相机运动或输入视频极度稀疏的情况下，该方法仍可能失败。
*   **未公开算力细节**：未说明计算资源消耗情况，难以评估其计算效率和实际部署成本。
*   **泛化性界限**：虽然验证了泛化性，但其设计主要针对室内环境，在室外等更广场景下的最佳表现可能仍有提升空间。

（完）
