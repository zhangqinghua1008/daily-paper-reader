---
title: Learning Efficient Fuse-and-Refine for Feed-Forward 3D Gaussian Splatting
title_zh: 学习高效融合与精炼的前馈3D高斯泼溅
authors: "Yiming Wang, Lucy Chai, Xuan Luo, Michael Niemeyer, Manuel Lagunas, Stephen Lombardi, Siyu Tang, Tiancheng Sun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=KsmgnL6PUb"
tags: ["query:gs-slam"]
score: 7.0
evidence: 改进前馈3DGS以实现高效稀疏视角场景重建
tldr: 针对现有前馈3D高斯泼溅（3DGS）中像素对齐基元导致的重叠冗余以及难以泛化到动态场景的问题，提出融合-精炼模块，通过融合多视角特征并优化3D高斯参数，实现高效稀疏视图三维重建，提高表示效率和灵活性。该方法在减少冗余的同时，更好地支持动态场景扩展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1359, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1347, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1301, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1163, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 779, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1278, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1513, \"height\": 1076, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmgnl6pub/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1493, \"height\": 916, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 581, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 837, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1266, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1276, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 800, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 582, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1049, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1025, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1203, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1459, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 567, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmgnl6pub/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 623, \"height\": 182, \"label\": \"Table\"}]"
motivation: 前馈3DGS像素对齐方式在多视图重叠时产生冗余，且难以处理动态内容。
method: 提出融合-精炼模块，融合多视图信息并精炼高斯参数，消除冗余并增强表达能力。
result: 在稀疏视图重建中，以更少的高斯数量实现更高质量和效率。
conclusion: 融合-精炼策略提升了前馈3DGS的性能，为实时三维重建奠定了基础。
---

## Abstract
Recent advances in feed-forward 3D Gaussian Splatting have led to rapid improvements in efficient scene reconstruction from sparse views. However, most existing approaches construct Gaussian primitives directly aligned with the pixels in one or more of the input images. This leads to redundancies in the representation when input views overlap and constrains the position of the primitives to lie along the input rays without full flexibility in 3D space. Moreover, these pixel-aligned approaches do not naturally generalize to dynamic scenes, where effectively leveraging temporal information requires resolving both redundant and newly appearing content across frames. To address these limitations, we introduce a novel Fuse-and-Refine module that enhances existing feed-forward models by merging and refining the primitives in a canonical 3D space. At the core of our method is an efficient hybrid Splat-Voxel representation – from an initial set of pixel-aligned Gaussian primitives, we aggregate local features into a coarse-to-fine voxel hierarchy, and then use a sparse voxel transformer to process these voxel features and generate refined Gaussian primitives. By fusing and refining an arbitrary number of inputs into a consistent set of primitives, our representation effectively reduces redundancy and naturally adapts to temporal frames, enabling history-aware online reconstruction of dynamic scenes. Trained on large-scale static scene datasets, our model learns an effective global strategy to process around 200k primitives within 15ms and significantly enhances reconstruction quality compared to pixel-aligned reconstruction approaches. Without additional training, our model generalizes to video by fusing primitives across time, yielding a more temporally coherent result compared to baseline methods with graceful handling of occluded content. Our approach achieves state-of-the-art performance in both static and streaming scene reconstructions while running at interactive rates (15 fps with 350ms delay) on a single H100 GPU.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义
- 研究背景：前馈式三维高斯泼溅（Feed‑Forward 3DGS）在稀疏视图重建中速度很快，但主流方法直接从输入图像像素生成高斯基元（像素对齐），导致：
  - 多视图重叠区域产生大量冗余基元。
  - 基元位置被约束在射线上，缺少三维空间灵活性。
  - 难以自然延展到动态场景，因为无法有效融合历史帧中重复或新出现的内容。
- 研究动机：需要在三维空间中合并、精炼多帧/多视图的基元，消除冗余，并支持利用历史信息进行流式重建。

