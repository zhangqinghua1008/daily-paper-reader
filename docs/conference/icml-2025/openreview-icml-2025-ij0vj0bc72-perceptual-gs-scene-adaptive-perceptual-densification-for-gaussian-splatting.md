---
title: "Perceptual-GS: Scene-adaptive Perceptual Densification for Gaussian Splatting"
title_zh: "Perceptual-GS: 场景自适应的感知稠密化高斯泼溅"
authors: "Hongbi Zhou, Zhangkai Ni"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ij0vj0BC72"
tags: ["query:gs-slam"]
score: 10.0
evidence: 基于感知敏感度的自适应高斯原语稠密化用于新视角合成。
tldr: Perceptual-GS针对3D高斯泼溅在新视角合成中难以平衡重建质量与效率的问题，提出一种场景自适应感知稠密化方法。受人类感知启发，该方法通过建模视觉敏感度来约束高斯原语数量，实现感知敏感度自适应的分布优化，从而在保持高重建质量的同时减少原语数量，提升了效率。实验表明，该方法在多种场景下均能取得竞争力的表现。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 790, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 841, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1764, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 1000, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1755, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1762, \"height\": 1075, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1778, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1776, \"height\": 1008, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1776, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1307, \"height\": 892, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1785, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1716, \"height\": 1735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ij0vj0bc72/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1758, \"height\": 343, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 807, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1706, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 873, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 736, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1706, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1772, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 619, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 775, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 589, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1015, \"height\": 549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 776, \"height\": 707, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1764, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1723, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1723, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1754, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1720, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1718, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1323, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1435, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1433, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1445, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1439, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1439, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1687, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1687, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1659, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1736, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1628, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1673, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1369, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1368, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1355, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1382, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1351, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1358, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1053, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1045, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ij0vj0bc72/table-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1037, \"height\": 261, \"label\": \"Table\"}]"
motivation: 现有3D高斯泼溅方法难以根据场景特性自适应优化高斯原语分布，导致质量与效率难以平衡。
method: 提出感知感知的表示方法，通过建模人类视觉敏感度约束高斯原语数量，并开发感知敏感度自适应的分布策略。
result: 在多个场景中实现了与最先进方法相当或更优的重建质量，同时使用更少的高斯原语。
conclusion: 通过引入感知敏感度，有效指导高斯泼溅的稠密化过程，提升了新视角合成的效率与质量平衡。
---

## Abstract
3D Gaussian Splatting (3DGS) has emerged as a powerful technique for novel view synthesis. However, existing methods struggle to adaptively optimize the distribution of Gaussian primitives based on scene characteristics, making it challenging to balance reconstruction quality and efficiency. Inspired by human perception, we propose scene-adaptive perceptual densification for Gaussian Splatting (Perceptual-GS), a novel framework that integrates perceptual sensitivity into the 3DGS training process to address this challenge. We first introduce a perception-aware representation that models human visual sensitivity while constraining the number of Gaussian primitives. Building on this foundation, we develop a perceptual sensitivity-adaptive distribution to allocate finer Gaussian granularity to visually critical regions, enhancing reconstruction quality and robustness. Extensive evaluations on multiple datasets, including BungeeNeRF for large-scale scenes, demonstrate that Perceptual-GS achieves state-of-the-art performance in reconstruction quality, efficiency, and robustness. The code is publicly available at: https://github.com/eezkni/Perceptual-GS

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文、以Markdown形式，对论文《Perceptual-GS: Scene-adaptive Perceptual Densification for Gaussian Splatting》进行结构化、深入、客观的总结。

# 论文总结：Perceptual-GS: 场景自适应的感知稠密化高斯泼溅

## 1. 论文的核心问题与整体含义

*   **核心问题**：现有的3D高斯泼溅（3DGS）方法在重建场景时，其高斯原语（Gaussian primitives）的分布优化策略（即稠密化，Densification）难以根据场景的特定内容进行自适应调整。这导致了一个核心矛盾：在纹理简单区域可能产生大量冗余原语，而在视觉关键区域（如物体边缘、丰富纹理）原语数量不足，造成模糊，从而难以在**重建质量和计算效率**之间取得平衡。
*   **整体含义**：本文从人类视觉系统（HVS）对局部结构（如边缘）高度敏感的洞察出发，提出了一种新的训练框架 **Perceptual-GS**。其核心思想是将**感知敏感度**（Perceptual Sensitivity）显式地集成到3DGS的训练与稠密化过程中，实现“按需分配”：在视觉敏感区域分配更多、更精细的高斯原语，同时抑制不敏感区域的冗余原语增长，最终在提升感知质量（如LPIPS指标）的同时，显著减少高斯原语总数，达到当前最优的质量-效率权衡。

