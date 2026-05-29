---
title: "MaterialRefGS: Reflective Gaussian Splatting with Multi-view Consistent Material Inference"
title_zh: "MaterialRefGS: 多视图一致材质推断的反射高斯泼溅"
authors: "Wenyuan Zhang, Jimin Tang, Weiqi Zhang, Yi Fang, Yu-Shen Liu, Zhizhong Han"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=I64ZLbUP6u"
tags: ["query:gs-slam"]
score: 8.0
evidence: 反射高斯泼溅用于逼真新视角合成
tldr: 针对高斯泼溅中反射材质推断约束不足导致的照明混叠和泛化性问题，MaterialRefGS从多视图一致性出发，结合物理环境建模，强制2D高斯产生一致材质，显著提升了反射场景的渲染真实感。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 994, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 742, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1427, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 827, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1431, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i64zlbup6u/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 580, \"height\": 442, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-i64zlbup6u/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1259, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i64zlbup6u/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 726, \"height\": 224, \"label\": \"Table\"}]"
motivation: 有限环境建模下材质推断缺乏足够约束，导致照明混叠和泛化差。
method: 从多视图角度强制2D高斯产生一致材质，并结合物理环境建模。
result: 实现了更准确的反射效果，提升了渲染真实感。
conclusion: 多视图一致材质推断是学习准确反射的关键。
---

## Abstract
Modeling reflections from 2D images is essential for photorealistic rendering and novel view synthesis. Recent approaches enhance Gaussian primitives with reflection-related material attributes to enable physically based rendering (PBR) with Gaussian Splatting. However, the material inference often lacks sufficient constraints, especially under limited environment modeling, resulting in illumination aliasing and reduced generalization. In this work, we revisit the problem from a multi-view perspective and show that multi-view consistent material inference with more physically-based environment modeling is key to learning accurate reflections with Gaussian Splatting. To this end, we enforce 2D Gaussians to produce multi-view consistent material maps during deferred shading. We also track photometric variations across views to identify highly reflective regions, which serve as strong priors for reflection strength terms. To handle indirect illumination caused by inter-object occlusions, we further introduce an environment modeling strategy through ray tracing with 2DGS, enabling photorealistic rendering of indirect radiance. Experiments on widely used benchmarks show that our method faithfully recovers both illumination and geometry, achieving state-of-the-art rendering quality in novel views synthesis. Project Page: https://wen-yuan-zhang.github.io/MaterialRefGS.

---

## 论文详细总结（自动生成）

好的，以下是根据你提供的论文内容撰写的详细中文总结。

### 1. 论文的核心问题与整体含义

*   **研究背景与动机**：
    *   从2D图像中建模反射效果，对于实现照片级真实感的渲染和新视角合成至关重要。
    *   近年来的方法，如3D高斯泼溅（3DGS），通过为高斯图元赋予材质属性（如金属度、粗糙度）并结合基于物理的渲染（PBR）来表现反射。然而，这类方法面临一个核心挑战：**材质推断是一个病态问题**。
    *   由于光照与材质组合的多样性可以解释相同的像素，且3DGS的视角依赖性与学习视角无关的材质属性的目标相冲突，导致在环境建模不充分时，容易出现**光照混叠（illumination aliasing）** 和**泛化能力下降**的问题。
*   **核心问题**：
    *   在基于高斯泼溅的框架下，如何实现对反射效果精确、鲁棒的光照分解与建模。
*   **整体含义/核心思想**：
    *   论文提出，从**多视图一致性**的角度重新审视该问题，通过引入更强的几何约束和更物理的环境建模，是学习准确反射效果的关键。

### 2. 论文提出的方法论

论文提出了 **MaterialRefGS**，其核心是**多视图一致的材质推断**。该方法基于2D高斯泼溅（2DGS）框架，主要包含以下关键技术：

*   **多视图材质一致性约束 (Multi-view Material Consistency)**：
    *   **核心思想**：强制同一表面点在不同视图中投影得到的材质图（漫反射、金属度、粗糙度）保持一致。
    *   **技术细节**：借鉴多视图立体匹配的思想，在一个视图上采样图像块，利用渲染的深度和法向将其通过单应矩阵（Homography）映射到邻近视图，然后对原始块与映射块在材质图上计算MSE损失。这迫使高斯图元的材质参数在不同视角下表现出一致的物理属性。

*   **多视图一致的反射强度先验 (Reflection Strength Prior)**：
    *   **核心思想**：利用高反射表面在不同视角下呈现显著外观差异的特性，作为显式监督信号。
    *   **技术细节**：
        1.  对参考视图的一个像素块，通过单应性变换将其映射至多个邻近视图。
        2.  计算该像素块在所有视图间亮度归一化后的平均标准差，作为该像素的**反射得分**。
        3.  将各视图的反射得分反投影融合到3D空间中，通过球查询（Ball Query）等方式生成一个全局一致的**反射强度先验** \(w_{ref}\)。
        4.  利用该先验作为权重，监督渲染得到的金属度图，对高反射区域施加更强的金属度约束。