### 方法论
- 核心思想：提出 **Fuse‑and‑Refine 模块**，将初步像素对齐的高斯基元转换到标准三维空间进行融合与优化，输出一套紧凑、一致的精炼高斯基元。
- 关键技术细节：
  - **混合 Splat‑Voxel 表示**：
    - *Splat‑to‑Voxel 转移*：将初始高斯基元按照位置和权重“沉积”到高分辨率体素网格中，计算体素属性（融合特征和原始参数）。
    - *粗‑细体素层级*：对高分辨率体素下采样得到粗体素网格，利用 MLP 聚合细体素特征形成粗体素特征，并根据体素权重稀疏化（保留前 20% 的粗体素），将 token 数降至 10K 以内。
    - *稀疏体素 Transformer*：对粗体素特征执行自注意力操作，然后将全局上下文复制回细体素，结合原始细体素属性，通过 MLP 预测高斯参数的残差，产生最终的高斯基元。
  - **零样本流式融合（动态场景）**：
    - 使用预训练二维点跟踪（TAPIR）获得历史帧到当前帧的二维对应，通过三角化恢复三维运动，并结合形变图（Embedded Deformation Graph）传播运动。
    - 在所有历史关键帧基元和当前帧基元上执行 Splat‑to‑Voxel 和 Voxel Transformer，通过基于渲染误差的自适应权重抑制错误历史基元，实现时间一致性融合。
  - 训练损失：MSE + 感知损失 LPIPS，对多视图 Transformer 和体素 Transformer 分别设置不同权重。

### 实验设计
- 数据集与场景：
  - 静态场景：RealEstate10K（256×256）、DL3DV（384×216）。
  - 动态场景（零样本流式）：Neural3DVideo（320×240，2输入视图）、LongVolumetricVideo（384×216/256×256，4输入视图）。
- 对比方法：
  - 静态：pixelSplat、MVSplat、TranSplat、HiSplat、OmniScene、DepthSplat、GS‑LRM等。
  - 动态：3DGS、3DGStream、4DGS、GS‑LRM。
- 评价指标：PSNR、SSIM、LPIPS，动态场景额外使用 flicker 指标衡量时间一致性。

### 资源与算力
- 训练硬件：NVIDIA A100 GPU。部分实验（如 Table 2）采用 8 块 A100，每卡 batch size 2，训练 200K 迭代；完整模型在 DL3DV 上用 batch size 128 训练 300K 迭代，预计使用多卡或更大算力，但文中未明确总卡数。
- 推理硬件：所有运行时间均在单块 NVIDIA H100 GPU 上测量（静态约 67ms，动态非关键帧 70ms，关键帧 350ms）。
- 训练时长：多视图 Transformer 预训练 200K 迭代，联合微调 100K 迭代；静态 RealEstate10K 上训练 100K 迭代。

### 实验数量与充分性
- 主要实验组：
  - 静态场景：RealEstate10K 与 DL3DV 上的基准对比（Table 1, 2）。
  - 动态流式：两个动态数据集上的零样本评测（Table 4, 11）。
  - 消融实验：验证粗‑细体素、稀疏化、splat特征、训练策略、时间组件（3D warping、误差感知融合）等（Table 2, 5, 7, 8）。
  - 泛化实验：不同输入视图数量（2/4/8/16）测试（Table 3）。
  - 与其他框架集成：集成到 DepthSplat 验证插件式提升（Table 14）。
  - 与 Gaussian Graph Network 对比（Table 13）。
- 总体评价：实验设计较全面，覆盖静态/动态、不同数据集、多组消融和泛化测试，对比方法丰富，具备较好的客观性和公平性。

### 主要结论与发现
- 提出的 Fuse‑and‑Refine 模块可将冗余像素对齐基元融合为一致的精炼表示，相比 GS‑LRM 提升约 2 dB PSNR（静态场景）。
- 模型仅用静态数据训练，即可零样本泛化到动态流式重建，显著降低 flicker 并获得更优的视图质量，同时维持 15 fps 的交互速率。
- 学习式融合远优于简单的启发式融合或直接拼接，粗‑细体素层级与稀疏 Transformer 是高效高质量的关键。
- 历史信息的引入和误差感知融合对动态场景的稳定重建至关重要。

### 优点
- 创新性地将高斯泼溅与体素 Transformer 结合，实现高效的基元融合与优化。
- 学习式策略取代手工融合规则，提升重建精度同时保持极低延迟。
- 仅需静态数据训练即可处理动态流式，克服多视图动态数据稀缺问题。
- 可与现有前馈 3DGS 框架（如 GS‑LRM、DepthSplat）无缝集成，拓展性强。

### 不足与局限
- 严重依赖初始高斯基元的质量；在大基线、复杂视角变化下，初始基元若较差，本方法提升有限。
- 动态场景中仍存在时间伪影，主要源于基于二维跟踪的简单 3D warping 策略在稀疏视图下误差较大。
- 实验未报告多次训练的统计误差条，可能影响结论的稳健性评估。
- 未开放代码，复现需依赖详细描述，可能延缓后续研究。

（完）
