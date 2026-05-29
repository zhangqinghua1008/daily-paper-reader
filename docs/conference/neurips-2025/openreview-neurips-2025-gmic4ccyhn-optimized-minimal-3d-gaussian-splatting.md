---
title: Optimized Minimal 3D Gaussian Splatting
title_zh: 优化最小化3D高斯泼溅
authors: "Joo Chan Lee, Jong Hwan Ko, Eunbyung Park"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=GMiC4ccyHn"
tags: ["query:gs-slam"]
score: 6.0
evidence: 压缩3DGS表示以实现高效场景表示
tldr: 针对3D高斯泼溅（3DGS）大量高斯带来的存储和内存开销问题，提出一种优化最小化高斯数量的方法，在保持渲染质量的同时大幅压缩场景表示，实现了存储与计算效率的平衡。该方法通过发现少数量高斯对压缩敏感，直接优化高斯数量而非仅压缩属性，达到了更高的压缩比和保持质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmic4ccyhn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 738, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmic4ccyhn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 672, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmic4ccyhn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1360, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmic4ccyhn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmic4ccyhn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1430, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gmic4ccyhn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 745, \"height\": 472, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1071, \"height\": 738, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 950, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 698, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1015, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1099, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 905, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1213, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1201, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1108, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1432, \"height\": 1199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gmic4ccyhn/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1015, \"height\": 563, \"label\": \"Table\"}]"
motivation: 3DGS表示需要大量高斯，造成存储和内存负担，压缩时过少高斯对属性压缩敏感。
method: 提出优化最小化3DGS，在训练中直接最小化高斯数量并联合优化属性，实现高效压缩。
result: 在显著减少高斯数量的同时，保持与原始3DGS相当的渲染质量。
conclusion: 优化最小化3DGS为资源受限环境下的三维场景表示提供了高效方案。
---

## Abstract
3D Gaussian Splatting (3DGS) has emerged as a powerful representation for real-time, high-performance rendering, enabling a wide range of applications. However, representing 3D scenes with numerous explicit Gaussian primitives imposes significant storage and memory overhead. Recent studies have shown that high-quality rendering can be achieved with a substantially reduced number of Gaussians when represented with high-precision attributes. Nevertheless, existing 3DGS compression methods still rely on a relatively large number of Gaussians, focusing primarily on attribute compression. This is because a smaller set of Gaussians becomes increasingly sensitive to lossy attribute compression, leading to severe quality degradation. Since the number of Gaussians is directly tied to computational costs, it is essential to reduce the number of Gaussians effectively rather than only optimizing storage. In this paper, we propose Optimized Minimal Gaussians representation (OMG), which significantly reduces storage while using a minimal number of primitives. First, we determine the distinct Gaussian from the near ones, minimizing redundancy without sacrificing quality. Second, we propose a compact and precise attribute representation that efficiently captures both continuity and irregularity among primitives. Additionally, we propose a sub-vector quantization technique for improved irregularity representation, maintaining fast training with a negligible codebook size. Extensive experiments demonstrate that OMG reduces storage requirements by nearly 50% compared to the previous state-of-the-art and enables 600+ FPS rendering while maintaining high rendering quality. Our source code is available at https://maincold2.github.io/omg/.

---

## 论文详细总结（自动生成）

# 论文结构化深入总结

## 1. 论文的核心问题与整体含义
* **研究背景**  
  * 3D Gaussian Splatting (3DGS) 通过大量显式高斯原语实现实时高质量渲染，但单个场景常需数百万个高斯，存储开销巨大（需 1GB 以上），且计算成本高。
  * 现有压缩方法主要通过属性量化降低存储，但通常仍依赖较多数量的高斯（百万级），因为高斯数大幅减少后对属性压缩损失极为敏感，导致质量骤降。
* **核心问题**  
  * 如何在尽可能少的高斯原语下，既保持高渲染质量，又实现高效存储，同时提升渲染速度。
* **整体含义**  
  * 提出 **Optimized Minimal Gaussians (OMG)**，通过减少高斯数量并专门为稀疏高斯设计紧凑属性表示，在存储占用和渲染速度上同时取得突破，为资源受限设备的实时渲染铺平道路。

## 2. 方法论：核心思想、关键技术细节、算法流程
* **核心思想**  
  * 直接减少高斯数量，同时为稀疏高斯设计精确且可压缩的属性表示，避免传统方法因压缩引发的质量坍塌。
* **关键技术一：基于局部独特性的重要性评分**  
  * 基础重要性：结合“是否为某光线最高贡献者”和“累计混合权重贡献”，若未成为最高贡献者则置0（公式7）。
  * 引入**局部独特性（Local Distinctiveness, LD）**：对每个高斯 i，计算其与 K 近邻的外观特征（静态特征 T）的 L1 距离均值，乘以 λ 作为惩罚，使与邻居相似的高斯被降权（公式8）。
  * 近似 KNN：采用 Morton 序排序后取相邻索引作为邻居，加速计算。
  * 利用 CDF 阈值裁剪低分高斯。
* **关键技术二：紧凑属性表示架构**  
  * 保留几何属性（尺度 s、旋转 r）的直接参数化，因为稀疏时几何更需要精确。
  * 外观属性（颜色、不透明度）：引入**空间特征 F**（由高斯中心位置经位置编码和微型 MLP 生成）与每高斯可学习特征（静态 T、视角相关 V）结合，再通过轻量 MLP 生成 SH 系数和不透明度。
  * 优势：既利用位置连续性（空间特征），又保留每高斯不规则性（每高斯特征），比单纯用超大神经场更高效。
