---
title: "SurfelSplat: Learning Efficient and Generalizable Gaussian Surfel Representations for Sparse-View Surface Reconstruction"
title_zh: "SurfelSplat: 学习高效通用高斯面元表示用于稀疏视角表面重建"
authors: "Chensheng Dai, Shengjun Zhang, Min Chen, Yueqi Duan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0sUihPtncP"
tags: ["query:gs-slam"]
score: 7.0
evidence: 利用高斯面元表示实现高效稀疏视角场景重建
tldr: 针对传统3DGS优化方法需密集视图且耗时长的局限，提出SurfelSplat，一种前馈框架，从稀疏视角图像直接生成像素对齐的高斯面元表示，实现高效且可泛化的表面重建，无需逐场景优化，能快速推理生成精确几何，适用于稀疏视角输入。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1419, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1416, \"height\": 944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 1050, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0suihptncp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 1064, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0suihptncp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 481, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0suihptncp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1515, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0suihptncp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 722, \"height\": 222, \"label\": \"Table\"}]"
motivation: 现有3DGS表面重建依赖密集视图和逐场景优化，耗时且无法泛化。
method: 设计前馈网络SurfelSplat，从稀疏视图生成像素对齐的高斯面元表示，实现快速表面重建。
result: 在稀疏视图输入下，高效重建出精确完整的表面，推理速度快。
conclusion: SurfelSplat为3DGS在表面重建任务中提供了高效且可推广的解决方案。
---

## Abstract
3D Gaussian Splatting (3DGS) has demonstrated impressive performance in 3D scene reconstruction. Beyond novel view synthesis, it shows great potential for multi-view surface reconstruction. Existing methods employ optimization-based reconstruction pipelines that achieve precise and complete surface extractions. However, these approaches typically require dense input views and high time consumption for per-scene optimization. To address these limitations, we propose SurfaceSplat, a feed-forward framework that generates efficient and generalizable pixel-aligned Gaussian surfel representations from sparse-view images. We observe that conventional feed-forward structures struggle to recover accurate geometric attributes of Gaussian surfels because the spatial frequency of pixel-aligned primitives exceeds Nyquist sampling rates. Therefore, we propose a cross-view feature aggregation module based on the Nyquist sampling theorem. Specifically, we first adapt the geometric forms of Gaussian surfels with spatial sampling rate-guided low-pass filters. We then project the filtered surfels across all input views to obtain cross-view feature correlations. By processing these correlations through a specially designed feature fusion network, we can finally regress Gaussian surfels with precise geometry. Extensive experiments on DTU reconstruction benchmarks demonstrate that our model achieves comparable results with state-of-the-art methods, and predict Gaussian surfels within 1 second, offering a 100× speedup without costly per-scene training.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：在稀疏视角（如仅 2 张图）下进行高精度的表面重建，传统方法（无论是神经隐式还是显式 3DGS 变体）要么需要密集视图，要么必须逐场景地进行长时间优化（数分钟至数小时），无法实现快速、可泛化的推理。
- **整体含义**：本文提出一种**前馈式**框架 SurfelSplat，可以直接从稀疏图像中一次性推理出几何准确的高斯面元（2D Gaussian Surfels）表示，无需任何逐场景训练，在保证重建质量的同时将推理速度提升至秒级（约 1 秒），是效率和几何精度的统一。

### 2. 论文提出的方法论
- **核心思想**：现有前馈网络（如 pixelSplat、MVSplat）预测的像素对齐高斯面元往往平行于图像平面，无法恢复真实表面朝向。作者从**奈奎斯特采样定理**出发，指出这是由于像素对齐基元的空间频率超出了多相机系统的空间采样率，导致网络无法学到准确的协方差（几何）信息。
- **关键技术细节**：
  - **奈奎斯特引导的面元适应模块**：计算每幅视图对应该面元的空间采样率（\( \hat{\nu}_k = f_x f_y / d^2 \)），并取所有可见视图的最大值。然后对每个高斯面元施加自适应低通滤波 \( \mathcal{G}^{\text{low}}_k \)（高斯核），将面元的空间频率限制在奈奎斯特阈值以下。
  - **交叉视图特征聚合模块**：将经过滤波的面元投影回各输入视图，找到对应的像素区域 \( \mathcal{R}_{ik} \)，提取这些区域的特征构成几何相关特征集合。利用交叉注意力（Q 来自原始特征，K、V 来自聚合特征）来增强每个面元的特征，最后再次回归得到几何精确的高斯面元参数（位置、缩放、旋转、颜色、不透明度）。