## 2. 论文提出的方法论

Perceptual-GS框架主要由四个核心模块构成：

*   **感知敏感度提取模块（Perceptual Sensitivity Extraction）**:
    *   **目的**: 将人类视觉对局部结构的敏感度量化为一个二值图，用于后续指导稠密化。
    *   **技术细节**: 首先使用Sobel算子计算多视角RGB图像的梯度幅值图。为解决不同区域梯度响应强度差异大导致的部分细微结构被忽略的问题，论文设计了“感知导向”的增强和“感知导向”的平滑操作。具体而言，通过设置阈值（τe）将梯度幅值图**二值化**，仅保留“是否超过感知阈值”的二元信息，再通过平均池化和阈值（τs）平滑，生成最终的感知敏感度图。这模拟了人类视觉的阈值特性和拓扑感知特性。

*   **双分支渲染（Dual-branch Rendering）**:
    *   **目的**: 将二维的感知敏感度图映射为三维高斯原语的可学习属性，并约束低感知区域的原语生成。
    *   **技术细节**: 除了原有的RGB渲染分支，新增一个**感知分支**。为每个3D高斯原语 `G_i` 增加一个可学习参数 `ϵ_i`（经Sigmoid激活到[0,1]），代表该原语所在区域的感知敏感度。感知分支使用与RGB分支相同的Alpha混合权重渲染出一张感知图 `RS_v`。训练时，RGB分支使用 L1 + D-SSIM 损失，感知分支使用二值交叉熵（BCE）损失将渲染结果与提取的感知敏感度真值 `IS_v` 对齐。总损失函数为 `L = (1 - λ_S) * L_C + λ_S * L_S`。该设计促使模型主动学习每个原语的感知等级。

*   **感知敏感度引导的稠密化（Perceptual Sensitivity-guided Densification）**:
    *   **目的**: 根据不同区域的感知敏感度，差异化地对高斯原语进行稠密化，实现“好钢用在刀刃上”。
    *   **技术细节**: 在训练预热后，根据原语学习到的敏感度参数 `ϵ_i` 将其分为三类：
        1.  **高感知原语 (`ϵ_i > τ_h`)**：代表视觉关键区域，并且已有权重约束，对它们执行稠密化（主要是**分割Split**操作）以增加细节表示能力。
        2.  **中感知原语 (`τ_l ≤ ϵ_i ≤ τ_h`)**：代表学习不充分的复杂区域，也进行稠密化以更好地捕获细节。
        3.  **低感知原语 (`ϵ_i < τ_l`)**：代表视觉不敏感区域，不进行额外的稠密化，从而抑制原语数量增长。
    *   此外，针对高感知原语在场景整体敏感度低（`β < τβ`）时，应用**克隆Clone**操作而非分割，这增强了方法对不同类型场景的适应性。整个过程还通过原语的最大视图权重 `ω_max` 进行约束，防止物体内部过密化。

*   **场景自适应的深度重初始化（Scene-adaptive Depth Reinitialization）**:
    *   **目的**: 解决在SfM初始点云稀疏的场景中，直接进行稠密化可能导致高斯原语分布不准确的问题。
    *   **技术细节**: 通过计算在预热后，属于“中感知等级”的“大尺寸”高斯原语的比例 `γ` 来判断场景点云是否稀疏。若 `γ` 超过阈值 `τγ`，则自动触发深度重初始化操作，以优化原语分布，增强鲁棒性。

*   **针对克隆操作的透明度衰减（Opacity Decline for Clone Operation）**:
    *   **目的**: 解决克隆操作中，新生原语继承原透明度导致该区域总透明度增加，从而更难被剪枝掉而产生冗余的问题。
    *   **技术细节**: 提出一个新的变换函数 `OD(·) = x^k`，旨在克隆操作后降低该空间区域的总透明度。通过求解方程 `α_hat + (1 - α_hat) * α_hat = OD(α)` 来计算克隆后两个原语的新透明度 `α_hat`，实现对小透明度原语的更强衰减，鼓励其被剪枝，同时保护高透明度的重要原语。实验选取 `k=1.2` 作为最佳平衡点。

## 3. 实验设计

*   **数据集与Benchmark**: 实验覆盖了共计**21个场景**，包括：
    *   **Mip-NeRF 360** (9个场景): 无界、大规模场景。
    *   **Tanks & Temples** (2个场景)。
    *   **Deep Blending** (2个场景)。
    *   **BungeeNeRF** (8个场景): 极端多尺度的大规模场景，用以验证鲁棒性。
*   **对比方法（Baselines）**: 选择了一系列以提升3DGS稠密化能力为目标的最新（SOTA）方法，包括：
    *   **3DGS*** (Vanilla 3DGS重训版)
    *   **Pixel-GS***
    *   **Mini-Splatting-D**
    *   **Taming-3DGS**
