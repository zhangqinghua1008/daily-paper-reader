---
title: "Gaussian Herding across Pens: An Optimal Transport Perspective on Global Gaussian Reduction for 3DGS"
title_zh: 高斯汇聚：一种基于最优传输的全局高斯缩减方法
authors: "Tao Wang, Mengyu Li, Geduo Zeng, Cheng Meng, Qiong Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=j1QkrVjNVF"
tags: ["query:gs-slam"]
score: 6.0
evidence: 提出全局高斯点缩减方法以实现紧凑的三维高斯场景表示
tldr: 针对3DGS大量冗余高斯原语导致内存与渲染负担大的问题，本工作从最优传输角度将压缩建模为全局高斯混合约减，通过KD树分区上的复合传输散度最小化生成紧凑几何表示，并解耦外观属性微调，显著减少高斯原语数量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1383, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1325, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1380, \"height\": 993, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1327, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1326, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-j1qkrvjnvf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1409, \"height\": 1735, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-j1qkrvjnvf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-j1qkrvjnvf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-j1qkrvjnvf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 731, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-j1qkrvjnvf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-j1qkrvjnvf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 934, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-j1qkrvjnvf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1025, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-j1qkrvjnvf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 437, \"label\": \"Table\"}]"
motivation: 3DGS需要数百万冗余高斯原语，导致内存和渲染开销过大。
method: 将3DGS压缩转化为全局高斯混合缩减，优化传输散度并解耦外观微调。
result: 在保证全局保真度的同时大幅减少了高斯原语数量。
conclusion: 最优传输为3DGS提供了一种全局保真的高效压缩方案。
---

## Abstract
3D Gaussian Splatting (3DGS) has emerged as a powerful technique for radiance field rendering, but it typically requires millions of redundant Gaussian primitives, overwhelming memory and rendering budgets. Existing compaction approaches address this by pruning Gaussians based on heuristic importance scores, without global fidelity guarantee. To bridge this gap, we propose a novel optimal transport perspective that casts 3DGS compaction as global Gaussian mixture reduction. Specifically, we first minimize the composite transport divergence over a KD-tree partition to produce a compact geometric representation, and then decouple appearance from geometry by fine-tuning color and opacity attributes with far fewer Gaussian primitives. Experiments on benchmark datasets show that our method (i) yields negligible loss in rendering quality (PSNR, SSIM, LPIPS) compared to vanilla 3DGS with only 10\% Gaussians; and (ii) consistently outperforms state-of-the-art 3DGS compaction techniques. Notably, our method is applicable to any stage of vanilla or accelerated 3DGS pipelines, providing an efficient and agnostic pathway to lightweight neural rendering.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：3D Gaussian Splatting (3DGS) 在渲染质量与实时性上非常成功，但其迭代稠密化过程会生成数百万个冗余的高斯原语（Gaussian primitives），导致显存占用高、存储开销大、单帧渲染时间长，严重限制了在资源受限平台（如移动端、AR/VR）上的部署。
- **现有方法的不足**：当前压缩方法（如 LightGaussian、PUP‑3DGS 等）多基于启发式重要性评分进行剪枝，这些方法独立地评估每个高斯原语，缺少全局保真度保证，容易丢失关键的结构细节或扭曲场景几何。
- **本文动机**：将 3DGS 压缩视为一个优化问题——用更少的高斯原语尽可能准确地近似原始三维场景。作者从统计学视角出发，将 3DGS 的几何结构解释为一个高斯混合模型（GMM），从而把压缩问题转化为高斯混合约减（Gaussian Mixture Reduction, GMR）问题，并利用最优运输理论（Optimal Transport）设计了一种全局性的压缩框架，以在显著减少高斯原语数量的同时最大限度地保持渲染质量。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将 3DGS 的几何（位置、协方差、不透明度）解释为未归一化的高斯混合密度，然后通过最小化复合传输散度（Composite Transportation Divergence, CTD）将该高混合阶的 GMM 近似为一个低混合阶的 GMM。整个压缩过程与外观属性解耦，压缩后仅对颜色和不透明度进行微调，从而在几何保真的基础上恢复逼真渲染效果。
- **关键技术细节**：
  - **几何压缩（GMR）**：
    - 定义两个高斯混合之间的 CTD 作为优化目标，该散度可以看作在高斯分布空间上的最优运输问题。
    - 问题求解可以转化为一个类似 k‑means 的迭代算法：分配步骤将每个高斯原语划分到最近的簇；更新步骤则计算簇的“重心”。作者采用了一种新的代价函数：  
      \(c(\phi(\cdot; \mu,\Sigma), \phi(\cdot; \mu',\Sigma')) = \|\mu-\mu'\|_2^2 + \|\Sigma-\Sigma'\|_F^2\)  
      该代价函数可使更新步骤退化为对均值和协方差的加权平均，避免了 KL 散度所需要的协方差矩阵求逆，大幅提高计算效率。
    - **分块 GMR（KD‑tree 分区）**：直接对整个场景运行 GMR 计算量巨大，因此利用 KD‑tree 对场景进行空间分块。每个块内独立执行 GMR，极大降低了每步的计算和内存开销。块的大小 s 和总深度 d 根据高斯总数 n 自适应确定。
  - **外观优化**：几何压缩后，冻结高斯的位置和协方差，仅用标准 3DGS 的渲染损失对颜色和不透明度（α 和 SH 系数）进行有限步数的微调（fine‑tune）。
  - **算法流程（GHAP）**：
    1. 标准 3DGS 训练 T 步，获得初始高斯集合。
    2. 使用 KD‑tree 将高斯中心点划分成块。
    3. 每个块内利用 GMR（上述代价函数和 k‑means 迭代）将高斯原语数量缩减到保留率 ρ（例如 10%）。
    4. 为每个压缩后的高斯选取外观初值（从原集合中取最近高斯的颜色和不透明度）。
    5. 再训练 T 步，仅优化外观参数。

