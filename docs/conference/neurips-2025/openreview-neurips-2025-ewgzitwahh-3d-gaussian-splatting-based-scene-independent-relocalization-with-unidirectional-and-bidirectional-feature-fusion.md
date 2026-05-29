---
title: 3D Gaussian Splatting based Scene-independent Relocalization with Unidirectional and Bidirectional Feature Fusion
title_zh: 基于三维高斯散点的场景无关重定位与单向双向特征融合
authors: "Junyi Wang, Yuze Wang, Wantong Duan, Meng Wang, Yue Qi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ewgZItWaHh"
tags: ["query:gs-slam"]
score: 8.0
evidence: 基于三维高斯散点的相机重定位网络与姿态优化
tldr: 该论文提出了一种新颖的基于三维高斯散点（3D GS）的RGB相机重定位框架。设计了两阶段流程：首先建立图像像素与三维高斯的2D-3D对应关系，然后利用3D GS渲染图像进行姿态精化。同时引入重定位网络GS-RelocNet，实现了场景无关的相机姿态估计。实验表明该方法能有效提升重定位精度，为视觉定位提供了新的可能性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ewgzitwahh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1388, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ewgzitwahh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ewgzitwahh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ewgzitwahh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ewgzitwahh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 317, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ewgzitwahh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ewgzitwahh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ewgzitwahh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 535, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ewgzitwahh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ewgzitwahh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ewgzitwahh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ewgzitwahh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 501, \"label\": \"Table\"}]"
motivation: 三维高斯散点为视觉定位提供了新的场景表示，但现有方法尚未充分挖掘其潜力。
method: 提出两阶段重定位框架：先由GS-RelocNet建立2D-3D对应，再基于渲染图像优化姿态。
result: 在场景无关的重定位任务中实现了高精度相机姿态估计。
conclusion: 该方法充分利用三维高斯散点，推动了视觉定位技术的发展。
---

## Abstract
Visual localization is a critical component across various domains.
The recent emergence of novel scene representations, such as 3D Gaussian Splatting (3D GS), introduces new opportunities for advancing localization pipelines.
In this paper, we propose a novel 3D GS-based framework for RGB based, scene-independent camera relocalization, with three main contributions.
First, we design a two-stage pipeline with fully exploiting 3D GS.
The pipeline consists of an initial stage, which utilizes 2D-3D correspondences between image pixels and 3D Gaussians,
followed by pose refinement using the rendered image by 3D GS.
Second, we introduce a 3D GS based Relocalization Network, termed GS-RelocNet, to establish correspondences for initial camera pose estimation.
Additionally, we present a refinement network that further optimizes the camera pose.
Third, we propose a unidirectional 2D-3D feature fusion module and a bidirectional image feature fusion module, integrated into GS-RelocNet and the refinement network, respectively, to enhance feature sharing across the two stages.
Experimental results on public 7 Scenes, Cambridge Landmarks, TUM RGB-D and Bonn demonstrate state-of-the-art performance.
Furthermore, the beneficial effects of the two feature fusion modules and pose refinement are also highlighted.
In summary, we believe that the proposed framework can be a novel universal localization pipeline for further research.

---

## 论文详细总结（自动生成）

## 论文总结：基于三维高斯散点的场景无关相机重定位与单向/双向特征融合

### 1. 研究背景与核心问题
- **核心问题**：现有视觉定位方法（特征匹配、绝对位姿回归、场景坐标回归）在表示场景时往往忽略纹理与光照信息，且多数3D高斯散点（3D GS）方法仅将其用于姿态精化，严重依赖初始位姿精度，缺乏鲁棒的初始位姿估计与场景无关的泛化能力。
- **研究动机**：3D GS 兼顾训练与渲染效率，为新型定位流水线带来机遇。本文旨在**首次构建一个完全利用3D GS、支持场景无关（scene‑independent）的相机重定位框架**，同时实现初始位姿估计与位姿精化，提升鲁棒性和精度。

### 2. 方法论
整体框架由两个阶段构成：
1. **初始位姿估计**：通过 GS‑RelocNet 建立输入图像像素与3D高斯的2D‑3D对应，再利用 PnP+RANSAC 求解初始相机位姿。
2. **位姿精化**：利用初始位姿通过3D GS渲染视图，然后用精化网络预测真实图像与渲染视图之间的相对位姿（残差坐标图→PnP），最终优化相机姿态。

#### 2.1 GS‑RelocNet（初始阶段）
- **输入**：单张RGB图像 + 3D GS场景模型。
- **输出**：像素与3D高斯的置信度矩阵（用于建立2D‑3D对应）。
- **结构**：
  - 图像分支：Swin Transformer 编码器。
  - 点云分支：Point Transformer V3 处理高斯的位置、透明度、协方差、球谐函数，并融合冻结的 DINOv2 特征与深度估计头。
  - 单向2D‑3D特征融合模块：将3D高斯特征单向注入图像描述子学习，不反向传播，因此模型描述子可预先计算以加速推理。
  - 置信度回归：通过位置编码、自注意力、交叉注意力及双重 softmax 预测 Ni×Ng 置信度矩阵。
- **训练损失**：真值置信度由3D高斯在图像平面投影的2D高斯分布密度定义（公式1）。

