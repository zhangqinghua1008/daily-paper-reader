---
title: Quantifying and Alleviating Co-Adaptation in Sparse-View 3D Gaussian Splatting
title_zh: 量化并缓解稀疏视角下3D高斯泼溅的共适应问题
authors: "Kangjie Chen, Yingji Zhong, Zhihao Li, Jiaqi Lin, Youyu Chen, Minghan Qin, Haoqian Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=GrPo8NTtzK"
tags: ["query:gs-slam"]
score: 7.0
evidence: 解决稀疏视角下3D高斯泼溅新视角合成的伪影问题
tldr: 该工作研究了稀疏视角下3D高斯泼溅（3DGS）的新视角合成伪影问题，发现高斯间的过度纠缠导致训练视图过拟合而非学习真实场景分布，提出共适应评分（CA）进行量化，并设计方法减少高斯纠缠，从而提升稀疏视角设置下的渲染质量和泛化性。实验表明，该方法有效缓解了共适应现象，提升了新视角的视觉保真度。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1135, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1416, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 719, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1452, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1448, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1437, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 590, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-grpo8nttzk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1097, \"height\": 363, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1168, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 944, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 946, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 943, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1016, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1012, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1020, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1159, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1017, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 867, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1439, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1152, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-grpo8nttzk/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 738, \"height\": 139, \"label\": \"Table\"}]"
motivation: 稀疏视角下3DGS产生伪影，原因在于高斯过度纠缠以适应训练视图，忽视真实场景分布。
method: 提出共适应评分量化高斯纠缠，并设计抑制纠缠的方法以缓解稀疏视角合成伪影。
result: 在稀疏视角条件下，新视角合成质量得到提升，伪影明显减少。
conclusion: 揭示了3DGS中的共适应问题，提供了分析工具和缓解策略，对稀疏视角重建有指导意义。
---

## Abstract
3D Gaussian Splatting (3DGS) has demonstrated impressive performance in novel view synthesis under dense-view settings. However, in sparse-view scenarios, despite the realistic renderings in training views, 3DGS occasionally manifests appearance artifacts in novel views. This paper investigates the appearance artifacts in sparse-view 3DGS and uncovers a core limitation of current approaches: the optimized Gaussians are overly-entangled with one another to aggressively fit the training views, which leads to a neglect of the real appearance distribution of the underlying scene and results in appearance artifacts in novel views. The analysis is based on a proposed metric, termed Co-Adaptation Score (CA), which quantifies the entanglement among Gaussians, i.e., co-adaptation, by computing the pixel-wise variance across multiple renderings of the same viewpoint, with different random subsets of Gaussians. The analysis reveals that the degree of co-adaptation is naturally alleviated as the number of training views increases. Based on the analysis, we propose two lightweight strategies to explicitly mitigate the co-adaptation in sparse-view 3DGS: (1) random gaussian dropout; (2) multiplicative noise injection to the opacity. Both strategies are designed to be plug-and-play, and their effectiveness is validated across various methods and benchmarks. We hope that our insights into the co-adaptation effect will inspire the community to achieve a more comprehensive understanding of sparse-view 3DGS.

---

## 论文详细总结（自动生成）

# 论文总结：《稀疏视角3D高斯泼溅中共适应的量化与缓解》

## 1. 研究动机与核心问题
- **背景**：3D高斯泼溅（3DGS）在密集视角的新视图合成中表现优异，但在稀疏视角（如3–8个训练视图）下，训练视图渲染逼真，但新视图常出现外观伪影（例如颜色噪点或不属于场景的颜色）。
- **核心问题**：论文指出，稀疏视角下的伪影源于**高斯之间的过度共适应**——多个高斯在训练视图上联合过拟合有限的像素，形成相互依赖的组合，忽略场景的真实外观分布，导致新视图渲染不稳定。
- **研究意义**：现有工作多从几何正则化入手提升稀疏视角重建，极少关注外观伪影的成因。本文首次定量分析并直接缓解这种共适应现象。

## 2. 方法论

### 2.1 共适应评分（Co-Adaptation Score, CA）
- **核心思想**：若多个高斯过度依赖彼此，随机丢弃一部分高斯会导致渲染结果剧烈变化。通过多次随机丢弃50%高斯、渲染同一视角，计算**像素级颜色方差**的平均值，即得到CA评分。
- **公式**：  
  \[
  CA(v) = \frac{1}{|\Omega_v|} \sum_{u\in\Omega_v} \text{Var}\left(I_u^{(1)},\dots,I_u^{(K)}\right)
  \]  
  其中 \(\Omega_v\) 是多次渲染中累积alpha值均大于0.8的稳定可见像素区域。
- **理论基础**：推导表明CA正比于各高斯颜色与不透明度乘积的平方和 \(\sum_i (c_i\alpha_i)^2\)，因此CA直接反映高斯颜色‑不透明度之间的耦合强度。

