---
title: "HyRF: Hybrid Radiance Fields for Memory-efficient and High-quality Novel View Synthesis"
title_zh: HyRF：面向内存高效高质量新视角合成的混合辐射场
authors: "Zipeng Wang, Dan Xu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3molquhFpv"
tags: ["query:gs-slam"]
score: 9.0
evidence: 使用显式高斯和神经场的混合辐射场进行新视角合成
tldr: HyRF解决了3D高斯溅射内存开销大的问题，通过将显式高斯和神经场结合，在保持高质量新视角合成的同时减少内存消耗，并比纯压缩方法更好地保留细节。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1420, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1434, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 709, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 709, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 703, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 692, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3molquhfpv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 1346, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 441, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1304, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 700, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 703, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 593, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 726, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 725, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1155, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 727, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 726, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1451, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 699, \"height\": 121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1449, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1445, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3molquhfpv/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 699, \"height\": 125, \"label\": \"Table\"}]"
motivation: 3DGS虽能实时高质量新视角合成，但逐高斯参数导致内存开销巨大，现有压缩方法又难以保持高频细节。
method: 提出HyRF，将场景分解为显式高斯和神经场，结合两者优势以表示辐射场。
result: HyRF在内存效率和重建质量上取得平衡，还原细节能力优于现有压缩方法。
conclusion: 混合表示有效降低了3DGS内存需求，同时保持高质量渲染，适合内存敏感应用。
---

## Abstract
Recently, 3D Gaussian Splatting (3DGS) has emerged as a powerful alternative to NeRF-based approaches, enabling real-time, high-quality novel view synthesis through explicit, optimizable 3D Gaussians.  However, 3DGS suffers from significant memory overhead due to its reliance on per-Gaussian parameters to model view-dependent effects and anisotropic shapes. While recent works propose compressing 3DGS with neural fields, these methods struggle to capture high-frequency spatial variations in Gaussian properties, leading to degraded reconstruction of fine details. We present Hybrid Radiance Fields (HyRF), a novel scene representation that combines the strengths of explicit Gaussians and neural fields. HyRF decomposes the scene into (1) a compact set of explicit Gaussians storing only critical high-frequency parameters and (2) grid-based neural fields that predict remaining properties. To enhance representational capacity, we introduce a decoupled neural field architecture, separately modeling geometry (scale, opacity, rotation) and view-dependent color. Additionally, we propose a hybrid rendering scheme that composites Gaussian splatting with a neural field-predicted background, addressing limitations in distant scene representation.Experiments demonstrate that HyRF achieves state-of-the-art rendering quality while reducing model size by over 20× compared to 3DGS and maintaining real-time performance.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：新视角合成在计算机视觉中至关重要，NeRF 类方法质量高但渲染慢，3DGS 实现实时高质量渲染却面临严重的显存开销（每高斯 59 参数，大量用于视角相关颜色和各向异性形状）。
- **核心问题**：现有压缩 3DGS 的方法（如结合神经场）往往难以捕捉高频空间变化，导致细节（薄结构、高频颜色）重建质量下降，而纯粹压缩又会牺牲渲染质量。
- **整体含义**：本文提出 Hybrid Radiance Fields (HyRF)，一种混合显式高斯与神经场的场景表示，旨在同时实现高渲染质量、实时速度与极低的模型内存占用。

### 2. 论文提出的方法论

- **核心思想**：将场景分解为两个互补部分：
  - 一组紧凑的显式高斯，每个仅存储 8 个关键高频参数（位置、漫反射颜色、各向同性尺度、不透明度）。
  - 基于网格的神经场（多分辨率哈希编码），预测其余属性（尺度、不透明度、旋转、视角相关颜色）。

- **解耦神经场架构**：
  - 几何场 (`Θ_geo`)：根据点位置 `p_i` 预测不透明度 `α_n`、尺度 `s_n` 和旋转 `r_n`。
  - 辐射场 (`Θ_rad`)：结合点位置编码和视角方向编码，预测视角相关颜色 `c_n`。
  - 这种解耦有利于分别学习几何和外观，提升表达能力。

- **显式与神经属性聚合**：
  - 将神经场预测的属性与显式存储的残差（`α_e`, `c_e`, `s_e`）相加后经激活函数得到最终高斯属性：
    - `α = σ(α_n + α_e)`
    - `c = σ(c_n + c_e)`
    - `s = σ(s_n + s_e)`
    - `r = Normalize(r_n)`
  - 显式残差用于恢复高频细节，解决网格神经场分辨率有限的问题。

