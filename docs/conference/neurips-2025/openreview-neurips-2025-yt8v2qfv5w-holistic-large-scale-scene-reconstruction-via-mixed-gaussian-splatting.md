---
title: Holistic Large-Scale Scene Reconstruction via Mixed Gaussian Splatting
title_zh: 通过混合高斯溅射的整体大规模场景重建
authors: "Chuandong Liu, Huijiao Wang, Lei YU, Gui-Song Xia"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yT8v2QFv5w"
tags: ["query:gs-slam"]
score: 7.0
evidence: 使用3DGS和视角感知表示的大规模场景重建
tldr: MixGS摒弃分治策略，提出整体优化框架，将相机位姿和高斯属性融入视角感知表示，实现全局一致且细节丰富的大规模场景重建。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yt8v2qfv5w/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yt8v2qfv5w/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1414, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yt8v2qfv5w/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yt8v2qfv5w/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yt8v2qfv5w/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yt8v2qfv5w/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1429, \"height\": 1987, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yt8v2qfv5w/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 1999, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yt8v2qfv5w/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yt8v2qfv5w/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 935, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yt8v2qfv5w/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 491, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yt8v2qfv5w/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 731, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yt8v2qfv5w/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yt8v2qfv5w/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1022, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yt8v2qfv5w/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 294, \"label\": \"Table\"}]"
motivation: 现有大规模重建方法依赖分治策略，易丢失全局信息且调参复杂。
method: 提出MixGS，将相机位姿和高斯属性编码为视角感知表示，通过解码和混合操作整合全局与局部高斯。
result: MixGS无需场景分割即可整体优化大规模场景，重建质量较高且减少调参。
conclusion: 混合高斯溅射可用于高效、高质的大规模场景重建，为AR/VR应用奠定基础。
---

## Abstract
Recent advances in 3D Gaussian Splatting have shown remarkable potential for novel view synthesis. However, most existing large-scale scene reconstruction methods rely on the divide-and-conquer paradigm, which often leads to the loss of global scene information and requires complex parameter tuning due to scene partitioning and local optimization. To address these limitations, we propose MixGS, a novel holistic optimization framework for large-scale 3D scene reconstruction. MixGS models the entire scene holistically by integrating camera pose and Gaussian attributes into a view-aware representation, which is decoded into fine-detailed Gaussians. Furthermore, a novel mixing operation combines decoded and original Gaussians to jointly preserve global coherence and local fidelity. Extensive experiments on large-scale scenes demonstrate that MixGS achieves state-of-the-art rendering quality and competitive speed, while significantly reducing computational requirements, enabling large-scale scene reconstruction training on a single 24GB VRAM GPU.

---

## 论文详细总结（自动生成）

好的，助手已就位。根据您提供的论文内容，我将生成一份详细的结构化中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：现有基于3D高斯溅射的大规模场景重建方法普遍采用“分而治之”的策略，即将大场景分割成多个块，独立优化后再合并。这种做法导致了两个主要缺陷：
    1.  **全局信息丢失**：独立的局部优化容易造成块与块之间在全局结构、光照和几何连续性上的不一致，产生边界伪影。
    2.  **复杂的参数调优**：场景分块需要根据具体场景手动调整大量参数（如块的数量、大小、可见性阈值等），泛化能力差，使用门槛高。
*   **整体含义**：本文提出了一种全新的“整体优化”（Holistic Optimization）框架，名为**MixGS**。它摒弃了分治策略，将整个大场景作为一个统一整体进行建模和优化，从根本上解决了全局一致性和繁琐调参的问题，同时实现了在单个消费级GPU上高质量训练大规模场景重建模型。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

MixGS的核心思想是通过一种视角感知的表示，将显式的高斯点云训练转化为隐式的特征学习，再通过“混合”机制融合场景的全局结构和局部细节。

**关键技术流程与细节如下：**

1.  **获取粗糙高斯**：
    *   首先，使用标准的3DGS流程在整个大规模场景上预训练一组高斯点云，记为 \( G_c \)。它捕获了场景的粗略几何和纹理信息，为后续步骤提供结构先验。

2.  **视角感知表示建模**：
    *   **视锥体提取**：根据当前训练的相机位姿 \( \tau_i \)，从粗高斯 \( G_c \) 中提取出位于视锥体内的可见高斯子集 \( G_v \)。
    *   **多分辨率哈希编码**：对 \( G_v \) 中每个高斯的中心位置 \( (x, y, z) \) 采用多分辨率哈希编码，获取多尺度的空间特征 \( h_s \)。这借鉴了Instant-NGP的思想，实现从粗到细的高效特征学习。
    *   **辅助高斯增强**：将 \( G_v \) 中每个高斯的旋转四元数 \( r \)、缩放向量 \( s \) 以及相机位姿 \( \tau_i \) 编码为辅助特征 \( h_a \)。然后，通过一个轻量级MLP将 \( h_a \) 转化为注意力得分，用于调制空间特征 \( h_s \)，生成融合后的视角感知特征 \( h_{gs} \)。

3.  **混合高斯光栅化**：
    *   **解码生成细粒度高斯**：使用一个多头的MLP \( f_{\theta_3} \)（解码器）将高维特征 \( h_{gs} \) 解码为一组新的高斯属性，记为解码高斯 \( G_{\Phi} \)，包括不透明度、颜色、旋转和缩放。解码高斯的数量与视锥体内原始高斯数量 \( N_v \) 相同。
    *   **偏移池**：设计了一个可学习的偏移池 \( O_c \)，用于存储每个解码高斯的空间位置偏移量。解码高斯的最终位置是原始高斯位置加上这个偏移量 \( \tilde{\mu} = \mu + o \)，这有助于模型更精确地捕获局部几何细节。
    *   **高斯混合**：将原始的可见高斯 \( G_v \) 和解码得到的高斯 \( G_{\Phi} \) 合并，形成最终用于渲染的混合高斯集合 \( G_h = G_v \cup G_{\Phi} \)。原始高斯负责维护全局结构（粗略信息），解码高斯负责补充局部细节和复杂光照（精细信息）。最后，对 \( G_h \) 进行可微光栅化得到渲染图像并计算损失。

