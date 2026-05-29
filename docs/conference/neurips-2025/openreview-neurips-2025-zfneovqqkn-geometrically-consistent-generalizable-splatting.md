---
title: Geometrically Consistent Generalizable Splatting
title_zh: 几何一致的泛化高斯泼溅
authors: "Mehdi Hosseinzadeh, Shin-Fang Chng, Ian Reid, Simon Lucey, Ravi Garg"
date: 2025-04-27
pdf: "https://openreview.net/pdf?id=ZfNeovqQkn"
tags: ["query:gs-slam"]
score: 7.0
evidence: 学习无位姿的泛化3D高斯泼溅用于新视角合成
tldr: 该工作针对自监督学习3D高斯泼溅（3DGS）中的固有歧义，提出几何一致性约束来指导网络预测无位姿的泛化高斯表示，解决了仅靠视角合成损失无法恢复有意义几何的问题，实现了多视角图像下无需位姿的泛化新视角合成。方法在多个数据集上取得与有监督方法相当的结果，并支持无位姿输入。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfneovqqkn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfneovqqkn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfneovqqkn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1544, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zfneovqqkn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1544, \"height\": 773, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfneovqqkn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 607, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfneovqqkn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zfneovqqkn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 195, \"label\": \"Table\"}]"
motivation: 仅靠视角合成损失不足以从多视图图像中自监督地学习有意义的3D高斯几何。
method: 提出几何一致性损失，指导网络预测几何一致的3D高斯，实现无位姿泛化泼溅。
result: 在无相机位姿条件下，泛化新视角合成质量接近有监督方法。
conclusion: 几何一致性约束是学习泛化3DGS的关键，为自由视角重建提供新思路。
---

## Abstract
Gaussian splatting has emerged as the preferred 3D scene representation due to its incredible speed and accuracy in novel view generation. Various attempts have thus been made to adapt multi-view structure prediction networks to directly predict per-pixel 3D Gaussians from images. However, most work has focused on enhancing self-supervised depth prediction networks to estimate additional parameters for 3D Gaussians -- orientation, scale, opacity, and appearance. We show that optimizing a view-synthesis loss alone is insufficient to recover geometrically meaningful splats in this simple manner. We systematically analyse and address the inherent ambiguities in learning 3D Gaussian splats with self-supervision to learn pose-free generalisable splitting. Our approach achieves state-of-the-art performance in 
(i) geometrically consistent reconstructions, 
(ii) relative pose estimation between images, and 
(iii) novel-view synthesis 
on the RealEstate10K and ACID datasets. We also showcase zero-shot capabilities of the proposed generalizable splatting on ScanNet, where our method substantially outperforms the prior art in recovering geometry and estimating relative pose.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **核心问题**：当前前馈式“泛化高斯泼溅”方法大多只是在已有深度预测网络上简单添加额外输出头，仅用视图合成损失进行自监督训练，严重忽略了 3D 高斯本身的过度参数化特性。这导致学习到的高斯方向、尺度和透明度无法反映场景的真实几何结构，出现退化现象（如方向杂乱、不必要伸长等）。
- **整体含义**：文章指出，仅靠光度损失无法在自监督条件下习得几何上有意义的泛化高斯场；必须引入明确的几何一致性先验，才能同时获得准确的相对位姿、高质量的深度渲染和一致的新视角合成。该工作为无位姿泛化高斯泼溅的几何可靠性奠定了基础。

### 2. 论文提出的方法论

- **主干架构**：以无位姿泛化泼溅方法 NoPoSplat 为基础，采用 2D 高斯（2DGS）表示场景，将每个高斯的第三维尺度设为零，使其退化为表面元素，降低过度参数化。
- **三个损失函数**：
  - \( \mathcal{L}_{synthesis} \)：标准的 RGB + LPIPS 视图合成损失。
  - \( \mathcal{L}_{orient} \)：方向-深度一致性损失。利用假设的像素对齐特性，由相邻像素的高斯中心直接估算局部表面法线，并与高斯方向（协方差矩阵零空间方向）计算 Huber 距离，强制方向与表面法线一致。
  - \( \mathcal{L}_{align} \)：像素对齐损失。显式约束每个高斯中心在给定相机参数下必须投影回其对应的像素位置，避免高斯在自监督时漂移至退化配置。
  \( \mathcal{L}_{total} = \mathcal{L}_{synthesis} + \lambda_o \mathcal{L}_{orient} + \lambda_a \mathcal{L}_{align} \)
