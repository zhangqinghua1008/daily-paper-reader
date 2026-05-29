---
title: "DGS-LRM: Real-Time Deformable 3D Gaussian Reconstruction From Monocular Videos"
title_zh: DGS-LRM：从单目视频实时重建可变形3D高斯
authors: "Chieh Hubert Lin, Zhaoyang Lv, Songyin Wu, Zhen Xu, Thu Nguyen-Phuoc, Hung-Yu Tseng, Julian Straub, Numair Khan, Lei Xiao, Ming-Hsuan Yang, Yuheng Ren, Richard Newcombe, Zhao Dong, Zhengqin Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=X2u8esISdb"
tags: ["query:gs-slam"]
score: 7.0
evidence: 从单目视频重建可变形3D高斯场景
tldr: DGS-LRM提出首个前馈方法，从单目带姿态视频预测可变形3D高斯溅射，实现实时动态场景重建，无需逐场景优化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2u8esisdb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2u8esisdb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2u8esisdb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 596, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2u8esisdb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2u8esisdb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2u8esisdb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2u8esisdb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 595, \"height\": 312, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2u8esisdb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 667, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2u8esisdb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 765, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2u8esisdb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 809, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2u8esisdb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 572, \"height\": 230, \"label\": \"Table\"}]"
motivation: 现有前馈重建方法限于静态场景，无法从单目视频捕捉动态物体运动，且训练数据和3D表示选择困难。
method: 提出DGS-LRM，使用前馈网络直接预测可变形3D高斯，应对动态场景重建。
result: 方法能从单目视频实时重建动态场景的3D高斯表示，渲染速度和效果兼具。
conclusion: DGS-LRM为动态场景的快速3D重建开辟了新途径，有望用于沉浸式内容生成。
---

## Abstract
We introduce the Deformable Gaussian Splats Large Reconstruction Model (DGS-LRM), the first feed-forward method predicting deformable 3D Gaussian splats from a monocular posed video of any dynamic scene. Feed-forward scene reconstruction has gained significant attention for its ability to rapidly create digital replicas of real-world environments. However, most existing models are limited to static scenes and fail to reconstruct the motion of moving objects. Developing a feed-forward model for dynamic scene reconstruction poses significant challenges, including the scarcity of training data and the need for appropriate 3D representations and training paradigms. To address these challenges, we introduce several key technical contributions: an enhanced large-scale synthetic dataset with ground-truth multi-view videos and dense 3D scene flow supervision; a per-pixel deformable 3D Gaussian representation that is easy to learn, supports high-quality dynamic view synthesis, and enables long-range 3D tracking; and a large transformer network that achieves real-time, generalizable dynamic scene reconstruction. Extensive qualitative and quantitative experiments demonstrate that DGS-LRM achieves dynamic scene reconstruction quality comparable to optimization-based methods, while significantly outperforming the state-of-the-art predictive dynamic reconstruction method on real-world examples. Its predicted physically grounded 3D deformation is accurate and can be readily adapted for long-range 3D tracking tasks, achieving performance on par with state-of-the-art monocular video 3D tracking methods.

---

## 论文详细总结（自动生成）

# DGS-LRM 论文详细总结

## 1. 论文的核心问题与整体含义

*   **核心问题**：从单目视频中快速重建动态场景的几何、外观和运动信息，是计算机视觉领域的重大挑战。传统的优化方法（如基于 NeRF 或 3DGS 的方法）虽然效果不错，但每段视频都需要耗费数小时进行逐场景优化，速度极慢，难以满足实时应用需求。
*   **研究动机**：近年来，前馈式（feed-forward）重建网络能够直接从稀疏图像中预测 3D 表示，速度比优化方法快几个数量级。然而，现有模型几乎都局限于静态场景，无法处理运动物体。核心挑战在于：缺乏大规模、带有真实运动标注的训练数据，以及缺乏适合前馈预测的动态 3D 表示。
*   **整体含义**：本文 **首次** 提出了一个名为 DGS-LRM 的前馈式模型，能够在单次推理（约0.6秒）内，从一段带相机位姿的单目视频中，直接预测可变形 3D 高斯泼溅（Deformable 3D Gaussians）表示。该表示不仅支持高质量的新视角合成，还支持精确的 2D/3D 跟踪，展现了将复杂的动态重建任务从“慢速优化”转向“实时推理”的巨大潜力，有可能会成为动态场景数字孪生、AR/VR等应用的新基础。

## 2. 论文提出的方法论