- **混合渲染流程**：
  - **可见性预剔除**：仅保留投影在视锥体内的点，大幅减少神经场查询开销。
  - **背景渲染**：在背景球上采样射线的交点，通过辐射场预测背景颜色，并与前景高斯按 alpha 混合，改善远景模糊问题。

- **优化**：使用与 3DGS 相同的 L1 + SSIM 损失，周期重置不透明度并修剪低不透明度的高斯。

### 3. 实验设计

- **数据集与场景**：
  - 标准真实场景：MipNeRF360（9 个场景）、Tanks & Temples（2 个场景）、Deep Blending（2 个场景）。
  - 合成物体场景：NeRF Synthetic（8 个场景）。
  - 大规模城市场景：Mill19 和 Urbanscene3D（共 4 个场景）。
  - 额外测试：街道场景 KITTI，各向异性合成场景（Spec-GS 数据集）。

- **对比方法**：
  - NeRF 类：Plenoxels、Instant-NGP、Mip-NeRF360 (M-NeRF360)。
  - 3DGS 类：3DGS、Scaffold-GS。
  - 压缩类：Niedermayr et al.、Lee et al.、Girish et al.、Papantonakis et al.、Chen et al. 等。
  - 其他近期 3DGS 变体：GOF、Spec-GS、Mini-Splatting2、DashGaussian。

- **评估指标**：PSNR、SSIM、LPIPS、模型大小（MB）、渲染帧率（FPS），部分实验还包括训练时间、GPU 峰值内存。

### 4. 资源与算力

- **GPU**：所有实验在单块 NVIDIA 3090 GPU 上进行。
- **训练时间**：未给出具体小时数，但通过训练曲线图（Fig. 8）展示收敛速度比基线更快；完整的模型训练时间约为 12.5 分钟（DeepBlending 数据集），远快于一些高精度方法（如 GOF 需 20.3 分钟）。详细训练时间/显存数据仅在部分补充比较中列出。

### 5. 实验数量与充分性

- **主要实验组数**：
  - 5 个数据集的综合定量比较（与 10+ 方法），覆盖 25+ 场景。
  - 模型压缩性能对比（与 5 种专有压缩方法）。
  - 消融实验：解耦神经场、混合渲染（背景）、神经高斯、可见性预剔除、各显式属性（颜色、尺度、不透明度）的作用。
  - 扩展实验：街景、各向异性合成场景、视角相关建模方式（SH vs. MLP）、显式高斯数量分析。
- **充分性与公平性**：实验覆盖广，对比基线丰富，消融细致；所有对比均保持相同评估指标，压缩实验中采用了公平的后处理流程（量化、Huffman 编码），具有较好的客观性和公平性。

### 6. 论文的主要结论与发现

- HyRF 在标准真实场景上以 **27.78 PSNR** 和仅 **49 MB** 大小达到 state-of-the-art，比 3DGS 小 12 倍以上，比 Scaffold-GS 小 1.5–5 倍，同时保持实时渲染（~100 FPS）。
- 在合成和大规模城市场景中均取得最佳或次佳的渲染质量，同时模型大小极低。
- 解耦神经场比单一场显著提升细节重建，混合背景渲染有效解决远景模糊；显式残差对于保持高频细节（颜色、边缘）不可或缺。
- 经过压缩后，HyRF 以 **18.04 MB** 超越所有对比的 3DGS 压缩方法，且无质量损失。

### 7. 优点

- **高效混合设计**：显式高斯只保留少量高频残差，神经场学习低维特征，极大减少参数量，同时避免细节丢失。
- **解耦架构**：独立处理几何和外观，提升复杂场景的表达力。
- **混合渲染**：预剔除和背景球渲染既保证速度又改善背景质量。
- **兼容性**：可与现有（量化、哈夫曼编码等）压缩技术无缝结合。
- **广泛实验验证**：覆盖多个数据集、多种基线，并提供控制良好的消融研究。
- **训练快速**：收敛速度快，训练时间远少于部分高精度 3DGS 变体。

### 8. 不足与局限

- **抗锯齿缺失**：和原始 3DGS 一样，未处理混叠问题，可能产生不准确的表面重建。
- **硬件依赖**：神经场组件高度依赖现代高端 GPU 来实现实时速度，在网页平台或集成显卡上效率不足。
- **训练时间对比有限**：虽然比一些方法快，但文中未提供系统的训练时间对比表格（仅部分补充实验提及）。
- **场景泛化**：测试场景虽丰富，但主要集中在室内外静态场景，未涉及动态场景或大规模长时间序列。
- **残差依赖**：显式残差仍需每个高斯存储部分属性，可能限制极端压缩比下的表现。
- **超参数敏感**：多分辨率哈希的尺寸、背景球半径等可能对不同场景需调参。

（完）
