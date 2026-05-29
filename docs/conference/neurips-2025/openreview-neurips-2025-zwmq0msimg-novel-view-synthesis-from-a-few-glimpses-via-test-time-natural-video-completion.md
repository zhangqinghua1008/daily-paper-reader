---
title: Novel View Synthesis from A Few Glimpses via Test-Time Natural Video Completion
title_zh: 通过测试时自然视频补全从少量瞥见进行新视角合成
authors: "Yan Xu, Yixing Wang, Stella X. Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=zwmq0MsIMG"
tags: ["query:gs-slam"]
score: 9.0
evidence: 使用视频扩散先验辅助3DGS进行稀疏视角的新视角合成
tldr: 本文从极少视图中合成新视角，先用视频扩散模型生成合理的中间视图作为伪监督，再用于训练3DGS重建欠观测区域，提升合成质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1406, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1396, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1405, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwmq0msimg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 212, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwmq0msimg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwmq0msimg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 625, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwmq0msimg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 233, \"label\": \"Table\"}]"
motivation: 稀疏视角新视角合成中，视觉间隙过大导致难以恢复完整的3D几何，传统方法效果有限。
method: 将任务重铸为测试时视频补全，利用预训练视频扩散模型生成中间伪视图，用不确定性感知机制融合到3DGS训练。
result: 方法在极稀疏输入（如3-5张）下合成的视角连贯且逼真，优于仅用3DGS或神经场的方法。
conclusion: 生成先验与3DGS结合可以处理极端稀疏数据的新视角合成，拓展了3D重建的边界。
---

## Abstract
Given just a few glimpses of a scene, can you imagine the movie playing out as the camera glides through it? That’s the lens we take on sparse-input novel view synthesis, not only as filling spatial gaps between widely spaced views, but also as completing a natural video unfolding through space. We recast the task as test-time natural video completion, using powerful priors from pretrained video diffusion models to hallucinate plausible in-between views. Our zero-shot, generation-guided framework produces pseudo views at novel camera
poses, modulated by an uncertainty-aware mechanism for spatial coherence. These synthesized frames densify supervision for 3D Gaussian Splatting (3D-GS) for scene reconstruction, especially in under-observed regions. An iterative feedback loop lets 3D geometry and 2D view synthesis inform each other, improving both the scene reconstruction and the generated views. The result is coherent, high-fidelity renderings from sparse inputs without any scene-specific training or fine-tuning. On LLFF, DTU, DL3DV, and MipNeRF-360, our method significantly outperforms strong 3D-GS baselines under extreme sparsity. Our project page is at https://decayale.github.io/project/SV2CGS.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的详细中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：研究**稀疏输入下的新视角合成**（Novel View Synthesis from Sparse Inputs）。即在仅有少数几张（如3到9张）已知相机姿态的图像时，如何生成场景在任意新视角下的逼真图像。
*   **研究动机与背景**：
    *   现有主流方法（如3D高斯泼溅3D-GS）虽然从密集视角重建效果很好，但在输入视角极度稀疏时，由于对场景的欠观测区域（under-observed regions）缺乏足够的几何和外观约束，性能会急剧下降，产生大量伪影。
    *   传统应对策略（如添加正则化项）并未从根本上解决信息缺失问题。
*   **整体含义与独特视角**：本文将稀疏视角合成重新定义为**测试时自然视频补全**（Test-time Natural Video Completion）任务。其核心洞见是将稀疏的输入视图视为一段不完整的、沿任意相机轨迹拍摄的视频，而目标是借助强大的、在海量视频数据上预训练的视频扩散模型（Video Diffusion Models）的先验知识，“脑补”出缺失的中间帧，从而为3D重建提供密集的监督信号。

### 2. 论文提出的方法论

该方法是一个零样本（zero-shot）、生成引导的迭代优化框架，无需针对特定场景进行微调。其核心流程包含四个步骤，并在迭代中相互促进。

*   **核心思想**：利用预训练视频扩散模型生成中间伪视图（pseudo views），为3D-GS训练提供额外监督，特别关注欠观测区域。
*   **关键技术细节与流程**：
    1.  **3D-GS初始化**：使用稀疏的输入图像，初步训练一个3D高斯泼溅模型。
    2.  **伪视图生成与不确定性感知调制 (Uncertainty-Aware Modulation)**:
        *   **创建引导图 (Guidance Feature Creation)**: 在需要插值的新相机位姿上，利用当前3D-GS渲染的深度图，通过反向扭曲（inverse warping）从最近的输入视图中采样像素来构建引导图像`I_guidance`。这保证了内容与结构的初始一致性。
        *   **不确定性评估 (Uncertainty Evaluation)**: 通过一个严格的前向-反向投影循环一致性检查来评估引导图的可靠性。如果某个像素颜色或几何位置在循环投影后不一致，则判定其不确定性高。不确定性`U_i(p)`的计算公式结合了几何误差（像素位置偏移）和光度误差（颜色差异）。
        *   **调制扩散过程**: 将引导图特征`g`注入到视频扩散模型的反向去噪过程中。在每个去噪时间步，通过一个优化问题，用加权项将模型自身的干净潜在预测`x_hat_0`引向引导特征`g`。**权重`γ_{t,i}`由不确定性图决定**：在不确定性高的区域，权重小，让扩散模型自由生成；在不确定性低（可靠）的区域，权重大，以保留引导图的内容。这种方式实现了自适应调制。
    3.  **3D-GS优化与高斯原语增密 (Gaussian Primitive Densification)**:
        *   **视图插值**: 将上述单视图外推流程扩展为两视图插值，通过在两个输入视图之间定义相机路径，并分别以前向和后向运行扩散过程，再将两条潜在序列进行混合，得到最终的插值伪视图。
        *   **增密操作**: 为了解决欠观测区域几何差的问题，从生成的伪视图中选取视图，利用立体视觉模型重建稠密点云，并过滤掉离群点，然后在3D-GS中点云稀疏的位置添加新高斯原语，以增强场景的完整性。
        *   **优化**: 使用原始输入视图和生成的伪视图共同监督3D-GS训练。针对生成的伪视图可能存在的时序不一致性，采用对感知差异更鲁棒的LPIPS损失函数，而非L1损失。

