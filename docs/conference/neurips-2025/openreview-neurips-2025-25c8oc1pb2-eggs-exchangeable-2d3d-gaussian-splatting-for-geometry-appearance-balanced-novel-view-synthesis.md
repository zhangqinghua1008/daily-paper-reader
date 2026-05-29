---
title: "EGGS: Exchangeable 2D/3D Gaussian Splatting for Geometry-Appearance Balanced Novel View Synthesis"
title_zh: "EGGS: 可交换的2D/3D高斯泼溅实现几何-外观平衡的新视角合成"
authors: "Yancheng Zhang, Guangyu Sun, Chen Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=25C8oC1pb2"
tags: ["query:gs-slam"]
score: 8.0
evidence: 提出混合2D/3D高斯表示以改进新视角合成
tldr: EGGS融合2D和3D高斯，通过混合光栅化和自适应类型交换，在保证高外观保真度的同时提升几何一致性，平衡新视角合成中的外观与几何。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1384, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 594, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 664, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 733, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 670, \"height\": 251, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1386, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 538, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1434, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1165, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-25c8oc1pb2/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1433, \"height\": 387, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1396, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 641, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 793, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 557, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1106, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 677, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 728, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-25c8oc1pb2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 758, \"height\": 280, \"label\": \"Table\"}]"
motivation: 3DGS外观保真度高但多视图几何不一致，2DGS几何一致但纹理细节差。
method: 提出可交换高斯表示，结合混合高斯光栅化与自适应类型交换，动态调整2D/3D高斯。
result: 实现了外观保真度与多视图几何精度之间的良好平衡。
conclusion: 为需要高几何精度的新视角合成应用提供了有效方案。
---

## Abstract
Novel view synthesis (NVS) is crucial in computer vision and graphics, with wide applications in AR, VR, and autonomous driving. While 3D Gaussian Splatting (3DGS) enables real-time rendering with high appearance fidelity, it suffers from multi-view inconsistencies, limiting geometric accuracy. In contrast, 2D Gaussian Splatting (2DGS) enforces multi-view consistency but compromises texture details. To address these limitations, we propose Exchangeable Gaussian Splatting (EGGS), a hybrid representation that integrates 2D and 3D Gaussians to balance appearance and geometry. To achieve this, we introduce Hybrid Gaussian Rasterization for unified rendering, Adaptive Type Exchange for dynamic adaptation between 2D and 3D Gaussians, and Frequency-Decoupled Optimization that effectively exploits the strengths of each type of Gaussian representation. Our CUDA-accelerated implementation ensures efficient training and inference. Extensive experiments demonstrate that EGGS outperforms existing methods in rendering quality, geometric accuracy, and efficiency, providing a practical solution for high-quality NVS.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 形式，对提供的论文《EGGS: Exchangeable 2D/3D Gaussian Splatting for Geometry-Appearance Balanced Novel View Synthesis》进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究背景与动机**：
    *   **新视角合成 (NVS)** 是计算机视觉和图形学的基础任务，广泛应用于AR/VR和自动驾驶等领域。
    *   **3D Gaussian Splatting (3DGS)** 实现了高外观保真度和实时渲染，但其使用的各向异性3D高斯核常导致多视图不一致，从而几何精度较差（如边缘模糊、表面不准确）。
    *   **2D Gaussian Splatting (2DGS)** 通过使用2D平面表示（surfels）强制多视图一致性，显著提升了几何精度和多视角一致性，但代价是牺牲了纹理细节和高频外观信息。
    *   **核心问题**：现有方法通常只采用单一的高斯表示（纯3D或纯2D），无法同时兼顾高质量外观和精确几何。简单地混合两者并不能保证重建质量的提升，因为它们的优势互补性未被有效利用。

*   **论文的整体含义**：
    *   本文提出了**可交换高斯泼溅 (EGGS)**，旨在通过一个统一的混合表示框架，动态地结合3D和2D高斯核的优势，以实现外观保真度和几何准确性的最佳平衡。

### 2. 论文提出的方法论

EGGS 的核心思想是让2D和3D高斯核在一个统一、可动态互转的框架中协同工作，并通过频率解耦的优化策略来发挥各自所长。
*   **核心技术一：混合高斯光栅化**
    *   **思想**：在一个可微分渲染管线中，根据高斯核的类型（`t=0`为2D，`t=1`为3D）采用不同的渲染方式。
    *   **细节**：
        *   对**3D高斯核**，使用基于仿射近似的投影（与3DGS相同）。
        *   对**2D高斯核**，使用基于光线-平面相交的投影（与2DGS相同），以保持几何精度。
        *   两种高斯的贡献和颜色通过统一的Alpha混合公式进行累积，并利用CUDA实现了高效的并行渲染。

*   **核心技术二：自适应类型交换**
    *   **思想**：在训练过程中，允许高斯核根据其几何形状的变化动态地在2D和3D类型之间切换。例如，一个变得越来越扁平的3D高斯可以变为2D高斯以更好地模拟表面；一个需要表达体积感的2D高斯可以变为3D高斯。
    *   **关键指标——有效秩**：引入有效秩 (erank) 作为判断依据。`erank` 通过高斯核的缩放向量计算，衡量其有效维度（3为各向同性体积，2为平面）。当3D高斯的erank低于阈值，或2D高斯的erank高于阈值时，触发类型交换。
    *   **稳定交换机制**：
        *   **3D转2D**：为将最小缩放轴置于z轴，通过置换矩阵对协方差矩阵进行重参数化，确保转换过程中协方差不变，弃用z轴缩放。
        *   **2D转3D**：引入一个**缩放调制**机制，通过一个基于不透明度(α)的软门控函数启用z轴缩放的梯度流，使其能逐步表达体积效果。