DGS-LRM 采用一个大型 Transformer 网络，一次性预测可变形 3D 高斯参数，主要包括三个核心设计和关键训练策略：

*   **核心表示：逐像素可变形 3D 高斯**
    *   **像素对齐**：类似静态 GS-LRM，模型为输入视频的每个关键帧的每个像素预测一个独立的 3D 高斯体 `gp`，包含颜色、不透明度、旋转、尺度、深度 `dp`。
    *   **可变形扩展**：每个高斯体 `gp` 额外携带一组 **3D 场景流向量** `fp = {f0, f1, ..., fN}`，表示该点从当前关键帧时刻到视频序列内任意时刻 `n` 的 3D 位移。
    *   **渲染方式**：渲染时间戳 `n` 的新视图时，将所有关键帧的高斯体根据对应位移 `fp[n]` 变形（平移）到时刻 `n`，得到一组新的 3D 高斯 `Wn`，再通过可微光栅化器渲染出图像。该过程无需变形旋转和透明度，仅平移足以。

*   **网络架构：时空压缩与 Transformer**
    *   **输入编码**：将输入视频帧 `I` 和参考帧 `R` 与对应的 Plücker 射线和时间戳归一化值拼接，作为初始特征。
    *   **时序标记化**：借鉴视频生成模型 MovieGen 的技术，将输入视频视为一个 **时空立方体**，使用 `s×s×l` 的立方块而非平面块进行标记化（tokenization）。其中 `l=4` 为时间下采样率，使得标记数量减少4倍，极大降低了后续 Transformer 的计算和内存开销。
    *   **Transformer 骨干**：使用一个 24 层多头自注意力 Transformer 处理这些时空标记。
    *   **输出投影**：最后通过两层 MLP 将每个标记投影为对应像素的可变形高斯参数。

*   **长序列处理：参考帧与流链接**
    *   **参考帧**：为解决输入视频窗口过短导致的基线和几何模糊性问题，模型额外接收 **4 个非预测参考帧** `R`，这些帧在时间上与输入帧相距较远，提供更大视差的几何线索。
    *   **流链接**：为处理超出模型输入长度的长视频，提出一种 **流链接** 算法。将两段短视频的预测场景流在重叠时间戳对齐，通过寻找空间位置和瞬时流方向均最近的点，将若干段短流拼接为长距离 3D 轨迹。

*   **训练策略与监督信号**
    *   **双视图采样**：为消除单目视频训练时的运动-几何歧义，训练时采用 **同步多视图视频**。每次迭代采样两个同步视频序列，并从中各取 `Q/2` 帧作为真值来监督渲染，显著提升收敛速度和稳定性。
    *   **直接几何与运动监督**：除了标准 RGB 渲染损失（MSE + LPIPS）外，还直接对模型预测的 **深度 `dp`** 和 **场景流 `fp`** 进行 L1 损失监督，而非仅监督渲染后的深度图或流图。这在大幅提升几何和运动精度方面被证明至关重要。
    *   **场景尺度归一化**：训练和推理时，先使用预训练的单目深度估计器估算场景尺度，将场景归一化到统一的尺度空间，增强泛化能力。

## 3. 实验设计

*   **训练数据**：
    *   **定制的 Kubric 合成数据集**：基于 Kubric 引擎生成 40,000 个动态场景，每个场景用 4 个同步相机拍摄，包含多视角图像、深度、和从物理引擎刚体运动导出的 **真值 3D 场景流**。
    *   通过设置更小的相机移动范围（最大0.5米）、增加运动模糊、变化焦距等方式缩小与真实视频的差异。

*   **测试基准与对比方法**：
    *   **动态新视角合成**：
        *   **数据集**：DyCheck (iPhone 子集) 和 DAVIS（仅定性）。
        *   **对比方法**：优化式方法（D3DGS、PGDVS）和前馈式方法（L4GM）。
        *   **评估指标**：mPSNR、mLPIPS (DynMask 动态区域)。
    *   **3D 跟踪**：
        *   **数据集**：PointOdyssey。
        *   **对比方法**：SpatialTracker、Chained RAFT3D、Lifted CoTracker。
        *   **评估指标**：ATE-3D、δ<0.1、δ<0.2 (阈值准确率)。
    *   **消融实验**：
        *   **组件**：时间标记化（TT）、双视图采样（DV）、场景流损失（SF）、参考帧（RF）。
        *   **基准**：DyCheck 和内部 Kubric 多视角测试集。

