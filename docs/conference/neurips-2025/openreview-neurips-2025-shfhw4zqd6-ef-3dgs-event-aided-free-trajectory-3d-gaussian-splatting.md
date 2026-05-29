---
title: "EF-3DGS: Event-Aided Free-Trajectory 3D Gaussian Splatting"
title_zh: EF-3DGS：事件辅助的自由轨迹三维高斯散点
authors: "Bohao Liao, Wei Zhai, Zengyu Wan, Zhixin Cheng, Wenfei Yang, Yang Cao, Tianzhu Zhang, Zheng-Jun Zha"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=shFhW4zqd6"
tags: ["query:gs-slam"]
score: 9.0
evidence: 将事件相机融入三维高斯散点，实现自由轨迹场景重建与改进的姿态估计
tldr: 该论文首次将事件相机引入自由轨迹三维高斯散点（3DGS）重建中，以应对传统相机在高速场景下因观测不足和姿态估计不精确导致的失败。通过三个关键组件无缝集成事件相机优势，提高了场景重建和新视角合成的质量，同时改善了相机姿态估计，实现了类SLAM的建图与定位功能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1359, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1327, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1382, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 575, \"height\": 249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1372, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 451, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 449, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 370, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 452, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 471, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 374, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 476, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1449, \"height\": 1497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 1824, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1459, \"height\": 1791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1458, \"height\": 1425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-shfhw4zqd6/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1458, \"height\": 1424, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1310, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 742, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1417, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1174, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1454, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1159, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1452, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 594, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1219, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-shfhw4zqd6/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1389, \"height\": 236, \"label\": \"Table\"}]"
motivation: 传统相机在高速场景下观测不足且姿态估计不准确，限制了3DGS重建效果。
method: 引入事件相机并通过三个关键组件将其无缝集成到3DGS框架中。
result: 在高速场景中显著提升了重建质量和相机姿态精度。
conclusion: EF-3DGS展示了事件相机与3DGS结合在自由轨迹重建与定位中的巨大潜力。
---

## Abstract
Scene reconstruction from casually captured videos has wide real-world applications. Despite recent progress, existing methods relying on traditional cameras tend to fail in high-speed scenarios due to insufficient observations and inaccurate pose estimation. Event cameras, inspired by biological vision, record pixel-wise intensity changes asynchronously with high temporal resolution and low latency, providing valuable scene and motion information in blind inter-frame intervals. In this paper, we introduce the event cameras to aid scene construction from a casually captured video for the first time, and propose Event-Aided Free-Trajectory 3DGS, called EF-3DGS, which seamlessly integrates the advantages of event cameras into 3DGS through three key components. First, we leverage the Event Generation Model (EGM) to fuse events and frames, enabling continuous supervision between discrete frames. Second, we extract motion information through Contrast Maximization (CMax) of warped events, which calibrates camera poses and provides gradient-domain constraints for 3DGS. Third, to address the absence of color information in events, we combine photometric bundle adjustment (PBA) with a Fixed-GS training strategy that separates structure and color optimization, effectively ensuring color consistency across different views. We evaluate our method on the public Tanks and Temples benchmark and a newly collected real-world dataset, RealEv-DAVIS. Our method achieves up to 3dB higher PSNR and 40% lower Absolute Trajectory Error (ATE) compared to state-of-the-art methods under challenging high-speed scenarios.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：传统相机在高速（或低帧率）场景下进行自由轨迹视频三维重建时，面临两大挑战：① 帧间观测不足导致场景重建欠约束，易产生过拟合或平凡解；② 相邻帧位移过大，破坏了局部连续运动假设，使基于光流或特征匹配的几何先验失效，进而导致相机姿态估计严重恶化。
- **整体含义**：首次将事件相机引入自由轨迹三维高斯散点（3DGS）重建任务，提出 **EF‑3DGS** 框架。利用事件相机高时间分辨率、低延迟的异步亮度变化记录能力，为帧间盲区提供连续的场景结构和运动信息，从而在高速场景下同时提升新视角合成质量和相机轨迹估计精度，实现类 SLAM 的建图与定位。

### 2. 论文提出的方法论
- **核心思想**：基于事件相机的两个成像模型（事件生成模型 EGM 和线性事件生成模型 LEGM）提取亮度变化和运动线索，无缝集成到 3DGS 的可微分渲染与姿态优化中，并通过光度捆绑调整与分阶段训练补偿事件缺失的颜色信息。
- **关键技术细节**：
  - **事件驱动的亮度监督（EGM）**：将相邻视频帧之间的事件流划分为多个子区间，累积成高频事件帧 \(E_{i,j}\)。通过与最近帧积分重建潜在强度图像 \(I_t\)，并用其监督 3DGS 渲染，损失函数 \(L_{\text{EGM}}\) 为 \(L_1\) 与 SSIM 的加权组合。
  - **统一对比度最大化与线性事件生成模型（CMax + LEGM）**：利用 3DGS 渲染的伪深度和相邻时间戳间的相对位姿，计算光流并扭曲历史事件帧，得到片状扭曲事件图像 IPWE。通过最大化 IPWE 的方差（即对比度）优化位姿（\(L_{\text{cm}}\)）；同时基于 LEGM 的线性关系（亮度变化 ≈ 图像梯度 · 光流），建立 IPWE 与渲染图像梯度域约束 \(L_{\text{grad}}\)，最终构成 \(L_{\text{LEGM}} = \lambda_{\text{cm}} L_{\text{cm}} + \lambda_{\text{grad}} L_{\text{grad}}\)。
  - **光度捆绑调整（PBA）与分阶段训练**：引入相邻视频帧的光度重投影误差 \(L_{\text{PBA}}\)，提升跨视图颜色一致性。并采用 **Fixed‑GS** 策略，第一阶段优化全部高斯属性与位姿，第二阶段固定结构参数仅优化球谐系数，分离结构与颜色优化，缓解事件流主导优化导致的色彩失真。
