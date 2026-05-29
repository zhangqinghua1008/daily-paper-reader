---
title: "HoliGS: Holistic Gaussian Splatting for Embodied View Synthesis"
title_zh: "HoliGS: 面向具身体验视图合成的整体化高斯泼溅"
authors: "Xiaoyuan Wang, Yizhou Zhao, Botao Ye, Xiaojun Shan, Weijie Lyu, Lu Qi, Kelvin C.K. Chan, Yinxiao Li, Ming-Hsuan Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=V56unBiTHP"
tags: ["query:gs-slam"]
score: 4.0
evidence: 使用3D高斯泼溅从单目视频进行新视角合成
tldr: HoliGS提出一种可变形高斯泼溅框架，从长单目RGB视频中合成新视角，将场景分解为静态背景和动态物体，通过层级形变实现鲁棒的自由视角渲染。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1333, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 512, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1375, \"height\": 734, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1417, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 1218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 1215, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1450, \"height\": 1220, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 1218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v56unbithp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 1216, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 760, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 752, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1424, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1417, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1216, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v56unbithp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 1336, \"label\": \"Table\"}]"
motivation: 现有4D高斯泼溅和动态NeRF难以高效处理分钟级长视频，训练开销大。
method: 使用可逆高斯泼溅形变网络，将场景分解为静态背景与时变物体，通过全局刚性变换、骨骼驱动和非刚体形变进行层级建模。
result: 在长视频捕获的大规模动态环境重建中实现准确的新视角合成。
conclusion: 该方法为具身智能体的视觉感知提供了一种高效、可扩展的动态场景表示。
---

## Abstract
We propose HoliGS, a novel deformable Gaussian splatting framework that addresses embodied view synthesis from long monocular RGB videos. Unlike prior 4D Gaussian splatting and dynamic NeRF pipelines, which struggle with training overhead in minute-long captures, our method leverages invertible Gaussian Splatting deformation networks to reconstruct large-scale, dynamic environments accurately. Specifically, we decompose each scene into a static background plus time-varying objects, each represented by learned Gaussian primitives undergoing global rigid transformations, skeleton-driven articulation, and subtle non-rigid deformations via an invertible neural flow. This hierarchical warping strategy enables robust free-viewpoint novel-view rendering from various embodied camera trajectories by attaching Gaussians to a complete canonical foreground shape (e.g., egocentric or third-person follow), which may involve substantial viewpoint changes and interactions between multiple actors. Our experiments demonstrate that HoliGS achieves superior reconstruction quality on challenging datasets while significantly reducing both training and rendering time compared to state-of-the-art monocular deformable NeRFs. These results highlight a practical and scalable solution for EVS in real-world scenarios. The source code will be released.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：从长单目RGB视频中实现具身体验的视图合成（Embodied View Synthesis, EVS），即重建动态3D场景，使得相机可以自由跟随运动主体（如人类、动物），生成第一人称或第三人称跟随的任意新视角。
- **研究动机**：现有方法存在严重瓶颈：
  - 4D Gaussian Splatting和动态NeRF在分钟级长视频上训练开销过高，难以实用。
  - 现有可变形高斯方法通常局限于短视频或轻度非刚体运动，在具有复杂交互和重度遮挡的EVS场景中产生大量伪影。
  - 依赖外部点跟踪（如CoTracker）的方法计算开销大且对遮挡脆弱，难以泛化到任意视角。
- **整体含义**：提出一种整体化（holistic）的可变形高斯泼溅框架，能够高效、鲁棒地处理长视频中的大规模动态场景，支持极端的视角变化和实时渲染，为AR/VR、机器人等应用提供可扩展的解决方案。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将动态场景分解为**静态背景高斯**和**时变前景高斯**。对前景对象采用**层级式运动建模**，从粗到细依次捕捉全局刚体运动、骨骼驱动的关节运动以及剩余的非刚体精细形变。
- **关键技术细节**：
  - **动态场景表示**：场景 \( S(t) = \mathcal{G}(t) \cup \mathcal{H} \)，其中 \(\mathcal{H}\) 为静态背景高斯，\(\mathcal{G}(t)\) 为动态前景高斯。
  - **层级形变流程**（以逆变形为例）：
    \[
    X_t = (G_t^o)^{-1} \cdot J_t^{-1} \cdot S^{-1}(X^*, \omega_t^d)
    \]
    1. **全局刚体变换** \(G_t^o\)：轻量傅里叶MLP为每帧预测对象根相对于相机的SE(3)位姿，无需外部跟踪器。
    2. **骨骼驱动变形** \(J_t\)：利用可学习的骨骼层级（B个骨骼），通过SE(3)指数映射得到每帧骨骼位姿，用马氏距离计算蒙皮权重，采用对偶四元数混合蒙皮（DQB）融合所有骨骼变换，解释肢体、躯干等大尺度关节运动。
    3. **软变形场** \(S\)：基于RealNVP可逆神经流实现可逆的非刚体校正，处理衣物褶皱、头发飘动等细节。通过3D循环一致性损失 \(\mathcal{L}_{cyc}\) 保证稳定训练。
