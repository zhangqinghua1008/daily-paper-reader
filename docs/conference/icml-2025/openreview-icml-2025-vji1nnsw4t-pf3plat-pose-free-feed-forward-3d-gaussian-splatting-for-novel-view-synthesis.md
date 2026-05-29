---
title: "PF3plat: Pose-Free Feed-Forward 3D Gaussian Splatting for Novel View Synthesis"
title_zh: PF3plat：无位姿前馈三维高斯泼溅新视角合成
authors: "Sunghwan Hong, Jaewoo Jung, Heeseong Shin, Jisang Han, Jiaolong Yang, Chong Luo, Seungryong Kim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VjI1NnsW4t"
tags: ["query:gs-slam"]
score: 10.0
evidence: 提出无位姿前馈3D高斯泼溅新视角合成框架
tldr: 本文针对无标定图像的新视角合成问题，提出PF3plat，一种不需要相机位姿的前馈式3D高斯泼溅框架。通过引入单目深度估计和跨视图对齐训练策略，解决了像素对齐3DGS在稀疏视图下训练不稳、模糊退化等挑战，在不依赖密集视图、准确位姿和大重叠的情况下实现高质量3D重建和视图合成。实验表明该方法在复杂场景下仍能生成细节丰富的新视角图像，显著拓展了3DGS的实用范围。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1549, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1583, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1756, \"height\": 2097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1741, \"height\": 2076, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1265, \"height\": 2071, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1479, \"height\": 2275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1123, \"height\": 2318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vji1nnsw4t/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1120, \"height\": 2291, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1461, \"height\": 632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1717, \"height\": 730, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1520, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 801, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 799, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 802, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 802, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vji1nnsw4t/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 870, \"height\": 248, \"label\": \"Table\"}]"
motivation: 现有3DGS方法依赖密集视图、精确位姿和大重叠，限制了实际应用。
method: 提出无位姿前馈框架，利用单目深度估计弥补跨视图高斯对齐不足，并设计训练策略处理稀疏梯度问题。
result: 在不给定相机位姿的条件下，成功实现高质量新视角合成，重建细节清晰。
conclusion: 该方法放松了3DGS的关键假设，使单次前馈即可从无位姿图像生成新视角，提升了实用性。
---

## Abstract
We consider the problem of novel view synthesis from unposed images in a single feed-forward. Our framework capitalizes on fast speed, scalability, and high-quality 3D reconstruction and view synthesis capabilities of 3DGS, where we further extend it to offer a practical solution that relaxes common assumptions such as dense image views, accurate camera poses, and substantial image overlaps. We achieve this through identifying and addressing unique challenges arising from the use of pixel-aligned 3DGS: misaligned 3D Gaussians across different views induce noisy or sparse gradients that destabilize training and hinder convergence, especially when above assumptions are not met. To mitigate this, we employ pre-trained monocular depth estimation and visual correspondence models to achieve coarse alignments of 3D Gaussians. We then introduce lightweight, learnable modules to refine depth and pose estimates from the coarse alignments, improving the quality of 3D reconstruction and novel view synthesis. Furthermore, the refined estimates are leveraged to estimate geometry confidence scores, which assess the reliability of 3D Gaussian centers and condition the prediction of Gaussian parameters accordingly. Extensive evaluations on large-scale real-world datasets demonstrate that PF3plat sets a new state-of-the-art across all benchmarks, supported by comprehensive ablation studies validating our design choices. We will make the code and weights publicly available.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- 论文针对的是**从稀疏、无位姿的图像集合中，通过单次前馈推理实现高质量新视角合成**的挑战。
- 现有方法（如 NeRF、3DGS）通常依赖密集视图、精确的相机位姿或深度、以及较大的图像重叠，限制了其在实际场景（如随意拍摄的照片）中的可用性。
- 近期虽然出现了无需位姿的泛化式新视角合成工作，但它们在渲染质量、速度以及训练稳定性上仍存在不足。
- **整体含义**：本文致力于放松 3DGS 对“密集视图、准确位姿、大重叠”等苛刻假设，提出一种**前馈式、无位姿的 3DGS 框架**，大幅提升实用性与性能。

### 2. 论文提出的方法论

