---
title: "TreeSplat: Mergeable Tree for Deformable Gaussian Splatting"
title_zh: TreeSplat：可合并树结构的形变高斯散点
authors: "Qiuhong Shen, Xingyi Yang, Xinchao Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5BfO9i4kj1"
tags: ["query:gs-slam"]
score: 6.0
evidence: 层次树结构用于形变高斯散点，实现动态场景重建与表示
tldr: 该论文针对动态三维场景重建中高斯散点（GS）方法计算成本高或独立建模的问题，提出了TreeSplat模型。利用树形数据结构分层表示高斯的运动，每个节点学习时变基函数系数。该方法利用场景动态的结构先验，更高效地表示复杂形变，为动态场景的GS重建提供了新的有效途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5bfo9i4kj1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5bfo9i4kj1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1372, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5bfo9i4kj1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 592, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5bfo9i4kj1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 336, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-5bfo9i4kj1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5bfo9i4kj1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1381, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5bfo9i4kj1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1311, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5bfo9i4kj1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1235, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5bfo9i4kj1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 792, \"height\": 294, \"label\": \"Table\"}]"
motivation: 现有高斯散点动态场景重建方法缺乏对运动层次结构的有效利用。
method: 采用树形结构分层表示高斯运动，学习时变基函数系数。
result: 能高效建模复杂形变，在动态场景重建中表现出优势。
conclusion: TreeSplat利用结构化先验改进了形变高斯散点的表示与重建效率。
---

## Abstract
Dynamic 3D scene reconstruction from multi-view videos demands representation to model complex deformations at scale. Current Gaussian Splatting based methods often either suffer from significant computation cost due to dense MLP-based modeling or explicit modeling deformation of each Gaussian independently. However, the dynamics of objects within a scene are typically hierarchical and exhibit structural correlations. To leverage these structural priors into the representation, we introduce **TreeSplat**, a **Tree** data structure for deformable Gaussian **Splat**ting. In TreeSplat, as the name suggests, motions of Gaussian are represented hierarchically within a tree. Each node learns coefficients for time-varying basis functions, defining a part of the motion. The full motion for any given Gaussian is then determined by accumulating these transformations along the tree path from its leaf node to the root node. This tree isn't predefined; instead, it is constructed adaptively alongside Gaussian densification, where cloning or splitting a Gaussian correspondingly creates new leaf nodes. One central property of TreeSplat is its mergeability; after optimization during training, the hierarchical motion parameters for each Gaussian can be efficiently consolidated. By performing this merging step before test time, we eliminate the need to traverse the tree explicitly for each Gaussian during rendering. This results in dramatically faster rendering over 200 FPS and compact storage, while maintaining state-of-the-art rendering quality. Experiments on diverse synthetic and real-world datasets validate these advantages.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究背景**：动态 3D 场景重建需要高效表示随时间变化的复杂形变。基于 3D 高斯散点（3DGS）的方法虽然渲染快，但在建模运动时存在两难：
  - **隐式方法**（如 4DGaussian）使用 MLP 为每个高斯预测形变，计算成本高、训练和渲染慢。
  - **显式方法**（如 DynMF, RealTime4DGS）为每个高斯独立学习运动参数，忽略了场景中物体运动的层次结构和空间相关性。
- **核心问题**：如何既保持显式方法的高效性，又能捕捉高斯之间结构化的运动关联，从而提升重建质量。
- **论文含义**：提出 **TreeSplat**，一个可合并的层次化运动树结构，将运动组织为树形层次，通过共享和聚合祖先节点的运动分量来建模高斯间的协作运动。训练完成后可合并系数，彻底消除推理时的树遍历开销，实现超 200 FPS 的实时渲染与 SOTA 重建质量。

## 2. 方法论

### 2.1 动态高斯基础

- 沿用显式参数化运动：每个高斯的位置和旋转由一个静态部分加上时变偏移组成，偏移通过可学习基函数的线性组合表示：
  
  \[
  \mu(t) = \mu_c + \sum_{j=1}^{B} c_{\mu j} b_{\mu j}(t), \quad q(t) = q_c + \sum_{j=1}^{B} c_{q j} b_{q j}(t)
  \]
  