#### 2.2 精化网络（Refinement Network）
- **输入**：真实图像 + 3D GS渲染图像。
- **输出**：残差坐标图（当前帧与前一帧相机坐标系下的坐标差），再由 PnP+RANSAC 求解相对位姿 Rpr, Tpr，最终通过公式（2）得到精化后位姿。
- **结构**：多个 Swin 块，配备**双向图像特征融合模块**，通过特征相加、自注意力和残差连接反复融合真实与渲染特征。
- **损失函数**：L1 损失（坐标图） + 辅助损失（直接回归位姿的 Huber 式损失，权重α=0.3，仅作辅助指导）。

#### 2.3 关键设计细节
- 高斯选择：空间均匀采样 4096 个高斯。
- 对应点建立：置信度阈值 0.7，像素坐标由多个高斯的加权平均计算。
- 初始位姿求解：改进的 RANSAC，以内点的置信度之和判定最优解。
- 位姿扩展：精化网络训练时对微小相对位姿进行固定系数放大（位置直接缩放，旋转通过四元数‑欧拉角转换扩展），以增强学习信号。

### 3. 实验设计
#### 3.1 数据集与场景
- **室内**：7 Scenes（静态）、TUM RGB‑D（动态）、Bonn（高度动态）、ScanNet（训练用）。
- **室外**：Cambridge Landmarks、MegaDepth（训练用）。
- **场景相关**：在目标场景上训练 GS‑RelocNet；**场景无关**：在 ScanNet/MegaDepth 上训练，在 7 Scenes/Cambridge 等上测试，评估泛化性。

#### 3.2 对比方法
- APR：MS‑Transformer、DFNet、Marepo、MS‑HyperPose 等。
- SCR：ACE、GLACE、DSAC*、DUSt3R、Reloc3R、DeViLoc 等。
- NeRF 方法：CROSSFIRE、NeRFMatch、PMNet 等。
- 3D GS 方法：DFNet+GS‑CPR、ACE+GS‑CPR、STDLoc。
- 传统/语义 SLAM：ORB‑SLAM2、DynaSLAM、LC‑CRF SLAM 等。

#### 3.3 评估指标
- 中值位置误差 (cm) 和旋转误差 (°)。
- RMSE ATE（用于动态数据集）。
- 高精度召回率（误差＜5cm,5° 和 ＜2cm,2° 的比例）。
- 运行时间（FPS）。

### 4. 资源与算力
- 推理平台：单张 **Nvidia 4090 GPU**，平均每帧 **65ms（约15.4 FPS）**，具体分解：置信度回归 39ms、初始 PnP 4ms、渲染 9ms、残差图回归 8ms、精化 PnP 5ms。
- 训练：文中未明确说明训练使用的 GPU 型号/数量和总时长，仅提到使用 AdamW 优化器、学习率 2×10⁻⁴ 以及 3D GS 训练的默认配置。算力细节略有缺失。

### 5. 实验数量与充分性
- **主实验表格约 7 张**，涵盖室内外、静态动态、场景相关/无关等多种条件。
- **消融研究全面**：特征融合模块有无及位置（编码器、解码器、精化）、单向融合迭代次数、高斯采样数量、用点云替代3D高斯、渲染方式（3D模型/NeRF/3D GS）、去除球谐函数、去除 DINOv2 特征、RANSAC 策略等。
- **对比方法超过 20 种**，覆盖多个流派和最新工作，实验规模充分、对比公平。
- 还提供了轨迹可视化结果和 AR 应用效果展示。

### 6. 主要结论与发现
- 提出的框架在 **7 Scenes、Cambridge Landmarks、TUM RGB‑D、Bonn** 上均达到 **SOTA 定位精度**，尤其在场景无关设置下显著领先（如 7 Scenes 上中值误差从 2.6cm/0.98° 降至 1.4cm/0.82°）。
- **位姿精化阶段**在所有场景下均能提升精度；即使不精化，依赖 GS‑RelocNet 的结果仍具竞争力。
- **单向/双向特征融合模块**有效促进几何与纹理特征共享，消融实验证明其关键作用。
- 推理速度（15.4 FPS）优于同期 3D GS 方法（STDLoc 7 FPS，ACE+GS‑CPR 5.3 FPS），兼具高精度与高效率。
- 首次实现**基于3D高斯散点的场景无关重定位**，为通用定位流水线提供了新思路。

### 7. 优点
- **创新性强**：深度挖掘 3D GS 在“初始估计+精化”双阶段中的潜力，突破场景依赖限制。
- **设计巧妙**：单向融合支持模型描述子预计算，加速推理；双向融合提升精化鲁棒性；损失函数辅助约束。
- **实验扎实**：大量数据集、丰富对比、详尽的消融实验，全面验证了各模块的贡献。
- **实用性好**：高精度、快速、可泛化，并有 AR 应用实例。

### 8. 不足与局限
- **依赖高质量 3D GS 模型**：若场景建模质量不佳（稀疏、噪声），定位性能会显著下降。
- **环境适应性未专门处理**：未考虑光照、天气等剧烈变化，但可借助 WildGaussians 等工作增强鲁棒性。
- **大规模场景未验证**：实验所用场景体积适中，超高分辨率或超大范围下的效率与精度有待检验。
- **训练细节披露不完整**：未明确训练 GPU 数量和总时长，复现时需额外调试。

（完）
