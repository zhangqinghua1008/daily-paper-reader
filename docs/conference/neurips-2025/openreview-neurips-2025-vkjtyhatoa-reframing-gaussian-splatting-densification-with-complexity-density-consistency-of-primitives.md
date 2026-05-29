---
title: Reframing Gaussian Splatting Densification with Complexity-Density Consistency of Primitives
title_zh: 基于基元复杂度-密度一致性的高斯泼溅稠密化重塑
authors: "Zhemeng Dong, Junjun Jiang, Youyu Chen, Jiaxin Zhang, Kui Jiang, Xianming Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=VKJTyhAtoA"
tags: ["query:gs-slam"]
score: 7.0
evidence: 改进3DGS稠密化策略以提升新视角合成质量
tldr: 针对现有3D高斯泼溅（3DGS）中基于渲染损失的稠密化策略偏向低频区域、忽视高频细节的问题，提出基于复杂度-密度一致性的稠密化方法。该方法利用训练视图中的视觉先验识别复杂区域，无需依赖损失信号，更有效地分配高斯基元，从而提升纹理丰富区域的建模精度和新视角合成质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vkjtyhatoa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vkjtyhatoa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vkjtyhatoa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 1350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vkjtyhatoa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vkjtyhatoa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vkjtyhatoa/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1420, \"height\": 796, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1377, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 699, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 937, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1136, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 622, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1272, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 661, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 650, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1451, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vkjtyhatoa/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1459, \"height\": 359, \"label\": \"Table\"}]"
motivation: 3DGS基于损失的稠密化常受低频主导，导致高频细节建模不足。
method: 提出复杂度-密度一致的高斯泼溅（CD-GS），利用视觉先验识别复杂区域进行稠密化。
result: 在纹理丰富区域实现了更精细的细节恢复，整体渲染质量优于现有3DGS方法。
conclusion: CD-GS通过挖掘视觉先验优化了高斯分配，为3DGS的稠密化提供了新视角。
---

## Abstract
The essence of 3D Gaussian Splatting (3DGS) training is to smartly allocate Gaussian primitives, expressing complex regions with more primitives and vice versa. 
Prior researches typically mark out under-reconstructed regions in a rendering-loss-driven manner. 
However, such a loss-driven strategy is often dominated by low-frequency regions, which leads to insufficient modeling of high-frequency details in texture-rich regions. As a result, it yields a suboptimal spatial allocation of Gaussian primitives.
This inspires us to excavate the loss-agnostic visual prior in training views to identify complex regions that need more primitives to model. 
Based on this insight, we propose Complexity-Density Consistent Gaussian Splatting (CDC-GS), which allocates primitives based on the consistency between visual complexity of training views and the density of primitives. 
Specifically, primitives involved in rendering high visual complexity areas are categorized as modeling high complexity regions, where we leverage the high frequency wavelet components of training views to measure the visual complexity. 
And the density of a primitive is computed with the inverse of geometric mean of its distance to the neighboring primitives. 
Guided by the positive correlation between primitive complexity and density, we determine primitives to be densified as well as pruned. 
Extensive experiments demonstrate that our CDC-GS surpasses the baseline methods in rendering quality by a large margin using the same amount of Gaussians. 
And we provide insightful analysis to reveal that our method serves perpendicularly to rendering loss in guiding Gaussian primitive allocation.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：3D高斯泼溅在训练过程中，对于高斯球（Gaussian primitives）的空间分配策略（即何处增加、何处减少）是决定渲染质量的关键。现有方法普遍采用**渲染损失驱动**策略，但该策略存在严重缺陷。
*   **损失驱动策略的缺陷**：在高频细节丰富、纹理复杂的区域（例如草坪、栅栏），由于渲染损失容易被平滑，导致梯度信号微弱，无法有效指示这些区域需要更多高斯球来精细建模（即“欠重建”）。反之，在低频平坦区域，损失信号可能导致高斯球冗余（即“过重建”）。
*   **核心含义与研究动机**：作者提出，应利用与渲染损失无关的**视觉先验**来识别场景的复杂区域，并以此指导高斯球的分配。这样可以为损失驱动策略提供一个垂直互补的维度，更智能地向复杂区域分配更多高斯球，从平坦区域移除冗余高斯球，从而在相同或更少的图元数量下，显著提升渲染质量。

### 2. 论文提出的方法论

*   **核心思想：复杂度-密度一致性**
    论文提出了一种名为“复杂度-密度一致的高斯泼溅”方法。其核心假设是：在良好重建的区域，高斯球的“视觉复杂度”与其局部的“空间密度”应呈现正相关性。通过检测并纠正这种一致性的破坏，即可定位欠重建和过重建区域。

