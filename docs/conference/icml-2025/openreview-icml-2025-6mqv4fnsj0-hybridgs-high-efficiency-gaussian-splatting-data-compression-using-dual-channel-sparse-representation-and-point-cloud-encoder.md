---
title: "HybridGS: High-Efficiency Gaussian Splatting Data Compression using Dual-Channel Sparse Representation and Point Cloud Encoder"
title_zh: HybridGS：基于双通道稀疏表示和点云编码器的高效高斯泼溅数据压缩
authors: "Qi Yang, Le Yang, Geert Van der Auwera, Zhu Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6mQv4fnsj0"
tags: ["query:gs-slam"]
score: 7.0
evidence: 通过双通道稀疏表示和点云编码实现高效3DGS压缩
tldr: 为解决3DGS隐式压缩方案编码耗时且格式不通用的问题，HybridGS提出双通道稀疏表示引导的显式紧凑生成方法，监督基元位置和特征位宽，并结合点云编码器实现标准化压缩。实验表明，该方法在保证快速编解码的同时显著减小模型体积，并兼容标准化点云格式，便于部署和交换。这一高效压缩技术有望降低3DGS场景表示在SLAM等应用中的存储与传输开销。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 760, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 720, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 830, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1252, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1064, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1065, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 709, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1418, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1426, \"height\": 1182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1775, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1742, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1741, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6mqv4fnsj0/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1750, \"height\": 644, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1547, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 561, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 639, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 786, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 515, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 611, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 917, \"height\": 632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1470, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1130, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1182, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6mqv4fnsj0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1150, \"height\": 1690, \"label\": \"Table\"}]"
motivation: 现有3DGS压缩方法编码慢、格式私有，难以实际部署。
method: 提出双通道稀疏表示监督生成紧凑基元，结合点云编码器进行标准化压缩。
result: 实现快速编解码，显著压缩3DGS模型，且保持渲染质量。
conclusion: 为3DGS的高效存储和交换提供了通用解决方案，对SLAM等应用具有潜在价值。
---

## Abstract
Most existing 3D Gaussian Splatting (3DGS) compression schemes focus on producing compact 3DGS representation via implicit data embedding. They have long encoding and decoding times and highly customized data format, making it difficult for widespread deployment. This paper presents a new 3DGS compression framework called HybridGS, which takes advantage of both compact generation and standardized point cloud data encoding. HybridGS first generates compact and explicit 3DGS data. A dual-channel sparse representation is introduced to supervise the primitive position and feature bit depth. It then utilizes a canonical point cloud encoder to carry out further data compression and form standard output bitstreams. A simple and effective rate control scheme is proposed to pivot the interpretable data compression scheme. HybridGS does not include any modules aimed at improving 3DGS quality during generation. But experiment results show that it still provides comparable reconstruction performance against state-of-the-art methods, with evidently faster encoding and decoding speed. The code is publicly available at https://github.com/Qi-Yangsjtu/HybridGS .

---

## 论文详细总结（自动生成）

# HybridGS 论文总结

## 1. 论文的核心问题与整体含义
*   **研究动机**：三维高斯泼溅（3DGS）虽能实现高质量实时渲染，但其显式数据格式和基元稠密化策略导致数据量巨大，存储和传输困难。
*   **现有挑战**：主流压缩方法分为两类。
    *   **生成式压缩**：压缩比高，但将数据隐式嵌入神经网络或定制格式，导致编解码极慢（常超过 1 秒甚至 1 分钟），难以标准化和实际部署。
    *   **传统压缩**：利用点云编码器，速度快且格式标准，但由于 3DGS 数据量庞大且对量化敏感，无损压缩下码率依然很高，有损压缩则失真明显。
*   **本文目标**：提出一种混合压缩框架 **HybridGS**，融合生成式压缩的紧凑性和传统压缩的标准化与高效率，实现兼顾重建质量、极快编解码速度以及标准比特流输出的方案。

