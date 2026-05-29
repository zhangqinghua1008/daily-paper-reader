---
title: Dynamic Gaussian Splatting from Defocused  and Motion-blurred Monocular Videos
title_zh: 散焦与运动模糊单目视频下的动态高斯泼溅
authors: "Xuankai Zhang, Junjin Xiao, Qing Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QeJOsm3qkS"
tags: ["query:gs-slam"]
score: 7.0
evidence: 从退化单目视频实现动态高斯泼溅的新视角合成
tldr: 为解决散焦和运动模糊单目视频的动态场景重建难题，提出统一框架，通过预测网络估计逐像素可靠模糊核，结合场景与相机信息处理两种模糊，实现了高质量的动态高斯泼溅和新视角合成。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1434, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1422, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1431, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1434, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1453, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1427, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1376, \"height\": 1279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1448, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1060, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qejosm3qks/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1422, \"height\": 516, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1357, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1257, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1272, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1183, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1264, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1279, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1464, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1197, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 610, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qejosm3qks/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1397, \"height\": 301, \"label\": \"Table\"}]"
motivation: 散焦与运动模糊成因差异大，现有方法各自为政，难以同时处理。
method: 利用模糊预测网络估计逐像素模糊核，联合处理两种模糊。
result: 在退化视频上实现了高质量的动态高斯泼溅重建。
conclusion: 统一模糊处理扩展了动态高斯泼溅的适用性。
---

## Abstract
This paper presents a unified framework that allows high-quality dynamic Gaussian Splatting from both defocused and motion-blurred monocular videos. Due to the significant difference between the formation processes of defocus blur and motion blur, existing methods are tailored for either one of them, lacking the ability to simultaneously deal with both of them. Although the two can be jointly modeled as blur kernel-based convolution, the inherent difficulty in estimating accurate blur kernels greatly limits the progress in this direction. In this work, we go a step further towards this direction. Particularly, we propose to estimate per-pixel reliable blur kernels using a blur prediction network that exploits blur-related scene and camera information and is subject to a blur-aware sparsity constraint. Besides, we introduce a dynamic Gaussian densification strategy to mitigate the lack of Gaussians for incomplete regions, and boost the performance of novel view synthesis by incorporating unseen view information to constrain scene optimization. Extensive experiments show that our method outperforms the state-of-the-art methods in generating photorealistic novel view synthesis from defocused and motion-blurred monocular videos. Our code is available at https://github.com/hhhddddddd/dydeblur.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容撰写的详细中文总结。

### 1. 论文的核心问题与整体含义

- **核心问题**：该论文聚焦于**从退化的单目视频（同时包含散焦模糊和运动模糊）中重建动态3D场景并进行高质量新视角合成**的难题。
- **研究动机与背景**：
    - 动态场景的新视角合成在AR/VR等领域有重要应用，近期基于3D高斯泼溅（3DGS）的方法虽取得进展，但对模糊视频的鲁棒性差。
    - 现有处理模糊视频的方法存在显著局限：要么专门针对运动模糊（如De4DGS），要么专门处理散焦模糊（如D2RF）。**由于两种模糊的物理形成机制差异巨大，目前没有一个统一框架能同时有效处理这两种退化**。
    - 虽然两种模糊都可以统一建模为模糊核卷积，但如何从动态场景中精确估计模糊核是一个核心难点，限制了这一方向的发展。

### 2. 论文提出的方法论

论文提出一个统一框架，其核心思想是通过联合优化清晰的动态3D高斯表示和逐像素的模糊参数，从退化视频中重建出清晰的场景。

- **核心思想：统一的物理模糊建模**
    - 无论是散焦还是运动模糊，其最终效果都可被统一建模为一个清晰像素与其邻域像素的加权组合（即模糊核卷积）。公式表示为：`~B(x) = Σ ~I(x_i) * k_x(x_i)`。
    - 关键创新在于设计了一个**模糊预测网络（BP-Net）**，来预测每个像素的模糊核`k_x`和一个额外的**模糊强度`m_x`**。模糊强度用于将原始的清晰渲染像素与卷积得到的模糊像素进行混合：`真实模糊图像 = (1 - m_x) * 清晰像素 + m_x * 模糊像素`。这一设计能迫使优化过程显式地将模糊建模在网络中，避免3DGS场景本身为拟合模糊而产生非刚性畸变。

- **关键技术细节**：
    - **动态场景的3D高斯初始化与稠密化**：
        - **初始化**：借鉴Shape-of-Motion（SoM），使用运动基（SE(3) Motion Bases）建模动态高斯。在规范帧使用可见的2D跟踪点进行初始化，以获得更准确的初始几何。
        - **动态高斯稠密化**：为解决因仅用可见点初始化而可能出现的Gaussian不全问题，提出在训练稳定后，从各观测帧的动态区域（由SAM模型识别）采样像素，并通过**前景重映射（Foreground Remapping）** 将其反投影并变换到规范帧，从而实现Gaussian的补充稠密化。
    - **模糊预测网络（BP-Net）**：
        - 输入：融合了场景信息（由特征提取器从渲染的清晰图像、深度、掩膜中编码）、相机信息（相机索引的可学习嵌入向量）和像素位置编码。
        - 输出：每个像素的**模糊核`k_x`**（经过Softmax归一化）和**模糊强度`m_x`**（经过Sigmoid激活）。
        - **模糊感知稀疏性约束（Blur-aware Sparsity Constraint）**：一种关键的正则化策略。该约束认为模糊强度`m_x`越大，其对应模糊核`k_x`的中心权重应越小（即核更分散）。通过建立一个基于`m_x`的目标中心权重，并约束模糊核的实际中心权重与之相近，有效防止了在轻度模糊区域预测出不合理的分散模糊核。
    - **不可见视角约束（Unseen View Information）**：
        - 为缓解单目视频训练视角不足导致的过拟合，在训练过程中引入不可见视角信息。
        - 通过反向双线性采样，利用已知训练视角的深度、颜色和掩膜，生成两类不可见新视角——平行视角（沿相机轨迹插值）和垂直视角（沿相机运动方向扰动），并用其渲染结果施加额外监督。

