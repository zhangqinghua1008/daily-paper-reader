---
title: "3D Gaussian Flats: Hybrid 2D/3D Photometric Scene Reconstruction"
title_zh: "3D Gaussian Flats: 混合2D/3D光度场景重建"
authors: "Maria Taktasheva, Lily Goli, Alessandro Fiorini, Zhen Li, Daniel Rebain, Andrea Tagliasacchi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=uVxQEIgXfL"
tags: ["query:gs-slam"]
score: 9.0
evidence: 混合2D/3D高斯表示用于高质量新视角合成与场景重建
tldr: 现有方法在平坦无纹理表面重建时会产生半透明不规则结果，3D Gaussian Flats提出混合2D平面高斯与3D自由高斯联合优化，动态检测并细化平面区域，在ScanNet++和ScanNet上达到最优深度估计，兼顾视觉保真度和几何精度。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1411, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 831, \"height\": 244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 1191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 589, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 1103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1424, \"height\": 1770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1507, \"height\": 1008, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1423, \"height\": 1321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 1978, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uvxqeigxfl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1446, \"height\": 1365, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-uvxqeigxfl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 764, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uvxqeigxfl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uvxqeigxfl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1357, \"height\": 576, \"label\": \"Table\"}]"
motivation: 平坦无纹理表面导致光度重建目标不适定，产生凹凸不平的半透明重建结果。
method: 联合优化受约束的二维平面高斯与自由三维高斯，动态检测平面区域。
result: 在ScanNet++和ScanNet上取得了最先进的深度估计性能。
conclusion: 混合表示有效解决了平面区域的退化问题，提升了整体重建质量。
---

## Abstract
Recent advances in radiance fields and novel view synthesis enable creation of realistic digital twins from photographs. However, current methods struggle with flat, texture-less surfaces, creating uneven and semi-transparent reconstructions, due to an ill-conditioned photometric reconstruction objective. Surface reconstruction methods solve this issue but sacrifice visual quality. We propose a novel hybrid 2D/3D representation that jointly optimizes constrained planar (2D) Gaussians for modeling flat surfaces and freeform (3D) Gaussians for the rest of the scene. Our end-to-end approach dynamically detects and refines planar regions, improving both visual fidelity and geometric accuracy. It achieves state-of-the-art depth estimation on ScanNet++ and ScanNetv2, and excels at mesh extraction without overfitting to a specific camera model, showing its effectiveness in producing high-quality reconstruction of indoor scenes.

---

## 论文详细总结（自动生成）

**论文总结：3D Gaussian Flats — 混合2D/3D光度场景重建**

### 1. 核心问题与整体含义
- **研究背景**：现代神经辐射场与高斯泼溅方法在室内场景中，对于墙壁、天花板、桌面等平坦无纹理表面，因光度重建目标严重不适定而产生凹陷、半透明等几何失真，难以提取高质量网格。
- **核心矛盾**：纯体积表示（如3DGS）在平坦区域缺乏几何约束，表面重建方法（如2DGS）虽能改善几何但牺牲视觉逼真度。
- **整体含义**：提出一种混合2D平面高斯与3D自由高斯的端到端表示，在训练过程中动态检测并细化平面区域，同时实现高视觉质量与高几何精度，达到最先进的深度估计和跨相机模态的网格提取。

### 2. 方法论
- **混合表示**：场景由两类高斯组成：
  - **2D平面高斯**：锁定在由原点与法向量定义的平面上，仅保留2D面内位置、旋转、缩放与不透明度/颜色，平面到世界变换将其映射为可渲染的3D高斯。
  - **3D自由高斯**：覆盖场景其余部分，不施加平面约束。
- **训练流程**：
  - **预热阶段**（3500次迭代）：仅用3D高斯进行标准光度优化。
  - **平面训练阶段**（循环交替）：
    1. **平面初始化**：根据预计算的语义分割掩码，选取投影在掩码内、不透明度高且深度接近的高斯，通过RANSAC拟合候选平面；将内点3D高斯“捕捉（snap）”为2D平面高斯（投影到平面局部坐标，去除垂直于平面的自由度）；若与已有平面相似则合并。
    2. **块坐标下降优化**：先固定高斯，仅优化平面参数（原点、法向10步，损失=光度损失+掩膜损失）；再固定平面，联合优化所有高斯参数（100步，损失额外包含总变分深度正则、尺度正则、不透明度正则）。
