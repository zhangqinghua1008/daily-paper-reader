---
title: "Deep Gaussian from Motion: Exploring 3D Geometric Foundation Models for Gaussian Splatting"
title_zh: "Deep Gaussian from Motion: 探索三维几何基础模型用于高斯泼溅"
authors: "Yu Chen, Rolandos Alexandros Potamias, Evangelos Ververas, Jifei Song, Jiankang Deng, Gim Hee Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sl4KqWBkDq"
tags: ["query:gs-slam"]
score: 9.0
evidence: 从未定位图像训练3DGS，实现同时定位与建图
tldr: Deep Gaussian from Motion利用预训练的三维几何基础模型，从无姿态图像中训练3D高斯泼溅，联合优化相机位姿和高斯参数，实现高保真渲染与准确图像配准。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1383, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1172, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1431, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1386, \"height\": 1044, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 1044, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1440, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1431, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1447, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1446, \"height\": 1129, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1443, \"height\": 1049, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sl4kqwbkdq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1449, \"height\": 1153, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1010, \"height\": 111, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1228, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 584, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 655, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 699, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 722, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 724, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 722, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1370, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1440, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1438, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1439, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1436, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1442, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1439, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1440, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1443, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sl4kqwbkdq/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1441, \"height\": 222, \"label\": \"Table\"}]"
motivation: 传统3DGS依赖SfM获取相机位姿，限制了其应对未定位图像的能力。
method: 使用3D几何基础模型预测点图作为神经场景表示，初始化并微调3DGS，同时优化相机姿态和渲染质量。
result: 无需SfM即可从无姿态图像重建高质量3DGS，实现准确的新视角合成。
conclusion: 为3DGS在无定位图像上的应用开辟了新路径，推动了自定位重建的发展。
---

## Abstract
Neural radiance fields (NeRF) and 3D Gaussian Splatting (3DGS) are popular techniques to reconstruct and render photorealistic images. However, the prerequisite of running Structure-from-Motion (SfM) to get camera poses limits their completeness. Although previous methods can reconstruct a few unposed images, they are not applicable when images are unordered or densely captured. In this work, we propose a method to train 3DGS from unposed images. Our method leverages a pre-trained 3D geometric foundation model as the neural scene representation. Since the accuracy of the predicted pointmaps does not suffice for accurate image registration and high-fidelity image rendering, we propose to mitigate the issue by initializing and fine-tuning the pre-trained model from a seed image. The images are then progressively registered and added to the training buffer, which is used to train the model further. We also propose to refine the camera poses and pointmaps by minimizing a point-to-camera ray consistency loss across multiple views. When evaluated on diverse challenging datasets, our method outperforms state-of-the-art pose-free NeRF/3DGS methods in terms of both camera pose accuracy and novel view synthesis, and even renders higher fidelity images than 3DGS trained with COLMAP poses.

---

## 论文详细总结（自动生成）

# Deep Gaussian from Motion 论文深度分析

## 1. 核心问题与整体含义
- **研究背景**：NeRF 和 3D Gaussian Splatting (3DGS) 需要预先通过 Structure‑from‑Motion (SfM) 获取相机位姿，这一解耦流程导致位姿不准确和渲染伪影。现有无位姿方法（如 NeRF‑, BARF, Nope‑NeRF, CF‑3DGS）仅适用于短序列或前向拍摄，无法处理无序、稠密或大视角变化的图像集合。
- **研究动机**：能否仅依靠光度损失训练一个完全可微的重建网络，免去 SfM 的依赖？同时，新兴 3D 几何基模型（DUSt3R、Spann3R 等）虽为神经 SfM 带来突破，但其点图精度不足，且显存消耗大，难以直接用于高保真渲染。因此需要将几何基模型与 3DGS 联合优化，实现从无位姿图像中端到端地重建高质量辐射场。