- **总体损失**：\(L_{\text{event}} = L_{\text{EGM}} + L_{\text{LEGM}} + \lambda_{\text{PBA}} L_{\text{PBA}}\)，在灰度域上计算事件相关损失，在 RGB 域计算 PBA 损失。

### 3. 实验设计
- **数据集与场景**：
  - **Tanks and Temples**：选取 9 个大型室内外静态场景，原始视频经 4× 下采样，通过时间下采样（6 / 4 / 3 / 2 / 1 FPS）模拟不同高速条件，合成事件数据由 V2E 生成。
  - **RealEv‑DAVIS**：自采真实数据集，使用 DAVIS346 相机（346×260）手持拍摄 40 秒序列，分为 SLOW（保留每第 2 帧）和 FAST（保留每第 5 帧）两种速度，COLMAP 提供真值位姿。
- **Benchmark 与评估指标**：
  - 新视角合成：PSNR、SSIM、LPIPS。
  - 位姿估计：绝对轨迹误差 ATE、相对位姿误差 RPE（平移与旋转），在统一时间分辨率下评估。
- **对比方法**：
  - 纯帧方法：LocalRF、F2‑NeRF（需位姿）、Nope‑NeRF、CF‑3DGS。
  - 事件‑帧混合方法：Event‑3DGS、EvDeblurNeRF、ENeRF、以及实现的自定义基线 EvCF‑3DGS（先基于事件插帧再送入 CF‑3DGS）。

### 4. 资源与算力
- 论文附录 A.4.3 明确提到在 **RTX 2080 Ti** 上测试速度。
- 训练时长随事件子区间数量 \(N\) 变化：\(N=2\) 约 1.3 小时，\(N=3\) 约 3 小时，\(N=6\) 约 7 小时；渲染阶段可达 30+ FPS。
- 未说明使用的 GPU 数量，推测为单卡训练。

### 5. 实验数量与充分性
- **多场景、多帧率评估**：在 Tanks and Temples 的 9 个场景下，分别测试 5 种帧率，与 6 个主流/相关方法对比，出具完整的渲染与位姿指标。
- **真实数据集验证**：在 RealEv‑DAVIS 的 4 个场景（SLOW 与 FAST）上评测，涵盖室内外。
- **消融实验**：对每个组件（EGM、LEGM、PBA、Fixed‑GS）逐一剥离，验证其贡献；探讨 CMax 扭曲窗口大小 \(r\)、子区间数 \(N\) 以及各损失系数的影响。
- **鲁棒性实验**：在 Tanks and Temples 上人为引入不同程度的位姿扰动，考察方法对初始化噪声的容忍度。
- **运动模糊扩展实验**：通过 EDI 模型额外处理模糊帧，与 EvDeblurNeRF 对比，表明即便不专门针对模糊仍表现良好。
- 整体实验设计合理、对比基线丰富、消融详尽，评估维度涵盖合成与渲染、定位精度，具备客观性与公平性。

### 6. 论文的主要结论与发现
- 事件相机能够有效补偿高速场景下帧间信息的缺失，使 3DGS 在极低帧率下依然保持较高的渲染质量与轨迹精度。
- EF‑3DGS 在 Tanks and Temples 的 1 FPS 极端条件下，PSNR 相较帧方法 CF‑3DGS 提升约 3.4 dB，ATE 降低近 60%；在 RealEv‑DAVIS 的 FAST 模式中，PSNR 超过 21 dB，定位误差显著优于基线。
- 各组件协同作用：EGM 提供密集亮度监督，CMax+LEGM 挖掘运动信息并改善位姿，PBA 与 Fixed‑GS 有效解决事件无色导致的色彩失真。
- 方法对位姿初始化扰动有更强鲁棒性，证明了联合优化框架的稳定性。

### 7. 优点
- **首次融合**：首次将事件相机与 3DGS 结合用于自由轨迹重建，填补了领域空白。
- **多模态信息挖掘**：从事件流中同时提取亮度变化（EGM）与运动线索（CMax/LEGM），形成互补约束。
- **双阶段解耦设计**：通过 Fixed‑GS 分阶段训练巧妙分离几何与颜色优化，缓解无色监督主导导致的颜色漂移。
- **真实场景验证**：自采 DAVIS346 数据集，弥补了自由轨迹事件数据缺失，增强了结果的实际参考价值。
- **效率与可扩展性**：延续 3DGS 的高效渲染特性，训练时长相较传统方法可控，且可与动态场分配等策略结合。

### 8. 不足与局限
- **依赖时间有序输入**：无法直接处理无序图像集，限制了在已知位姿的有序采集场景中的应用。
- **超参数敏感性**：关键损失权重（\(\lambda_{\text{cm}}, \lambda_{\text{grad}}, \lambda_{\text{PBA}}\)）需根据场景或速度手动调整，缺乏自适应机制。
- **静态场景假设**：方法基于静态场景，未涵盖动态物体或外观变化。
- **运动模糊非显式建模**：虽通过 EDI 展示了扩展能力，但原生方法未内置去模糊模型，极端模糊可能影响性能。
- **真实数据覆盖有限**：真实数据集仅有 4 个手持序列，场景多样性一般，且相机分辨率和运动模式较单一。
- **算力要求**：事件子区间数增加时训练时间显著增长（N=6 需 7 小时），对长视频或高帧率处理可能带来效率挑战。

（完）