*   **基于光线追踪的环境建模 (Environment Modeling via Ray Tracing)**：
    *   **核心思想**：解决物体间遮挡导致的间接光照问题，提供更具物理意义的信号。
    *   **技术细节**：将入射辐射度分解为直接和间接部分。通过2DGS进行可微的光线追踪，从表面点沿反射方向追踪射线，确定被遮挡的情况。通过深度排序和Alpha混合（Splatting），计算出间接光照的颜色和遮挡概率 \(O(\omega_i)\)。这种方法将直接光照（从环境贴图查询）和间接光照（通过光线追踪计算）统一起来，实现了对遮挡区域的真实感渲染。

*   **优化流程**：
    *   整体优化采用分阶段策略：首先使用法向先验训练基础2DGS以保证几何稳定，然后加入PBR和环境建模，最后移除部分强先验并引入多视图一致性正则化项继续优化。总损失函数为：
         \[
        L = L_c + \lambda_{n-d}L_{n-d} + \lambda_{n}L_{n} + \lambda_{mv}L_{mv} + \lambda_{ref}L_{ref}
        \]

### 3. 实验设计

*   **使用数据集**：
    *   两个合成数据集：**ShinyBlender** 和 **GlossySynthetic**。
    *   两个真实世界数据集：**Ref-Real** 和 **Mip-NeRF 360**。
    *   这些数据集均包含具有挑战性的复杂反射表面。

*   **评估指标**：
    *   **新视角合成质量**：PSNR， SSIM， LPIPS。
    *   **几何精度**：法向量的平均角度误差（MAE）以及倒角距离（CD，用于几何重建评估）。

*   **对比方法**：
    *   **NeRF类**：Ref-NeRF， ENVIDR。
    *   **3DGS类**：3DGS， 2DGS。
    *   **反射建模GS**：GaussianShader， 3DGS-DR， Ref-Gaussian， EnvGS。
    *   对比方法涵盖了该领域最新的主流工作，对比体系完整。

### 4. 资源与算力

*   **论文中未明确提及**：提供的文本中没有关于模型训练所使用的GPU型号、数量、内存消耗或具体训练时长的详细说明。

### 5. 实验数量与充分性

*   **实验数量**：
    *   在 **4个** 不同规模和类型的数据集上进行了定量和定性评估。
    *   进行了 **多组消融实验**，系统验证了各个核心模块（多视图材质损失、反射强度先验、环境建模、法向先验）的有效性，并分析了它们对几何恢复精度的贡献。
    *   同时对光照分解结果（漫反射、金属度、粗糙度、环境贴图）进行了可视化分析。

*   **充分性与公平性分析**：
    *   **充分**：实验设计非常全面。覆盖了合成与真实场景，对比了NeRF和GS两大类最新的SOTA方法，并通过详尽的消融实验，清晰地证明了每个提出模块的作用和必要性。
    *   **客观公平**：采用通用的评估指标，对比方法均为该领域有影响力的公开模型，通过数值表格和视觉对比图直观展示了其优越性，实验比较客观公平。

### 6. 论文的主要结论与发现

*   **主要结论**：MaterialRefGS 通过多视图一致的材质推断和基于光线追踪的环境建模，成功地解决了高斯泼溅中反射建模的材质推断病态和照明混叠问题。
*   **核心发现**：
    *   **多视图一致性约束**是提升光照分解效果、避免视角过拟合的关键。
    *   基于光度变化的**反射强度先验**能为材质学习提供有效且明确的引导。
    *   可微的2DGS**光线追踪**能有效补偿间接光照，提升被遮挡区域的渲染真实感。
    *   该方法在多个基准数据集上均取得了最优的新视角合成效果，证明了其强大的性能和通用性。

### 7. 优点

*   **方法创新性**：提出了一种新颖的多视角约束框架来解决高斯泼溅中的反射建模问题，思路清晰。
*   **物理可解释性**：结合了基于物理的渲染、多视图几何与光线追踪，使得模型更加符合物理规律，分解出的材质和光照更具解释性。
*   **性能优异**：在合成和真实场景的多个benchmark上全面超越现有方法，实现了SOTA的渲染质量和几何精度。
*   **分析充分**：通过详尽的消融实验和分解可视化，深入剖析了各模块的作用，增强了论文的说服力。

### 8. 不足与局限

*   **计算效率未明示**：如多视图一致性约束、光线追踪等模块引入的计算开销未被讨论，其实时性或实际部署效率存疑。
*   **对训练数据的依赖**：反射强度先验的计算依赖于拍摄的相机轨迹和光度变化，对于无纹理或视角变化小的区域可能失效或效果不佳。
*   **复杂场景的极限未知**：虽然在Mip-NeRF 360上表现较好，但对于更广阔、光照条件更不受控、具有极强多次反射（如镜子间相互反射）的复杂室内/室外场景，其性能和健壮性有待进一步检验。
*   **与逆渲染的差异**：论文明确指出该方法并非为标准的逆渲染任务设计（漫反射部分由高斯直接预测），因此可能不适用于需要精确材质拆分和重光照任务的应用场景。

（完）