## 2. 方法论
- **核心思想**：将预训练 3D 几何基模型（Spann3R）改造为“场景回归器”，输出全局坐标系下的稠密点图和每像素 3D 高斯原语，随后通过自监督渐进训练同时优化相机位姿和场景外观。
- **关键技术细节**：
  - **场景回归器**：在 Spann3R 基础上增加 DPT 头预测 3D 高斯参数（偏移量、协方差、不透明度、球谐系数）。输入图像对 \(I_i, I_j\)，输出点图 \(X_i, X_j\) 和高斯组 \(\mathbf{G}_i, \mathbf{G}_j\)。
  - **渐进式增量训练**（模拟增量式 SfM，但以图像对为单位，且使用光度损失）：
    1. **种子初始化**：基于 NetVLAD 全局描述符构建相似图，选取度最大的图像作为种子，固定恒等位姿，用光度损失微调回归器 500 次，使网络适应新场景。
    2. **渐进注册与位姿精化**：  
       - 粗位姿：对未注册图像与参考图像对通过回归器获得 2D‑3D 对应，用 DSAC（RANSAC+PnP）求解初始位姿 \(T_k^{\mathrm{coarse}}\)，内点数达标即加入训练缓冲。  
       - 多位姿一致性精化：用 **点‑射线一致性损失** \(\sum_{i,k} \rho(\lVert d_{i,k} \cdot \nu_{i,k} - (X_i - t_k) \rVert^2)\) 优化新注册图像的位姿和 3D 点。该损失比重投影更鲁棒，且固定早期位姿、仅优化当前批次以节省显存。  
       - 每注册一批图像，就用光度损失 \(\mathcal{L}_{\mathrm{photo}} = \sum_k \| I - \mathcal{R}(T_k^{\mathrm{refine}}, K, \{\mathbf{G}_i\}) \|_1\) 继续微调回归器。
    3. **最终优化**：所有图像注册完毕后，释放前期固定约束，对所有位姿进行一次全局一致性优化；随后用普通 3DGS 的稠密化/剪枝策略提炼细节。
  - 该流程与经典增量 SfM 的主要区别：① 从单张种子图初始化而非图像对；② 使用渲染损失而非重投影误差；③ 预测密集几何而非稀疏结构。

## 3. 实验设计
- **数据集**：LLFF（8 个前向场景）、Mip‑NeRF360（4 个 360° 场景：Bicycle, Counter, Garden, Kitchen）、Tanks‑and‑Temples（4 个场景）、Sequential Tanks‑and‑Temples（8 个视频段）、7‑Scenes（4 个室内场景）。
- **评估指标**：
  - 相机位姿精度：以 COLMAP 位姿为伪真值，计算旋转误差（度）和尺度归一化的平移误差。
  - 新视角合成：PSNR、SSIM、LPIPS。
- **对比方法**：
  - 无位姿 NeRF：NeRF‑‑, BARF, Nope‑NeRF。
  - 无位姿 3DGS：CF‑3DGS。
  - 神经重建：ACE0（MLP 场景坐标回归）、Spann3R（原始前馈）。
  - 传统基座：COLMAP + 3DGS，以及带位姿优化的 COLMAP/ACE0 + 3DGS（⋆ 版）。

## 4. 资源与算力
- **GPU 型号与显存**：训练使用 **NVIDIA 4090 GPU**，单卡，显存约 21 GB（batch size=1）。文中还提到与 VGGT、Fast3R 等的比较（VGGT 需 40 GB，Fast3R 需 33 GB，OOM 发生在 CF‑3DGS 等），凸显其显存友好性。
- **训练时长**：LLFF、7‑Scenes、Seq TnT：约 25 分钟/场景（2 个 epoch 收敛）；Mip‑NeRF360 和 T&T：约 2 小时/场景（5‑15 个 epoch）。评估过程也计入了训练时间。