- **流程概览**（文字版）：
  1. 用 U-Net/Transformer 提取多视图图像特征 \( \mathbf{F} \)。
  2. 预测逐像素深度 \( d_i \) 和高斯初始属性 \( f_i \)。
  3. 计算每个面元的空间采样率，用低通滤波调整面元形状，使其满足奈奎斯特条件。
  4. 将调整后的面元投影到各视图，融合对应区域的图像特征，送入交叉注意力网络。
  5. 细化后的特征再次通过属性头，输出最终的几何准确的面元。
- **损失函数**：渲染损失（L1 + LPIPS）+ 几何损失（深度/法向一致性对齐损失及 MSE）。

### 3. 实验设计
- **数据集**：
  - **表面重建基准**：DTU 数据集（128 个场景，官方 15 个测试场景），输入为 2 张稀疏视角图，评估尺度为 256×320。
  - **额外验证**：BlendedMVS 数据集（定性比较）。
  - **新视角合成对比**：同样在 DTU 上与 pixelSplat、MVSplat 比较渲染质量。
- **评估指标**：Chamfer Distance（CD，从重建到真值的双向距离）；表 3 中还用到了法向 MSE。
- **对比方法**：
  - 神经隐式：NeuS、NeuSurf、VolRecon、UFORecon。
  - 神经显式/3DGS：2DGS、Gaussian Surfels (GauSurf)、FatesGS。
  - 前馈式：间接通过与 pixelSplat、MVSplat 在新视角合成上的比较体现。

### 4. 资源与算力
- **硬件**：所有实验在**单块 NVIDIA RTX A6000 GPU** 上完成。
- **训练方案**：先在 RealEstate10K 数据集上预训练 **30 万次迭代**，再在 DTU 上**微调 2000 次迭代**。
- **推理速度**：每场景约 **1±0.05 秒**（不含后续网格提取的约 30 秒），比现有方法快 10 倍到 3600 倍不等。

### 5. 实验数量与充分性
- **主体实验**：在 DTU 15 个测试场景上逐场景报告 CD 值，并计算均值，对比 7 种 SOTA 方法，定量充分。
- **效率实验**：表 2 对比了每种方法的推理/训练时间，清晰展示速度优势。
- **奈奎斯特验证**：图 5 显示适应前后法向图的可视化差异，图 6 通过统计频率分布证明模块能将面元频率全部压入阈值内——直观验证理论。
- **消融研究**：表 3 分别移除面元适应模块、特征聚合模块，报告 CD 与法向 MSE 的退化，证明各模块有效。
- **额外定性实验**：图 4 提供多方法深度法向对比，图 7 在 BlendedMVS 上展示，图 8 在新视角合成上对比。
- 总体实验种类较为全面（定量 + 定性 + 验证 + 消融 + 泛化），对比方法涵盖主流路线，比较**客观且公平**。

### 6. 论文的主要结论与发现
- 前馈网络无法直接学习准确的高斯面元几何，根源在于**像素对齐基元的空间频率过高，违背了奈奎斯特采样定理**。
- 通过**采样率引导的低通滤波**适应面元形状，并**聚合交叉视图对应区域的特征**，可以成功回归出表面贴合的高斯面元。
- SurfelSplat 在稀疏视图表面重建上达到与 SOTA 优化方法相当甚至更优的精度，同时**推理速度提升约 100 倍**（约 1 秒），且无需任何逐场景优化。

### 7. 优点
- **学术创新**：首次将奈奎斯特采样定理引入前馈高斯面元推理，从信号处理角度解释并解决了几何不准问题。
- **效率与精度的平衡**：在保持高重建精度的同时，实现超快的推理速度（前馈式，~1 s /scene）。
- **可泛化性**：通过在大数据上预训练，模型具备跨场景泛化能力，不像优化方法需要每场景重训。
- **理论分析完整**：提供了详细的采样率、空间频率推导及奈奎斯特条件满足的严格证明（附录）。
- **实验充分**：覆盖定量/定性、消融、理论验证、效率对比，多种数据集和方法对比，说服力较强。

### 8. 不足与局限
- **高分辨率扩展性**：像素对齐的方式导致在输入分辨率较高（如 1024×1024）时会产生超百万个高斯面元，大幅增加推理和渲染开销。
- **未观测区域**：对视角覆盖不足的部分，重建性能受限；作者设想可结合扩散模型等生成式方法补全。
- **相机位姿配置敏感**：当输入视图重叠区域过小时，深度预测困难；训练数据量和位姿分布多样性不足，泛化能力有边界。
- **资源消耗**：虽然推理快，但预训练仍需要较大规模数据（RealEstate10K）和数十万次迭代。
- **冗余表示**：直接合并各视图预测的高斯面元，在重叠区域会产生大量冗余基元，未做进一步合并或压缩。

（完）
