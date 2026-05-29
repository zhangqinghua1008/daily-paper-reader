---
title: "Understanding while Exploring: Semantics-driven Active Mapping"
title_zh: 边探索边理解：语义驱动的主动建图
authors: "Liyan Chen, Huangying Zhan, Hairong Yin, Yi Xu, Philippos Mordohai"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=RkHUDvy9QR"
tags: ["query:gs-slam"]
score: 7.0
evidence: 基于3DGS的主动语义建图用于探索
tldr: ActiveSGM以3D高斯溅射地图为骨干，预测语义和几何不确定性来衡量信息量，主动选择最有益的观测视角，提升建图完整性和精度。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1287, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1313, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1083, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1304, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1168, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1398, \"height\": 871, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rkhudvy9qr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 1138, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rkhudvy9qr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rkhudvy9qr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rkhudvy9qr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rkhudvy9qr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rkhudvy9qr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 916, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rkhudvy9qr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1158, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rkhudvy9qr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1013, \"height\": 345, \"label\": \"Table\"}]"
motivation: 机器人在未知环境自主探索需要主动规划视角以高效获取完整精确的语义空间信息。
method: ActiveSGM基于3DGS建图，利用语义和几何不确定性量化评估候选观测的信息量，指导视角选择。
result: 在Replica和Matterport数据集上，主动探索策略比随机或基线方法更快获得完整准确的3D语义地图。
conclusion: 3DGS与主动语义建图结合提升了机器人探索效率和地图质量，对现实世界部署有重要意义。
---

## Abstract
Effective robotic autonomy in unknown environments demands proactive exploration and precise understanding of both geometry and semantics. In this paper, we propose ActiveSGM, an active semantic mapping framework designed to predict the informativeness of potential observations before execution. Built upon a 3D Gaussian Splatting (3DGS) mapping backbone, our approach employs semantic and geometric uncertainty quantification, coupled with a sparse semantic representation, to guide exploration. By enabling robots to strategically select the most beneficial viewpoints, ActiveSGM efficiently enhances mapping completeness, accuracy, and robustness to noisy semantic data, ultimately supporting more adaptive scene exploration. Our experiments on the Replica and Matterport3D datasets highlight the effectiveness of ActiveSGM in active semantic mapping tasks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- 在未知环境中，机器人需要主动选择观测视角以高效构建既准确又语义丰富的三维地图，而现有方法多被动接受固定轨迹或只关注几何重建。
- 本文目标：提出 **ActiveSGM**，首次在 3D 高斯泼溅（3DGS）基础上实现主动语义建图，使得机器人能够在探索过程中边理解场景边规划最优视角，用更少的观测获得更完整、准确的语义地图。

## 2. 方法论
**整体框架**  
ActiveSGM 将观测、建图和规划统一为闭环系统：在每一步，由深度相机 RGB‑D 帧结合预训练分割模型生成语义预测，更新语义高斯地图；同时维护探索地图（占有栅格），根据几何覆盖与语义不确定性评价候选视角，选出最优下一视点，由路径规划器执行。

**核心组件**  
- **语义高斯地图（Semantic Gaussian Mapping）**  
  以 SplaTAM 为 SLAM 骨干，采用各向同性高斯体，优化颜色、位置、半径和透明度。  
  - 使用 OneFormer 作为语义观测来源，输出每个像素的类别概率分布。
  - **稀疏语义表示**：每个高斯体仅保留概率最高的 top‑k 个类别索引和概率值，大幅降低存储和渲染开销（Replica 102 类场景下渲染加速约 20 倍）。
  - 语义渲染同颜色/深度一样通过 alpha 混合实现，但仅对保留的 top‑k 类别计算。
  - 语义损失：结合 Hellinger 距离与余弦相似度，并利用熵掩膜滤除低置信度的监督，仅反向传播到语义属性，防止干扰几何和颜色优化。
  - **关键帧选择**：局部关键帧（高三维重叠）+ 全局关键帧（低渲染质量、低语义熵且未知标签少），以 50‑50 比例混合，缓解过拟合并覆盖欠观测区域。

- **探索规划**  
  候选视角从新占用的体素中采样，评价准则同时考虑几何和语义不确定性：
  - **几何探索准则** \(I_v^{\text{geo}}\)：渲染当前地图在候选视角的剪影，计算零值像素数目，归一化后作为几何信息量。
  - **语义探索准则** \(I_v^{\text{seman}}\)：渲染语义概率图并计算每个像素熵的总和，归一化后作为语义不确定性。
  - **距离正则化**：引入候选视角与当前相机位置的 L2 距离的 softmax 惩罚，鼓励就近探索。
  - 总体得分：\((1 - \sigma(l_v)) \cdot (I_v^{\text{geo}} \cdot I_v^{\text{seman}})\)。
  - 采用“先粗后细”策略：粗阶段用较大采样步长和较少方向快速广域评估，细阶段加大密度和多个高度平面，剔除冗余视角。

