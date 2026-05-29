---
title: Enhancing Visual Localization with Cross-Domain Image Generation
title_zh: 利用跨域图像生成增强视觉定位
authors: "Yuanze Wang, Yichao Yan, Shiming Song, Songchang Jin, Yilan Huang, Xingdong Sheng, Dianxi Shi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ruj5ILBUuK"
tags: ["query:gs-slam"]
score: 9.0
evidence: 利用跨域3DGS增强视觉定位以实现绝对相机位姿跟踪
tldr: 针对视觉定位方法在跨域场景中表现受限的问题，本文利用跨域3D高斯泼溅精确建模光度变化，并结合文本引导图像编辑生成多样化数据，增强视觉定位模型。实验表明该方法有效提升了绝对相机位姿预测的准确性和鲁棒性。将3DGS引入定位任务，为相机跟踪提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 740, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1766, \"height\": 1164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 813, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1422, \"height\": 1234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ruj5ilbuuk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 1033, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 119, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 538, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 886, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ruj5ilbuuk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 889, \"height\": 183, \"label\": \"Table\"}]"
motivation: 现有方法聚焦单相机图像和有限外观变化，难以应对真实跨域场景和长尾分布。
method: 构建跨域3DGS建模光度变化，使用文本引导图像编辑增强数据多样性，训练视觉定位模型。
result: 生成的跨域数据显著提升了视觉定位方法的性能，特别是在复杂场景下。
conclusion: 跨域3DGS和文本编辑能有效增强视觉定位，为SLAM中的相机跟踪提供了可迁移的技术。
---

## Abstract
Visual localization aims to predict the absolute camera pose for a single query image. However, predominant methods focus on single-camera images and scenes with limited appearance variations, limiting their applicability to cross-domain scenes commonly encountered in real-world applications. Furthermore, the long-tail distribution of cross-domain datasets poses additional challenges for visual localization. In this work, we propose a novel cross-domain data generation method to enhance visual localization methods. To achieve this, we first construct a cross-domain 3DGS to accurately model photometric variations and mitigate the interference of dynamic objects in large-scale scenes. We introduce a text-guided image editing model to enhance data diversity for addressing the long-tail distribution problem and design an effective fine-tuning strategy for it. Then, we develop an anchor-based method to generate high-quality datasets for visual localization. Finally, we introduce positional attention to address data ambiguities in cross-camera images. Extensive experiments show that our method achieves state-of-the-art accuracy, outperforming existing cross-domain visual localization methods by an average of 59\% across all domains. Project page: https://yzwang-sjtu.github.io/CDG-Loc.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化深度总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前先进的视觉定位方法（用于估计查询图像的绝对相机位姿）大多局限于**单域**场景，即仅处理单一相机类型（如针孔相机）和有限的外观变化（如恒定光照）。这导致它们难以应对真实世界中常见的**跨域**挑战。
*   **具体挑战**：
    1.  **跨相机差异**：不同相机（针孔、鱼眼、360°等）因畸变和视场角不同，导致图像间存在巨大差异。
    2.  **外观剧烈变化**：场景在不同时间（如白天/夜晚）、光照条件下，其光度（外观）会发生巨大变化。
    3.  **长尾分布问题**：真实数据集往往呈现长尾分布，例如白天（主要域）数据充足，而夜晚（次要域）数据极其稀疏。
    4.  **动态物体干扰**：场景中的动态物体会破坏多视图一致性，影响场景重建的准确性。
*   **整体含义**：本文旨在通过提出一种新的**跨域数据生成方法**来增强视觉定位的性能，尤其是针对绝对位姿回归（APR）方法。其核心思想是利用生成的多样化、跨域、跨相机的训练数据，来解决上述真实世界中的视觉定位难题。

### 2. 论文提出的方法论

论文提出了一套完整的数据生成与模型训练流程，其核心思想是通过改造3D高斯泼溅（3DGS）并结合图像编辑模型，为视觉定位任务生成高质量、多样化的训练数据。

