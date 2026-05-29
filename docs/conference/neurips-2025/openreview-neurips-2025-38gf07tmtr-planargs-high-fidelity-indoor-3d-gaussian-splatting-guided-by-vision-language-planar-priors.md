---
title: "PlanarGS: High-Fidelity Indoor 3D Gaussian Splatting Guided by Vision-Language Planar Priors"
title_zh: "PlanarGS: 基于视觉语言平面先验的高保真室内三维高斯泼溅"
authors: "Xirui Jin, Renbiao Jin, Boying Li, Danping Zou, Wenxian Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=38GF07Tmtr"
tags: ["query:gs-slam"]
score: 9.0
evidence: 使用3D高斯泼溅进行室内新视角合成与场景重建
tldr: 针对3DGS在室内低纹理区域导致几何模糊的问题，PlanarGS提出利用视觉语言模型提取平面先验，通过跨视图融合和几何验证优化三维高斯表示，在室内场景中实现高保真的表面重建和新视角合成。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1155, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 875, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1162, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1309, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1306, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1305, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1443, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1443, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1439, \"height\": 1036, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1450, \"height\": 2081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1447, \"height\": 2096, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1442, \"height\": 2098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 1126, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1439, \"height\": 1002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38gf07tmtr/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1420, \"height\": 2071, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-38gf07tmtr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1315, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38gf07tmtr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1418, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38gf07tmtr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38gf07tmtr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 247, \"label\": \"Table\"}]"
motivation: 3DGS在室内低纹理大区域中优化时几何模糊，无法恢复高保真表面。
method: 设计语言提示平面先验(LP3)管道，利用预训练分割模型和跨视图融合精细化平面区域。
result: 在室内数据集上实现了高保真表面重建。
conclusion: 结合视觉语言先验显著提升了3DGS在室内低纹理场景的重建质量。
---

## Abstract
Three-dimensional Gaussian Splatting (3DGS) has recently emerged as an efficient representation for novel-view synthesis, achieving impressive visual quality. However, in scenes dominated by large and low-texture regions, common in indoor environments, the photometric loss used to optimize 3DGS yields ambiguous geometry and fails to recover high-fidelity 3D surfaces. To overcome this limitation, we introduce PlanarGS, a 3DGS-based framework tailored for indoor scene reconstruction. Specifically, we design a pipeline for Language-Prompted Planar Priors (LP3) that employs a pretrained vision-language segmentation model and refines its region proposals via cross-view fusion and inspection with geometric priors. 3D Gaussians in our framework are optimized with two additional terms: a planar prior supervision term that enforces planar consistency, and a geometric prior supervision term that steers the Gaussians toward the depth and normal cues. We have conducted extensive experiments on standard indoor benchmarks. The results show that PlanarGS reconstructs accurate and detailed 3D surfaces, consistently outperforming state-of-the-art methods by a large margin. Project page: https://planargs.github.io

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义
- **核心问题**：三维高斯泼溅（3DGS）在室内场景中，因存在大量低纹理的平面区域（如墙壁、地板），仅依靠光度损失优化会导致几何模糊，无法恢复高保真的3D表面。
- **整体含义**：旨在通过引入视觉-语言模型提取的平面先验，强化3DGS在室内环境下的几何重建能力，实现高精度的表面重建与高质量的新视角合成。

## 2. 论文提出的方法论
- **整体思路**：PlanarGS 框架在3DGS优化过程中额外加入平面先验监督和几何先验监督，其中平面先验由语言提示的管道（LP3）生成。
- **LP3 平面先验生成管道**：
  - 使用预训练视觉语言分割模型 **GroundedSAM**，通过文本提示（如“wall”“floor”）获取初始平面检测框。
  - **跨视角融合**：利用邻帧深度先验将检测框反投影到3D并重投影回当前视图，补充单帧漏检的平面区域。
  - **几何检验**：基于多视图深度先验计算法向图和平面距离图，通过聚类和离群点分析分离非平行平面和去除非平面碎片，得到可靠平面掩码。
