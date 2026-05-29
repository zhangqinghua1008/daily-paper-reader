---
title: Generalizable Hand-Object Modeling from Monocular RGB Images via 3D Gaussians
title_zh: 通过3D高斯从单目RGB图像进行可泛化的手-物建模
authors: "Xingyu Liu, Pengfei Ren, Qi Qi, Haifeng Sun, Zirui Zhuang, Jing Wang, Jianxin Liao, Jingyu Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=JTF0HYfGiL"
tags: ["query:gs-slam"]
score: 6.0
evidence: 从单目RGB使用3D高斯溅射进行手物建模
tldr: HOGS提出适应性3D高斯溅射框架，从无约束单目RGB图像重建手和物体，无需密集3D标注，可推广到多样化环境。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 823, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 611, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 690, \"height\": 1063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 687, \"height\": 1057, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1429, \"height\": 1294, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1331, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 647, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 749, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 590, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1458, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 875, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 898, \"height\": 362, \"label\": \"Table\"}]"
motivation: 现有手物建模方法依赖密集3D表面标注或局限于短序列，泛化性差。
method: HOGS融合视觉光度线索和物理结构先验，构建可适应3DGS框架，从单目图像重建手-物交互形状和外观。
result: HOGS在多种环境和运动模式下准确重建手和物体，泛化能力强于先前方法。
conclusion: 3DGS结合物理先验为单目手物交互重建提供了可泛化的新思路。
---

## Abstract
Recent advances in hand-object interaction modeling have employed implicit representations, such as Signed Distance Functions (SDF) and Neural Radiance Fields (NeRF) to reconstruct hands and objects with arbitrary topology and photo-realistic detail. However, these methods often rely on dense 3D surface annotations, or are tailored to short clips constrained in motion trajectories and scene contexts, limiting their generalization to diverse environments and movement patterns. In this work, we present HOGS, an adaptively perceptive 3D Gaussian Splatting (3DGS) framework for generalizable hand-object modeling from unconstrained monocular RGB images. By integrating photometric cues from the visual modality with the physically grounded structure of 3D Gaussians, HOGS disentangles inherent geometry from transient lighting and motion-induced appearance changes. This endows hand-object assets with the ability to generalize to unseen environments and dynamic motion patterns. Experiments on two challenging datasets demonstrate that HOGS outperforms state-of-the-art methods in monocular hand-object reconstruction and photo-realistic rendering.

---

## 论文详细总结（自动生成）

好的，作为资深学术论文分析助手，我将以 Markdown 形式，对提供的论文《Generalizable Hand-Object Modeling from Monocular RGB Images via 3D Gaussians》进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究问题**：现有基于隐式表示（如 NeRF、SDF）的手物交互建模方法，虽然能重建高保真模型，但普遍存在两大局限性，导致其跨场景、跨动作的**泛化能力不足**：
    1.  **数据依赖性强**：高度依赖精确但获取成本高昂的密集 3D 表面标注。
    2.  **场景与动作固化**：通常针对特定短视频序列进行优化，模型学习到的外观和运动模式受限于该序列的特定光照、遮挡和运动轨迹，无法适应新环境或新动作。
*   **整体含义**：本文旨在探索一种**无需密集3D标注、且能从海量非受限单目RGB图像中学习到通用先验**的新范式，使重建出的手物资产能够泛化到未见过的视觉环境和动态运动模式中，实现从“逐场景定制优化”到“一次性训练、多场景即用”的跨越。

### 2. 论文提出的方法论

论文提出了一个名为 **HOGS (Hand-Object Gaussian Splatting)** 的自适应感知 3D 高斯溅射框架。其核心思想是将神经网络的可学习感知能力与3D高斯原语的物理几何结构相结合，将手物几何属性与瞬变的外观变化（如光影）解耦。

**关键技术细节与流程如下：**