- **初始化策略**：先用神经SDF代理联合优化位姿、关节和软变形，获得快速收敛的形变场，再表面采样高斯点并切换到可变形高斯泼溅优化，避免从零开始的局部最小值。
- **优化目标**：包括光度一致性、深度（UniDepth）、法线、分割（SAM）、光流（RAFT）和循环损失，以及SDF的Eikonal约束。

### 3. 实验设计：使用了哪些数据集/场景，它的benchmark是什么，对比了哪些方法
- **数据集**：自采集数据集，包含11段立体相机序列（30fps），时长约0.5–1分钟（400–900帧），涉及人类与动物复杂交互的场景（如人-狗、人-猫），用左相机训练、右相机验证。
- **Benchmark指标**：
  - 视觉指标：PSNR、SSIM、LPIPS（在新视角上计算）。
  - 深度指标：在0.1米内的准确率（Acc@0.1m）和RMS深度误差（以立体深度为真值）。
- **对比方法**：HyperNeRF、D2NeRF、Total-Recon、Deformable-GS、4DGS、GS-Marbles、MoSca、Shape-of-Motion，以及部分方法的深度监督变体。还包含了短片段评估以公平对比内存受限的方法。

### 4. 资源与算力
- **GPU**：NVIDIA H20用于主训练，同时也在RTX A6000上与Total-Recon进行了等条件对比。
- **训练时长**：
  - 预训练与联合微调大约各需30分钟，整个场景（包含多个可变形对象）约2小时内收敛（约800帧）。
  - 与Total-Recon在A6000上的约12小时相比，实现了约10倍加速。
- **内存**：各预处理阶段峰值显存：深度约12GB，光流约6GB，分割约16GB，位姿估计＜1GB；主训练约10GB；而密集点跟踪基线超80GB，长视频极易OOM。

### 5. 实验数量与充分性
- **主实验**：11段序列的全量评估，包括视觉质量（表2，6项指标×11序列）和深度质量（表3，2项指标×11序列），对比了7种以上基线。
- **消融实验**：系统性移除深度监督、法线监督、骨髛变形场、软变形组件、根位姿初始化、根位姿刚性变换等，验证各组件的必要性（表4，图6）。
- **效率实验**：展示了不同模块的显存占用和墙钟时间（表5、表6），并针对长序列进行可扩展性分析。
- **公平性补充**：针对无法处理长视频的方法，增设200帧短片段评估（表8），覆盖6组序列，对比HoliGS与MoSca、Shape-of-Motion、GS-Marble。
- **评估**：实验设计全面，涵盖新视角合成与深度几何，对比方法丰富，消融充分，且考虑了公平性（短片段）、效率，结论客观。

### 6. 论文的主要结论与发现
- HoliGS在所有11个长序列的视觉和深度指标上均显著超越现有最佳方法（如Total-Recon、Deformable-GS等），重建质量更高，伪影更少。
- 层级式运动建模至关重要：骨骼变形解释了约90%的运动能量，软变形场补充细节；去掉根位姿刚性变换将直接导致优化失败。
- 几何监督（深度、法线）对保持物体间尺度一致性和边界清晰度至关重要。
- 方法在训练效率上实现约10倍加速，内存开销远小于密集点跟踪方法，可扩展到分钟级视频。
- 即使缩短到200帧窗口，HoliGS仍保持竞争力，体现了更强的时间一致性和辐射-几何一致性。

### 7. 优点：方法或实验设计上的亮点
- **层级运动分解**：将全局刚体、骨骼关节、非刚体细变分层处理，各模块专注不同频段的运动，收敛更快且效果更优。
- **可逆软变形**：采用RealNVP可逆流和循环一致性损失，确保形变场稳定且可逆，有利于长时间训练。
- **两阶段初始化**：先神经SDF代理提供良好初值，再切换到高斯泼溅，避免了高斯点易陷入局部最小的痛点。
- **全面的几何约束**：集成单目深度、光流、分割、法线等多模态2D监督，提升几何精度和时空一致性。
- **效率与可扩展性**：预处理均单次前馈且可并行，主重建成本随场景复杂度而非帧数增长，在分钟级视频上显存可控，渲染可达交互帧率。
- **实验公平性考虑**：额外提供短片段对比和等硬件条件的时间对比，增加说服力。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **初始化依赖**：泛化位姿估计（PoseNet）有时无法达到专用参数化模型（如SMPL）的解剖学精度，可能影响重建质量。
- **不连续运动处理**：方法假设光滑连续变形，对突变的运动（如突然跳跃）处理能力不足，作者建议未来集成事件相机等。
- **数据集存在偏差**：仅在自采集的11个人-动物交互视频上测试，场景多样性有限，对更复杂的日常场景、多物体交互的泛化性未验证。
- **计算需求仍较高**：虽然优于NeRF，但预处理阶段仍需要多种大型模型（SAM、UniDepth等），总预处理时间较长，且训练仍需较高端GPU。
- **缺乏错误分析**：定量结果未报告方差或置信区间，可能掩盖随机性；对于失败案例的定性分析未展开。

（完）
