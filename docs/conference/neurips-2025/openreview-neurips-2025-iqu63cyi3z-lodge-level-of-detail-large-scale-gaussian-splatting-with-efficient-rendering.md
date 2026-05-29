---
title: "LODGE: Level-of-Detail Large-Scale Gaussian Splatting with Efficient Rendering"
title_zh: LODGE：大规模高斯散点的细节层次高效渲染
authors: "Jonas Kulhanek, Marie-Julie Rakotosaona, Fabian Manhardt, Christina Tsalicoglou, Michael Niemeyer, Torsten Sattler, Songyou Peng, Federico Tombari"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Iqu63cYI3z"
tags: ["query:gs-slam"]
score: 4.0
evidence: 三维高斯散点的细节层次渲染实现大规模场景实时可视化，有助于高效SLAM表示
tldr: 该论文提出了一种用于三维高斯散点的细节层次（LOD）渲染方法，通过基于相机距离迭代选择最优高斯子集，并利用深度感知滤波、重要性剪枝和动态区块加载，在内存受限设备上实现大规模场景的实时渲染。该方法可有效降低渲染时间和内存开销，为高效三维场景表示提供了新方案，有可能应用于SLAM系统的实时可视化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqu63cyi3z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqu63cyi3z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqu63cyi3z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 935, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqu63cyi3z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 333, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqu63cyi3z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqu63cyi3z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1428, \"height\": 1162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iqu63cyi3z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 310, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqu63cyi3z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqu63cyi3z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqu63cyi3z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1221, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iqu63cyi3z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 399, \"label\": \"Table\"}]"
motivation: 内存受限设备上大规模三维高斯散点场景的实时渲染面临挑战。
method: 构建层次化LOD表示，根据相机距离动态选择高斯子集并分块加载。
result: 显著减少了渲染时间和GPU内存使用，保持了视觉保真度。
conclusion: LODGE实现了大规模高斯散点场景的高效实时渲染，拓展了应用场景。
---

## Abstract
In this work, we present a novel level-of-detail (LOD) method for 3D Gaussian Splatting that enables real-time rendering of large-scale scenes on memory-constrained devices. Our approach introduces a hierarchical LOD representation that iteratively selects optimal subsets of Gaussians based on camera distance, thus largely reducing both rendering time and GPU memory usage. We construct each LOD level by applying a depth-aware 3D smoothing filter, followed by importance-based pruning and fine-tuning to maintain visual fidelity. To further reduce memory overhead, we partition the scene into spatial chunks and dynamically load only relevant Gaussians during rendering, employing an opacity-blending mechanism to avoid visual artifacts at chunk boundaries. Our method achieves state-of-the-art performance on both outdoor (Hierarchical 3DGS) and indoor (Zip-NeRF) datasets, delivering high-quality renderings with reduced latency and memory requirements.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义
- 大规模三维场景的3D Gaussian Splatting（3DGS）在实时渲染时面临 **内存占用高** 和 **渲染速度慢** 的双重瓶颈，尤其难以在移动设备等资源受限平台运行。
- 现有方法要么需要将所有高斯保留在 GPU 显存中（无法在低端设备运行），要么在每帧动态计算活跃高斯子集（引入额外开销），缺乏兼顾质量、速度与内存的整体方案。
- LODGE 旨在设计一种层次化细节级别（Level-of-Detail, LOD）表示，通过 **基于相机距离自动选择高斯子集** 与 **分块预加载机制**，在不牺牲视觉质量的前提下大幅降低渲染延迟和显存占用，实现大规模场景在移动设备上的实时渲染。

### 方法论
#### 核心思想：层次化 LOD + 分块预计算
- 将场景表示为多个 `LOD` 级别 ({G}^{(0)}最精细，{G}^{(l)}逐渐粗糙)，渲染时根据相机中心到高斯中心的距离 d 自动选择对应级别的高斯子集：
  
  \[
  \tilde{\mathcal{G}}(\mathbf{c}) = \bigcup_{l=0}^{L-1} \{ g_i \in \mathcal{G}^{(l)} : d_l \le \|\boldsymbol{\mu}_i^{(l)} - \mathbf{c}\|_2 < d_{l+1} \}
  \]
- 远距离区域使用粗糙级别的较少高斯，近距离区域使用精细级别的高斯，从而减少像素级可见高斯数量，加速渲染。

#### LOD 级别构建技术细节
1. **深度感知 3D 平滑滤波**：借鉴 Mip‑Splatting 的思想，为保证在距离 d 处无锯齿，对高斯施加平滑滤波，使其在 3D 空间中的尺寸满足奈奎斯特采样定理，同时使大量冗余高斯贡献下降。
2. **重要性剪枝与微调**：对滤波后的高斯计算重要性分数（取所有训练视图中该高斯对 alpha 合成的最大贡献），迭代剪除低于阈值的低贡献高斯；剪枝后执行少量（1000步）微调，微调时使用目标 LOD 级别及更精细级别的联合渲染，并加入随机距离扰动增强鲁棒性。
3. **自动深度阈值选择**：将阈值搜索问题简化为按成本函数（平均每像素 tile 的高斯数）贪心添加新阈值，避免对每个场景手动调参。

