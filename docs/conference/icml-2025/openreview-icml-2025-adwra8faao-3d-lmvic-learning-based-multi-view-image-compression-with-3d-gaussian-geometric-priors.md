---
title: "3D-LMVIC: Learning-based Multi-View Image Compression with 3D Gaussian Geometric Priors"
title_zh: 3D-LMVIC：基于3D高斯几何先验的学习式多视图图像压缩
authors: "Yujun Huang, Bin Chen, Niu Lian, Xin Wang, Baoyi An, Tao Dai, Shu-Tao Xia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AdWRA8faAO"
tags: ["query:gs-slam"]
score: 4.0
evidence: 使用3D高斯泼溅为多视图压缩提供几何先验
tldr: 现有基于学习的多视图图像压缩方法难以处理大基线系统中的复杂视差。本文提出3D-LMVIC框架，利用3D高斯泼溅提取几何先验，实现准确的视差估计，并结合深度图压缩和视图排序策略，提升了压缩效率。这项工作展示了3DGS在几何建模方面的潜力，虽然主要面向压缩，其方法可能迁移到场景表示任务中。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1752, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1780, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1680, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1770, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1777, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-adwra8faao/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1780, \"height\": 1214, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-adwra8faao/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1344, \"height\": 591, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-adwra8faao/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-adwra8faao/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-adwra8faao/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1314, \"height\": 211, \"label\": \"Table\"}]"
motivation: 现有方法依赖2D投影相似性预测视差，在广基线系统中精度不足。
method: 提出3D-LMVIC，利用3D高斯泼溅提取几何先验进行视差估计，并引入深度图压缩和多视图排序消除冗余。
result: 压缩框架提升了多视图图像压缩的率和质量，证明了3DGS几何先验的有效性。
conclusion: 3DGS可作为有效的几何先验来源，改进多视图压缩，其思路可推广至场景表示领域。
---

## Abstract
Existing multi-view image compression methods often rely on 2D projection-based similarities between views to estimate disparities. While effective for small disparities, such as those in stereo images, these methods struggle with the more complex disparities encountered in wide-baseline multi-camera systems, commonly found in virtual reality and autonomous driving applications. To address this limitation, we propose 3D-LMVIC, a novel learning-based multi-view image compression framework that leverages 3D Gaussian Splatting to derive geometric priors for accurate disparity estimation. Furthermore, we introduce a depth map compression model to minimize geometric redundancy across views, along with a multi-view sequence ordering strategy based on a defined distance measure between views to enhance correlations between adjacent views. Experimental results demonstrate that 3D-LMVIC achieves superior performance compared to both traditional and learning-based methods. Additionally, it significantly improves disparity estimation accuracy over existing two-view approaches.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 多视图图像压缩是 VR/AR、自动驾驶等 3D 应用的关键技术，但现有方法主要基于 2D 投影相似性（如同源矩阵、块匹配或交叉注意力）来估计视差，难以处理**广基线多相机系统**中复杂的视差和旋转造成的非刚性形变。
- 论文要解决的核心问题是：**如何利用显式的 3D 几何先验来提升多视图压缩的效率与视差估计精度**。通过引入 3D 高斯泼溅（3D Gaussian Splatting）作为几何先验，把视角间的 2D 图像关联提升到 3D 空间，从而实现更准确的视差对齐和冗余消除。

### 2. 论文提出的方法论
整体框架 **3D‑LMVIC** 包含三个关键模块：

- **基于 3D‑GS 的深度与视差估计**
  - 先对多视图图像训练一个 3D‑GS 模型，利用中值深度估计（沿射线透射率首次低于 0.5 的点）得到每视图深度图 \(d_n\)。
  - 通过相机内外参，将目标视图像素反投影到 3D 世界点，再投影到参考视图像素坐标，得到像素级视差 \(\Delta_n\)。
  - 同时计算一个**重叠掩膜** \(x_{n,m}\)，用于剔除因遮挡、出视场或非正半空间而无效的视差区域，避免融合噪声。

- **图像与深度压缩模型**
  - **图像压缩模型**：以重建的深度图 \(\hat{d}_{n-1},\hat{d}_n\) 作为输入，通过视差提取器（含 DPE 模块）和参考特征提取器（RFE）生成多尺度参考特征；利用**图像上下文传输模块（ICT）** 将参考特征按视差对齐后注入当前视编码/解码主干。
  - **深度图压缩模型**：基于前一视图的重建深度 \(\hat{d}_{n-1}\) 进行跨视深度预测（CVDP 模块），生成预测深度 \(d_{n,p}\) 和掩膜，再通过深度上下文集成模块（DCI）融合到深度编解码器中。
  - 两者均使用超先验熵模型与四分树分区熵模型（QPEM）。训练损失综合考虑图像失真、深度 MSE 和所有码率。

- **多视图序列排序策略**
  - 定义视图间距离度量 \(D_V(i,j)=\|V_iV_j^{-1}-I\|_F\)（证为度量），利用贪心算法从无序视图中挑选相邻重叠最大的顺序，增强视图间相关性。