- 基函数 \(b_{\mu j}(t), b_{q j}(t)\) 由一个小型 MLP \(f_\theta\) 以正弦时间嵌入 \(\gamma(t)\) 为输入生成，所有高斯共享这组基，MLP 只需每个时间戳查询一次，极大降低计算。

### 2.2 层次化运动树

- **数据结构**：
  - 运动场 \(F \in \mathbb{R}^{M \times B}\)，每个节点存储一个系数向量（长度为 \(B\)）。
  - 每个叶子节点唯一对应一个高斯（通过节点条目 \(E\) 映射）。
  - 父索引 \(P\) 记录节点间的父子关系，节点层级 \(L\) 指示从叶子到根的步数。
- **运动聚合**：高斯 \(i\) 的运动由其叶子节点出发，沿祖先路径向上聚合所有节点的运动分量：
  \[
  \hat{\mu}_i(t) = \sum_{k=0}^{\ell_i} \sum_{j=1}^{B} F_{\text{anc}(i,k), j} \, b_{\mu j}(t)
  \]
  其中 \(\ell_i\) 为层级，\(\text{anc}(i,k)\) 返回往上第 \(k\) 步的祖先节点索引。
- **树的自适应生长**（与高斯稠密化同步）：
  - **Leaf Expansion**：水平扩展宽度。新稠密化出的高斯链接到与源高斯同一父节点下的新叶子节点，树深度不变。
  - **Depth Promotion**：垂直增加深度。将现有叶子节点提升为父节点，稠密化产生的两个新高斯作为其子叶子节点，层级+1。
  - 两种模式交替调度（先多轮 Leaf Expansion 后一次 Depth Promotion），使树在宽度和深度上自适应增长。
- **衰减加权聚合**：引入可学习的衰减因子 \(\beta_i \in (0,1]\)，深层祖先的贡献被 \(\beta_i\) 的幂次衰减：
  \[
  \hat{\mu}_i(t) = \sum_{k=0}^{\ell_i} \left( \prod_{p=0}^{k-1} \beta_i \right) \sum_{j=1}^{B} F_{\text{anc}(i,k), j} \, b_{\mu j}(t)
  \]
  这有效抑制了深层祖先从大量后代接收的累积梯度爆炸，稳定优化，并让每个高斯自适应控制感受野。

### 2.3 可合并性与高效推理

- 训练完成后固定树结构，通过重新排列求和顺序，预先把每一条祖先路径上的系数合并为单个向量 \(c_i \in \mathbb{R}^B\)：
  \[
  \hat{\mu}_i(t) = \sum_{j=1}^{B} b_{\mu j}(t) \left( \sum_{k=0}^{\ell_i} \left( \prod_{p=0}^{k-1} \beta_i \right) F_{\text{anc}(i,k), j} \right) = \sum_{j=1}^{B} b_{\mu j}(t) c_{ij}
  \]
- 合并操作离线完成，推理时仅需对每个高斯做 \(B\) 次标量-向量乘法，完全消除树遍历。合并前后仅存在浮点累加顺序带来的微小数值差异（PSNR 变化 < \(10^{-6}\)），且存储减少、帧率显著提升。

### 2.4 训练流程

- 初始阶段先训练静态分量，随后引入时间动态。稠密化指标为平均屏幕空间 2D 梯度。训练损失为 MSE 和 SSIM 的加权和。
- 定期的叶子节点剪枝、定制 CUDA 核函数保证训练时树遍历开销极低。

## 3. 实验设计

- **数据集**：
  - **D-NeRF 数据集**：8 个合成动态场景，单目视频，仅一张训练视图，评估新视角渲染。
  - **Neural 3D Video (N3V) 数据集**：6 个真实室内动态场景（2704×2028，半分辨率使用），18–21 个相机，取中心相机为测试集，共 300 帧。
