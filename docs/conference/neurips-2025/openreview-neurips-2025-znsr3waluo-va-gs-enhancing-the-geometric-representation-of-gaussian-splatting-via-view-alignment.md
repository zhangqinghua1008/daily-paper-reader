---
title: "VA-GS: Enhancing the Geometric Representation of Gaussian Splatting via View Alignment"
title_zh: "VA-GS: 通过视角对齐增强高斯泼溅的几何表示"
authors: "Qing Li, Huifang Feng, Xun Gong, Yu-Shen Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ZnsR3waLUo"
tags: ["query:gs-slam"]
score: 9.0
evidence: 提升3D高斯泼溅新视角合成的几何表示
tldr: VA-GS针对3D高斯泼溅（3DGS）在新视角合成中几何表示不佳的问题，提出基于视角对齐的增强方法。该方法在渲染损失中融入边缘感知的图像线索，以改善表面边界的描绘；同时引入可见性感知的光度对齐损失，强制多视角几何一致性，从而显著提升表面重建精度和渲染质量。实验表明，VA-GS在多视角一致性和几何细节恢复上优于现有方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-znsr3waluo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 873, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-znsr3waluo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1287, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-znsr3waluo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-znsr3waluo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 681, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-znsr3waluo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 607, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-znsr3waluo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 652, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-znsr3waluo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-znsr3waluo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 701, \"height\": 617, \"label\": \"Table\"}]"
motivation: 3DGS的离散非结构化高斯导致仅靠图像渲染损失难以获得精确几何和一致多视角对齐。
method: 提出VA-GS，在渲染损失中加入边缘感知图像提示，并引入可见性感知的光度对齐损失实现视角对齐。
result: 在表面边界描绘和多视角一致性方面取得显著改善，提升了重建的几何精度。
conclusion: VA-GS有效增强了3DGS的几何表示能力，为高质量场景重建提供了新途径。
---

## Abstract
3D Gaussian Splatting has recently emerged as an efficient solution for high-quality and real-time novel view synthesis. However, its capability for accurate surface reconstruction remains underexplored. Due to the discrete and unstructured nature of Gaussians, supervision based solely on image rendering loss often leads to inaccurate geometry and inconsistent multi-view alignment. In this work, we propose a novel method that enhances the geometric representation of 3D Gaussians through view alignment (VA). Specifically, we incorporate edge-aware image cues into the rendering loss to improve surface boundary delineation. To enforce geometric consistency across views, we introduce a visibility-aware photometric alignment loss that models occlusions and encourages accurate spatial relationships among Gaussians. To further mitigate ambiguities caused by lighting variations, we incorporate normal-based constraints to refine the spatial orientation of Gaussians and improve local surface estimation. Additionally, we leverage deep image feature embeddings to enforce cross-view consistency, enhancing the robustness of the learned geometry under varying viewpoints and illumination. Extensive experiments on standard benchmarks demonstrate that our method achieves state-of-the-art performance in both surface reconstruction and novel view synthesis. The source code is available at https://github.com/LeoQLi/VA-GS.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：3D Gaussian Splatting (3DGS) 在新视角合成上效率高、质量好，然而其离散、非结构化的高斯基元导致难以从纯RGB监督中恢复精确、一致的表面几何，尤其在复杂光照、物体边界处易出现几何漂移、孔洞或伪影。
- **研究动机**：现有几何增强方法（如 SuGaR、2DGS、GOF、GS-Pull、PGSR 等）虽然有所改进，但仍难以同时解决“光照引起的伪影”与“表面边界模糊”这两大挑战。因此，需要一种能够通过多视角一致性约束来显著提升三维高斯几何表示能力的方法。
- **整体含义**：VA‑GS 通过视角对齐（View Alignment）增强 3DGS 的几何表示，既保留了实时渲染的优势，又极大改善了表面重建的精度和完整度，旨在实现高质量的同步表面重建与新视角合成。

### 2. 论文提出的方法论
- **总体思想**：在训练过程中逐步引入单视角和多视角的对齐损失，从边缘感知、法线约束、光度一致性和深层特征一致性等多个层面引导高斯基元逼近真实表面。
- **关键技术细节与损失函数**：
  - **单视角对齐**：
    - *边缘感知图像重建损失* \(L_I\)：在 L1 + SSIM 的基础上，加入图像梯度的 L1 损失，强化对物体轮廓和高频细节的保留。
    - *法线一致性损失* \(L_{nc}\)：利用深度图梯度估计表面法线，并约束渲染法线与其一致，同时通过边缘感知权重 \(\delta = (1 - \nabla I)^2\) 降低边界区域的损失贡献。
    - *法线平滑损失* \(L_{ns}\)：惩罚相邻像素法线的剧烈变化（使用 ReLU 和指示函数），增强局部平滑性，保留有意义的结构边缘。
  - **多视角对齐**：
    - *多视角光度对齐损失* \(L_p\)：基于平面片假设，通过单应矩阵 \(H_{rs}\) 将参考片投影到源视图，用归一化互相关（NCC）衡量光度一致性，并引入**可见性项** \(\upsilon_{rs}\) 和**遮挡权重** \(\omega\) 剔除不可见或遮挡点。
    - *多视角特征对齐损失* \(L_f\)：利用预训练网络提取的图像特征，计算参考视图与源视图投影点特征向量的余弦相似度，对光照变化、低纹理区域更加鲁棒。
  - **总损失**：\(L = L_I + \lambda_1 L_{nc} + \lambda_2 L_{ns} + \lambda_3 L_p + \lambda_4 L_f\)。