* **关键技术三：子向量量化（Sub-Vector Quantization, SVQ）**  
  * 将待量化向量 z 分割为 M 段（每段长度 L），每段使用独立小码本（B 个 codeword）进行向量量化。
  * 相较于标准 VQ：码本小、计算轻。相较于 R-VQ：只需单层索引，无额外索引开销。
  * 应用于几何属性（s, r）和外观特征组合后量化。
  * 训练优化：最后 1K 次迭代冻住由 K-means 初始化的索引，仅优化码本，几乎无额外训练时间。
* **整体架构流程**  
  * 输入：稀疏高斯场景（基于 Mini‑Splatting 预训练）。
  * 训练过程：引入每高斯特征与空间特征，通过 MLP 得到外观属性；20K 迭代时利用 LD 评分简化高斯；最后 1K 迭代应用 SVQ 微调码本。
  * 后处理：将位置 16-bit 量化并使用 G‑PCC 编码；SVQ 索引用 Huffman + LZMA 压缩。

## 3. 实验设计
* **数据集**  
  * Mip‑NeRF 360（室内外无界场景）
  * Tanks & Temples（大规模室外）
  * Deep Blending（多曝光场景）
  * 额外在 Zip‑NeRF 数据集上展示扩展性。
* **评价指标**  
  * 渲染质量：PSNR, SSIM, LPIPS
  * 存储：文件大小（MB）
  * 速度：FPS（渲染帧率）
* **对比方法**  
  * 原始 3DGS、Scaffold‑GS、Mini‑Splatting
  * 压缩/高效类：CompGS、Compact‑3DGS、C3DGS、LightGaussian、EAGLES、SOG、HAC、LocoGS（多个变体，包含 COLMAP 初始化版本）
  * 消融实验：移除空间特征、移除 LD 评分、移除两者、替换 SVQ 为 VQ 或 RVQ
  * 泛化性测试：将 OMG 表示应用于 3DGS‑MCMC

## 4. 资源与算力
* **GPU 型号**  
  * 主要：NVIDIA RTX 3090 和 RTX 4090（文中两者均有报告，低端设备测试还用 GTX 1080Ti）
* **训练时长**  
  * OMG 各变体训练时间约 20 分钟至 22 分钟（表 3），与 Mini‑Splatting 接近，远快于 LocoGS（约 1 小时）。
* **代码与开源**  
  * 提供源代码链接。

## 5. 实验数量与充分性
* **实验数量**  
  * 主表 3 个数据集对比十余种方法，包括 OMG 五个变体（XS, S, M, L, XL）。
  * 丰富的消融研究：空间特征、LD 评分、SVQ 对比 VQ/RVQ、LD 评分单独效果（图 5）、泛化至 MCMC。
  * 不同初始化（COLMAP）对比（表 1、2，LocoGS*）。
  * 低端设备速度测试（表 10）。
  * 存储分布分析（表 12）、后处理消融（表 11）、KNN 近似有效性（表 9）。
* **充分性与公平性**  
  * 对比方法均为近期 SOTA，指标一致，渲染速度在相同硬件上测量，公平可信；消融全面，证明各模块独立贡献。

## 6. 主要结论与发现
* OMG 将存储需求相较上届 SOTA（LocoGS）**降低约 49%**（如 OMG‑XS 仅 4.06 MB），同时保持相当渲染质量。
* 使用**极少高斯**（如 0.43M），却实现 **600+ FPS** 渲染（4090 上），且在低端 GTX 1080Ti 上仍达 106 FPS。
* LD 评分有效剔除冗余高斯，在不压缩属性时以更少高斯维持相近质量（图 5）。
* 空间特征 + 每高斯特征的混合表示在稀疏高斯情况下既压缩参数又保持连续性。
* SVQ 在码本初始化时间、存储效率、渲染质量上均优于同配置的 VQ 和 RVQ。

## 7. 优点
* **压缩与速度双领先**：4 MB 级存储下质量不塌陷，且帧率极高，适合实时应用。
* **局部独特性指标**：首次在高斯重要性评分中融入局部色彩差异，有效减少冗余而不损失。
* **子向量量化**：巧妙平衡码本大小与索引开销，计算量小、训练快，几乎无额外训练时间。
* **模块化与泛化性**：可插接到其他 3DGS 变体（如 MCMC），提升压缩效率。
* **实验扎实**：多数据集、多指标、消融完整，跨硬件验证。

## 8. 不足与局限
* **基线依赖**：方法建立在 Mini‑Splatting 等高效修剪基线上，若基线的渲染质量或高斯密度不足（如 Zip‑NeRF 场景），OMG 也会受限于此。
* **大规模场景局限**：在 Zip‑NeRF 需借助 MCMC 密集化才能获得足够高斯，原始的 3DGS/Mini‑Splatting 无法有效代表。
* **属性表示特定设计**：空间特征的引入在处理极度稀疏或高度不规则场景时可能增益减弱（文中虽验证有效，但极端情况未深入）。
* **量化策略**：SVQ 仍涉及每子向量的码本索引，虽比 R‑VQ 索引少，但未来可考虑更先进的熵模型。
* **未探索动态场景**：实验集中在静态场景，动态或时间相关应用未涉及。

（完）