- **平面重定位**：当自由高斯靠近已检测平面时（垂直距离和面内距离均小），依据概率 \( p \sim B(\beta) \) 将其转化为平面高斯，其中 \(\beta = (1-\Phi(d_\perp/\sigma_\perp))\cdot(1-\Phi(d_\parallel/\sigma_\parallel))\)，加速平面生长。
- **与MCMC densification结合**：沿用3DGS-MCMC的动静克隆策略，并对低不透明度高斯进行重定位。

### 3. 实验设计
- **数据集**：
  - **ScanNet++**：11个室内场景，iPhone视频流采样（每10帧训练，每8帧测试），带有真实深度网格。
  - **ScanNetv2**：5个场景，视图更稀疏，无SfM初始化，随机初始化点云。
- **基准对比方法**：
  - 体积重建：3DGS、3DGS-MCMC、RaDe-GS
  - 表面重建：2DGS、PGSR
  - 平面重建方法：AirPlanes、PlanarRecon（用于网格提取任务）
- **评价指标**：
  - 图像质量：PSNR、SSIM、LPIPS
  - 深度质量：RMSE、MAE、AbsRel、δ阈值准确率
  - 网格质量：精度、完整性、Chamfer距离、F1分数、VOI、RI、SC（平面网格分割与提取）
- **任务**：新视角合成（NVS）、深度估计、平面网格提取。

### 4. 资源与算力
- **硬件**：单张NVIDIA A6000 ADA GPU（46 GB显存）。
- **训练时长**：单个ScanNet++/ScanNetv2场景约1小时，与PGSR相当，比3DGS-MCMC长约1.5倍。
- **额外时间**：网格提取约3分钟，SAM掩膜传播平均7分钟。

### 5. 实验数量与充分性
- **主要实验**：
  - 两个数据集（ScanNet++、ScanNetv2）上的NVS与深度评估，共对比5种基线的定量表格与定性示意图。
  - 网格提取实验：在DSLR和iPhone两子集上与2种平面重建基线对比，提供网格与分割指标。
- **消融研究**：
  - 损失组件：去除Lmask、LTV的影响。
  - 优化策略：固定平面参数不优化 vs 同时联合优化。
  - 2D高斯设计：取消snap操作（即纯3D+平面正则）、用正则替代snap、取消平面重定位。
  - 初始化鲁棒性：对比SfM初始化和随机初始化下的性能。
- **实验充分性**：覆盖多数据集、多基线、多任务，消融设计针对各核心组件，定量与定性结合，比较公平客观。

### 6. 主要结论与发现
- 混合2D/3D表示在室内场景深度估计上达到最先进水平，同时保持与全3D方法（3DGS-MCMC）相当的图像质量。
- 在稀疏视图的ScanNetv2上，本方法利用平面先验，在图像与深度两方面均大幅度超越2DGS和3DGS方法。
- 平面网格提取跨不同相机模型（iPhone/DSLR）保持高质量，克服了以往方法对特定采集模态的过拟合问题。
- 消融实验证实：交替优化、平面捕捉、重定位和掩膜损失对最终几何精度至关重要。

### 7. 优点
- **兼顾视觉与几何**：在平面区域用2D高斯保证致密、不透明的几何，复杂区域用3D高斯保证表达力，消除孔洞和半透明问题。
- **端到端联合优化**：平面检测与光场重建同时进行，无需后处理重拟合，优化相互促进。
- **兼容渲染管线**：完全继承3DGS的快速光栅化框架，额外开销可控。
- **泛化能力强**：零样本跨相机模态网格提取，不依赖特定训练分布。
- **动态平面成长与重定位**：通过概率重定位和合并策略，逐步完善平面覆盖，避免陷入欠生长。

### 8. 不足与局限
- **依赖初始重建质量**：预热阶段3DGS在弱纹理平坦区域生成的高斯数量可能不足，影响平面检测。
- **外观模型限制**：使用的球谐系数较弱，可能迫使场景产生多余几何来补偿视角相关效果，限制了可恢复的平面数量。
- **外部掩膜依赖**：方法需要语义平面掩膜作为输入（如SAMv2+PlaneRecNet生成），掩膜错误会传播，但可随分割技术进步而改善。
- **计算开销**：RANSAC平面拟合与块坐标下降交替优化使训练时间比基础3DGS-MCMC长约50%。
- **场景类型受限**：目前主要针对室内场景，对室外复杂拓扑或非平面区域占优的场景尚未验证。

（完）