## 2. 论文提出的方法论
HybridGS 由两大步骤构成：**双通道稀疏表示生成紧凑显式 3DGS** 和 **点云编码器标准化压缩**。

### 2.1 双通道稀疏表示
此步骤负责在 3DGS 训练过程中直接产出紧凑且满足点云编码器要求的数据格式（整数坐标、唯一位置、量化特征）。

*   **属性稀疏表示**：
    *   **特征通道降维**：利用 PCA 分析发现颜色和旋转特征具有可压缩性。采用“**可学习低维潜在特征 + 可训练轻量解码器（单隐藏层 MLP）**”的方式，重构高维属性，实现特征通道的稀疏化。该方法可被视为广义 PCA，但通过端到端训练保留更多细节。
    *   **特征精度控制（量化）**：将量化操作整合进生成过程。对潜在特征、透明度、缩放等属性使用**鲁棒量化器（RQ）**或普通均匀量化（UQ）。RQ 通过注入扰动并建立岭回归重构（公式 \(a = \text{Cov}(f, q)/(\text{Var}(q) + \lambda), b = \bar{f} - a\bar{q}\)），有效缓解量化噪声导致的失真。量化后可按设定位深（BD）计算每个基元的比特数：\(P_{\text{bit}} = 3(\text{BD}_p + \text{BD}_s) + k_c \text{BD}_c + \text{BD}_o + k_r \text{BD}_r\)。
*   **基元稀疏化（位置控制）**：
    *   **可学习量化器方法（LQM）**：生成具有整数坐标且可直接用于渲染（无需反量化）的唯一基元。流程分四步：预热训练标准 3DGS -> 平移并缩放至目标位深对应的空间（坐标范围 \([-2^{N-1}+1, 2^{N-1}-1]\)） -> 将整数坐标分解为**基向量** \([2^{N-2}, ..., 1]\) 与**编码向量**（取值 \(\{-1, 0, 1\}\)）的内积进行优化 -> 执行渐进式唯一性保证与剪枝。
    *   **渐进式剪枝与唯一性**：在训练后期逐步剪除冗余基元，并保证几何位置上无重复基元（若重复，保留缩放量最大的基元）。通过设定多个时间节点（稠化结束 \(T_d\)、最佳质量 \(T_{\text{top}}\)、剪枝开始 \(T_p\)、唯一性结束 \(T_u\) 且 \(T_d < T_{\text{top}} < T_p < T_u \approx T\)），在控制基元数量的同时减少质量波动。

### 2.2 高效编码与速率控制
*   **编码器选择**：采用基于几何的点云压缩标准测试模型（GPCC v23）。将 3DGS 拆分为“位置 + 单个属性”的多个“xyza”格式子文件，利用 GPCC 的八叉树模式压缩位置，RAHT 模式压缩其他属性。解码后合并还原。
*   **速率控制**：利用显式紧凑表示的码率可计算性。提出两种方法：（1）**控制基元数量**（渐进剪枝）；（2）**调整特征位深**（逐步降低各路特征的 BD）。公式为 \(R(GS) = n \cdot P_{\text{bit}} / L\)，其中 \(L\) 为下游编码器的无损压缩比。实验表明基于剪枝的方法控制更精确。

## 3. 实验设计
*   **数据集与场景**：选取了 5 个典型场景覆盖不同数据集类型：
    *   `playroom`（Deep Blending）
    *   `train`（Tanks&Temples）
    *   `bicycle`、`room`（Mip-NeRF360 室外/室内）
    *   `dance`（PKU-DyMVHumans 首帧）
*   **对比基准方法**：
    *   生成式压缩：Scaffold-GS， Compact3D， C3DGS， CompGS(ECCV)， LightGaussian， Eagles， HAC， CompGS(MM)。
    *   传统压缩：GGSC， HGSC。
*   **评价指标**：主要使用重构质量的 PSNR（dB）与压缩后文件大小（MB），同时对比编解码时间（秒）与帧率（FPS）。