*   **关键技术细节**
    *   **复杂度度量**：利用2D离散小波变换提取训练视图的高频分量（水平、垂直、对角细节），组合成“复杂度图”。然后将每个高斯球在渲染过程中对该图的加权贡献进行最大值聚合，定义为该高斯球的视觉复杂度参数 \(\Gamma(G_i)\)。
    *   **密度度量**：计算每个高斯球与其空间最近邻高斯球中心距离的几何平均值的倒数，作为其密度参数 \(\Psi(G_i)\)。
    *   **一致性分数与分配策略**：
        1.  标准化复杂度和密度后，计算两者乘积作为“一致性分数” \(s_i\)。\(s_i\) 为负值时表示不一致。
        2.  **欠重建识别**：当高斯球呈现高复杂度但低密度时，视为欠重建。该方法会增选这些高斯球进行克隆/分裂，以增加该区域图元。
        3.  **过重建识别**：当高斯球呈现低复杂度但高密度时，视为过重建。该方法会以较高概率剪枝这些高斯球。
        4.  **互补策略**：此基于先验的选择策略与传统基于梯度（损失驱动）的选择策略共同作用，形成互补。
    *   **复杂度感知自适应阈值**：为了使损失驱动的稠密化对复杂区域更敏感，论文为每个高斯球设定了个性化的稠密化阈值。复杂度越高的高斯球，其阈值越低，更易被梯度方法选中进行稠密化。公式为 \( \tau(\Gamma) = \tau_{low} + (\tau_{upp} - \tau_{low}) \cdot [1 - \sigma(\lambda \cdot \Gamma)] \)。

### 3. 实验设计

*   **数据集与场景**：遵循3DGS标准评估协议，在三个真实世界数据集上评估。
    *   Mip-NeRF 360: 9个场景。
    *   Tanks & Temples: 2个场景。
    *   Deep Blending: 2个场景。
*   **评估基准（Metrics）**: PSNR, SSIM, LPIPS。每个实验用不同种子重复三次，报告平均值。
*   **对比方法**: 对比了一系列代表性高斯图元分配方法，包括：Vanilla 3DGS, Taming-3DGS, AbsGS, Mini-Splatting-D, Pixel-GS。

### 4. 资源与算力

*   **硬件配置**: 论文明确指出所有实验均在**单个NVIDIA RTX 3090 GPU**上完成。
*   **训练时长**: 论文在附录的消融实验中报告了训练时间。在Mip-NeRF 360数据集上，完整的CDC-GS模型训练时长为**35分36秒**，相较于基线3DGS的29分06秒，增加了约**6分30秒**的开销。这些额外开销主要来自小波变换计算复杂度和K近邻密度计算。

### 5. 实验数量与充分性

*   **实验组数**：论文进行了多组、多维度的实验，覆盖三个标准数据集，整体实验设计较为充分和客观。
*   **实验充分性分析**：
    *   **主实验（定量与定性）**：在两组不同高斯球数量级别下，与五种主流方法进行了全面对比，包含渲染质量和图元数量的权衡。
    *   **机制验证实验**：通过可视化高斯球的复杂度-密度散点图及一致性得分变化曲线，有力论证了所提策略是独立于损失梯度的垂直互补方法。
    *   **消融实验**：验证了“复杂度感知自适应阈值”和“复杂度-密度一致性剪枝/稠密化”两个核心模块的效果增益。
    *   **对比与敏感性实验**：在附录中，将小波变换与Sobel、Scharr等传统高频滤波器对比，将几何均值与算术均值对比，并设计了逆向分配策略的消融实验。这些实验充分证明了所提模块设计的鲁棒性和正确性。

### 6. 论文的主要结论与发现

*   通过引入视觉先验，论文提出的CDC-GS方法能在相同或更少的图元数量下，显著超越现有基于损失驱动的稠密化方法，在**渲染质量（PSNR, SSIM, LPIPS）上取得了一致的、大幅度的提升**。
*   分析表明，基于图像频率的“复杂度-密度一致性”指标与渲染损失梯度在对图元分配区域的识别上是**垂直正交**的，能有效发现被损失驱动策略忽略的欠重建区域。
*   该方法能更加智能地分配高斯图元，使得复杂纹理区域获得更多图元，而平坦区域图元更少，提升了图元分配的**整体效率**。

### 7. 优点

*   **方法论创新**：跳出对渲染损失的单一依赖，首次提出利用视觉复杂度先验来指导3DGS的稠密化与剪枝，开辟了新的思路。
*   **见解深刻与论证完备**：不仅提出方法，还通过定量的相关性分析和直观的可视化，深入论证了其与损失驱动策略的“垂直互补”特性，说服力强。
*   **技术实现简洁有效**：利用成熟的离散小波变换和简单的空间距离统计，核心机制清晰，易于理解和复现。
*   **性能与效率双赢**：在提升高质量细节的同时，能有效控制甚至减少图元总数，没有像部分基线方法那样产生过量的冗余图元。

### 8. 不足与局限

*   **依赖损失驱动的局限**：方法本身是基于视觉先验的补充策略，无法完全独立于损失驱动信号。论文也明确指出，视觉先验本身对重建质量缺乏直接感知，因此仍需依赖现有基于损失的稠密化信号。
*   **训练开销增加**：相较于基线3DGS，该方法带来了约22%的额外训练时间。
*   **应用范围限制**：实验主要集中于静态场景的新视角合成标准基准测试，对于其在动态场景、大规模场景等其他下游任务上的泛化能力，文中并未探讨。
*   **实验偏差风险**：虽然对比了多种方法，但所有基线结果均由作者复现，且实验均在公认难度适中的基准上进行。未来若能在更广阔或更具挑战性的数据集（如更大规模城市场景）上测试，会使其结论更有说服力。

（完）