## 3. 实验设计
- **数据集/场景**：
  - Tanks & Temples（Truck, Train）
  - Mip‑NeRF 360（Bicycle, Bonsai, Counter, Flowers, Garden, Kitchen, Room, Stump, Treehill）
  - Deep Blending（Dr. Johnson, Playroom）
- **评价指标**：PSNR、SSIM、LPIPS，以及高斯原语数量（kGaussians）。
- **对比方法**：
  - 端到端压缩变体：Mini‑Splatting、3DGS‑MCMC、LocoGS。
  - 后处理压缩方法：LightGaussian、PUP‑3DGS、Trimming the Fat、MesonGS。
  - 所提方法的两种配置：3DGS+GHAP（以 vanilla 3DGS 为骨干），MiniSplatting+GHAP（以 Mini‑Splatting 为骨干）。
- **实验设置**：所有方法均训练共 30k 次迭代，后处理方法先训练 15k 取得同一骨干模型，再压缩并微调 15k；端到端方法按各自默认配置完成训练。

## 4. 资源与算力
- **硬件信息**（论文附录 B 中给出）：
  - 服务器：256 GB RAM，96 核 Intel Xeon Platinum 8255C CPU。
  - 工作站：5 张 NVIDIA RTX 3090 GPU，每张 24 GB VRAM。
- **训练时长**：未明确给出具体小时数，但所有方法均在 30k 迭代框架下完成；压缩阶段的额外开销主要来自 KD‑tree 构建和块内 GMR 迭代，论文指出相比其他压缩方法，GHAP 的运行时间处于中间偏快水平，内存稍高但未超出一个数量级。

## 5. 实验数量与充分性
- **实验组数丰富**：
  - 3 个标准数据集、多个室内外场景，场景覆盖不同复杂度和光照条件。
  - 多种对比方法（端到端与后处理方法共 8 种以上）。
  - 压缩率对比：10%、20%，以及保留率‑失真率曲线（RD 曲线）。
  - 即插即用验证：在 3DGS、AtomGS、Mini‑Splatting‑D 三种不同骨干上的压缩效果。
  - 消融实验：
    - KD‑tree 深度对性能、内存、时间的影响。
    - 损失函数中 LPIPS 权重的消融。
    - GMR vs 随机子采样（控制变量），验证几何压缩的有效性。
    - 压缩频率（多次压缩 vs 一次压缩）的影响。
- **公平性与客观性**：所有方法采用相同的训练总迭代次数、相同的评估指标，骨干模型统一初始化；不同压缩率下均以相同微调步数进行比较，实验设计较为公平客观。

## 6. 论文的主要结论与发现
- **高效且保真**：GHAP 可以在仅保留 10% 高斯的极端压缩下，保持与原始 3DGS 接近的渲染质量（PSNR、SSIM、LPIPS 仅轻微下降），甚至在某些场景（如 “Kitchen”）因为正则化效果而超越原模型。
- **显著优于启发式剪枝**：在所有数据集和压缩率上，GHAP 的性能始终优于 LightGaussian、PUP‑3DGS、Trimming the Fat 等启发式剪枝方法，也优于同数量级高斯数的 3DGS‑MCMC。
- **算法无关即插即用**：GHAP 可灵活嵌入多种 3DGS 变体（包括 Mini‑Splatting、AtomGS 等），作为后处理模块提升压缩效果，且计算开销合理，不牺牲实用性。
- **理论与工程结合**：首次将 GMR 与最优运输理论应用于 3DGS 压缩，提出的新代价函数和分块策略使得理论与大规模场景的实际需求相结合。

## 7. 优点：方法或实验设计上的亮点
- **全局几何保真**：不同于对单个高斯独立打分的剪枝方法，GHAP 通过最小化 CTD 来全局调整高斯的位置与形状，理论上能更好地保持场景的整体几何结构。
- **解耦优化**：将几何压缩与外观优化分离，既保证了 GMR 的数学性质，又可通过轻量级微调恢复渲染细节。
- **可扩展与高效**：KD‑tree 分块策略使复杂度从 \(O(\rho n^2)\) 降低到 \(O(\rho s^2 \log n)\)，块间可并行，适合大规模场景。
- **代价函数设计巧妙**：采用均值和协方差的 Frobenius 范数平方和作为代价，使得分配和更新步骤均闭式、稳定、计算成本低。
- **综合性评估**：多数据集、多骨干、多压缩率、多种对比方法与消融实验，验证全面。

## 8. 不足与局限
- **对输入质量依赖性强**：若原始 3DGS 模型本身因原语不足而存在明显伪影，GHAP 无法从根本上纠正这些缺陷（文中“Bicycle”场景的案例）。
- **LPIPS 指标略有不足**：文中指出，基础损失配置下 LPIPS 略逊于某些剪枝方法，但可通过调整损失权重改善（代价是 PSNR 和 SSIM 轻微下降）。
- **分块可能引入边界不连续**：块内独立压缩可能导致块边界附近新的高斯分布不够平滑，影响渲染连续性。
- **未在动态场景测试**：所有实验基于静态场景数据集，尚未扩展到动态 3DGS 或实时时序渲染。
- **外观与几何仍非完全解耦**：外观微调阶段虽冻结了几何，但颜色和不透明度的更新仍可能影响最终的隐含几何表达，严格解耦仍有提升空间。
- **部分实验细节未公开**：附录虽给出硬件，但未报告具体训练总时长和微调收敛性具体表现，复现时需参考源代码。

（完）