4.  **多阶段优化策略**：
    *   **阶段一（粗糙阶段）**：只优化粗高斯 \( G_c \)，快速建立全局几何结构。
    *   **阶段二（细节阶段）**：固定 \( G_c \) 的参数，只优化哈希编码器、MLP解码器和偏移池等参数 \( \Phi \)，让模型专注于学习局部细节。
    *   **阶段三（联合阶段）**：同时微调所有参数（\( G_c \) 和 \( \Phi \)），整合全局与局部信息，消除边界效应，进一步提升整体质量。

### 3. 实验设计

*   **数据集/场景**：使用了两个大型真实城市场景数据集进行评测：
    *   **UrbanScene3D** 数据集中的 **Residence** 和 **Sci-Art** 场景。
    *   **Mill19** 数据集中的 **Building** 和 **Rubble** 场景。所有场景均由无人机拍摄的高分辨率图像构成。
*   **评估指标 (Benchmark)**：采用新视角合成任务的标准指标：
    *   PSNR ↑ (峰值信噪比)
    *   SSIM ↑ (结构相似性)
    *   LPIPS ↓ (学习感知图像块相似度)
    *   此外还评估了渲染速度 FPS (每秒帧数)。
*   **对比方法**：与7种先进方法进行了比较，涵盖了NeRF和3DGS两大范式：
    *   **NeRF-based**: Mega-NeRF, Switch-NeRF, GP-NeRF。
    *   **3DGS-based**: 原生3DGS, VastGaussian, CityGaussian, Hierarchy-GS, DOGS。

### 4. 资源与算力

*   **GPU信息**：所有训练和评估均在一张 **NVIDIA RTX 3090 GPU** (24GB显存) 上完成。
*   **训练时长**：论文报告了总训练步数为330,000次迭代（30k+40k+260k），但未提供具体的训练时长（小时/分钟）。不过，在附录中有与其他方法的资源对比分析，表明其显存占用稳定且有所降低，但单卡训练时间比部分多卡分布式方法要长。

### 5. 实验数量与充分性

*   **实验数量**：实验设计较为全面，主要包括：
    1.  **主实验**：在4个大型场景上与7种不同方法进行了定量与定性对比，共生成约 (4场景 × 8方法) 组以上的对比数据。
    2.  **消融实验**：以Rubble场景为例，对6个核心组件（哈希编码、辅助增强、粗糙阶段训练、细节阶段训练、偏移池、高斯混合）分别进行了消融研究。
    3.  **参数敏感性分析**：探究了混合高斯比例K（解码高斯与粗高斯的数量比）对性能与显存的影响。
    4.  **附加实验**：在附录中，还补充了在MatrixCity和Campus场景上的实验，以及6倍下采样的实验。
*   **充分性与公平性**：
    *   **客观公平性**：实验遵循了领域内公认的数据集划分标准和评估指标。对比方法包括了官方预训练模型的结果或复现结果，并明确指出VastGaussian的对比去除了其色彩校正等后处理模块，保证了公平性。
    *   **充分性**：实验覆盖了多个场景和多种对比方法，消融实验设计清晰地验证了每个模块的有效性。可视化结果直观地展示了MixGS在全局一致性和细节重建上的优势。

### 6. 论文的主要结论与发现

*   MixGS作为一种全新的大规模场景重建框架，成功地将复杂的“分而治之”问题转化为一个端到端的整体优化问题。
*   通过视角感知表示和高斯混合渲染，MixGS能够同时保持场景的**全局一致性**（如光照和几何连续）和**局部细节**（如清晰纹理）。
*   在多个大型场景的基准测试中，MixGS取得了**最先进**或极具竞争力的新视角合成质量，尤其在SSIM指标上全面领先。
*   该方法显著降低了计算资源门槛，仅需一张24GB显存的消费级GPU即可完成训练，渲染速度也能达到实时。

### 7. 优点

*   **方法新颖性**：提供了一个从根本上不同于主流分治策略的新范式，创新性地将隐式特征学习与显式高斯表达相结合。
*   **效果显著**：有效解决了分治法中难以避免的全局不一致和繁琐调参问题，在视觉质量和几何连续性上表现更优。
*   **资源友好**：将大场景重建的训练要求降低到单张消费级显卡，具有很高的实用和推广价值。
*   **设计精巧**：多阶段训练、偏移池、特征注意力调制等设计都针对性地解决了整体优化中的特定问题，有理有据。

### 8. 不足与局限

*   **训练效率**：尽管节省了显存，但采用单卡和复杂的多阶段训练策略导致其**总训练时间较长**，慢于多GPU并行的方法。论文也指出了这一点，并计划未来采用分布式训练框架进行加速。
*   **实验场景局限**：实验主要集中在无人机拍摄的户外城市场景，对于更大尺度（如城市级）、更复杂动态环境或室内场景的泛化能力尚未验证。
*   **依赖初始点云**：方法仍依赖于COLMAP提供的初始点云和位姿，在无法提供可靠SfM结果的场景下可能失效。
*   **LPIPS指标**：在某些场景下，其LPIPS指标并非最优。论文解释这是为了全局一致性而进行的微小局部色彩调整所致，但这可能在评价感知相似度时成为一个短板。

（完）
