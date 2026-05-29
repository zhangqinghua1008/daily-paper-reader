---
title: "Motion Matters: Compact Gaussian Streaming for Free-Viewpoint Video Reconstruction"
title_zh: 运动至关重要：面向自由视点视频重建的紧凑高斯流传输
authors: "Jiacong Chen, Qingyu Mao, Youneng Bao, Xiandong MENG, Fanyang Meng, Ronggang Wang, Yongsheng Liang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=tDT6HF7jK5"
tags: ["query:gs-slam"]
score: 8.0
evidence: 紧凑高斯流传输用于自由视点视频的新视角合成
tldr: 针对在线自由视点视频重建中巨大存储问题，ComGS利用运动局部性和一致性，通过关键点驱动的运动表示建模对象一致的高斯点运动，仅传输关键点属性，实现了存储高效的紧凑高斯流传输，在保持质量的同时大幅降低存储需求。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 208, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1431, \"height\": 1296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tdt6hf7jk5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1433, \"height\": 1007, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 751, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 683, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 728, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1418, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1270, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1107, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 963, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1216, \"height\": 1215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tdt6hf7jk5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1151, \"height\": 166, \"label\": \"Table\"}]"
motivation: 在线FVV重建点式建模未利用运动特性，存储开销过大。
method: 利用关键点驱动运动表示，建模对象一致的高斯点运动，仅传输关键点。
result: 在保证高保真度的同时显著减少了存储需求。
conclusion: 利用运动特性实现紧凑表示，推动了在线FVV的实际应用。
---

## Abstract
3D Gaussian Splatting (3DGS) has emerged as a high-fidelity and efficient paradigm for online free-viewpoint video (FVV) reconstruction, offering viewers rapid responsiveness and immersive experiences. However, existing online methods face challenge in prohibitive storage requirements primarily due to point-wise modeling that fails to exploit the motion properties. To address this limitation, we propose a novel Compact Gaussian Streaming (ComGS) framework, leveraging the locality and consistency of motion in dynamic scene, that models object-consistent Gaussian point motion through keypoint-driven motion representation. By transmitting only the keypoint attributes, this framework provides a more storage-efficient solution. Specifically, we first identify a sparse set of motion-sensitive keypoints localized within motion regions using a viewspace gradient difference strategy. Equipped with these keypoints, we propose an adaptive motion-driven mechanism that predicts a spatial influence field for propagating keypoint motion to neighboring Gaussian points with similar motion. Moreover, ComGS adopts an error-aware correction strategy for key frame reconstruction that selectively refines erroneous regions and mitigates error accumulation without unnecessary overhead. Overall, ComGS achieves a remarkable storage reduction of over 159 × compared to 3DGStream and 14 × compared to the SOTA method QUEEN, while maintaining competitive visual fidelity and rendering speed. Project page: https://chenjiacong-1005.github.io/ComGS/.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机与背景**：
    *   在线自由视点视频（FVV）重建旨在让用户能够即时、沉浸式地观看多视角动态场景。3D Gaussian Splatting（3DGS）因其实时渲染和高保真度成为该领域的有效范式。
    *   现有在线FVV方法（如3DGStream, QUEEN）面临严峻的**存储开销过大**问题，通常每帧数据量超过20MB，严重阻碍了实时传输。
    *   存储瓶颈的根源在于**逐点建模（point-wise modeling）**，即对场景中所有高斯点进行逐帧更新，未能有效利用动态场景中运动区域集中、运动模式一致的特性。

*   **核心问题**：
    *   如何设计一种存储高效的在线FVV流式传输框架，在保持高视觉保真度和渲染速度的同时，**大幅降低带宽和存储需求**，从而真正实现实时传输。

### 2. 方法论
*   **核心思想**：
    *   提出**紧凑高斯流（Compact Gaussian Streaming, ComGS）**框架，其核心是利用动态场景中运动的**局部性**（运动只发生在局部区域）和**一致性**（同一物体上的高斯点具有相似运动）。
    *   通过少量**关键点驱动的运动表示**来建模整个场景的运动，仅传输关键点的属性，极大减少需要更新的参数量。

