---
title: "Instant4D: 4D Gaussian Splatting in Minutes"
title_zh: Instant4D：分钟级四维高斯散点
authors: "Zhanpeng Luo, Haoxi Ran, Li Lu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HTLa6Ao0jG"
tags: ["query:gs-slam"]
score: 9.0
evidence: 结合深度视觉SLAM与四维高斯散点的单目系统，用于动态场景重建与新视角合成
tldr: 该论文提出了Instant4D单目重建系统，可从未校准的日常视频中快速重建动态场景。系统首先通过深度视觉SLAM恢复几何结构，然后采用高效的4D高斯表示进行优化，并通过网格剪枝大幅减少模型尺寸。该方法在几分钟内即可完成重建，压缩率高，同时保持了几何完整性，为动态场景的快速新视角合成提供了实用的解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-htla6ao0jg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-htla6ao0jg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-htla6ao0jg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-htla6ao0jg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-htla6ao0jg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 717, \"height\": 245, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-htla6ao0jg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-htla6ao0jg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-htla6ao0jg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-htla6ao0jg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 731, \"height\": 263, \"label\": \"Table\"}]"
motivation: 未校准视频的动态场景重建存在优化慢、参数估计复杂等挑战。
method: 结合深度视觉SLAM与剪枝后的精简4D高斯表示，实现分钟级重建。
result: "模型尺寸减少到原来的10%以内，重建速度快且保持几何精度。"
conclusion: Instant4D实现了高效的单目动态场景重建，推动了4D表示的实际应用。
---

## Abstract
Dynamic view synthesis has seen significant advances, yet reconstructing scenes
from uncalibrated, casual video remains challenging due to slow optimization and
complex parameter estimation. In this work, we present **Instant4D**, a monocular
reconstruction system that leverages native 4D representation to efficiently process
casual video sequences within minutes, without calibrated cameras or depth sensors.
Our method begins with geometric recovery through deep visual SLAM, followed
by grid pruning to optimize scene representation. Our design significantly reduces
redundancy while maintaining geometric integrity, cutting model size to under **10%**
of its original footprint. To handle temporal dynamics efficiently, we introduce a
streamlined 4D Gaussian representation, achieving a **30×** speed-up and reducing
training time to within two minutes, while maintaining competitive performance
across several benchmarks. Our method reconstruct a single video within 10
minutes on the Dycheck dataset or for a typical 200-frame video. We further
apply our model to in-the-wild videos, showcasing its generalizability. Our project
website is published at https://instant4d.github.io/.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化、深入、客观的中文总结。

### 1. 论文的核心问题与整体含义

*   **研究动机**：从用户日常拍摄的、未校准（无已知相机参数）的单目视频中，快速且高质量地重建动态3D场景，是计算机视觉领域的核心难题。它对AR/VR、沉浸式内容创作等应用至关重要。
*   **核心挑战**：
    *   **优化速度慢**：现有方法（如基于NeRF的RoDynRF）通常需要数小时甚至数天的优化时间，效率极低。
    *   **参数估计复杂**：需要同时恢复复杂的场景几何、相机运动、物体形变和遮挡关系。
    *   **资源消耗大**：许多方法模型庞大，内存占用高，难以实际应用。
*   **整体含义**：本文提出的Instant4D系统，旨在构建一个全自动、高效的管线，将单目动态场景的重建时间从数小时缩短至**分钟内**，同时保持甚至超越现有方法的渲染质量，显著提升了4D重建技术的实用性和可及性。

### 2. 论文提出的方法论

Instant4D的核心思想是结合**深度视觉SLAM**进行高效几何初始化，并设计了一个**精简高效的4D高斯表示**来进行动态场景优化。其完整管线分为两大阶段：

