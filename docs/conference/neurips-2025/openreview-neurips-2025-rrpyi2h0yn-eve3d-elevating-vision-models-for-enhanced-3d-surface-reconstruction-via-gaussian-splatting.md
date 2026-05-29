---
title: "Eve3D: Elevating Vision Models for Enhanced 3D Surface Reconstruction via Gaussian Splatting"
title_zh: Eve3D：通过高斯散点提升视觉模型以增强三维表面重建
authors: "Jiawei Zhang, Youmin Zhang, Fabio Tosi, Meiying Gu, Jiahe Li, Xiaohan Yu, Jin Zheng, Xiao Bai, Matteo Poggi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=rRPyI2h0yN"
tags: ["query:gs-slam"]
score: 9.0
evidence: 视觉先验与三维高斯散点联合优化用于新视角合成与表面重建
tldr: "该论文提出了Eve3D框架，通过联合优化预训练视觉模型提供的先验信息与三维高斯散点（3DGS）主干网络，形成相互增强的循环。同时引入基于光束法平差的优化步骤，克服了标准3DGS的局部监督限制。在Tanks & Temples等数据集上取得了领先的表面重建和新视角合成效果，展示了视觉先验与3DGS结合的巨大潜力。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1410, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1437, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 544, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1449, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rrpyi2h0yn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 982, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 728, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 709, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1418, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1410, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1401, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1145, \"height\": 112, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rrpyi2h0yn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1402, \"height\": 228, \"label\": \"Table\"}]"
motivation: 现有方法依赖不完美的视觉模型先验，未能充分联合优化先验与3DGS。
method: 联合优化视觉先验与3DGS，并引入光束法平差实现全局优化。
result: 在表面重建和新视角合成任务上达到最先进水平。
conclusion: Eve3D通过联合优化与全局约束，显著提升了三维重建质量。
---

## Abstract
We present Eve3D, a novel framework for dense 3D reconstruction based on 3D
Gaussian Splatting (3DGS). While most existing methods rely on imperfect priors
derived from pre-trained vision models, Eve3D fully leverages these priors by
jointly optimizing both them and the 3DGS backbone. This joint optimization
creates a mutually reinforcing cycle: the priors enhance the quality of 3DGS, which
in turn refines the priors, further improving the reconstruction. Additionally, Eve3D
introduces a novel optimization step based on bundle adjustment, overcoming the
limitations of the highly local supervision in standard 3DGS pipelines. Eve3D
achieves state-of-the-art results in surface reconstruction and novel view synthesis
on the Tanks & Temples, DTU, and Mip-NeRF360 datasets. while retaining fast
convergence, highlighting an unprecedented trade-off between accuracy and speed.

---

## 论文详细总结（自动生成）

好的，下面是对这篇论文的结构化深入总结。

### 1. 论文的核心问题与整体含义

*   **研究背景与动机**:
    *   基于3D高斯泼溅 (3D Gaussian Splatting, 3DGS) 的方法在三维重建和新视角合成领域取得了显著成功，但其原始框架主要关注外观建模，难以精确拟合真实的三维表面几何结构。
    *   近期工作尝试通过引入预训练视觉模型提供的几何先验（如深度、法线图）来改善重建质量，但这些先验本身存在两个关键局限：
        1.  **不完美性**：视觉模型预测的先验并非绝对准确，包含噪声。
        2.  **局部性**：受限于模型输入（如单帧、立体对），这些先验缺乏对场景的全局多视图一致性理解。
    *   将这种不完美的、局部的先验作为刚性监督信号，会限制3DGS优化，导致最终重建精度存在瓶颈。

*   **本文核心目标**:
    *   提出 **Eve3D** 框架，核心思想是**充分挖掘并利用率视觉模型先验的潜力**，而非将其视为固定监督。
    *   通过**联合优化**3DGS表示和这些先验信息，形成一个相互增强的良性循环，从而突破传统3DGS在表面重建任务上的局限性。

### 2. 论文提出的方法论

*   **核心思想**:
    *   **联合优化**：将来自预训练模型的深度先验视为可学习参数，与3D高斯泼溅场景表示一同进行梯度下降优化。这允许模型在训练过程中修正先验中的错误，同时利用修正后的更优先验来监督3DGS学习，实现“先验增强重建，重建优化先验”的协同效应。

*   **关键技术细节**:
    *   **先验计算与初始化 (Priors Computation)**:
        *   为克服单目深度估计的歧义性，利用3DGS自身的渲染能力，为每一帧输入图像通过虚拟立体基线生成一个虚拟右视图，从而构成立体图像对。
        *   将立体对输入到最先进的立体匹配基础模型 FoundationStereo 中，预测视差图，并将其转化为深度先验 `D*`。同时通过左右一致性检查生成一个初始的置信度掩码 `M_c`。
    *   **先验参数化与两阶段优化 (Parameterized Prior & Joint Optimization)**:
        *   将深度先验 `D*` 复制为可学习的参数 `D_hat`。
        *   训练分为两阶段：
            *   **预训练阶段** (`iter < T_joint`)：使用原始的 `D*` 作为固定监督，指导3DGS进行初步优化，避免早期陷入较差的局部最小值。
            *   **联合优化阶段** (`iter >= T_joint`)：切换为使用可学习参数 `D_hat` 作为监督，将其与3DGS参数共同优化。此时，3DGS重建质量的提升会驱动 `D_hat` 的更新，反之亦然。
    *   **融合先验的局部光束法平差 (Prior-Involved Local Bundle Adjustment)**:
        *   这是解决多视图一致性的关键步骤。在每个训练迭代步中，针对当前视图 `V_i`，选取其 `K` 个共视邻居视图 `V_j`，构建一个因子图。
        *   通过对可学习的深度 `D_hat` 进行优化，强制满足：
            1.  **几何一致性**: 最小化由深度导出的平面块在不同视图间的投影误差。
            2.  **光度一致性**: 最小化跨视图投影的像素块之间的光度误差。
        *   这使得深度先验不再停留在单视图，而是被全局地、多视图一致地优化，极大提升了其质量和可靠性。
    *   **置信度掩码动态更新 (Confidence Mask Update)**:
        *   随着深度先验在联合优化和局部光束法平差中被不断优化，其质量发生变化，因此初始的置信度掩码会过时。
        *   通过判断像素在多视图几何一致性检查中的表现（即光束法平差中的权重 `W_ij`）来动态更新掩码，并引入 `L_pull` 损失，鼓励低置信度区域的高斯泼溅向渲染深度靠近，从而不断修复和纳入更多可靠区域。