*   **核心技术1：跨域3D高斯泼溅（Cross-Domain 3DGS）**
    *   **目标**：在大规模场景中，精确建模光度变化并抑制动态物体干扰。
    *   **光度变化建模**：引入可学习的光度嵌入向量（Photometric Embeddings），对图像的光度直方图进行编码。这些嵌入与锚点高斯特征（基于Scaffold-GS）相结合，输入多层感知机（MLP）预测高斯属性，从而建模整个场景的光度变化。
    *   **动态物体抑制**：引入动态置信度（Dynamic Confidence）作为高斯属性之一，用于生成动态置信度图（M）。在训练时，对高动态置信度区域分配较低的损失权重，从而忽略动态物体。同时，引入动态光度嵌入（\(e_d\)）和动态光度项（\(h_d\)）来辅助预测和补偿光度损失。
    *   **公式表示**：静态颜色 \(c_s = MLP_s(e_s, f_{gs})\)，动态属性 \(h_d, \beta = MLP_d(e_d, f_{gs})\)。最终渲染的像素颜色 \(\hat{C}(x) = \sum_{i \in N} (c_s + h_d) \sigma_i \prod_{j=1}^{i-1} (1 - \sigma_j)\)。
    *   **两阶段训练策略**：
        1.  **第一阶段**：仅使用**主要域**（白天）图像训练，学习精确的静态场景几何和外观。
        2.  **第二阶段**：解冻几何相关参数，仅微调光度相关参数，使用**扩增后的次要域**（夜晚）图像训练。这能防止次要域图像中的幻觉噪声破坏已学好的场景几何。

*   **核心技术2：次要域数据增强**
    *   **目标**：解决次要域（如夜晚）数据稀疏的长尾分布问题。
    *   **方法**：使用文本引导的图像编辑模型（如InstructPix2Pix），将主要域图像转换为次要域图像。
    *   **微调策略**：用精心构造的数据集微调预训练编辑模型，使其生成与目标域一致的图像并减少幻觉。
        *   **时间变换数据集**：利用第一阶段3DGS渲染与稀疏次要域图像对应的主要域图像（\(I_a\)），与真实次要域图像（\(I_b\)）和编辑文本（如“make it nighttime”）配对。
        *   **场景先验数据集**：将对静态和动态主要域图像的编辑指令（如“add dynamic objects to the scene”）配对，帮助模型掌握全局场景先验，避免动态噪声。

*   **核心技术3：面向视觉定位的训练**
    *   **基于锚点的图像生成方法**：为确保生成图像与光度嵌入正确关联且分布均匀，以跨域3DGS中的光度嵌入为锚点，在其关联的位姿（\(P_a\)）周围半径为\(L\)的球形区域随机采样新位姿（\(P_g\)）和视角，并渲染图像。
    *   **在线跨相机图像生成**：充分利用360°图像的全覆盖视场，通过相机投影/反投影函数（\(\Phi_i\)）在线地将渲染的360°图像映射为其他相机域（针孔、鱼眼）的图像，以降低存储成本。
    *   **位置注意力机制（Positional Attention）**：为解决跨相机图像因畸变、视场角不同导致的**数据歧义**（相同位姿的图像特征不对齐），计算每个相机域图像坐标在全局360°图像坐标空间中的对应位置，并将其归一化后作为位置注意力图与原图像拼接，输入视觉定位网络，以引导特征对齐。

### 3. 实验设计

*   **数据集与场景**：在 **360Loc** 大规模数据集上进行实验，该数据集包含4个场景（Atrium, Concourse, Hall, Piatrium），包含动态物体和显著的昼夜光照变化。
*   **相机域**：覆盖5个相机域（360°, 针孔Pinhole, 鱼眼Fisheye1/2/3）。
*   **数据划分**：人为构建了一个**长尾分布**的映射数据集，即主要域（白天）数据充足，次要域（夜晚）数据极其稀疏（如581/10帧）。
*   **Benchmark与基线方法**：使用了当前先进的跨域视觉定位Benchmark，并与以下方法对比：
    *   **APR方法**：PoseNet (PN), MS-Transformer (MS-T)。
    *   **跨域数据增强方法**：PN-VC2, MS-T-VC2（360Loc提出的方法）。

### 4. 资源与算力