### 3. 实验设计

- **数据集与评价指标**：
    - **散焦模糊数据集**：来自D2RF，包含8个动态场景，使用其左视图模糊序列训练，右视图清晰序列评估。
    - **运动模糊数据集**：来自DyBluRF，包含6个动态场景，同样采用左右视图划分。
    - **评价指标**：PSNR、SSIM、LPIPS，进行定量比较。
- **对比方法**：
    - **通用/专项重建方法**：DeformableGS (D3DGS)、Shape-of-Motion (SoM)。
    - **散焦模糊专精方法**：D2RF。
    - **运动模糊专精方法**：DyBluRF、Deblur4DGS (De4DGS)。
    - **“先去模糊后重建”策略**：将SOTA视频去模糊方法BSSTNet的去模糊结果输入给D3DGS或SoM进行重建。

### 4. 资源与算力

- **GPU型号**：单块NVIDIA RTX 3090 GPU。
- **训练时长**：对于序列分辨率为 $512 \times 288$ 的场景，完整训练约需**1小时**。
- **推理速度**：在相同分辨率下，渲染速度可达**65.143 FPS**。

### 5. 实验数量与充分性

- **主要对比实验**：
    - 在散焦模糊（D2RF，8个场景）和运动模糊（DyBluRF，6个场景）两个标准数据集上，与5种现有的SOTA方法以及2种“先去模糊后重建”的组合方法进行了全面比较。这构成了**约14组主实验**。
    - 实验包含定量指标对比和定性视觉对比，结果一致表明本文方法的优越性。
- **消融实验**：
    - 针对4个核心组件设计消融实验：模糊感知稀疏性约束、BP-Net中的跳跃连接、动态高斯稠密化策略、不可见视角约束。共**4组**。
    - 分析了不同模糊核尺寸（K值）对性能的影响。**1组（多个K值）**。
- **评估充分性与公平性**：
    - **充分性**：实验覆盖了两种截然不同的模糊类型，对比了多个SOTA方法族（动态重建、去模糊、去模糊后重建），并通过消融实验验证了各模块的有效性，结论令人信服。
    - **公平性**：对比方法均使用其公开的实现或作者提供的模型及推荐参数设置，确保了公平性。在附录中还补充了与静态场景去模糊重建方法、以及在混合模糊生成数据集上的对比，进一步增强了说服力。

### 6. 论文的主要结论与发现

- 本文成功提出了**首个能从散焦和运动模糊单目视频中重建动态3D场景的统一框架**。
- 通过联合优化动态3D高斯场和基于**BP-Net**的逐像素模糊表示，可以有效处理两种不同成因的模糊。
- **模糊强度与模糊感知稀疏性约束**的设计，是防止3DGS解剖面为拟合模糊而畸变，并得到合理模糊核的关键。
- **动态高斯稠密化**和**不可见视角约束**策略，能有效应对单目视频重建中的信息不足和过拟合问题，提升新视角合成质量。
- 该方法在生成逼真新视角方面，性能显著超越了现有处理单一模糊类型的SOTA方法，同时在计算效率上也有优势（1小时训练，65.143 FPS推理）。

### 7. 优点

- **统一框架的开创性**：首次成功将动态3DGS重建扩展到同时处理散焦和运动模糊的场景，填补了领域空白。
- **方法论设计精巧**：
    - BP-Net预测“模糊核+模糊强度”并进行混合的设计，巧妙地将模糊建模与场景优化解耦，防止场景表示本身“学到”模糊。
    - 模糊感知稀疏性约束是基于物理先验的智能正则化手段，有效约束了模糊核估计。
    - 动态高斯稠密化和不可见视角约束解决了单目动态重建中的两个固有难点（区域不完整和过拟合）。
- **性能优势显著且效率高**：在多个数据集上相比SOTA方法有大幅性能提升，同时保持了很高的计算效率（1小时训练，>65 FPS渲染），具有较好的应用潜力。
- **实验扎实全面**：在两种标准模糊数据集上进行了充分的主实验、消融研究和鲁棒性分析，验证了其有效性、泛化性和鲁棒性。

### 8. 不足与局限

- **对2D先验的依赖**：方法严重依赖现成的2D模型（如用于深度的Depth-Anything、用于掩膜的SAM、用于跟踪的TAPIR）。论文明确指出，这些2D预测（尤其是深度估计和分割）产生的错误会累积并影响最终的重建质量。
- **无法处理大尺度非刚性运动模糊**：论文在失败案例分析中诚实展示了当场景中存在剧烈、大范围的非刚性运动时，该方法与其他SOTA方法一样，难以生成无伪影的高质量结果。
- **场景需单独优化**：方法继承了vanilla 3DGS的特性，需要对每一个新场景从头开始优化，不具备泛化到新场景的即时推理能力。

（完）