*   **关键技术细节与流程**：
    *   **运动敏感关键点选择（Motion-Sensitive Keypoint Selection）**：
        *   **目的**：从海量高斯点（~200K）中选出位于运动区域的少量关键点（仅为200个）。
        *   **方法**：使用**视空间梯度差策略**。计算前一帧高斯位置在前一帧图像和当前帧图像上的渲染损失梯度差异（公式4-6），将梯度差异（动态显著性分数）最大的前k个高斯点选为关键点。这确保关键点精准定位在运动区域，并自然地在复杂运动区分配更多关键点，避免静态区域的冗余建模。
    *   **自适应运动驱动机制（Adaptive Motion-Driven Mechanism）**：
        *   **目的**：让选中的关键点控制其周围具有相似运动的邻近高斯点，实现运动传播。
        *   **方法**：为每个关键点学习一个可优化的**空间影响场**（一个3D高斯椭球，由$\Sigma_i^{adap}$决定）。对于邻近高斯点，计算其到关键点的距离和在该影响场下的权重（公式7）。若权重超过阈值$\tau_{adap}$，则该邻近点被该关键点控制（公式8）。一个点可被多个关键点控制。
        *   **运动聚合**：每个关键点有可学习的平移$\Delta\mu$和旋转$\Delta q$。被控高斯点的最终运动增量由所有控制它的关键点运动按其影响权重加权求和得到（公式9）。这种设计避免了KNN方法无法区分动静态区域和运动尺度不一致的问题。
    *   **关键帧的误差感知修正（Error-Aware Correction for Key Frames）**：
        *   **目的**：关键点驱动仅能处理刚体运动，无法应对非刚体运动和新增物体，导致误差积累。修正这些误差需更新所有高斯点属性，造成极大存储开销。
        *   **方法**：每隔$s$帧设置一个关键帧（GoF），在关键帧重建时，选择性地仅修正那些存在重建错误的高斯点。
        *   **实现**：为每个高斯点学习一个可微分的掩码$m_i$，通过阈值二值化（使用Straight-Through Estimator, STE）得到一个{0,1}的硬掩码$m_i^{hard}$（公式10-11）。将掩码作用于属性残差$\Delta\theta_i^t$上，即$\theta_i^t = \theta_i^{t-1} + m_i^{hard} \Delta\theta_i^t$。训练中引入稀疏正则化损失$L_{error}$（公式13）来鼓励掩码稀疏，最终只存储和传输掩码为1的高斯点的属性残差，极大减少非必要更新。

*   **优化与压缩**：
    *   **首帧**：使用COLMAP初始化点云，按3DGS流程优化3000轮。
    *   **非关键帧**：使用L1和D-SSIM损失的组合$\mathcal{L}_{recon}$训练150轮。
    *   **关键帧**：使用总损失$\mathcal{L}_{total} = \mathcal{L}_{recon} + \lambda_{error} \mathcal{L}_{error}$训练1000轮。
    *   **压缩**：对首帧高斯属性和关键帧的残差属性进行量化和熵编码以进一步压缩。但对关键点属性不进行量化以保证精度。

### 3. 实验设计
*   **数据集与场景**：
    1.  **Neural 3D Video (N3DV)**：6个室内多视角视频序列，18-21个视点，分辨率2704x2028下采样至1/2，30FPS。使用中心视点测试。
    2.  **MeetRoom**：4个室内多视角场景，13个相机，分辨率1280x720，30FPS。使用中心参考相机测试。
    3.  **长视频评估**：使用N3DV中的`flame salmon`序列（1200帧）进行测试。
*   **Benchmark与评价指标**：
    *   渲染质量：PSNR, SSIM, LPIPS。
    *   存储效率：每帧所需存储（MB）。
    *   运行效率：训练时间（秒/帧），渲染帧率（FPS）。
*   **对比方法**：
    *   **在线方法**：StreamRF, TeTriRF, 3DGStream, QUEEN（-s/-l变体）。
    *   **离线方法**：NeRFPlayer, HyperReel, 4D-GS, SpaceTime-GS。
    *   **长视频方法**：E-NeRF, 4DGS, TGH。