*   **GPU型号**：**1张 NVIDIA GeForce RTX 4090**。
*   **训练时长/迭代次数**：
    *   **跨域3DGS**：第一阶段训练60,000次迭代，第二阶段微调20,000次迭代；图像分辨率缩放为400×400。
    *   **图像编辑模型微调**：在512×512分辨率下微调10,000次迭代。
    *   **视觉定位模型**：在256×256分辨率下训练300轮（epochs）。
*   **总体评价**：文中明确给出了单卡RTX 4090的算力配置及关键训练迭代次数，计算资源需求相对清晰。

### 5. 实验数量与充分性

实验设计较为全面和充分，主要包括：

*   **主实验（2组×4场景×5相机域）**：分别在**主要域（白天）和次要域（夜晚）**两个大条件下，对所有4个场景和5个相机类型进行定位精度评估。对比了PoseNet、MS-T、PN-VC2、MS-T-VC2等多个基线。
*   **定性评估（多组）**：展示了跨域图像生成效果、动态物体抑制、稀疏次要域重建、与预训练模型微调效果的对比。
*   **消融实验（4组）**：分别验证了**跨域3DGS、微调策略、基于锚点的生成方法、位置注意力**的有效性。
*   **公平性**：所有基线方法均在本文构建的长尾分布数据集上复现，保证了对比的公平性。
*   **总体评价**：实验覆盖了多个域、多个场景和多个相机类型，既有定量对比又有定性展示，且包含系统性的消融实验，实验量充足，论证严谨。

### 6. 论文的主要结论与发现

*   **性能显著提升**：提出的方法在所有跨域场景和相机类型上均达到了最先进的精度，平均超越先前最佳方法MS-T-VC2 **59%**（白天提升**51%**，夜晚提升**67%**）。
*   **数据增强至关重要**：实验证明视觉定位是高度数据饥渴的，有效的跨域数据增强能极大提升性能，特别是在长尾分布的次要域上。
*   **视场角（FOV）是关键瓶颈**：定位精度与相机的视场角强相关，视场角越小（如针孔相机），性能越差。这表明在实际应用中选择广角相机至关重要。
*   **方法有效性已验证**：消融实验证实了所提出的跨域3DGS、模型微调策略、锚点生成方法以及位置注意力机制均对最终性能提升有显著贡献。

### 7. 优点

*   **系统化的解决方案**：论文提出了一套完整、新颖的流程，系统性地解决了跨域视觉定位中的数据多样性、光度不连续性、动态干扰、长尾分布和跨相机对齐等核心挑战。
*   **创新的技术结合**：巧妙地将 **3D高斯泼溅（3DGS）的优秀渲染能力**与**扩散模型的图像编辑能力**相结合，优势互补，用于生成高质量训练数据。
*   **精细的模型设计**：跨域3DGS中对光度嵌入、动态抑制模块和两阶段训练策略的设计非常精巧，有效处理了“野外”场景的复杂性问题。
*   **实验论证充分扎实**：在具有挑战性的基准数据集上进行了全面的实验，包含详尽的定量、定性结果和消融研究，论证过程令人信服。
*   **实用性考量**：提出的在线跨相机图像生成方法和位置注意力机制，充分考虑了实际部署中的存储成本和数据对齐问题。

### 8. 不足与局限

*   **对初始360°数据的依赖**：整个流程建立在拥有一个**带有位姿的360°图像映射集**的基础之上。对于无法获取此类数据的场景，该方法的直接适用性受限。
*   **场景几何变化的局限性**：论文明确指出，方法假设**场景几何结构不变**。对于发生显著几何变化（如建筑施工、大型物体移动）的真实场景，该方法会失效。
*   **计算开销**：虽然优化了流程，但整个方法包含了训练跨域3DGS、微调扩散模型和训练视觉定位器等多个阶段，其训练成本和时间可能相对较高，未被详细讨论。
*   **泛化能力验证**：实验仅在360Loc一个数据集上进行，该数据集虽具挑战性，但对其在更多样化真实世界场景（如剧烈天气变化、季节变化）中的泛化能力验证仍显不足。

（完）
