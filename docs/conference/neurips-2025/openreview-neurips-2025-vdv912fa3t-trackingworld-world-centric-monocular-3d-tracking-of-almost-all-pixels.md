---
title: "TrackingWorld: World-centric Monocular 3D Tracking of Almost All Pixels"
title_zh: TrackingWorld：以世界为中心的单目3D几乎全像素跟踪
authors: "Jiahao Lu, Weitao Xiong, Jiacheng Deng, Peng Li, Tianyu Huang, Zhiyang Dou, Cheng Lin, Sai-Kit Yeung, Yuan Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vDV912fa3t"
tags: ["query:gs-slam"]
score: 4.0
evidence: 从单目视频中进行密集3D跟踪并估计相机运动
tldr: TrackingWorld提出以世界为中心的密集3D跟踪框架，分离相机运动和前景物体运动，实现包括新出现目标在内的全像素跟踪。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vdv912fa3t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vdv912fa3t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1425, \"height\": 761, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vdv912fa3t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vdv912fa3t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 697, \"height\": 395, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 764, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 620, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 669, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1035, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1223, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vdv912fa3t/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 174, \"label\": \"Table\"}]"
motivation: 现有单目3D跟踪难以分离相机和物体运动，且无法密集跟踪新出现的目标。
method: 提出TrackingWorld，包含跟踪上采样器和世界坐标对齐模块，实现任意点长期3D跟踪。
result: 在多个基准上，方法能够准确跟踪大量像素的3D轨迹，并处理新目标。
conclusion: 世界中心范式为单目视频的长期3D理解提供了强大的表示基础。
---

## Abstract
Monocular 3D tracking aims to capture the long-term motion of pixels in 3D space from a single monocular video and has witnessed rapid progress in recent years. However, we argue that the existing monocular 3D tracking methods still fall short in separating the camera motion from foreground dynamic motion and cannot densely track newly emerging dynamic subjects in the videos. To address these two limitations, we propose TrackingWorld, a novel pipeline for dense 3D tracking of almost all pixels within a world-centric 3D coordinate system. First, we introduce a tracking upsampler that efficiently lifts the arbitrary sparse 2D tracks into dense 2D tracks. Then, to generalize the current tracking methods to newly emerging objects, we apply the upsampler to all frames and reduce the redundancy of 2D tracks by eliminating the tracks in overlapped regions. Finally, we present an efficient optimization-based framework to back-project dense 2D tracks into world-centric 3D trajectories by estimating the camera poses and the 3D coordinates of these 2D tracks. Extensive evaluations on both synthetic and real-world datasets demonstrate that our system achieves accurate and dense 3D tracking in a world-centric coordinate frame.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：单目视频的3D跟踪旨在恢复每个像素在三维空间中的长期运动，是动态场景理解、视频编辑等下游任务的基础。现有方法（如 OmniMotion、SpatialTracker、DELTA）存在两个明显短板：
  - **相机与物体运动未解耦**：大多数方法假设相机静止，仅在相机坐标系下建模3D流，无法区分相机自身运动与场景中物体的独立运动。
  - **无法跟踪新出现的目标**：现有工作通常只对视频第一帧的稀疏像素进行跟踪，无法处理视频中间帧新出现或原来被遮挡的物体，也无法实现“所有帧的所有像素”的密集跟踪。
- **整体含义**：提出 **TrackingWorld**，首次在**世界中心坐标系**下对单目视频中几乎全部像素进行密集3D跟踪，同时显式恢复相机姿态，从而分离静态背景、动态前景以及背景中微小的动态变化。

## 2. 论文提出的方法论

TrackingWorld 的整体流程包含预处理、密集2D跟踪和2D轨迹到世界中心3D轨迹的优化反投影三大阶段。

### 2.1 预处理
- 使用现有的基础模型获取每帧的：
  - 稀疏2D轨迹（CoTrackerV3 或 DELTA 的2D部分）
  - 前景动态物体掩膜（VLM+GroundingSAM 或 SegmentAnyMotion）
  - 单目深度图（UniDepth）
- 这些预测不要求绝对精确，后续优化会进行校正。

### 2.2 密集2D跟踪（覆盖新出现物体）
- **稀疏到密集的上采样**：借用 DELTA 的 track upsampler 模块，该模块以稀疏轨迹及其特征为输入，预测一个权重矩阵，通过加权组合将稀疏轨迹 `P_sparse` 升采样为密集轨迹 `P_dense`（公式1）。该上采样器可泛化至任意2D轨迹。
- **逐帧跟踪与去冗余**：对视频的每一帧均执行2D跟踪与上采样，以捕获新出现的区域。为避免计算浪费，若某像素附近已有来自先前帧的可见轨迹，则丢弃该像素的轨迹，从而大幅降低后续优化中的轨迹冗余。