## 4. 资源与算力
*   论文中所有实验均在 **Intel Core i9-14900HX CPU** 及 **单个 NVIDIA RTX 4090 Laptop GPU** 上进行（见附录 A.1）。
*   训练设定：总训练轮次固定为 70,000 次。文中未报告完整的训练耗时，但重点展示了压缩模型的重建质量和编解码时间。

## 5. 实验数量与充分性
实验设计较为全面，覆盖了性能、效率、分析与可控性多个维度：
*   **主结果**：提供了一张包含 5 个数据集、14 种对比方法变体的定量对比表（表 1）。
*   **效率分析**：对比了 3 种骨架方法在 `bicycle` 和 `room` 上的编解码时间（表 2）。
*   **比特分配**：详细列出了 `bicycle` 和 `dance` 场景下各组件（位置、颜色、透明度等）的比特开销（表 3）。
*   **速率控制**：在 `train` 和 `dance` 上验证了两种速率控制方法的精度（表 4）。
*   **参数敏感性**：分析了不同位深（12~16 bit）和量化器（RQ vs UQ）对性能的影响（表 5）。
*   **消融与验证实验**：包括 PCA 与可学习低秩近似的对比（表 6）、LQM 中异常点移除与平移的影响（图 9）、基元唯一性的影响（表 7）、不同点云编码器对位置的压缩效果（图 11）等。整体上，实验从对照、消融、分析多角度展开，客观且充分。

## 6. 论文的主要结论与发现
*   **可比的重建质量**：HybridGS 在不引入任何质量提升模块（以上限为原生 3DGS）的前提下，压缩后 PSNR 与最先进的生成式方法持平或更优（如 `dance` 上优于 CompGS(MM)，`playroom` 上与 C3DGS 质量相同但体积更小）。
*   **极快的编解码速度**：HybridGS 的编解码总时间通常在 0~2 秒以内，相比 HAC（80+秒）和 HGSC（数十秒），速度提升百倍级，满足实时流式传输对低延迟的要求。
*   **有效的速率控制**：基于显式数据量的计算和渐进式剪枝/降位深，能够较精确地达到目标码率。
*   **标准化兼容性**：输出符合标准点云编码器格式的比特流，利于未来标准化和广泛部署。

## 7. 优点
*   **架构融合的巧思**：将生成式压缩用于“预处理”（产出紧凑显式基元），再交由成熟的传统点云编码器完成标准化编码，兼顾了各自的优点。
*   **速度优势巨大**：编解码时间远远低于其他 SOTA 生成式压缩方法，是该方法最突出的亮点。
*   **可解释性与可控性强**：压缩过程中每个基元的比特数可计算，速率控制策略直观，流量分配透明。
*   **实用导向**：不改变原生 3DGS 质量上界，专注于压缩本身，且输出格式标准，易于集成到现有视频/点云传输管道中。

## 8. 不足与局限
*   **压缩效率上限**：最优压缩比（同等质量下体积）低于采用率失真损失（RD loss）进行端到端训练的最新生成式方法（如 HAC、CompGS(MM)），因为该方法未对 3DGS 生成过程进行质量增强。
*   **超参数依赖**：需要手动选择潜在特征维度（\(k_c, k_r\)）和位深（BD）。文中指出，自适应参数选择算法可能进一步改善效果。
*   **速率控制局限**：当目标码率极低时，仅靠降位深可能无法达到要求；且降低潜在特征维度可能引起特征空间崩溃，文中未实现平滑降维的速率控制。
*   **点云编码器效率**：GPCC 对 3DGS 属性的压缩比尚有提升空间（文中指出 RAHT 对 3DGS 属性的压缩效果有待改进），且学习基点云编码器（SparsePCGC）因要求位置唯一性，直接使用会造成严重失真，需适配。
*   **实验范围**：虽然覆盖了主流数据集，但全为静态场景。对于动态 3DGS 序列的压缩效果和实时性，文中未作探讨。

（完）