## 3. 实验设计
**数据集与设置**  
- Replica（8 个场景）、ReplicaSLAM（4 个场景）、Matterport3D（5 个大型场景），使用 Habitat 模拟器生成 680×1200 分辨率的 RGB‑D。
- 语义评价：主要指标为平均 mIoU（ReplicaSLAM 按可见类别计算）、Top‑1/Top‑3 准确率、mAP、F1 分数；Matterport3D 用平均 IoU。
- 几何/颜色评价：精度（cm）、完成度（cm）、完成率（5 cm 阈值）、PSNR、SSIM、LPIPS、深度 L1。
- 所有实验假设相机位姿已知，不进行在线定位。

**对比方法**  
- 被动语义 SLAM（基于真值标签）：NIDS‑SLAM、DNS‑SLAM、SNI‑SLAM、SGS‑SLAM。
- 被动语义建图（用预测标签，禁用定位）：将 SGS‑SLAM 改造为仅建图，并配合本文的被动模式。
- 主动语义建图：SSMI、TARE、Zhang et al. 的方法（Matterport3D 上对比）。
- 几何主动建图：NARUTO、ActiveGAMER 等。

**公平性处理**  
- 所有基线都在同一设置下运行，包括预测标签的使用、仅建图模式等，确保比较对象条件对齐。
- 关键的语义表示对比：SGS‑SLAM 的彩色编码存在跨视图融合导致标签混淆，本文稀疏表示具有明显优势。

## 4. 资源与算力
- 实验服务器：2 块 NVIDIA RTX A6000 GPU，Intel i9‑10900X 20 核 CPU。
- 软件环境：Python 3.8，CUDA 11.7。
- 运行时间示例：Replica 的 room0 场景，ActiveSGM 在 1082 步探索中共耗时约 48 分钟；其中稀疏语义渲染仅需 3.1 ms（相比稠密 61 ms）。
- OneFormer 微调：每场景先用几何探索收集 500 帧，再微调 3000 步。

## 5. 实验数量与充分性
- 实验覆盖三个数据集共 17 个场景，比较了约 10 种基线，包括语义 SLAM、被动语义建图、主动语义建图、几何主动建图等。
- 消融实验：在 Replica 的 office0 和 room0 上，探讨了 top‑k 数量（5, 8, 16）和损失函数组合（Hellinger 距离、KL 散度、余弦相似度）的影响。
- 还单独分析了稀疏渲染的速度优势。
- 整体实验设计系统、对照全面，结果一致支持方法有效性，评估较为客观公平。

## 6. 主要结论与发现
- ActiveSGM 能用远少于被动方法的步数（如 Replica 上手均 777 步 vs 2000 步）达到更高的语义分割精度（mIoU 84.89% vs 被动 80.14%），并且在 Matterport3D 上大幅超过所有主动语义基线。
- 稀疏语义表示在保持精度的同时，极大降低了内存和计算开销，渲染时间缩短 20 倍。
- 基于几何覆盖和语义熵的探索准则能有效提升语义映射的完整性和准确性，且对噪声语义输入具有鲁棒性。
- 主动的几何‑语义协同建图在重建精度和完成率上也接近甚至超过纯几何主动方法。

## 7. 优点
- **首个基于 3DGS 的主动语义建图系统**，填补了该方向的空白。
- **稀疏语义表示**巧妙平衡了类别辨别力与存储/计算开销，具有实用性。
- **无需真值语义标签**，仅依赖 OneFormer 的预测即可实现高精度语义重建，更贴近真实场景。
- **探索准则设计合理**，同时考虑几何覆盖和语义不确定性，并引入距离惩罚，避免冗余运动。
- **实验扎实**，多数据集、多基线对比，且提供了健全性评估（包括仅建图模式的公平比较）。

## 8. 不足与局限
- 假设相机位姿完全已知，实际部署需额外定位模块。
- 依赖外部分割模型 OneFormer，域差异可能影响建图质量；模型更弱时效果待验证。
- 探索效率虽高，但在大型场景中仍可能因候选池管理策略导致提前终止或遗漏。
- 实验均在仿真环境中进行，缺乏真实机器人验证，无法完全反映传感器噪声和导航不确定性。
- 优化时将语义损失与几何损失解耦，虽能稳定训练，但可能限制了联合优化的潜在增益。

（完）