#### 分块渲染与不透明度混合
- **分块**：对训练相机位置进行 K‑means 聚类，每个块分配固定的活跃高斯集合（以块中心为参考 + 偏移块半径），预加载到 GPU，避免每帧重新计算活跃高斯。
- **可见性过滤**：在每个块内，使用原始相机位置+随机方向采样扩充视图，进一步剪枝该块完全不可见的高斯，降低加载量。
- **不透明度混合**：渲染时取最近两个块的高斯并集，对只属于其中一个块的高斯，按相机在块中心连线上的投影位置线性调整其不透明度 α̂，实现块间平滑过渡，防止跳变伪影。

### 实验设计
#### 数据集与基准
- **室外场景**：Hierarchical 3DGS 数据集中的 `SmallCity` 和 `Campus`（约 1000‑2000 张图像）。
- **室内场景**：Zip‑NeRF 数据集中的 `Alameda`、`London`、`NYC`（1000‑2000 张，使用降采样 2 倍）。
- **评价指标**：PSNR、SSIM、LPIPS（VGG）、渲染速度 FPS 以及 GPU 显存中的高斯数量（#G）。

#### 对比方法
- 非 LOD 基线：Zip‑NeRF（极慢，仅作质量参考），原始 3DGS，Mip‑Splatting，Scaffold‑GS。
- LOD 基线：H3DGS，FLOD，Octree‑GS，CityGS。
- 所有方法均在单块 NVIDIA A100 SXM4 40GB GPU 上训练和评估，并按各自最优设置训练（如 H3DGS 45K 迭代、Octree‑GS 40K 迭代、Ours 36K 迭代等）。

### 资源与算力
- 训练与评估使用 **单块 NVIDIA A100 SXM4 40GB**。
- 本文方法总训练迭代数 36K（相比 Zip‑NeRF 的 200K 大幅减少）。
- 移动端渲染测试使用 iPhone 13 Mini、iPhone 15 Pro、MacBook Air M3 和 HP Chromebook，无需强大 GPU。
- 论文未提供训练时间的具体分钟或小时数，但给出了迭代次数和相对训练开销。

### 实验数量与充分性
- **对比实验**：在两个不同性质的数据集（室内/室外）上对比了 8 个以上现有方法，定量与定性结果丰富（表1、表2，图5、图6）。
- **消融实验**：在 SmallCity 场景上，系统分析了 LOD 级别数量、深度阈值自动/手动、分块、可见性过滤、不透明度混合等各组件的质量‑速度‑内存影响（表3、图7），透明度高。
- **移动设备测试**：在四款真实低功耗设备上测试渲染帧率，验证了方法的实用性和泛化性（表4）。
- 总体实验设计**充分且公平**，覆盖了主流基线、关键组件消融以及实际部署场景。但未提供误差条（作者说明因算力限制），统计显著性未知。

### 主要结论与发现
- LODGE 在 Hierarchical 3DGS 和 Zip‑NeRF 数据集上取得了 **最优或次优的渲染质量**，同时渲染速度 (FPS) 远超现有 LOD 方法（如 SmallCity 达到 257 FPS，比最快的 FLOD 还高约 50 FPS），且 GPU 内存占用更低。
- 自动深度阈值选择策略避免了手动逐场景调参，并获得了接近甚至优于手动调参的性能。
- 分块预计算活跃高斯与不透明度混合有效消除了块边界伪影，并在内存受限设备上实现**首个真正意义上的实时大规模 3DGS 渲染**（如 iPhone 13 Mini 上达到 41 FPS）。
- 重要性剪枝与 3D 平滑滤波的结合是构建轻量 LOD 级别的关键步骤，可大幅降低可视高斯数量而不明显损失质量。

### 优点
- **移动端部署能力突出**：是第一篇在手机上实现大规模场景实时渲染的 LOD 3DGS 方法，显著拓展了应用场景。
- **自动超参数选择**：深度阈值无需人工调节，提升了方法的易用性和可复现性。
- **模块化设计**：LOD 构建在已有 3DGS 模型之上，可与多种重建方法结合；纹理、压缩等后续压缩技术可进一步叠加。
- **视觉过渡平滑**：独创的两块不透明度混合方案以极低成本解决了分块渲染的跳动问题。
- **实验详尽**：覆盖室内外、多个强基线、消融与移动端性能，充分支撑其宣称的优势。

### 不足与局限
- **假设高效的高斯流式加载**：方法默认块间切换时高斯数据能快速从存储加载到 GPU，实际部署需要高效的 Web 服务器和压缩协议，这部分尚未实现。
- **未提供误差条**：由于算力限制，实验未报告多次运行的统计不确定性，结果的稳健性略有不足。
- **外观变化场景表现未知**：论文主要关注固定光照/曝光的场景，未评估不同时间、季节或曝光大幅变化时的性能（文中仅提到暴露变化时自身 LPIPS 稍差）。
- **边界情况鲁棒性**：来自训练相机分布较远的视角可能产生质量下降，虽添加了随机扰动训练，但极端视角下的抗锯齿和保真度仍需验证。
- **块数量依赖场景**：块数量由第一级 LOD 深度阈值决定，该启发式可能在极其狭长或不规则的轨迹下产生不理想的分块。

（完）