## 4. 资源与算力

*   **训练硬件**：使用 **64 块 80GB H100 GPU** 进行分布式训练。
*   **训练流程**：
    *   **第一阶段**：在 256×256 分辨率下训练 40,000 次迭代，单卡 batch size 为 15。
    *   **第二阶段**：在 512×512 分辨率下微调 20,000 次迭代，单卡 batch size 为 8。
*   **推理速度**：在单块 **A100 GPU** 上，一次前向推理耗时 **0.495 秒**（约 24 FPS），达到实时性要求。

## 5. 实验数量与充分性

*   **实验组数**：共进行了 **3 项主要评估**（动态视图合成、3D 跟踪、消融研究）和 **1 项细化分析**（静态 vs 动态、关键帧 vs 非关键帧性能），覆盖了模型主要声明的能力。
*   **充分性与客观性**：
    *   **充分**：实验设计较为全面。在主要任务（新视角合成和跟踪）上，选取了最先进的优化式和前馈式方法进行对比，并使用了该领域的标准基准（DyCheck、PointOdyssey）和评价指标。消融实验验证了各个核心组件（DV、SF、RF、TT）的必要性。
    *   **公平性**：与优化方法对比时，所有方法使用相同的 SfM 深度进行初始化或场景归一化，确保了比较的公平性。与 L4GM 对比时，遵循其设定仅在动态前景区域评估。
    *   **存在的局限**：由于 DyCheck 的大视角遮挡问题，其对使用短输入窗口的 DGS-LRM 相对不利。定性实验在 DAVIS 上只展示了效果，未进行定量评估。

## 6. 论文的主要结论与发现

*   **性能比拟优化方法**：DGS-LRM 在 DyCheck 数据集上的动态新视角合成质量，达到了与需要数小时优化的方法（如 PGDVS）**相当甚至部分更优**的水平，大幅超越前馈式基线 L4GM（提升 3 个 PSNR 点）。
*   **实时性与泛化性**：模型能以 **0.5秒** 的速度完成推理，并成功从纯合成数据**零样本泛化到真实世界的复杂视频**，展现出强大的场景理解能力。
*   **精准的 3D 运动预测**：模型预测的场景流可直接用于 3D 跟踪，在长距离跟踪基准 PointOdyssey 上取得与最先进的 SpatialTracker **可比** 的性能，且在无纹理区域表现更鲁棒。
*   **核心设计有效**：大规模合成数据、双视图训练、直接场景流监督以及参考帧机制，是模型摆脱单目歧义、稳定收敛并取得高性能的关键。

## 7. 优点

*   **首创性与速度突破**：首次实现从单目视频实时前馈预测可变形 3D 高斯，将重构时间从“小时级”缩短到“毫秒级”，为该领域探索实时反馈应用提供了可能。
*   **统一的强大表示**：提出的逐像素可变形 3D 高斯简洁且强大，能够同时完成新视角渲染、几何重建和 3D 运动估计，是一个多功能的场景表示。
*   **纯合成训练与泛化的成功**：展示了仅用物理模拟的合成数据（配合跨域随机化）训练出能在真实视频上强泛化的模型，验证了合成数据在复杂动态任务中的潜力，并解决了真实数据标注困难的问题。
*   **有效的训练范式**：“双视图采样”和“直接流/深度监督”的组合，简单而高效地解决了动态重建中严重的多义性问题，训练策略设计巧妙。

## 8. 不足与局限

*   **相机运动类型限制**：模型只能处理时间连续的相机运动视频，无法处理非连续视角或“瞬移”相机拍摄的图像。
*   **大运动处理能力不足**：受限于仿真数据的运动分布，对视频中幅度极大的物体运动预测可能失效。
*   **流链接导致视觉效果瑕疵**：用于长视频的流链接方法虽然在跟踪指标上有效，但在拼接点附近渲染图像时会产生可见的外观跳跃。
*   **视角外推能力受限**：当新视角严重偏离输入视频轨迹时，渲染质量会因可见面信息缺失而显著下降。
*   **实验偏差风险**：
    *   DyCheck 基准的评估协议更利于使用全序列优化的方法，对仅使用24帧短窗口的 DGS-LRM 有偏差。
    *   DAVIS 上的结果仅有视觉比较，缺乏定量数据支持。
    *   合成训练数据以 **刚体运动** 为主，可能导致对衣物变形、流体运动等复杂非刚体场景的泛化仍有局限，这一点在论文的讨论中着墨不多。

（完）