### 3. 实验设计
- **数据集**
  - **Tanks&Temples**：21 个室内外场景。
  - **Mip‑NeRF 360**：9 个无边界场景（5 室外、4 室内）。
  - **Deep Blending**：9 个涵盖室内外、植被、夜景的复杂场景。
  - 每个场景 90% 图像用于训练，10% 用于测试。

- **Benchmark 与方法对比**
  - 传统多视图编码：MV‑HEVC（HTM‑16.3）。
  - 学习式多视图编码：HESIC/HESIC+、MASIC、SASIC、LDMIC‑Fast/LDMIC、BiSIC‑Fast/BiSIC（共 8 种变体）。
  - 3D‑GS 压缩方法：HAC。
  - 与 HEVC 视频编码也做了补充对比（HM‑18.0, lowdelay P, YUV444）。

- **评价指标**
  - 率失真曲线（bpp vs. PSNR/MS‑SSIM）和 BDBR 节省率。

### 4. 资源与算力
- 文中未明确说明训练所用的 GPU 型号、数量及总训练时长。仅提及：
  - 训练超参：Adam 优化器，batch size = 2，初始学习率 \(10^{-4}\)，每 60 epoch 衰减一半，共训练 300 epoch。
  - 推理复杂度：给出 MACs、参数量、编解码时间和内存（在 Intel Xeon Gold 6330 CPU + 10752 核 GPU 上测量），编码/解码时间分别为 0.19s 和 0.18s。
- 算力资源描述欠完整，无法精确评估训练开销。

### 5. 实验数量与充分性
- **实验组数**：
  - 三个数据集上的主压缩实验，对比 10+ 种方法，含 PSNR 和 MS‑SSIM 两种失真指标，并提供 BDBR 表。
  - 对齐质量实验（Tanks&Temples 的 Train 场景），对比 8 种对齐/光流/深度估计方法，给出 PSNR/MS‑SSIM 和可视化。
  - 消融实验（Tanks&Temples）：5 种变体（无跨视信息、直接拼接、无掩膜、无深度预测、随机排序 vs 排序），展示 RD 曲线。
  - 补充实验：与 HEVC 的 BDBR 对比；复杂度表格；可视化重建质量。
- **公平性**：所有学习式方法在同一训练/测试集上训练和评估，确保公平；BDBR 以 MV‑HEVC 为锚点，可横向比较。
- **充分性**：多数据集、多种基线、消融和额外对比，实验设计较为完整。但未进行跨数据集的泛化测试（例如在一个数据集上训练后在另一个测试），没有动态场景结果。

### 6. 论文的主要结论与发现
- 3D‑LMVIC 在所有三个数据集上均以显著的 BDBR 节省超越传统 MV‑HEVC 和最新的学习式多视图编码器（如 BiSIC），尤其在 PSNR 和 MS‑SSIM 上都取得最优。
- 基于 3D‑GS 几何先验的视差估计方法在视觉对齐精度上（PSNR 18.14 dB, MS‑SSIM 0.8053）大幅优于块匹配、光流、纯深度估计等方案。
- 深度压缩模型与掩膜设计有效滤除了非重叠区域噪声；视图排序策略使无序序列性能接近人工排序。
- 该方法打通了 3D 场景表示与 2D 压缩之间的桥梁，为 geometry‑aware 压缩提供了新范式。

### 7. 优点
- **新颖性强**：首次将 3D Gaussian Splatting 作为明确的几何先验引入多视图图像压缩，将视差估计从 2D 图像域提升到 3D 空间。
- **完整的系统设计**：覆盖深度估计、视差和掩膜计算、跨视图特征融合、深度图压缩、视图排序，环环相扣。
- **性能优异**：在三个代表性数据集上均取得最佳 RD 性能，且视差对齐质量明显优于现有方法。
- **可解释性好**：通过显式几何变换和掩膜，避免了黑盒注意力对齐，可视化合理。
- **模块化实验**：消融实验清晰验证了掩膜、深度预测、排序等每个组件的贡献。

### 8. 不足与局限
- **依赖预训练 3D‑GS**：方法需要为每个场景训练一个 3D‑GS 模型并获得相机参数，增加了预处理开销，可能限制实时或在线场景应用。
- **算力与训练细节缺失**：未公布训练 GPU 型号、数量和总训练时间，难以评估实际计算成本和可复现性。
- **静态场景假设**：实验均在静态多视图数据集上进行，未讨论动态物体或时间序列中的运动补偿，对动态内容压缩的适用性存疑。
- **泛化性未验证**：仅在三个性质相近的数据集上测试，未在自动驾驶（如 nuScenes）或移动拍摄等更复杂的真实场景下评估跨数据集泛化能力。
- **复杂度偏高**：编码器 MACs 479 G，虽然推理速度尚可，但模型参数多（编码器约 42 M），可能对移动端部署不够友好。

（完）
