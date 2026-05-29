---
title: "HAIF-GS: Hierarchical and Induced Flow-Guided Gaussian Splatting for Dynamic Scene"
title_zh: "HAIF-GS: 层次化与诱导流引导的动态场景高斯泼溅"
authors: "Jianing Chen, Zehao Li, Yujun Cai, Hao Jiang, Chengxuan Qian, Juyuan Kang, Shuqin Gao, Honglong Zhao, Tianlu Mao, Yucheng Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ztVk8XNffY"
tags: ["query:gs-slam"]
score: 9.0
evidence: 从单目视频使用动态三维高斯泼溅进行新视角合成
tldr: 针对单目视频动态场景重建中运动一致性不足的问题，HAIF-GS提出层次化与诱导流引导的高斯泼溅框架，通过稀疏锚点驱动的变形场实现结构化运动建模，解决了冗余更新和复杂非刚性变形的挑战，在动态场景渲染质量与效率上取得提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ztvk8xnffy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ztvk8xnffy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1407, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ztvk8xnffy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ztvk8xnffy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ztvk8xnffy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 645, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ztvk8xnffy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 1149, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ztvk8xnffy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1378, \"height\": 1606, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 769, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 794, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1220, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1005, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1029, \"height\": 447, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1149, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 951, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ztvk8xnffy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 765, \"height\": 321, \"label\": \"Table\"}]"
motivation: 单目动态重建中存在冗余高斯更新、运动监督不足及复杂变形建模弱等问题。
method: 构建锚点驱动的层次化变形表示，结合诱导流实现结构化和一致的运动建模。
result: 在动态场景渲染中实现了更连贯高效的重建质量。
conclusion: 通过层次化与流引导提高了三维高斯的运动建模能力。
---

## Abstract
Reconstructing dynamic 3D scenes from monocular videos remains a fundamental challenge in 3D vision. While 3D Gaussian Splatting (3DGS) achieves real-time rendering in static settings, extending it to dynamic scenes is challenging due to the difficulty of learning structured and temporally consistent motion representations. This challenge often manifests as three limitations in existing methods: redundant Gaussian updates, insufficient motion supervision, and weak modeling of complex non-rigid deformations. These issues collectively hinder coherent and efficient dynamic reconstruction. To address these limitations, we propose HAIF-GS, a unified framework that enables structured and consistent dynamic modeling through sparse anchor-driven deformation. It first identifies motion-relevant regions via an Anchor Filter to suppress redundant updates in static areas. A self-supervised Induced Flow-Guided Deformation module induces anchor motion using multi-frame feature aggregation, eliminating the need for explicit flow labels. To further handle fine-grained deformations, a Hierarchical Anchor Propagation mechanism increases anchor resolution based on motion complexity and propagates multi-level transformations. Extensive experiments on synthetic and real-world benchmarks validate that HAIF-GS significantly outperforms prior dynamic 3DGS methods in rendering quality, temporal coherence, and reconstruction efficiency.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：从单目视频中重建动态三维场景是计算机视觉中的一个根本性挑战。尽管3D高斯泼溅（3DGS）在静态场景渲染中效果显著，但将其扩展到动态场景仍面临困难。
- **现有方法局限**：当前主流的动态3DGS方法学习变形场来驱动高斯点的运动，但存在三个主要局限性：
    1.  **冗余更新**：在每一时间步对所有高斯点进行查询和更新，计算效率低下。
    2.  **运动监督不足**：训练仅依赖于图像重建损失，缺乏显式的运动约束，导致时序不一致和伪影。
    3.  **复杂非刚性变形建模弱**：简单的MLP变形场难以表达精细的、空间变化的非刚性运动。
- **整体含义**：本研究旨在解决上述局限性，提出一个统一的框架，实现高效、连贯且结构化的动态场景重建。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：**HAIF-GS** 框架通过**稀疏锚点驱动的变形**实现结构化和时序一致的动态建模。其核心是使用一组稀疏的、可学习的3D运动锚点作为变形的基本单元，而不是直接操作海量的高斯点。
- **关键技术细节与算法流程**:
    1.  **稀疏运动锚点与动态-静态分解**:
        - **锚点表示**: 从规范空间中的高斯点通过最远点采样初始化一组稀疏运动锚点。每个锚点通过其3D位置和影响范围建模。
        - **动态过滤**: 引入一个**Anchor Filter (锚点过滤器)** 模块，为每个锚点预测一个动态置信度分数α，用于识别运动区域并抑制静态区域的冗余计算。优化时通过2阶段策略（软权重调制+硬阈值分解）实现，并辅以稀疏性损失L_sparsity和熵损失L_entropy进行正则化。
        - **变换插值**: 对于每个高斯点，计算其到K个最近锚点的归一化高斯核权重ω_{ij}。然后通过线性混合蒙皮的策略，将锚点的刚性变换（平移ΔT，旋转ΔR）插值到高斯点，驱动其运动。
    2.  **诱导流引导变形 (Induced Flow-Guided Deformation, IFGD)**:
        - 这是一个**自监督**模块，无需显式光流标签。它由一个**Induced Flow MLP**和一个**Deformable MLP**组成。
        - 对于给定时间t的锚点，Induced Flow MLP预测其到t-1和t+1帧的场景流。
        - 利用预测的流，构造t-1, t, t+1三个时刻的查询点，送入Deformable MLP提取时序特征。
        - 通过加权聚合三个时刻的特征得到一个时序一致的特征，用于预测锚点的变换，从而实现时序一致的变形预测。此外，还引入**循环一致性损失L_cycle**来监督场景流的学习。
    3.  **层次化锚点传播 (Hierarchical Anchor Propagation, HAD)**:
        - 为了捕捉复杂区域的精细形变，根据锚点在不同时间步下平移量的方差识别运动复杂区域。
        - 对方差超过阈值的锚点进行复制并添加微小偏移，生成更高分辨率的子锚点，形成多尺度层级结构。
        - 子锚点的变形预测会参考父锚点的信息，实现由粗到精的运动传播。