- **位姿估计**：利用像素对齐的高斯中心，通过 PnP+RANSAC 恢复相对位姿，并可进一步通过光度优化精调。

### 3. 实验设计

- **训练数据**：RealEstate10K (RE10K) 数据集（67,477 个训练场景），无深度监督，仅使用图像和已知内参。
- **测试数据与基准**：
  - 域内测试：RE10K 测试集（7,289 场景）。
  - 跨域零样本测试：ACID（航拍自然场景）和 ScanNet-V1（室内 RGB-D）。
- **对比方法**：
  - 位姿估计：CoPoNeRF†、DUSt3R†‡、MASt3R†‡、RoMa†‡（† 额外数据，‡ 额外监督）及 NoPoSplat。
  - 几何评估（深度）：pixelSplat、MVSplat、DepthSplat、NoPoSplat 等。
  - 消融研究：逐步添加 2DGS 表示、\( \mathcal{L}_{align} \)、\( \mathcal{L}_{orient} \) 以及同时使用两者。
- **评估指标**：
  - 相对位姿：AUC@5°、10°、20°。
  - 深度：绝对相对误差（Abs Rel）、δ<1.10, δ<1.25 精度。
  - 新视角合成质量（在补充材料中）。

### 4. 资源与算力

- 论文正文未明确提及所使用的 GPU 型号、数量、训练时长等具体算力信息。仅提到训练遵循近期泛化泼溅方法的设置，详细内容在补充材料中。**未说明算力资源**。

### 5. 实验数量与充分性

- **实验组数**：包含约 3 个主要表格和多个定性结果图。
  - 表 1：位姿估计，覆盖 3 个数据集、8 种方法/变体，区分为仅 PnP 和加光度优化两种模式。
  - 表 2：ScanNet 上新视角的深度评估，比较 6 种方法及其变体。
  - 表 3：ScanNet 上源视角的深度评估，比较 8 种方法及其变体。
  - 消融实验：系统性验证 2DGS、\( \mathcal{L}_{align} \)、\( \mathcal{L}_{orient} \) 的独立和组合效果，体现在位姿和深度两个维度。
  - 定性对比：包括网格重建（图1）、高斯参数可视化（图2）、渲染深度图（图3、4）。
- **评估充分性**：实验设计覆盖了多个基准数据集、多种前沿方法，以及对关键组件的拆分验证。对比方法包含了有监督、无监督、位姿依赖和无位姿等多种范式，比较公平、客观。

### 6. 论文的主要结论与发现

- 仅依赖视图合成损失无法产生几何一致的高斯参数，方向、尺度等易出现退化。
- 采用 2DGS 表示可有效降低过度参数化，但仍需额外的先验约束。
- 所提出的局部法线一致性丢失（\( \mathcal{L}_{orient} \)）和像素对齐丢失（\( \mathcal{L}_{align} \)）能够显著稳定训练过程，使高斯方向贴合真实表面法线，并消除高斯位置的漂移问题。
- 结合上述先验后，无位姿泛化泼溅在相对位姿估计上超过多数专门训练的匹配和几何方法，在新视角深度渲染上也大幅领先现有方法。
- 在零样本跨域任务（ScanNet、ACID）上表现出优异的泛化能力。

### 7. 优点

- **问题洞察深刻**：首次系统分析并指出泛化高斯泼溅的几何退化根源。
- **方案简洁有效**：通过极低代价的像素对齐和局部法线一致性约束，在无需深度真值的条件下显著提升几何质量。
- **性能突出**：在无位姿相对位姿估计上超越多类强基准（包括使用额外数据或监督的方法）；深度渲染结果甚至优于位姿已知的方法。
- **通用性强**：提出的先验不依赖于特定主干网络，理论上可集成到其他泛化泼溅框架。

### 8. 不足与局限

- **对基础架构的依赖**：以 NoPoSplat 为基线，未验证在其他骨干网络（如 pixelSplat、MVSplat）上的适用性。
- **表示假设**：采用 2D 高斯假定场景表面为局部平坦的薄片，可能在复杂拓扑或细小结构处受限。
- **算力信息缺失**：未提供训练时间、GPU 数量等关键效率数据，难以评估其计算开销。
- **场景多样性有限**：训练仅使用室内为主的 RE10K，虽展示了跨域零样本能力，但在更复杂的户外大规模场景上的表现仍需验证。
- **动态场景未涉及**：默认为静态刚性场景。

（完）