*   **几何恢复与初始化**
    *   **深度视觉SLAM**：利用MegaSAM从输入视频中估计出相机位姿、内参和时序一致的深度图。
    *   **网格剪枝**：将从深度图反投影得到的大规模密集点云（例如，一个4秒视频可产生3000万点），通过规则体素网格（Voxel Grid）进行过滤。每个体素内只保留点的质心，从而将数据量**减少92%**，极大降低了模型的内存占用和后续优化的负担。体素大小会根据场景尺度自适应调整。
    *   **运动概率估计**：利用SLAM流程中的运动概率图，通过Otsu阈值法分割静态背景与动态前景，以便在后续进行差异化、更高效的资源分配。

*   **4D高斯优化**
    *   **精简的4D高斯表示**：
        *   **外观模型**：抛弃了复杂的球柱谐函数（SCH），改用简单的**RGB颜色值**，将每个高斯原语的参数量削减了60%以上，减少了单目场景下的过拟合风险。
        *   **各向同性高斯**：将空间协方差矩阵简化为一个标量缩放因子，并固定旋转矩阵为单位阵。这增强了数值稳定性，降低内存占用，起到了隐式正则化的作用。
        *   **运动感知高斯**：这是处理动态场景的关键设计。通过为静态区域的高斯设定一个接近整个视频时长的大时间尺度 $s_t$，防止它们随时间推移而消失；而动态高斯的时间尺度 $s_t$ 则较短，允许它们根据时间戳快速改变位置和透明度 $o_t$。其原理是控制4D高斯在时间维度上的条件概率分布。
    *   **优化目标**：渲染时，通过将4D高斯在给定时刻 $t$ 的条件下，投影为3D高斯，然后使用与标准3DGS类似的损失函数进行优化。

### 3. 实验设计

论文在多个标准基准数据集上进行了定量和定性评估，以验证其方法的有效性和效率。

*   **数据集与场景**：
    *   **NVIDIA Dynamic Scene 数据集**：包含7个场景，每场景仅有12帧用于训练，测试从固定视角的连续时间帧进行。遵循RoDynRF的评估协议。
    *   **Dycheck iPhone 数据集**：包含“Apple”、“Block”、“Paper-Windmill”、“Spin”、“Teddy”等五个挑战性场景（剧烈运动和视差）。遵循RoDyGS的评估协议，报告每场景PSNR、训练总时间和峰值GPU内存。
    *   **DAVIS 数据集**：用于定性评估在“野外”（in-the-wild）视频上的泛化能力。
*   **对比方法**：
    *   **NVIDIA数据集对比**：包括HyperNeRF、DynamicNeRF、RoDynRF、Casual-FVS、InstantSplat风格的基线，以及本文复现的4DGS基线。对比指标包括PSNR、训练时间（Runtime）和渲染帧率（FPS）。
    *   **Dycheck数据集对比**：包括D-NeRF、RoDynRF、RoDyGS、4DGS、Deform3D等，并区分了使用真值相机位姿和不使用真值位姿的方法。对比指标包括PSNR、SSIM、训练总时间和峰值GPU内存。

### 4. 资源与算力

*   **GPU型号**：实验在单块 **NVIDIA A6000 GPU**（48GB显存）上进行。
*   **训练/重建时长**：
    *   **Dycheck数据集**：Lite模型平均每场景约 **0.03小时（约2分钟）**，Full模型为 **0.12小时（约7.2分钟）**。
    *   **NVIDIA数据集**：约 **0.02小时（约1.2分钟）**。
    *   **In-the-wild视频**：一个82帧的“Bear”视频，SLAM校准约2分钟，4D重建约2分钟，总计约4分钟。
*   **内存占用**：
    *   **Dycheck数据集**：Lite模型峰值内存为 **1.1GB**，Full模型为 **8GB**。
    *   通过网格剪枝，在NVIDIA数据集上，模型内存占用从 **10.7GB降至0.83GB**（92%的降幅）。
*   **渲染帧率 (FPS)**：Lite模型达到 **>500 FPS**，Full模型在NVIDIA数据集上可达 **981 FPS**。

### 5. 实验数量与充分性