## 5. 实验数量与充分性
- **主要对比实验**：
  - 相机位姿精度表（Table 2）：在 4 个数据集上对比 8 种方法。
  - 新视角合成表（Table 3）：同样 4 个数据集，对比 11 种配置（含位姿联合优化版本）。
- **消融实验**：
  - 精化步骤消融：对比 Spann3R 原始、Ours coarse、Ours refine（Table 4），表明精化大幅提升位姿精度（旋转误差从 10.2° 降至 0.17°）。
  - 最终全局优化消融：对比有无最终化步骤（Table 5），旋转/平移误差降低一半以上。
- **定性分析**：大量可视化：位姿轨迹图、新视角渲染对比（图 3–8 及附录中多张图）。
- **公平性**：所有无位姿方法与我们的方法都使用官方代码或标准流程复现，COLMAP、ACE0 等基座在相同 3DGS 框架下训练。对比包括有/无位姿优化的版本，充分说明联合优化的难度和我们的优势。
- 结论：实验覆盖了前向、360°、室内、视频段等多种场景，消融严谨，对比全面，实验设计客观且充分。

## 6. 主要结论与发现
- DeepGfM 在所有数据集上均取得最优的相机位姿精度（如 LLFF 旋转误差 0.17°，平移 0.005），大幅超越 ACE0、Spann3R 及各类无位姿 NeRF。
- 在新视角合成中，PSNR、SSIM、LPIPS 综合最佳，甚至在某些场景下 **超越 COLMAP + 3DGS** （如 Mip‑NeRF360 平均 PSNR 28.19 vs. 28.08，LPIPS 更低）。
- 渐进式增量精化和点‑射线一致性损失是成功的关键，能有效克服预训练模型点图精度不足的问题。
- 方法可处理无序图像、大视角变化和视频序列，泛化性强，且显存相比前馈大模型（VGGT）更具优势。
- 与 COLMAP 联合优化的对比表明：即使用 GT 级初始位姿，直接优化位姿对 3DGS 提升甚微甚至不稳定，而 DeepGfM 通过场景回归器获得了更准确的位姿，间接提升了渲染质量。

## 7. 优点（方法或实验亮点）
- **完全无位姿**：无需任何 SfM 预处理，从单张图像开始即可自监督重建。
- **架构无关性与模块化**：可灵活替换基模型（如 Spann3R、Fast3R 等），且渐进训练解耦了显存负载，支持在消费级 GPU（24 GB）上运行。
- **创新的位姿精化损失**：点‑射线一致性损失比传统重投影损失更鲁棒，避免了梯度发散。
- **显存管理**：增量训练只优化当前批次位姿，最终全局精化仅需一轮快速收敛，避免了 DUSt3R 式对齐导致的 OOM 问题。
- **实验扎实**：覆盖多种数据分布，对比最新方法，消融完整，并提供位姿优化联合版本的细致对比，揭示了之前方法的不足。

## 8. 不足与局限
- **依赖基模型性能**：场景回归器以 Spann3R 为骨干，其训练速度和收敛性受限于基模型；若基模型在极端域外场景失效，整体流程可能退化。
- **显存与规模**：虽然能处理数百张图像，但空间记忆模块会随场景增大显存开销，未来需整合更高效的 Transformer 变体（如 Fast3R、CUT3R）或使用 LoRA 等高效微调技术。
- **训练速度**：与 ACE0 等 MLP 方法相比，微调 Transformer 更耗时（约 2 小时/大场景），可能不适合实时应用。
- **实验偏差风险**：所有位姿精度以 COLMAP 为伪真值，但 COLMAP 自身在弱纹理或重复纹理区域可能存在误差，这种以 SfM 结果为参照的评估方式具有一定偏差。
- **应用限制**：当前主要用于后期离线重建，尚未在 SLAM 或在线系统中验证其鲁棒性；且 512 分辨率限制了最高细节保真度（虽然第二阶段稠密化能改善）。

（完）
