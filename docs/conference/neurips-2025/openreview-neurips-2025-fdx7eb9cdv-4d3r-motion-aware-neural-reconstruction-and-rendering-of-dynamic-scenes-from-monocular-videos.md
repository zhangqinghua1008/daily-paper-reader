---
title: "4D3R: Motion-Aware Neural Reconstruction and Rendering of Dynamic Scenes from Monocular Videos"
title_zh: 4D3R：从单目视频中运动感知的动态场景神经重建与渲染
authors: "Mengqi Guo, Bo Xu, Yan Li, Gim Hee Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FDX7EB9CDv"
tags: ["query:gs-slam"]
score: 6.0
evidence: 从单目视频中进行无姿态动态新视角合成并估计相机姿态
tldr: 4D3R从无姿态标注的单目视频重建动态场景，首先估计初始位姿和几何，再用运动感知的捆绑调整进行细化，实现高质量自由视点渲染。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdx7eb9cdv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1298, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdx7eb9cdv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1231, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdx7eb9cdv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1293, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdx7eb9cdv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 863, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdx7eb9cdv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1296, \"height\": 998, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdx7eb9cdv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1372, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdx7eb9cdv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1478, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdx7eb9cdv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 915, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdx7eb9cdv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 903, \"height\": 539, \"label\": \"Table\"}]"
motivation: 从单目视频进行动态场景新视角合成需要同时估计未知相机位姿和场景结构，现有方法难以兼顾。
method: 提出4D3R，两阶段框架：先用3D基础模型估计位姿和几何，再通过运动感知细化实现姿态和场景联合优化。
result: 4D3R在有挑战性的动态场景数据上实现了精确的位姿估计和逼真的新视角渲染。
conclusion: 无姿态的动态神经渲染为移动端自由视点视频应用提供了可行的技术路线。
---

## Abstract
Novel view synthesis from monocular videos of dynamic scenes with unknown camera poses remains a fundamental challenge in computer vision and graphics. While recent advances in 3D representations such as Neural Radiance Fields (NeRF) and 3D Gaussian Splatting (3DGS) have shown promising results for static scenes, they struggle with dynamic content and typically rely on pre-computed camera poses.
We present 4D3R, a pose-free dynamic neural rendering framework that decouples static and dynamic components through a two-stage approach. Our method first leverages 3D foundational models for initial pose and geometry estimation, followed by motion-aware refinement. 4D3R introduces two key technical innovations: (1) a motion-aware bundle adjustment (MA-BA) module that combines transformer-based learned priors with SAM2 for robust dynamic object segmentation, enabling more accurate camera pose refinement; and (2) an efficient Motion-Aware Gaussian Splatting (MA-GS) representation that uses control points with a deformation field MLP and linear blend skinning to model dynamic motion, significantly reducing computational cost while maintaining high-quality reconstruction.
Extensive experiments on real-world dynamic datasets demonstrate that our approach achieves up to 1.8dB PSNR improvement over state-of-the-art methods, particularly in challenging scenarios with large dynamic objects, while reducing computational requirements by 5× compared to previous dynamic scene representations.

---

## 论文详细总结（自动生成）

### 1. 论文核心问题与研究意义
- 该论文聚焦 **单目视频中动态场景的新视角合成**，其核心挑战在于 **相机位姿未知**，且场景包含显著运动和变形。
- 传统方法（如 NeRF、3D Gaussian Splatting）在静态场景表现优异，但动态场景方法大多 **依赖预计算的相机位姿（如 COLMAP）**，在位姿未知时性能急剧下降。
- 将位姿估计与场景重建割裂处理（例如 MonST3R + 4DGS）在大范围动态区域下极易失效，因为大量动态点会被视为异常值，破坏对应关系。
- 该文旨在提出一种 **无姿态的动态神经渲染框架**，通过将位姿估计与运动感知重建深度融合，实现鲁棒、高效率的 4D 场景重建与渲染。

### 2. 方法论
#### 整体框架
- 采用 **两阶段** 策略：先利用 3D 基础模型获取初始位姿与几何，再进行运动感知的联合优化与重建。
- 三个核心模块：**4D‑感知信息提取器**、**运动感知捆调（MA‑BA）**、**运动感知高斯溅射（MA‑GS）**。

#### 关键技术细节
- **4D‑感知信息提取**  
  - 使用预训练 ViT 编码器‑解码器（基于 MonST3R）输出场景坐标图 \(X_t\)、置信度图 \(W_t\)，并融合光流。  
  - 通过高置信度、有限深度的点筛选，结合 SAM2 生成精细动态掩膜 \(M_t\)，用于区分动静态区域。

- **运动感知捆调（MA‑BA）**  
  - 只选择 **静态点**（\(M_t(p_i)=0\)）进行 PnP‑RANSAC 求解初始位姿，大幅降低动态噪声。  
  - 利用可微分密集捆调层（DBA）进一步优化位姿与深度，损失函数中同样 **仅用静态区域** 计算重投影误差，权重由置信度决定。