**核心思想**：利用预训练的单目深度估计与视觉匹配模型提供**粗对齐**，再通过可学习的模块进行**精细对齐**（深度与位姿的进一步优化），并引入**几何置信度**来评估高斯中心可靠性，从而指导高斯参数（透明度、协方差、颜色）的预测。

**关键技术细节与流程**（文字描述）：

1.  **粗对齐（Coarse Alignment）**
    - 使用现成的单目深度模型（如 UniDepth）估计初始深度图 \(D_i\)，使用视觉匹配模型（如 LightGlue）获得图像间对应点 \(\mathcal{M}_{ij}\) 及置信度。
    - 通过鲁棒求解器（RANSAC/PnP）估计相对位姿，再结合深度获得初始相机位姿 \(P_i\) 和 3D 高斯中心（通过反投影 \(p\) 处深度得到 \(\mu_i(p)\)）。

2.  **多视角一致性深度估计（Fine Alignment – Depth Refinement）**
    - 利用深度网络的特征图 \(F_i\)，通过 Transformer 层（自注意力）预测逐像素深度偏移 \(\Delta\delta_i\)。
    - 得到精细化深度 \(\hat{D}_i = D_i + \Delta\delta_i\)。这一步骤不微调整个深度网络，仅训练轻量级适配层，避免遗忘和计算开销。

3.  **相机位姿精化（Fine Alignment – Pose Refinement）**
    - 使用精化后的深度重新计算相对位姿 \(\hat{P}_{ij}\)，再通过可微分、基于幂迭代的平移同步操作恢复绝对位姿 \(\hat{P}_i\)。
    - 将位姿转换为 Plücker 坐标，与原特征图及一个可学习的位姿令牌一起输入自/交叉注意力层（Transformer），预测旋转与平移的偏移量，更新绝对位姿。

4.  **3D 高斯参数预测（Geometry Confidence & Gaussian Parameter Prediction）**
    - 利用精化后的位姿和单目深度构建两个代价体：**多视角代价体** \(C_{\text{multi}}\) 与**引导代价体** \(C_{\text{guide}}\)。
    - 通过交叉注意力融合二者得到聚合代价体 \(C_{\text{agg}}\)，在其上应用 softmax 并取最大值，生成几何置信度图 \(S^{\text{geo}}\)。
    - 置信度图作为额外条件输入，与图像、深度特征等共同预测高斯透明度、协方差（从旋转/尺度派生）和球谐系数颜色。

5.  **损失函数**
    - 图像重建损失：L2 + SSIM + LPIPS。
    - 2D-3D 一致性损失：利用匹配点 \(\mathcal{M}\)，将源点通过深度和位姿投影到目标视图，计算 Huber 损失，促使高斯中心落在物体表面。
    - 3D-3D 一致性损失：直接最小化对应高斯中心之间的欧式距离，增强双向一致性。
    - 总损失：\(\mathcal{L} = \mathcal{L}_{\text{img}} + \mathcal{L}_{\text{2D-3D}} + \lambda_{3D-3D}\mathcal{L}_{\text{3D-3D}}\)，其中 \(\lambda_{3D-3D}=0.05\)。

### 3. 实验设计

**数据集与场景**：
- **RealEstate10K**：包含室内外场景，训练 21,618 个场景，测试 7,200 个场景（由于部分视频不可用，使用子集）。
- **ACID**：户外沿海场景，训练 10,935 个场景，测试 1,893 个场景。
- **DL3DV**：多样化的室内外真实环境，训练 10,510 个场景，测试标准 140 个场景基准。

**对比方法**：
- **新视角合成**：与需要真值位姿的方法（PixelNeRF、Du et al.、PixelSplat、MVSplat）仅作参考对比；主要对比无位姿泛化方法，包括 DBARF、FlowCAM、CoPoNeRF。
- **相机位姿估计**：对比基于对应关系的 SfM 方法（SP+SG、PDC-Net+、DUSt3R、MASt3R）以及直接回归位姿的方法（8ViT、RelPose），重点比较无位姿视图合成方法（DBARF、FlowCAM、CoPoNeRF）内置的位姿估计性能。

**评估协议**：
- 输入为三元组图像 \((I_1, I_2, I_t)\)，按 \(I_1\) 和 \(I_2\) 之间的重叠程度划分小、中、大三个难度等级。
- 新视角合成指标：PSNR、SSIM、LPIPS、MSE。
- 位姿估计指标：旋转和平移误差的平均值与中值。