### 3. 实验设计

*   **数据集与场景**:
    *   **LLFF**: 8个前向面场景，仅使用**3张**输入视图（下采样8倍）。
    *   **DTU**: 物体中心化场景，遵循RegNeRF协议使用**3张**输入视图（下采样4倍），并使用掩膜评估前景。
    *   **DL3DV**: 复杂室内外场景，相机运动多样且无约束，分别在**3、6、9张**输入视图的设置下评估。
    *   **MipNeRF-360**: 大范围无界场景，使用**9张**输入视图评估。
*   **基准对比方法**:
    *   **传统/标准方法**: Mip-NeRF, 3D-GS。
    *   **NeRF类方法**: DietNeRF, RegNeRF, FreeNeRF, SparseNeRF。
    *   **3D-GS类方法**: SparseGS, FSGS, DNGaussian, IPSM。
    *   **最新的前馈式方法**: MVSplat360, ViewCrafter, 3DGS-Enhancer。
*   **评估指标**: 使用标准的PSNR、SSIM和LPIPS来量化渲染质量。

### 4. 资源与算力

*   论文**未明确提及**具体的GPU型号、数量或总训练时长。文中仅在局限性部分简要提及“迭代训练程序相对于普通3D-GS管道增加了开销”。
*   致谢部分提及使用了“NAIRR Pilot under CIS240421”提供的额外计算支持。

### 5. 实验数量与充分性

*   **实验数量多，覆盖广泛**: 在**4个不同特性**的数据集（LLFF, DTU, DL3DV, MipNeRF-360）上进行了评估，其中DL3DV数据集还测试了3种不同程度的稀疏性。
*   **对比充分且公平**: 与多达十余种主流且性能强大的基准方法进行了对比，包括NeRF和3D-GS两大技术路线，以及最新发布的前馈式方法。
*   **消融实验扎实**:
    *   对**伪视图生成模块**进行了消融，验证了扭曲引导（warping guidance）、几何不确定性、光度不确定性等组件的重要性。
    *   对**3D-GS优化模块**进行了消融，验证了高斯原语增密、点云过滤策略以及LPIPS损失函数的有效性。
    *   实验设计全面，能够有力地支撑论文的结论。

### 6. 论文的主要结论与发现

*   提出的零样本、生成引导框架能够显著提升极度稀疏输入下的新视角合成质量。
*   将问题重新定义为“视频补全”并引入视频扩散先验是有效的，其效果优于仅使用图像扩散先验或传统正则化方法。
*   不确定性感知调制机制是实现可靠、可控的伪视图生成的关键，能有效避免扩散模型引入的伪影。
*   高斯原语增密模块对于改善欠观测区域的几何重建至关重要。
*   在多个数据集和稀疏设置下，本方法均取得了最优性能，例如在DL3DV的9视角设置下，PSNR比第二名的FSGS高出**超过2.5 dB**。

### 7. 优点

*   **视角新颖**: 将稀疏视角合成与视频补全相结合，为利用大规模视频模型的先验知识开辟了新途径。
*   **框架设计精妙**: 3D-GS与视频扩散模型通过不确定性感知调制形成了有效的迭代反馈闭环，相互促进。
*   **零样本与泛化性强**: 无需昂贵的场景特定微调，可即插即用于多种预训练视频扩散模型，在不同类型场景的数据集上均表现出色。
*   **实验严谨**: 对比方法全面，消融实验细致，充分证明了各模块的有效性和方法的整体优越性。

### 8. 不足与局限

*   **对基座模型的依赖**: 方法的性能高度依赖于预训练视频扩散模型的能力，在极端视角或复杂场景下可能受其生成伪影的影响。
*   **计算开销**: 迭代的优化和生成过程增加了计算量，相比标准3D-GS更慢。
*   **初期不稳定**: 在训练初期，不准确的3D-GS几何体（深度误差）会影响引导图和不确定性的质量，尽管这种影响会随时间减弱。
*   **无统计显著性检验**: 论文报告的结果没有包含误差线或统计显著性检验，结果的稳定性无法从数字上直接判断。
*   **对比资源细节缺失**: 未提供与其他基于扩散模型的方法（如3DGS-Enhancer）在训练时间和资源消耗上的量化对比，实用性评估略有不足。

（完）