*   **评价指标（Metrics）**:
    *   **质量指标**: PSNR, SSIM, LPIPS。
    *   **效率指标**: 高斯原语数量 (#G, 单位百万 M)，渲染速度 (FPS)。
    *   还通过“质量-效率平衡”图表和自创的综合指标QEB来衡量整体表现。

## 4. 资源与算力

*   **硬件配置**: 所有训练和测试均在**单张NVIDIA RTX 4090 GPU（24GB显存）** 上进行。
*   **训练时长**: 论文未明确说明具体训练时长，但指出其训练设置与原始3DGS基线方法保持一致，仅在稠密化间隔等超参数上有新调整。

## 5. 实验数量与充分性

论文进行了非常全面且充分的实验验证，具体体现在：
*   **主实验**: 在4个数据集、21个场景上与4种主流方法进行了定量与定性对比，覆盖了常规和大规模场景。
*   **消融实验**: 针对提出的**5个关键模块/设计**（感知提取增强、高/中感知导引稠密化、深度重初始化、透明度衰减）均进行了详尽的消融研究（表4），清晰展示了每个组件的贡献。
*   **超参数分析**: 对多个核心超参数（如 `λ_S`, `τ_ωh`, `τ_ωm`, 稠密化间隔等）进行了敏感性分析（表11）。
*   **可集成性验证**: 将Perceptual-GS的核心思想集成到**3DGS、Pixel-GS、CoR-GS**等**3种**不同类型的基线方法中，均取得了质量和/或效率的提升，证明了其良好的泛化能力（表5, 6, 7）。
*   **深入分析**: 还分析了在低感知区域的渲染质量（表9）、双分支渲染对原语数量的约束效果（表8）等。
*   **客观性与公平性**: 为确保公平比较，作者重训了部分基线（如3DGS*, Pixel-GS*）以获取原语数量等指标，并统一在自身设备上测试了FPS。该做法保证了对比的客观性。

## 6. 论文的主要结论与发现

*   **突破质量-效率权衡**: Perceptual-GS成功地在提升感知重建质量（特别是LPIPS和SSIM）的同时，显著减少了高斯原语的数量，实现了当前最优的质量-效率平衡。
*   **感知引导的有效性**: 将人类视觉的感知特性（对局部结构敏感）显式地建模并融入稠密化过程，是一种比单纯优化梯度指标更高效的原语分配策略。
*   **显著增强鲁棒性**: 方法能够自适应于不同类型场景，特别是在Pixel-GS等方法会显存溢出（OOM）的BungeeNeRF等大规模场景中表现稳健，证明了其优越的鲁棒性和可扩展性。
*   **方法通用性强**: 该方法的核心模块可以被轻易集成到其他3DGS变体中，并稳定提升其性能，展现了极大的应用潜力。

## 7. 优点

*   **创新性强**: 将感知质量评估的思想（SSIM的局部结构敏感性）巧妙、系统地融入3DGS的训练与稠密化核心循环中，这是方法论上的亮点。
*   **设计精巧且系统**: 从感知图提取、到3D映射（双分支渲染），再到差异化的稠密化策略（高/中/低感知），最后辅以场景自适应的初始化与后处理，整个框架逻辑连贯，环环相扣。
*   **实验极其扎实**: 实验设计全面、覆盖场景广、对比丰富，消融研究深入，并通过集成到其他模型验证了方法的可迁移性，科学性和说服力很强。
*   **实践价值高**: 证明了在相同算力下可以获得更好的视觉质量，或在同等质量下使用更少的存储和计算资源，对实际应用有指导意义。

## 8. 不足与局限

*   **超参数敏感性**: 方法引入了多个新的超参数（`τe`, `τs`, `λS`, `τh`, `τl`, `τωh`等，见表10），尽管论文做了敏感性分析，但在缺少调整指南的情况下，这可能增加新用户在“非标准”场景下的调参负担。
*   **预计算开销**: 感知敏感度图依赖在多视角图像上运行边缘检测等操作进行预计算，这为训练流程增加了一个先验步骤，但其计算开销在文中未与模型训练的整体开销做明确对比。
*   **感知模型简化**: 所采用的感知模型（基于梯度的二值化）是对人类视觉系统的高度简化和近似。这可能在面对更复杂的视觉现象（如高层次的语义理解、特定的纹理错觉）时存在局限性，难以区分人眼真正关注的内容和单纯的复杂纹理。
*   **适用场景边界**: 论文未探讨该方法在动态场景、非朗伯表面（如高反光、透明物体）或高度无纹理场景下的表现，其在这些场景下的有效性是未知的。

（完）