*   **基础表示 (Sec 3.1)**：使用可形变的 3D 高斯原语 $\{G_h\}$ 和 $\{G_o\}$ 分别在手部和物体的规范空间建模。通过**线性混合蒙皮** 和**6自由度刚体变换**，将规范空间的高斯原语根据手部姿态和物体位姿驱动到观测空间。所有高斯原语通过阿尔法混合进行联合渲染，得到像素颜色 $C$。

*   **视觉驱动泛化感知模块 (V-PM) (Sec 3.2)**：这是应对视觉环境变化的**核心创新**。
    *   **解耦机制**：将标准 3DGS 的参数解耦为**几何不变模板**（如初始位置 $p$、SH 颜色 $c_{sh}$）和**视觉依赖分量**（如颜色偏移、位置微调）。
    *   **自适应调制**：利用视觉 Transformer (ViT) 提取图像特征 $F$，并通过像素对齐采样获得每个高斯投影位置的特征 $F(\pi(p_t))$。一个 MLP $\psi$ 接收这些视觉特征和高斯参数 $G$，预测出视觉依赖分量 $Z_v$。
    *   **自适应外观**：一个关键设计是，颜色分量由一个**自适应权重 $\alpha$** 来混合原始的 SH 颜色 $c_{sh}$ 和视觉依赖颜色分量，公式为 $c = (1-\alpha) \cdot c_{sh} + \alpha \cdot \text{Sigmoid}(Z_v)$。这使得模型能学习如何根据视觉环境动态调整外观。类似地，位置、尺度和旋转也通过预测偏移量（$\delta p, \delta s, \delta q$）进行微调。

*   **几何驱动位姿优化模块 (G-PM) (Sec 3.3)**：为提升对新运动模式的泛化能力，该模块利用 3D 高斯原语蕴含的显式几何和物理信息来优化粗糙的初始手物位姿。
    *   **3D 几何编码**：将位姿变换后的高斯中心 $p_t$ 视为点云，使用经过多模态预训练（ULIP）的 PointNet++ 作为 3D 骨干网络，提取融合了几何与视觉属性的 3D 高斯特征矩阵 $F_G$。
    *   **位姿回归与物理约束**：将提取的特征送入 Transformer 编码器和 MLP，回归物体的相对平移和旋转偏移量（$\Delta T_o, \Delta R_o$）。同时，将手物高斯中心作为点云，施加**接触和穿透损失函数**，以物理规则约束手物交互的合理性，无需依赖物体模板。

### 3. 实验设计

*   **数据集与场景**：
    *   **DexYCB**：用于评估手物联合重建和照片级渲染。按官方分割划分训练/测试集，并将视频下采样至 6 FPS 用于重建评估。
    *   **HO3D_v3**：用于评估手持物体的网格重建质量，按特定协议选取 18 个序列进行训练。
*   **对比方法**：
    *   **3D密集监督方法 (SDF-based)**：Hasson et al., Grasping Field, AlignSDF, gSDF, HORT 等。
    *   **2D光度监督方法**：MOHO, HOLD, DiffHOI, iHOI 等。
    *   **改进的 3DGS 基线**：将用于人体建模的 `3DGS-Avatar` 和用于静态场景重建的 `GOF` 进行适配，形成手物交互重建的新基线（由 † 标记）。
*   **评估指标**：覆盖几何和渲染两大方面。
    *   **几何指标**：Chamfer Distance (CD, $cm^2$)，F-score (不同阈值)，物体位姿误差 (CD$_{pose}$, OCE, MCE, ADD-S)。
    *   **渲染指标**：PSNR, SSIM, LPIPS。

### 4. 资源与算力

*   **GPU 型号**：使用**单张 NVIDIA RTX 4090 GPU** 完成所有训练。
*   **训练时长**：在 DexYCB 数据集上，共训练 36 万次迭代，耗时约**10 小时**；在 HO3D 数据集上训练 20 万次迭代。训练完毕后，还会冻结 3D 高斯参数，对其余模块进行额外的 10 个 epoch 训练。