- **运动感知高斯溅射（MA‑GS）**  
  - 引入一组 **控制点** \(P\)（含 3D 坐标和 RBF 半径），仅对动态区域的控制点进行优化，极大压缩参数空间。  
  - 通过变形场 MLP \(\Theta\) 预测每个控制点在时间 \(t\) 的 6‑DoF 变换（四元数旋转 + 平移）。  
  - 高斯点通过 **线性混合蒙皮（LBS）** 插值获得变形：  
    \[
    \mu'_j = \sum_{k} w_{jk} (R_k^t(\mu_j - p_k) + p_k + T_k^t)
    \]
    其中权重 \(w_{jk}\) 由高斯中心与控制点的欧氏距离经指数归一化得到。  
  - 对方向也进行四元数混合，保持平滑变形。  
  - **两阶段训练**：第一阶段仅优化动态控制点；第二阶段优化高斯参数，并施加梯度隔离，避免控制点与高斯参数竞争。

- **正则化与自适应**  
  - 在目标函数中加入 **ARAP**（局部刚性）与 **刚性约束**（\(L_{rigid}\)）损失。  
  - 自适应控制点：根据梯度幅度在重建影响大的区域增加控制点。

### 3. 实验设计
- **数据集**  
  - HyperNeRF（复杂变形与相机运动）  
  - DyNeRF（多视角同步拍摄的动态视频，仅用单目训练）  
  - MPI Sintel（提供真实位姿，用于位姿评估）
- **评估指标**  
  - 新视角合成：PSNR, MS‑SSIM, SSIM  
  - 位姿估计：ATE（绝对平移误差）, RPE trans/rot（相对平移/旋转误差）
- **对比方法**  
  - 需要已知位姿的动态方法：Nerfies, HyperNeRF, TiNeuVox‑B, 3DGS, FDNeRF, 4DGS, SC‑GS  
  - 无姿态动态方法：RoDynRF, MonST3R+SC‑GS  
  - 专用位姿估计器：DROID‑SLAM, DPVO, ParticleSFM, LEAP‑VO, CasualSAM, NeRF–, BARF 等

### 4. 资源与算力
- 所有实验均在 **单张 NVIDIA RTX3090 GPU** 上运行。
- 训练时间大幅缩短：在 HyperNeRF 上 **仅需 50 分钟**，而 COLMAP‑dependent 方法常需 4‑32 小时，无姿态基线 RoDynRF 需 28 小时。
- 模型存储仅 **80 MB**（对比 MonST3R+SC‑GS 153 MB，RoDynRF 200 MB），计算总需求降低约 **5 倍**。
- 推理速度 **45 FPS**，保持实时性。

### 5. 实验数量与充分性
- 进行了 **三个标准数据集** 上的完整定量评估（Table 1‑4），覆盖复杂动态场景与位姿估计专项测试。
- 与 **十余种** 现有代表性方法全面对比，包括有姿态、无姿态、位姿估计三类，对比公平。
- 系统性 **消融实验**（Table 3）：分别去除运动掩膜、SAM 精炼、MA‑GS 模块，验证各组件贡献（PSNR 下降 5.2 dB ~ 1.8 dB），证明设计合理性。
- 实验设计充分，指标通用，对比基准公开可复现，结论可靠。

### 6. 主要结论与发现
- 提出 **首个运动感知的无姿态动态高斯溅射框架**，将位姿估计与动态重建紧密耦合，打破了传统任务分离的瓶颈。
- 运动感知捆调通过 **静态区域引导的 RANSAC 与 DBA**，显著提升了动态场景下的位姿精度。
- MA‑GS 利用控制点与 LBS 实现高效形变建模，使训练时间、存储和推理开销大幅降低。
- 在多个数据集上，PSNR 提升最高达 **1.8 dB**，且在 **大动态物体场景中优势尤为显著**，达到甚至超过已知位姿方法的水平。

### 7. 优点
- **任务集成创新**：首次将位姿估计、运动分割与 4D 高斯重建在统一框架内联合优化，避免了传统方法位姿误差向重建传导。
- **高效表示**：控制点 + LBS 的紧凑形变设计，NVIDIA GPU 上可实时渲染（45 FPS），存储需求低。
- **鲁棒性增强**：利用 SAM2 细化掩膜并结合置信度筛选，在动态目标占画面主体时仍能稳定工作，而以往方法常失败。
- **训练快速**：两阶段训练策略、梯度隔离与自适应控制点机制，使训练比 COLMAP 依赖方法快 5 倍以上。
- **全面的实验验证**：兼做新视角合成与位姿估计评测，与多个 SOTA 基线公平对比，消融分析完整。

### 8. 不足与局限
- **对场景依赖较强**：需要纹理丰富的帧和足够的静态区域，若动态元素极度复杂且填充大部分画面，性能可能下降。
- **动态对象假设**：假设可区分动态物体（通过 SAM2 分割），对透明、镜面反射或运动模糊严重的物体可能分割不准，影响位姿与重建。
- **非刚体变形有限**：虽用 ARAP 正则化处理软体，但对非常复杂的大变形（如流体、烟雾）可能仍无法精确建模。
- **隐私与伦理**：可能被滥用于监控或未经授权的 3D 重建，作者建议引入隐私保护机制。
- **泛化性**：仅在三个特定数据集上测试，场景多样性有限，在智能手机手持拍摄、直播视频等更随机的真实场景下性能未验证。

（完）