- **优化目标**: 最终损失函数是光度损失（L1+ D-SSIM）和上述多个正则化项的加权和，以平衡重建质量、时序一致性和模型简洁性。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集与场景**:
    - **NeRF-DS**: 真实世界数据集，包含7个具有高光反射、快速移动物体的日常场景视频（如筛子、盘子、铃铛等）。
    - **D-NeRF**: 合成数据集，包含8个具有精确相机轨迹和真实形变的动态场景（如钩子、跳跃杰克、地狱战士等）。
- **基准（Benchmark）**: 动态场景的新视角合成，使用标准指标进行评估：
    - PSNR (峰值信噪比)
    - SSIM / MS-SSIM (结构相似性)
    - LPIPS (学习感知图像块相似度)
- **对比方法**:
    - **NeRF-based**: TiNeuVox, HyperNeRF, NeRF-DS
    - **3DGS-based**: 3DGS（静态基线）, Deformable 3DGS, 4DGS, SC-GS, SP-GS

### 4. 资源与算力

- 文中明确提到，所有实现基于PyTorch框架，并使用**单一NVIDIA RTX 3090 GPU**进行训练。
- 附录中的资源消耗对比表显示，在D-NeRF数据集上，HAIF-GS的平均训练时间约为**29分钟**，显存占用约**3.3 GB**，渲染速度可达**215.4 FPS**。这表明其在算力消耗和训练速度上具有优势或竞争力。

### 5. 实验数量与充分性

- **实验数量**:
    - 在2个主要数据集（NeRF-DS, D-NeRF）上与超过7种主流方法进行了全面的定量和定性比较。
    - 在附录中提供了2个额外真实世界数据集（HyperNeRF(misc), Dycheck）的定量对比。
    - 进行了详细的**消融实验**，分别验证了诱导流模块（IF）、循环一致性损失(L_cycle)、锚点过滤器(AF)和层次化锚点传播(HAD)等关键组件的有效性。
    - 对关键模块的组合、锚点传播策略、以及不同损失函数的权重进行了消融分析。
- **实验充分性与客观性**:
    - 实验设计**较为充分**，覆盖了合成与真实、简单与复杂运动场景，并从重建质量、时序一致性、计算效率等多个维度进行评估。
    - 对比方法均为当前主流，且评估指标为标准通用指标，保证了公平性。
    - 消融实验系统地证实了各个提出模块的有效性，结果具有说服力。

### 6. 论文的主要结论与发现

- HAIF-GS框架有效解决了动态3DGS在冗余更新、运动监督和复杂变形建模方面的挑战。
- 提出的Anchor Filter成功抑制了静态区域的冗余更新，使模型专注于动态部分。
- 自监督的Induced Flow-Guided Deformation模块通过多帧特征聚合和循环一致性约束，显著提升了运动的时序一致性，无需外部流标签。
- Hierarchical Anchor Propagation机制增强了模型对复杂、局部、非刚性运动的表达能力。
- 综合上述技术，HAIF-GS在多个基准测试中，在**渲染质量、时间连贯性和重建效率**上均显著超越了以往的方法。

### 7. 优点：方法或实验设计上有哪些亮点

- **统一的框架设计**: 将稀疏锚点、自监督流引导和层次化传播有机融合，共同解决动态重建难题。
- **自监督的流引导**: 不依赖难以获取的真实光流标签，通过多帧聚合隐式地学习时序一致性，这是一个实用且高效的设计。
- **动态-静态分解**: Anchor Filter 模块通过预测动态置信度和相应的正则化损失，实现了有效的运动/静态区域分离，减少了计算冗余。
- **层次化运动建模**: HAD 模块提供了一种由粗到精的变形学习方法，能够有效捕捉局部精细运动，增强了模型对复杂场景的适应性。
- **出色的性能与效率权衡**: 在取得SOTA渲染质量的同时，保持了较快的训练速度和极高的渲染FPS，展现了良好的实用性。
- **详尽的实验验证**: 在多个数据集和大量基线方法上进行了全面对比，并通过细致的消融实验验证了每个模块的贡献，论证非常扎实。

### 8. 不足与局限

- **内存消耗**: 对于包含高度复杂运动动态的场景，由于层级锚点的增多，整体内存占用仍不可忽视。
- **对遮挡的敏感性**: 自监督场景流是隐式诱导的，在存在严重遮挡的区域，多帧特征对齐可能失败，影响变形预测的稳定性。
- **实验设定**: 尽管在多个标准数据集上表现优异，但所有实验均基于给定相机参数和有限时间窗口的视频，对于超长视频、相机位姿未知或剧烈光照变化的场景，方法的泛化能力和鲁棒性尚未得到验证。
- **视角数的影响**: 未曾探究不同训练视角数量对重建效果的影响。

（完）