- **基准指标**：PSNR、SSIM、LPIPS，训练时间，推理帧率（FPS），模型存储大小（MB），高斯数量（#Gauss）。
- **对比方法**：
  - NeRF 类：DNeRF, K-Planes, HexPlanes, TiNeuVox, NeRFPlayer, HyperReel, DyNeRF, MixVoxels 等。
  - GS 类：4DGaussian, CompactDGS, DynMF, 4DRotorGS, RealTime4DGS, SpaceTimeGS, Grid4D 等。

## 4. 资源与算力

- 所有实验在单张 **NVIDIA RTX4500 Ada** GPU 上进行。
- 训练时间：D-NeRF 平均每场景 **4 分钟**，N3V 平均每场景 **0.57 小时**；推理帧率可达 **230 FPS**（D-NeRF）和 **206 FPS**（N3V）。
- 未报告多卡或 CPU 混合训练。

## 5. 实验数量与充分性

- 两组主实验（各 8 个和 6 个场景）与大量 SOTA 方法对比（至少 10 种以上）。
- 消融实验：
  - 树深度效应（5 个档位：0, 4, 15, 29, 73），评估 PSNR/SSIM；
  - 树合并不合并的数值差异（∆PSNR, ∆SSIM, ∆LPIPS, ∆存储, ∆FPS）；
  - 衰减加权聚合有无的视觉对比；
  - 时间不透明度窗口的有无及其影响；
  - 树深度分布的统计分析（直方图与平均高斯数）。
- 实验设计客观，与主流协议一致，消融充分支撑核心设计选择，对比公平。

## 6. 主要结论与发现

- TreeSplat 在两个动态数据集上均取得 **SOTA 重建质量**（D-NeRF 平均 37.11 dB，N3V 平均 32.21 dB），同时维持 **200 FPS 以上渲染**、模型体积小（28 MB / 170 MB）、训练快（4 分钟 / 0.57 小时）。
- 层次化运动树能有效捕获高斯之间的结构化运动关联，树深度适度增长（如 29）带来显著质量提升，过深则可能引入噪声。
- 衰减加权聚合稳定了优化，避免了深层祖先的梯度爆炸。
- 合并策略可无损高效实现，数值差异可忽略，是模型部署的关键优势。
- 时间不透明度窗口在本框架中不必要，甚至有害，因为运动本身已能表达透明度的时变。

## 7. 优点

- **创新性**：首次将层次化树结构与显式运动基函数结合，并与高斯稠密化“共增长”，自适应捕获多尺度运动相关性。
- **高效性**：训练树遍历开销低，推理时通过离线合并彻底消除遍历，实现极速渲染与低存储。
- **稳定性**：衰减加权聚合优雅地解决了深层梯度爆炸问题，允许树在训练中加深。
- **完备性**：论文提供了从理论公式、实现细节（CUDA 核）到广泛实验的完整链条，可复现性强。
- **实用性**：设计不依赖特定基函数形式，为未来扩展（如不同基函数或更大规模场景）提供了灵活接口。

## 8. 不足与局限

- **树深度调节需手工设定**：深度增长间隔（如每 500 次迭代）为超参数，不同场景的最佳深度可能不同，目前缺乏自适应终止或自动调节机制。
- **对极度不规则运动的泛化性未知**：运动树依赖局部子树的共享先验，若场景包含大量独立、无规律的运动，层次结构可能引入错误归纳偏置。
- **合并后丧失可编辑性**：离线合并使推理高效，但丧失了层次结构，不利于后续对局部运动进行交互式编辑或动画重定向。
- **训练时仍须维护树结构**：虽然开销已优化，但对于数十万高斯的场景，树更新和遍历仍有一定内存和计算代价，未能实现完全“推理级”的训练效率。
- **基础假设限制**：需已知相机位姿和多视角同步视频输入；对极度稀疏视角或快速运动可能退化（文中未讨论）。
- **局限性讨论缺失细节**：正文指出局限性在附录，但提供的文本中未呈现具体分析，可能影响完整评估。

（完）