### 5. 实验数量与充分性

论文通过多维度、多组别的实验设计，验证了方法的有效性和各模块的贡献，实验较为充分和客观。

*   **主实验**：
    1.  **表面重建**：在 DexYCB 和 HO3D_v3 上与多个 SOTA 方法进行定量对比（表 2, 3）。
    2.  **照片级渲染**：在 DexYCB 上与 3DGS 基线方法进行定量对比（表 4）。
    3.  **手持物位姿估计**：在 DexYCB 上与位姿估计方法对比（表 5）。
    4.  **可视化对比**：提供了大量渲染和重建的定性结果（图 3, 4）。
*   **消融实验**：
    1.  **视觉环境变化鲁棒性分析**：通过施加色彩抖动来模拟光照变化，对比 `HOGS`、`HOGS (w/o V-PM)` 和 `3DGS-Avatar` 的性能，有力地证明了 V-PM 的泛化能力（表 6, 图 5）。
    2.  **核心模块有效性**：逐步移除接触优化、预训练 3D 骨干、G-PM、自适应外观和 V-PM，全面验证了各组件对渲染、位姿和几何重建的贡献（表 7）。
    3.  **视觉驱动组件粒度**：对 V-PM 内部的全局特征、像素对齐特征和 3DGS 参数进行消融，证明多粒度特征融合的效果最佳（表 8）。

### 6. 论文的主要结论与发现

1.  **性能卓越**：HOGS 在 DexYCB 和 HO3D 数据集上，在手物重建、照片级渲染和位姿估计等多个任务上均达到或超越了当前 SOTA 方法的性能水平。
2.  **强泛化能力**：所提出的 V-PM 和 G-PM 模块成功赋予了模型跨视觉环境和运动模式的泛化能力，无需对新场景进行微调。例如，在色彩抖动干扰下，本方法的渲染质量下降远小于基线。
3.  **物理感知建模的重要性**：显式利用 3D 高斯的物理几何属性进行位姿优化和接触推理（G-PM），比纯粹依赖图像信号的方法能够获得更准确、更合理的交互位姿。

### 7. 优点

*   **创新性强**：首次将 3DGS 与神经网络的适应性感知能力深度融合，用于解决单目手物重建的泛化问题，区别于传统的逐序列优化范式。
*   **解耦设计精巧**：V-PM 对几何不变部分和视觉依赖部分的解耦，以及自适应颜色混合机制，是对 3DGS 在动态、多变场景下建模能力的重要改进。
*   **物理感知**：G-PM 不依赖物体模板，通过高斯原语的几何属性进行位姿优化和接触约束，是一种更通用、物理上更合理的思路。
*   **实验扎实**：实验设计全面，不仅在标准条件下对比，还通过色彩抖动等鲁棒性测试和详尽的消融实验，有力论证了每个模块的价值。
*   **实用性强**：方法仅需单目 RGB 图像作为输入，训练效率高（单卡 10 小时），且开源了代码，具有很好的实际应用潜力。

### 8. 不足与局限

*   **物体类别泛化受限**：论文明确指出，其泛化能力主要体现在视觉环境和运动模式上，而对于**训练时未见过的新物体类别**，其重建能力有限。这是一个核心的零样本学习局限。
*   **依赖初始位姿估计**：3D 高斯原语的形变驱动依赖于一个离线的回归器提供的初始手物位姿。方法的最终性能会在一定程度上受限于该初始回归器的精度。
*   **数据集覆盖范围**：实验仅在 DexYCB 和 HO3D 这两个实验室环境采集的数据集上进行，数据集中的物体种类、交互动作和场景多样性仍然有限，模型在“in-the-wild”场景下的性能有待进一步检验。
*   **动态模糊和剧烈光照**：虽然 V-PM 旨在处理瞬变外观，但论文未专门讨论在存在严重运动模糊或极端光照（如强逆光、镜面反射）等更具挑战性的真实场景下的表现。

（完）