### 4. 资源与算力
*   **硬件平台**：论文明确指出所有实验均在**单块NVIDIA A100 GPU**上完成。
*   **训练时长**（详见论文和附录）：
    *   首帧优化：3000轮。
    *   非关键帧重建：150轮/帧。
    *   关键帧微调：1000轮/帧。
    *   给出了在N3DV和MeetRoom数据集上的综合训练时间（秒每帧）。

### 5. 实验数量与充分性
*   **实验数量**：实验组数充足，覆盖多个方面。
    *   **主实验**：在两个标准数据集（N3DV和MeetRoom）上与7种基线方法（含在线/离线）进行了定量（表1）和定性（图3）比较。
    *   **长视频实验**：在1200帧长序列上测试了模型的可扩展性（表2）。
    *   **消融实验**：
        *   核心组件的消融（表3）：验证了运动敏感关键点选择、自适应运动驱动机制、关键帧误差感知修正的必要性。
        *   组件设计的消融：对比了自适应驱动与KNN策略（表4），验证了误差感知修正的有效性（表5）。
        *   超参数分析：研究了关键点数量（表7）、帧组长度（表8）和损失权重$\lambda_{error}$（表9）的影响。
    *   **额外实验**：提供了支持随机访问版本的性能结果（表6），并展示了每个场景的详细结果（表10，11）。
    *   **公平性与客观性**：对比基线均采用其论文结果或广泛使用的开源实现，评价指标为标准度量，实验在公认的基准数据集上进行，对比全面且公平。消融实验设计逻辑清晰，能有效证明各模块的贡献。

### 6. 主要结论与发现
*   **方法有效性**：提出的ComGS框架能够利用运动局部性和一致性，通过少量关键点极高效地表示动态场景运动。
*   **存储效率突破**：在N3DV数据集上，ComGS-s相较3DGStream存储降低**159倍**，相较QUEEN-s降低**14倍**，所需存储低至每帧**0.049 MB**，实现了真正的实时传输潜力。
*   **性能无损失**：在获得巨大存储压缩的同时，渲染质量（PSNR）和渲染速度（FPS）均保持或超越了现有在线方法，甚至在MeetRoom上超越3DGStream 0.7dB PSNR。
*   **长视频适应**：在长视频序列上同样取得有竞争力的结果，表明了框架的扩展性和鲁棒性。
*   **模块贡献**：消融实验证实了运动敏感关键点选择、自适应运动驱动和误差感知修正对最终性能都至关重要。

### 7. 优点
*   **创新性强**：首次将“运动模式共享”的思想系统地应用于在线FVV重建，用稀疏的关键点驱动大量高斯点，从根本上改变了逐点更新的范式。
*   **极致的存储效率**：通过减少静态区域冗余和消除相似运动冗余，实现了数量级上的存储压缩，解决了该领域从离线走向实时传输的核心瓶颈。
*   **机制设计精巧**：
    *   **运动敏感关键点选择**：计算效率高，且能自适应地分配关键点密度。
    *   **自适应运动驱动**：通过可学习的空间影响场，比KNN方法更精准地适应不同尺度和形状的运动。
    *   **误差感知修正**：优雅地解决了误差累积问题，仅用极小的额外存储代价维持了长序列的一致性。

### 8. 不足与局限
*   **对首帧初始化敏感**：论文指明，框架严重依赖首帧的重建质量。若首帧初始化不佳，误差会在后续帧中传播和放大，影响整体性能。
*   **输入依赖密集视点**：当前方法依赖多视角密集相机输入，这在现实应用中成本高昂。未来需扩展到稀疏视角或单目输入场景。
*   **编码阶段训练效率**：虽然渲染和传输效率高，但论文未将训练（编码）速度作为核心优化目标，现阶段训练耗时仍较长，有待提升。
*   **运动建模能力边界**：关键点驱动机制本质上主要针对刚体运动，非刚体运动和全新物体出现依赖于误差感知修正模块来补偿，修正频率（GoF大小）成为质量和存储的权衡点。

（完）