### 2.3 世界中心3D轨迹优化（解耦相机与物体运动）
- **初始化相机姿态估计**：利用粗动态掩膜选取静态区域的2D轨迹，结合单目深度将其反投影到3D，通过最小化重投影误差来优化相机姿态 `π_t`（公式2）。为提升效率，先将视频切分为多个片段并行估计姿态，再拼接。
- **动态背景细化**：由于粗掩膜通常不完整（遗漏背景中的动态物体），引入“尽可能静态”的偏移量 `O_static` 来建模背景点的微小运动。每个静态轨迹对应唯一的世界3D点 `T_static`，加上时间相关偏移 `O_static` 后得到时变3D点（公式3）。联合优化相机姿态和这些3D点，使用重投影损失（公式4）和深度一致性损失，并对偏移施加 L1 正则化以强制大部分背景点静止（公式5）。由此既能剔除背景动态点对相机估计的干扰，也能捕获背景物体的真实运动。
- **动态物体跟踪**：将前景动态区域以及背景中偏移显著的轨迹视为动态轨迹 `T_dynamic`，使用已优化的相机姿态和单目深度初始化，然后通过重投影、深度一致性、as-rigid-as-possible（ARAP）和时序平滑等损失联合优化其3D坐标。

最终输出全帧的世界中心静态3D轨迹、动态3D轨迹以及每帧相机姿态。

## 3. 实验设计

- **评测维度与基准**：
  - 相机姿态估计：在 **Sintel**、**Bonn**、**TUM-D** 三个动态数据集上对比，指标为 ATE↓、RTE↓、RRE↓。
  - 密集3D跟踪的深度精度：在相同数据集上评估相机坐标系下的深度，指标为 Abs Rel↓ 和 δ<1.25↑。
  - 稀疏3D跟踪：在 **ADT**（运动相机）和 **PStudio**（静态相机）上测试，指标为 AJ↑、APD 3D↑、OA↑。
  - 密集2D跟踪光流：在 **CVO-Clean** 和 **CVO-Final** 上评估，指标为 EPE↓、IoU↑。
- **对比方法**：
  - 姿态估计：DROID-SLAM、DPVO、COLMAP、Robust-CVD、DUSt3R、MonST3R、Align3R、Uni4D 等。
  - 深度/跟踪：DELTA（搭配多种深度先验）、CoTrackerV3+UniDepth、SpatialTracker、OmniTrackFast、RAFT、CoTracker、DOT-3D 等。

## 4. 资源与算力

- 实验使用 **一块 RTX 4090 GPU**。
- TrackingWorld 是基于优化的方法，不涉及训练，主要算力消耗在推理优化阶段。处理一段 **30 帧的视频约需 20 分钟**。
- 文中未提及大规模训练所需的算力，仅给出单视频推理时间。

## 5. 实验数量与充分性

- **主要实验** 覆盖四个任务维度（姿态、深度、稀疏3D跟踪、密集光流），涉及 5 个以上不同数据集，与超过 10 种现有方法进行了全面比较。
- **消融实验** 包括 7 项关键设计选择：是否逐帧跟踪、有无初始姿态估计、有无动态物体跟踪、是否使用内点过滤、有无背景偏移建模、有无深度一致性损失，以及不同深度估计模型和动态掩膜分割器的替换测试。每项消融均在 Sintel 数据集上报告了姿态和深度指标。
- 整体实验设计**系统且公平**，从多个角度验证了方法的有效性，并详细分析了各组件的作用和重要超参数的影响，足够支撑论文的主要声明。

## 6. 论文的主要结论与发现

- TrackingWorld 成功实现了**世界坐标系下几乎全像素的密集3D跟踪**，并且能够处理视频中新出现的物体。
- 显式分离相机姿态和物体运动显著提升了3D跟踪的精度，尤其是在相机运动的场景中。
- 提出的“动态背景细化”策略有效解决了掩膜不准确问题，进一步提高了相机姿态估计的鲁棒性。
- 与其他方法相比，TrackingWorld 在相机姿态估计、深度估计和3D跟踪一致性等核心指标上均取得领先或极具竞争力的结果。

## 7. 优点

- **方法创新**：首次将密集2D跟踪逐帧拓展，并结合世界中心优化，统一解决相机解耦和新目标跟踪两大难题。
- **技术贡献**：提出“尽可能静态”约束的背景动态建模，优雅地处理了不完美动态掩膜，并利用上采样器实现了高效密集轨迹生成。
- **评估全面**：从相机姿态、3D深度、稀疏/密集跟踪等多个角度进行验证，并配有详尽的消融实验，论证扎实。
- **工程优化**：采用分段并行姿态初始化和轨迹去冗余策略，提高了优化效率。

## 8. 不足与局限

- **计算效率**：优化过程较慢（30帧约20分钟），难以满足实时应用的需求。
- **依赖上游模型**：整体性能受限于 CoTracker、UniDepth、动态掩膜分割器等基础模型的预测质量，若上游模型在特定场景失效，可能影响最终结果。
- **局限性讨论隐藏**：论文在主文中仅说明局限性在补充材料中，未详细展开，可能存在复杂遮挡、快速旋转、极度非刚性形变等场景下的潜在失效风险。
- **无显式鲁棒性分析**：未专门讨论对深度先验误差或轨迹异常值的敏感程度。

（完）
