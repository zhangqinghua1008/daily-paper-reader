---
title: High Dynamic Range Novel View Synthesis with Single Exposure
title_zh: 基于单曝光的高动态范围新视角合成
authors: "Kaixuan Zhang, HuWang, Minxian Li, Mingwu Ren, Mao Ye, Xiatian Zhu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=iMp2vzs4f8"
tags: ["query:gs-slam"]
score: 4.0
evidence: 从单曝光LDR图像进行新视角合成，与SLAM中的场景表示相关
tldr: 首次研究单曝光LDR图像下的高动态范围新视角合成（HDR-NVS）问题，提出Mono-HDR-3D方法，包含亮度补偿和高动态重建模块。该方法有效解决了多曝光HDR-NVS的运动伪影和采集成本问题，在合成质量上达到领先水平。作为新视角合成的分支，其技术可为基于3D高斯或NeRF的SLAM系统提供更鲁棒的渲染能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 842, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1626, \"height\": 955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1744, \"height\": 969, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1609, \"height\": 950, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1711, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imp2vzs4f8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1709, \"height\": 1023, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-imp2vzs4f8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1704, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imp2vzs4f8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imp2vzs4f8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 821, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imp2vzs4f8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 818, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imp2vzs4f8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 730, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imp2vzs4f8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 814, \"height\": 656, \"label\": \"Table\"}]"
motivation: 多曝光HDR-NVS存在运动伪影和高采集成本，而单曝光LDR图像无法同时捕捉亮部和暗部。
method: 提出Mono-HDR-3D，包含亮度补偿模块和高动态重建模块，仅用单曝光LDR图像训练。
result: 在HDR-NVS基准上取得最优结果，消除了运动伪影并降低了采集要求。
conclusion: 简化了HDR场景重建流程，对实时SLAM中的高质量渲染有启示意义。
---

## Abstract
High Dynamic Range Novel View Synthesis (HDR-NVS) aims to establish a 3D scene HDR model from Low Dynamic Range (LDR) imagery. Typically, multiple-exposure LDR images are employed to capture a wider range of brightness levels in a scene, as a single LDR image cannot represent both the brightest and darkest regions simultaneously. While effective, this multiple-exposure HDR-NVS approach has significant limitations, including susceptibility to motion artifacts (e.g., ghosting and blurring), high capture and storage costs.
To overcome these challenges, we introduce, for the first time, the  single-exposure HDR-NVS problem, where only single exposure LDR images are available during training. We further introduce a novel approach, Mono-HDR-3D, featuring two dedicated modules formulated by the LDR image formation principles, one for converting LDR colors to HDR counterparts, and the other for transforming HDR images to LDR format so that unsupervised learning is enabled in a closed loop. Designed as a meta-algorithm, our approach can be seamlessly integrated with existing NVS models. Extensive experiments show that Mono-HDR-3D significantly outperforms previous methods.
Source code is released at https://github.com/prinasi/Mono-HDR-3D.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- 现有高动态范围新视角合成（HDR‑NVS）方法大多依赖**同一场景的多曝光 LDR 图像**，以覆盖从暗部到亮部的完整亮度范围。
- 多曝光方式存在明显缺陷：
  - 易产生**运动伪影**（重影、模糊），尤其是在动态场景或长曝光下。
  - 需要**精确的多曝光对齐**，计算成本高。
  - **采集和存储成本高**，在快速变化的环境或移动设备上不实用。
- 本文首次提出**单曝光 HDR‑NVS 问题**：仅使用单一曝光时间下的 LDR 多视图图像进行训练，生成任意新视角的 HDR 图像。
- 单曝光设置下，单张 LDR 图像常出现过曝或欠曝，信息严重不足，因此任务更具挑战性。
- 该研究旨在降低数据获取门槛，同时消除多曝光方法的固有缺陷，使 HDR 新视角合成更易部署。

## 2. 论文提出的方法论

### 2.1 整体框架：Mono‑HDR‑3D

- 作为**元算法**，可与现有 3D 场景表示模型（如 NeRF、3DGS）无缝集成。
- 核心思路：首先从单曝光 LDR 多视图图像训练一个 **LDR 3D 场景模型**，然后通过相机成像原理驱动的颜色转换模块将其提升为 HDR 模型，并引入闭环设计以在缺乏 HDR 真值时也能优化 HDR 特征。

### 2.2 关键模块

#### （a）L2H‑CC（LDR‑to‑HDR Color Converter）

- 模拟相机成像过程的逆过程，将 LDR 颜色映射到 HDR 颜色：
  
  \(c_{hi} = f_{l2h}(c_{li})\)

- 结构设计遵循相机成像公式的逆向推导（式 6），包含三个部分：
  - 线性层 + ReLU 做特征转换。
  - 三个子模块（分别对应 **S(·)** 修正项、**X(·)** 缩放因子、**Y(·)** 噪声校正）均由 MLP 实现，激活函数与物理约束一致（ReLU 保证非负输出，噪声部分无激活）。
  - 残差连接以稳定训练并保留细节。

#### （b）H2L‑CC（HDR‑to‑LDR Color Converter）

- 模拟相机成像的 **LDR 形成过程**（式 5），将 HDR 图像转换回 LDR 图像：
  
  \(I_l = f_{h2l}(I_h)\)