### 2.2 缓解策略（plug‑and‑play）
1. **随机高斯Dropout**  
   - 训练时以概率 \(p\) 随机丢弃高斯，使用保留的子集渲染并监督。  
   - 测试时使用所有高斯，但将不透明度缩放为 \((1-p)\,\alpha_{\text{train}}\)。  
   - 作用：强迫每条射线在部分高斯缺失时仍能正确着色，从而消除固定高斯组合的依赖。

2. **不透明度乘性噪声注入**  
   - 训练时对不透明度施加乘性高斯噪声：\(\alpha \leftarrow \alpha \cdot (1+\epsilon),\; \epsilon \sim \mathcal{N}(0,\sigma^2)\)。  
   - 作用：轻微扰动高斯的贡献权重，破坏共适应依赖，鼓励相邻高斯在颜色和透明度上可相互替代。

## 3. 实验设计

### 3.1 数据集与基准
- **LLFF**（3个训练视图，图像下采样8倍）
- **DTU**（3个训练视图，下采样4倍）
- **Blender合成数据集**（8个训练视图，下采样2倍）
- 评价指标：PSNR、SSIM、LPIPS，以及本文提出的CA评分。

### 3.2 对比方法
baseline均为稀疏视角3DGS方法（部分结合了深度先验或关键点初始化）：
- 3DGS（原始方法）
- DNGaussian、FSGS、CoR‑GS、Binocular3DGS
- 在每种baseline上分别施加dropout和opacity noise进行对比。

## 4. 资源与算力
- 文中明确说明使用 **8块NVIDIA RTX 3090 GPU** 完成所有实验。
- 未提供单次训练时长或总计算时数的详细统计。

## 5. 实验数量与充分性
- **实验维度丰富**：涵盖3个数据集（LLFF、DTU、Blender），5种基线方法，2种策略及其组合。
- **消融实验细致**：
  - Dropout概率 \(p\)（0.0~0.6）；
  - Opacity噪声标准差 \(\sigma\)（0.0~1.0）；
  - 不同参数注入噪声（位置、SH、缩放），证明opacity噪声最优；
  - 不同SH阶数的影响；
  - 推断时渲染策略（单次dropout、多次平均、不透明度缩放）；
  - 多视图训练、Concrete Dropout、密度感知dropout等探索；
  - 深度图质量的评估。
- **公平性**：所有baseline使用官方实现，统一训练设置（如Binocular3DGS改为白背景以对齐其他方法），CA计算统一采用50%丢弃比例，且训练时若使用dropout则在计算CA时调整丢弃比例以保持可比性。
- 实验整体设计充分，对比公平，结论可靠。

## 6. 主要结论与发现
- **共适应是稀疏视角3DGS外观伪影的重要来源**，训练视图越多，共适应程度自然越低（CA降低）。
- 所提出的CA评分能有效量化高斯间的纠缠强度，并与渲染质量存在关联（但并非单调下降总是有益）。
- **随机高斯dropout**和**不透明度噪声注入**两种策略均能显著降低CA值，并提升PSNR、SSIM、LPIPS等指标，减少新视图的彩色斑点等伪影。
- 两种策略结合未能进一步带来额外收益，说明它们作用于同一问题机制。
- 过弱的共适应（过于强烈的抑制）反而可能导致表达能力的损失，因此适度缓解是关键。

## 7. 优点
- **问题新颖**：首次形式化定义3DGS中的共适应现象，并提供定量度量，视角独特。
- **机制可解释**：既有直观可视化解释，也有理论推导将CA与颜色‑不透明度耦合直接关联。
- **方法简洁即插即用**：dropout与不透明度噪声无需修改模型结构，易于集成到现有方法中，计算开销小。
- **实验全面**：多数据集、多基线、多消融实验，验证了策略的普适性和鲁棒性。
- **分析深入**：探讨了不同参数扰动的影响，以及共适应与训练动态、view数量、SH阶次等的关系。

## 8. 不足与局限
- **过度缓解的副作用**：论文明确指出CA降到过低值后重建质量不再提升甚至退化，说明共适应并非全无益处；目前缺乏自适应的抑制强度调控机制。
- **策略局限**：仅作用于外观层面的协同依赖，未结合几何结构进行更精细的分离。
- **实验覆盖**：所有实验基于静态物体数据集，未涉及大规模场景或动态场景；未在更具挑战的无序照片集或野外稀疏数据上验证。
- **算力与效率细节缺失**：虽说明使用8块3090，但未报告训练时间延长比例（dropout需额外前向开销），也未讨论对训练速度的影响。
- **评估指标**：CA评分设定阈值0.8，丢弃比例固定为0.5，这些超参可能影响对不同场景的敏感度，文中未详细讨论其鲁棒性。
- **理论分析简化**：CA推导使用了线性展开近似，忽略了高阶项，可能影响在复杂场景下的精确性。

（完）