### 4. 资源与算力

- 训练硬件：**4 块 NVIDIA A100 GPU**。
- 优化器：Adam，学习率 \(8\times10^{-4}\)，每个 GPU 批次大小为 9。
- 训练迭代：**50,000 次**，总训练时间约 **2 天**。
- 推理速度：2 视图输入时渲染单张目标视图约 0.39 秒（包括整个 pipeline 时间）；6 视图约 2.05 秒；12 视图约 5.73 秒。

### 5. 实验数量与充分性

**实验组数概览**：
- 在 **3 个大规模真实世界数据集**（RealEstate10K、ACID、DL3DV）上进行了新视角合成和位姿估计的完整评估。
- 与 **超过 10 种现有方法**进行了定量和定性对比。
- 进行了详细的**组件消融实验**（表 4），包括：
  - 移除精化深度/位姿模块；
  - 移除几何置信度模块；
  - 移除视觉匹配网络或单目深度网络的预训练权重；
  - 对深度网络进行完全微调或仅调整尺度/位移；
  - 移除一致性损失函数（2D-3D 或 3D-3D）。
- 进一步分析了：
  - 与**场景特定优化方法**（InstantSplat、CF-3DGS）的对比及测试时优化（表 5a）；
  - **推理速度**随输入视图数和渲染视图数的变化（表 5b）；
  - 扩展到 **N 视图（6、12）**的场景（表 5c）；
  - **跨数据集泛化**能力（RealEstate10K → DL3DV 及反向，表 5d）；
  - 不同**粗对齐策略**的影响（表 6）。

**评估充分性**：实验设计全面，覆盖了多个真实数据集、多种难度级别、多种任务指标，消融研究细致，额外分析考虑了可扩展性、效率、跨域泛化以及底层模块替换，证据较为充分，对比公平。

### 6. 论文的主要结论与发现

- PF3plat 在三个大规模真实数据集上均取得了**最先进的性能**，与之前的无位姿方法相比，PSNR 提升显著（在 RealEstate10K 上比 CoPoNeRF 高 4 dB）。
- 粗对齐结合可学习的精细对齐模块有效地稳定了像素对齐 3DGS 的训练过程，解决了稀疏/噪声梯度导致的不收敛问题。
- 几何置信度评分能够很好地评估高斯中心的可靠性，并通过反馈机制提升深度和位姿估计的准确性。
- 方法能够自然地扩展到多视图输入，且推理速度显著优于已有的前馈方法，并可与测试时优化结合进一步提性能。
- 跨数据集评估表明方法具有良好的泛化能力。

### 7. 优点

- **实用性强**：彻底摆脱了对真值位姿和深度的依赖，输入仅需无位姿图像和相机内参，贴近真实应用。
- **设计巧妙**：将成熟的单目深度与视觉匹配模型作为“粗对齐”引导，再通过轻量级模块精化，既利用了基础模型的先验，又避免了灾难性遗忘和巨大计算开销。
- **训练稳定**：针对像素对齐 3DGS 的梯度问题，通过几何一致性损失（2D-3D 和 3D-3D）有效约束，显著提升了训练收敛性。
- **性能优异**：在渲染质量、位姿精度和推理速度上全面超越已有无位姿方法，部分指标可比肩甚至超越需要真值位姿的方法。
- **模块化与可扩展**：框架中的粗对齐模块可替换（如更换匹配或深度模型），且自然支持多视图输入，易于扩展。

### 8. 不足与局限

- **动态场景限制**：方法未设计处理动态场景的机制，不能捕捉场景动力学或进行视角外推。
- **依赖预训练模型**：性能受限于底层粗对齐（深度估计、视觉匹配）模型的精度；若这些模型在目标域失效，整体框架可能性能下降。
- **位姿精度相关**：在场景尺度极大或纹理欠缺的场合（如 ACID 数据集上的天空），位姿估计精度仍然与专用 SfM 方法有差距。
- **计算与工程复杂度**：对于超过一定数量的输入视图，两两匹配的鲁棒求解器耗时增加，虽然总体推理仍具竞争力，但仍可进一步优化。
- **依赖相机内参**：与大多数无位姿方法共享此局限，实际中可能无法获取准确内参。

（完）