- 结构包含两个子模块：
  - **D(·)** 线性缩放（ReLU 激活）。
  - **B(·)** 偏移与校正（Tanh 激活，符合物理意义）。
- 该闭环设计使得即使仅提供 LDR 训练图像，也能通过 LDR 重建损失间接优化 HDR 模型。

### 2.3 损失函数与优化

- 总损失：
  
  \(L = L_{ldr} + \alpha L_{hdr} + \beta L_{h2l}\)

- 具体化到不同基座模型：
  - **Mono‑HDR‑GS**：LDR 损失为 L1 + D‑SSIM，HDR 损失为 μ‑law 域内的 L2 损失。
  - **Mono‑HDR‑NeRF**：均使用 MSE 损失。

## 3. 实验设计

### 3.1 数据集与场景

- **合成数据集**：8 个由 Blender 创建的合成场景。
- **真实数据集**：4 个真实拍摄场景。
- 每场景包含 **5 种不同曝光时间**（\(t_1\)‑\(t_5\)）下拍摄的 35 张图像。
- **单曝光设置**：仅选取一种曝光时间的图像用于训练和评估（实验中随机选取 \(t_1, t_3, t_5\) 之一）。
- 训练视图：18 个视角；测试视图：17 个新视角，同时输出 HDR 和 LDR 结果。

### 3.2 对比方法

- **HDR‑NeRF**（首个 HDR‑NVS 模型，基于 NeRF）。
- **HDR‑GS**（基于 3DGS 的高效 HDR‑NVS）。
- 两方法原为多曝光设计，本文将其直接应用于单曝光设置以进行公平对比。

### 3.3 评价指标

- **PSNR**、**SSIM**、**LPIPS**（感知相似度）。
- HDR 结果在 tone‑mapped 域进行评估，并定性展示使用 Photomatix Pro 映射后的效果。

## 4. 资源与算力

- 文中明确指出使用 **Adam 优化器**，并采用了与 HDR‑NeRF、HDR‑GS **相同的参数设置**。
- 对 L2H‑CC/H2L‑CC 的学习率和衰减给出了具体数值（如 5e‑4/1e‑3，衰减至 5e‑5/5e‑4）。
- **未提及** GPU 型号、数量、训练批次大小或具体训练时长。
- 考虑到其效率与原方法相当（推理速度 fps 持平），推断其计算开销并未显著增加。

## 5. 实验数量与充分性

实验设计较为全面，主要包括：

- **定量对比实验**（合成 + 真实，表格 1、2）：评估 LDR 和 HDR 新视角合成质量，与两种 SOTA 方法对比。
- **消融实验**（表格 3‑6）：
  - 模块设计对比（L2H‑CC / H2L‑CC 用普通 MLP 替代）。
  - 闭环设计作用（有无 H2L‑CC）。
  - 损失项贡献（\(L_{ldr}\)、\(L_{hdr}\)、\(L_{h2l}\) 的各种组合）。
  - 不同 LDR/HDR 数据比例下模型鲁棒性。
- **定性分析**：多个场景的可视化对比，覆盖合成与真实数据，展示过曝/欠曝区域的重建细节。
- 实验设置统一，基准方法使用官方仓库复现，保证了客观性和公平性。

## 6. 论文的主要结论与发现

- 首次定义并解决 **单曝光 HDR‑NVS** 问题。
- 提出的 **Mono‑HDR‑3D** 在合成数据上大幅优于现有方法（如 Mono‑HDR‑GS PSNR 达 38.57 dB，比 HDR‑GS 的 35.30 dB 提升 3.27 dB）。
- 闭路设计（H2L‑CC）即使有 HDR 真值也能带来微弱的性能提升，且在仅 LDR 数据时依然能训练出合理的 HDR 模型，展现数据效率优势。
- 该方法可以**无缝接入** NeRF 或 3DGS，不牺牲推理速度（fps 与基座方法持平）。
- LDR 损失和闭路损失共同增强了场景几何和光度一致性。

## 7. 优点

- **问题创新**：开拓了低成本、高鲁棒的单曝光 HDR‑NVS 研究方向。
- **物理驱动设计**：模块结构严格遵循相机成像公式，使网络学习更符合物理过程，提高了可解释性和训练稳定性。
- **通用元算法**：可集成到不同 3D 表示模型（如 NeRF、3DGS），扩展性强。
- **实验全面**：多指标、多场景、多消融，验证了各模块的有效性和鲁棒性。
- **开源代码**，利于复现和后续研究。

## 8. 不足与局限

- **训练依赖 HDR 真值**：在无 HDR 监督时，性能急剧下降（PSNR 仅约 13.5 dB），表明完全无监督的 HDR 重建仍不现实。
- **真实场景评估受限**：真实数据集缺少 HDR 真值，只能通过 LDR 结果间接评估，HDR 的实际质量无法完全验证。
- **单曝光设置仍受曝光质量影响**：若单次曝光选择不当，信息缺失严重，模型性能可能波动（实验汇总了多种曝光，但未讨论极端曝光下的退化极限）。
- **应用环境限制**：目前仅在静态场景的多视图数据上验证，对动态场景的适用性未探索。
- **计算资源未透明**：未给出实际训练时间和硬件需求，影响复现和部署前的评估。
- **感知指标与主观质量**：LPIPS 等指标虽有提升，但部分真实场景下优势不明显，用户感知的 HDR 质量可能还需要进一步人类评估佐证。

（完）