*   **实验组数**：论文设计了较为全面的实验验证体系，大致包括：
    1.  **2个标准基准数据集的性能对比**：定量评估了渲染质量、速度和资源占用。
    2.  **1个“野外”数据集的定性评估**：展示泛化能力。
    3.  **消融实验**：通过两组消融研究（分别在NVIDIA和Dycheck数据集上）验证各个核心组件的有效性，包括：
        *   球谐函数（SCH） vs. RGB颜色
        *   使用/不使用体素过滤
        *   使用/不使用3DGS的致密化
        *   运动感知高斯 (Motion-Aware Gaussian)
        *   各向同性高斯 (Isotropic Gaussian)
*   **充分性与公平性**：
    *   **充分**：实验设计逻辑清晰，从整体性能到单一组件影响均有覆盖。对比了多个当前最优的基线方法，并区分了有无真实位姿的条件，使得对比较为公平。
    *   **客观**：指标选择了领域内公认的PSNR、SSIM、训练时间、内存和FPS。通过消融实验，清晰地证明了每个简化设计（如RGB、各向同性）和核心策略（运动感知）都带来了显著的正向收益，而非仅仅工程堆叠。例如，禁用运动感知高斯导致PSNR下降3.4dB，有效支撑了该模块的必要性。

### 6. 论文的主要结论与发现

*   **速度与效率的巨大飞跃**：Instant4D可以在**2-10分钟内**完成过去需要数小时甚至数天的动态场景重建任务，实现了 **30倍**的加速。
*   **质量的显著提升**：在Dycheck数据集上，仅用几分钟优化的Full模型（PSNR 24.52 dB）性能超越了需要真实位姿的Deform3D（22.63 dB）和24小时训练的D-NeRF（21.50 dB），远超同条件下的其他方法。
*   **极致的资源利用效率**：通过网格剪枝和精简的4D高斯表示，模型大小和内存占用降低了**90%** 以上，且能在单张消费级GPU上运行，实现了超过500 FPS的实时渲染。
*   **关键设计的有效性**：
    *   用**简单RGB**替代球谐函数不仅更高效，性能反而更好。
    *   **各向同性高斯**作为一种正则化手段，在单目动态场景中比各向异性高斯更稳定有效。
    *   **运动感知高斯**是处理静态背景和动态前景共存的单目4D场景的关键，能有效防止高斯原语不合理的消失或模糊。

### 7. 优点

*   **系统级创新**：论文构建了一个完整的、端到端的从非标定视频到4D重建的快速流水线，工程整合价值高。
*   **“减法”设计哲学**：通过简化外观模型（RGB）、简化几何表示（各向同性）和剪枝冗余点云，在提升速度的同时避免了过拟合，实现了“少即是多”的效果，思路巧妙。
*   **精巧的“运动感知”机制**：通过时间尺度 $s_t$ 的巧妙设计来区分和处理动静态区域，解决了4DGS在单目视图下的关键挑战，理论简单但效果显著。
*   **全面的效率评估**：论文将训练时间、渲染帧率、峰值内存作为与视觉质量同等重要的评估指标，并以此为导向进行系统设计，非常契合实际应用需求。
*   **可复现性强**：详细描述了实施细节、超参数设置，并承诺开源代码。

### 8. 不足与局限

*   **长视频的可扩展性受限**：论文明确指出，视觉SLAM组件的内存消耗随视频帧数线性增长，导致其在处理长时间视频时面临瓶颈。
*   **对SLAM的强依赖**：整个系统的鲁棒性依赖于前端视觉SLAM的精度。文中也提到，在“低纹理”场景（如Kite-surf视频中海面占主导），SLAM定位失败会导致重建对象消失。
*   **挑战性材质处理不足**：对高反光或透明表面的重建仍然是挑战，因为这些情况会严重影响深度估计的稳定性。
*   **实验比较基准**：在NVIDIA数据集上，报告的性能（23.99 dB）略低于一些使用额外正则化技术的方法（如RoDynRF的25.89 dB），虽然在速度上远超对方，但这表明在绝对质量上仍有提升空间。
*   **泛化性验证有限**：“野外”视频的评估仅为定性展示，缺乏系统性的定量比较，其在不同场景类型下的鲁棒性有待更广泛的验证。

（完）