*   **核心技术三：频率解耦优化**
    *   **思想**：低频信号主导几何结构，高频信号对应纹理细节。这与2D高斯擅长几何、3D高斯擅长外观的特性相吻合。因此，对不同类型的核施加不对称的频率监督。
    *   **频率分解**：使用**离散小波变换 (DWT)** 将渲染图像和真实图像分解为低频 (Ill) 和高频 (Ih) 分量。
    *   **梯度冲突投影**：
        *   **问题**：若将低频和高频损失同时应用于所有高斯核，会产生冲突的梯度更新方向。
        *   **解决方案**：对于每个高斯核，计算其低频和高频梯度的内积。若为负值（表示冲突），则根据其类型执行梯度投影：
            *   对**2D高斯核**，保留低频梯度，将高频梯度投影到低频梯度的法向量上，以移除冲突部分。
            *   对**3D高斯核**，保留高频梯度，将低频梯度投影到高频梯度的法向量上。

### 3. 实验设计

*   **数据集与Benchmark**：
    *   **外观评估**：
        *   Mip-NeRF360（室内/室外场景）
        *   LLFF（前向场景）
        *   Tanks&Temples（大规模场景）
        *   **评估指标**：PSNR， SSIM， LPIPS。
    *   **几何评估**：
        *   DTU（提供真实点云用于计算Chamfer Distance）
        *   Tanks&Temples（提供真实深度图用于计算F1分数）
    *   **泛化能力评估**：
        *   LLFF（少样本, 3 views）
        *   OOD-NVS（分布外视角合成）

*   **对比方法**：
    *   **3D高斯类**：3DGS， GaussianPro， GOF， FreGS。
    *   **2D高斯类**：2DGS, TextureGS。

### 4. 资源与算力

*   **明确说明**：文中明确指出所有实验均在**单块A5000 GPU**上运行。
*   **训练时长**：
    *   所有方法均训练**30K次迭代**。
    *   在LLFF数据集上，EGGS的训练时间为**9分钟**（对比3DGS 10分钟，2DGS 11分钟，GaussianPro 20分钟），在Tanks&Temples上为**11分钟**，是参评方法中最短的。
*   **推理速度 (FPS)**：
    *   LLFF: 268 FPS (高于2DGS的187，低于3DGS的323)。
    *   EGGS在效率和精度间取得了良好平衡。

### 5. 实验数量与充分性

*   **实验数量**：从论文看，实验覆盖了约**5-6个不同规模和特性的数据集**（Mip-NeRF360， LLFF， Tanks&Temples， DTU， OOD-NVS），对比了**7个主流或最新基线方法**。
*   **充分性与公平性**：
    *   **充分性**：实验设计较为全面，不仅包含标准的外观和几何质量对比，还专门测试了少样本和OOD等挑战性场景下的模型泛化能力，并提供了消融实验、效率对比和可视化结果。
    *   **客观性与公平性**：对比方法涵盖了3DGS和2DGS两大流派的代表性工作，评估指标遵循了领域标准。所有模型均在相同迭代次数下训练。实验表明EGGS在多个指标上均取得了最优或次优效果，尤其是在平衡外观与几何方面表现突出，证据充分。

### 6. 论文的主要结论与发现

*   **性能优越**：EGGS在多个基准数据集上，在渲染质量 (PSNR， SSIM， LPIPS)、几何精度 (Chamfer Distance) 和多视角一致性（OOD PSNR）方面，全面超越或匹配了现有的纯3D或纯2D高斯方法。
*   **有效平衡**：EGGS成功结合了3DGS的高外观保真度和2DGS的高几何精度，解决了单一表示的内在权衡问题。
*   **机制有效**：消融实验证明，混合光栅化、自适应类型交换和频率解耦优化这三个核心组件均对最终性能有积极贡献，且组合使用时效果最佳。
*   **高效通用**：EGGS作为一种通用的底层表示，不仅训练速度快，而且对少样本和OOD场景也具有出色的鲁棒性和泛化能力。

### 7. 优点：方法或实验设计上的亮点

*   **方法新颖性**：首次提出一个真正可动态互转的混合2D/3D高斯表示框架，超越了此前简单叠加或针对特定任务的混合方法。
*   **巧妙的设计思路**：
    *   引入**有效秩**作为判断类型交换的定量指标，使过程有据可循，而非启发式规则。
    *   通过**梯度投影**解决多频段监督中的梯度冲突，是一种优雅且有效的策略，充分发挥了两种高斯核的特性。
*   **实验严谨全面**：评估不仅限于标准的外观和几何，还包含了挑战性的泛化场景和详细的效率分析，论证更具说服力。代码也予以公开，提高了可复现性。

### 8. 不足与局限

*   **初始化策略**：论文承认，高斯类型的初始化是随机的，未能利用稀疏点云中的语义或结构先验。这可能限制了早期优化的有效性。
*   **场景局限性**：论文也指出，该模型尚未在例如低光照、高反射或含有大量瞬态物体等极端条件下进行明确测试，其在这些挑战性场景下的鲁棒性仍有待验证。
*   **有效秩阈值的经验性**：虽然有效秩是一个有原则的指标，但其阈值的设定仍具有经验性，且在边缘情况下（如形状极端的核）可能存在非单调行为。

（完）