- **训练流程**：先仅用颜色损失预训练 7000 步；再加入边缘项和法线对齐；然后依次加入多视角光度对齐（8000 步）和特征对齐（5000 步）；新视角合成任务额外训练 10000 步。

### 3. 实验设计
- **数据集与场景**：
  - **表面重建**：DTU 数据集（15 个场景，前景评估）、Tanks and Temples (TNT) 数据集（6 个场景，前景评估）。
  - **新视角合成**：Mip‑NeRF 360 数据集（包含室内外大规模场景，每 8 张取 1 张测试）。
- **评价指标**：
  - DTU：Chamfer Distance。
  - TNT：F1‑score（含 Precision 和 Recall）。
  - Mip‑NeRF 360：PSNR、SSIM、LPIPS。
- **对比方法**：
  - 隐式方法：NeRF、VolSDF、NeuS、NeuralWarp、Neuralangelo、PSDF 等。
  - 显式高斯方法：3DGS、SuGaR、GaussianSurfels、2DGS、GS‑Pull、GOF、RaDe‑GS、PGSR、GausSurf 等。

### 4. 资源与算力
- **硬件**：单张 NVIDIA RTX 4090 GPU。
- **训练时间**：
  - DTU 表面重建：约 15.5 分钟。
  - TNT 表面重建：约 20.6 分钟。
  - Mip‑NeRF 360 新视角合成：未明确给出总时长，但训练步数为 30000 步（含附加的 10000 步），明显慢于原始 3DGS，但仍在可接受范围。
- **其他**：使用 COLMAP 生成稀疏点云初始化高斯；源视图数 \(N=3\)，进一步增加源视图无额外收益且增加计算开销。

### 5. 实验数量与充分性
- **主体实验**：在 3 个标准基准上进行了全面定量对比，涉及 20+ 种已有方法，覆盖隐式与显式重构方案。
- **消融实验**：在 TNT 数据集上设计了多项消融（详见论文 Table 4）：移除全部对齐项、移除边缘项、移除法线项、移除多视角项、改变源视图数量、尝试平面化 3D 高斯等，系统地验证了每一损失项和设计选择的贡献。
- **充分性与客观性**：实验设计遵循领域惯例，指标公开透明，对比方法丰富且含多类代表性工作；消融实验覆盖主要模块，结论能相互印证，实验较为充分且公平。

### 6. 论文的主要结论与发现
- VA‑GS 通过集成边缘感知、可见性感知的多视角对齐、法线约束和深度特征一致性，显著提升了 3D 高斯的几何表示质量。
- 在 DTU 和 TNT 表面重建任务上取得了最优的 Chamfer Distance 和 F1‑score，同时能恢复完整的背景几何。
- 在 Mip‑NeRF 360 新视角合成任务上也达到了最高的 SSIM 和 LPIPS，且 PSNR 名列前茅，证明几何增强并未牺牲视图渲染质量。
- 所提出的多层面对齐策略能有效减轻复杂光照和边界模糊带来的几何误差，生成的网格更加完整、清晰且细节丰富。

### 7. 优点
- **多视角一致性设计**：独创性地将几何对齐、光度对齐和特征对齐统一到高斯优化框架中，克服了单视图和纯颜色损失的局限。
- **鲁棒的边界与光照处理**：边缘感知损失和特征对齐损失分别提升了边界锐度和对光照变化的鲁棒性。
- **状态‑of‑the‑art 性能**：在多个任务和数据集上全面超越同期高斯重建方法，甚至优于部分神经网络隐式表示。
- **模块化与可复现**：损失项设计清晰，权重等超参明确给出，代码开源，便于复现和进一步改进。
- **无损新视角合成**：几何增强的同时并未降低渲染性能，某些指标反而更优，实现了几何与渲染质量的共赢。

### 8. 不足与局限
- **训练速度**：相较原始 3DGS 等快速方法仍显缓慢（如 DTU 上用 15.5 分钟，而 3DGS 仅需 3.4 分钟），受多视角对齐计算所累。
- **动态场景与大规模扩展**：当前方法针对静态场景设计，如何高效泛化到动态或超大规模场景有待探索。
- **对源视图数的依赖**：\(N\) 的选择影响精度与开销，尽管 \(N=3\) 是权衡之选，但某些场景可能需要更多视图才能发挥最佳效果。
- **平面假设局限性**：多视角对齐中的局部平面假设在严重非平面或细薄结构处可能引入误差，文中虽然尝试缓解，但仍可能成为潜在的几何偏差来源。
- **未提供统计误差分析**：实验未报告多次运行的方差或置信区间，不同随机种子下的稳定性未完全验证。

（完）