### 3. 实验设计

*   **使用数据集与任务**:
    *   **三维表面重建**: 使用大规模室外/室内场景数据集 **Tanks and Temples** 和物体级数据集 **DTU**。
    *   **新视角合成**: 使用无界大场景数据集 **Mip-NeRF360**。

*   **评估指标**:
    *   表面重建：在DTU上使用 **Chamfer Distance (CD)**，在Tanks and Temples上使用 **F1-Score**。
    *   新视角合成：使用 **PSNR**, **SSIM**, **LPIPS**。

*   **对比基线方法**:
    *   与两大类最先进方法进行了全面比较：
        1.  **隐式表示方法**: NeuS, Neuralangelo, NeuralWarp 等。
        2.  **显式3DGS方法**: 3DGS, 2DGS, SuGaR, GOF, PGSR, GS-Pull, GS2Mesh 等。

### 4. 资源与算力

*   **训练时长**: 论文明确报告了总训练时间，这是一个核心优势。
    *   **Eve3D (标准版)**: 在 Tanks and Temples 上**总耗时约1.2小时**（包括3DGS预训练4分钟、立体渲染和先验预测8分钟、最终训练60分钟）。
    *   **Eve3D -fast (快速版)**: 总耗时约**20分钟**（最终训练仅8分钟）。
    *   **DTU 数据集**: 总耗时**15分钟**。
*   **GPU型号与数量**: 论文正文中未明确提及所使用的GPU具体型号（如A100, V100等）和数量。这是一个信息的缺失。

### 5. 实验数量与充分性

*   **实验组数充足**: 实验设计非常全面。
    1.  **主实验**: 在三个主流且具有挑战性的数据集上（DTU, Tanks and Temples, Mip-NeRF360），同时覆盖了表面重建和新视角合成两大核心任务。
    2.  **对比方法多样**: 对比了十余种代表性基线方法，既包括计算昂贵的隐式方法，也包括主流的显式3DGS方法，对比公平。
    3.  **消融实验详尽**: 在 Tanks and Temples 数据集上设计了详细的消融实验，系统地验证了各个核心组件（单视图先验损失、联合优化、局部光束法平差、联合优化的各个子策略）的贡献。
    4.  **鲁棒性分析**: 额外分析了方法对不同的视觉先验模型（立体匹配、多视图立体等）、虚拟立体基线长度、以及局部光束法平差邻居视图数量的敏感性。
*   **客观性与公平性**: 实验严格遵循了各数据集的官方评估协议，与对比方法使用相同的数据处理流程和分辨率，确保了对比的公平性。

### 6. 论文的主要结论与发现

*   Eve3D通过联合优化先验与3DGS，成功地创建了一个相互增强的优化循环，使得最终重建质量远超将先验作为固定监督的传统范式。
*   引入的融合先验的局部光束法平差策略，显著提升了模型捕捉全局多视图几何一致性的能力，这是重建准确性的关键。
*   该方法在表面重建精度上取得了多项最佳结果，同时将训练时间压缩至小时级别甚至分钟级别，实现了前所未有的**精度与速度之间的最优平衡**。

### 7. 优点

*   **方法论创新**: “联合优化先验”的思想具有高度的原创性和洞察力，从根本上改变了使用视觉模型先验的方式，具有未来可扩展性（即模型可以持续从更好的先验中获益）。
*   **性能卓越**: 在多个基准数据集上取得了最先进的表面重建精度，同时在新视角合成任务上也表现出色。
*   **效率极高**: 相比隐式方法动辄数十小时的训练时长，Eve3D的训练效率显著提升，其快速版本在仅20分钟内就能获得极具竞争力的结果，非常实用。
*   **实验扎实**: 实验设计严谨、全面，消融研究深入，有力地支撑了论文的论点。定性结果的可视化对比非常直观。

### 8. 不足与局限

*   **对立体匹配模型的依赖**: 核心局限在于其先验质量依赖于一个强大的立体匹配基础模型。这带来了一个额外的渲染立体图像的开销。虽然论文讨论了使用其他类型模型的可能，但目前立体模型仍是性能和效率的最优解。
*   **计算资源细节缺失**: 未披露具体的GPU型号，使得精确复现其“速度”优势的门槛不够明确。
*   **动态场景的限制**: 论文明确指出，其设计不处理动态物体/主体，这限制了其在有移动目标场景中的应用。
*   **社会影响的分析全面**: 论文的社会影响部分已讨论被滥用于监控等隐私侵犯的风险，但也指出该方法不处理动态主体，因此用于处理非自愿拍摄视频的可能性较低。

（完）