- **平面先验监督**：
  - **平面引导初始化**：将平面区域像素反投影为稠密3D点补充稀疏SfM点云。
  - **高斯扁平化**：最小化高斯的最小尺度因子，使其退化成平面盘，以便渲染光滑深度和法向。
  - **共面约束**：将渲染深度图在平面区域内拟合出全局平面，计算拟合平面深度与渲染深度的L1损失，强制高斯共面。
- **几何先验监督**：
  - 使用预训练多视图基础模型 **DUSt3R** 获取视图一致的深度和法向先验。
  - **深度先验约束**：在低纹理区域，约束对齐后的深度先验与渲染深度的L2损失。
  - **法向先验约束**：在平面区域内，约束渲染表面法向与先验法向一致。
  - **深度法向一致性**：在低纹理区域约束渲染的高斯法向与渲染表面法向一致，优化高斯旋转。
- **总损失**：`L_total = L_RGB + L_s + λ1·L_dn + λ2·L_p + λ3·L_rd + λ4·L_rn`。

## 3. 实验设计
- **数据集与场景**：
  - **Replica**（合成）：8个场景（office0-4, room0-2），100视图。
  - **ScanNet++**（真实）：4个场景。
  - **MuSHRoom**（真实，复杂室内）：5个场景（coffee_room, classroom等）。
- **对比方法**：3DGS、2DGS、GOF、PGSR、QGS、DN-Splatter 等前沿方法。
- **评估指标**：
  - 表面重建：Accuracy, Completion, Chamfer Distance, F-score (5cm), Normal Consistency。
  - 新视角合成：PSNR, SSIM, LPIPS。

## 4. 资源与算力
- 使用 **Nvidia RTX 3090 GPU** 进行3DGS训练，所有场景训练 **30,000 次迭代**。
- DUSt3R 深度先验生成在 **NVIDIA A6000 (48GB)** 上运行，每组输入40张图像。
- 文中提到 PlanarGS 训练时间**在一小时以内**，与其他3DGS方法相当。

## 5. 实验数量与充分性
- **主要对比实验**：在三个数据集上与6种方法进行了表面重建和NVS的定量定性对比。
- **消融实验**：
  - 平面先验来源对比（ZeroPlane、GroundedSAM w/o LP3、完整LP3）。
  - 逐个移除共面约束、几何先验约束、深度法向一致性约束，分析各模块贡献。
  - 鲁棒性分析：更换多视图模型（VGGT）、分割模型（YoloWorld+SAM）、增加提示词，验证方法稳定性。
- **充分性与公平性**：实验覆盖合成与真实数据，包含主流基线，消融分析全面，结果具有统计说服力，对比公平。

## 6. 论文的主要结论与发现
- 引入语言提示的平面先验与多视图几何先验，能够有效解决3DGS在室内大平面低纹理区域的几何模糊问题。
- PlanarGS 在多个室内基准上大幅领先现有方法，重建出的表面既全局平坦又局部光滑，同时保持了高渲染质量。
- 利用基础模型 + 跨视角融合 + 几何检验的 LP3 管道比专用平面检测器更准确、更灵活。

## 7. 优点
- **方法创新**：将大规模预训练视觉语言模型引入3DGS优化，实现语义级平面约束。
- **管道鲁棒**：跨视角融合和几何检验解决了单视图分割的漏检和错合并问题。
- **多约束协同**：共面约束保证全局平面性，深度/法向先验提供尺度与方向指导，深度法向一致性对齐高斯方向。
- **灵活可扩展**：通过简单修改文本提示即可适应不同室内场景。

## 8. 不足与局限
- **场景限制**：平面先验仅对检测到的平面有效，无法改善曲面墙壁或无平面结构的室外自然场景。
- **依赖基础模型**：平面分割与深度先验的质量受预训练模型影响，极端光照或未见物体可能导致失效。
- **低纹理依赖**：共面约束主要作用于平面区域，曲面上仍可能依赖常规几何先验。
- **未讨论资源开销**：DUSt3R 和 GroundedSAM 的推理需要额外GPU内存与时间，但未对总管线耗时做详细剖分。

（完）
