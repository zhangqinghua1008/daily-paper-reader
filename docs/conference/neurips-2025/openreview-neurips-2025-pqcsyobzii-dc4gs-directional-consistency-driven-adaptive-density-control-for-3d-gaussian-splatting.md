---
title: "DC4GS: Directional Consistency-Driven Adaptive Density Control for 3D Gaussian Splatting"
title_zh: DC4GS：方向一致性驱动的3D高斯溅射自适应密度控制
authors: "Moonsoo Jeong, Dongbeen Kim, Minseong Kim, Sungkil Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PQcSYOBZii"
tags: ["query:gs-slam"]
score: 8.0
evidence: 具有方向一致性的3DGS自适应密度控制
tldr: "DC4GS利用梯度的方向一致性改进3DGS基元分裂策略，在保持渲染质量的条件下减少高达30%的高斯数量，提升内存效率。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 255, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 2019, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 1918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1430, \"height\": 1951, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 1856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1446, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1436, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqcsyobzii/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1427, \"height\": 1615, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1460, \"height\": 1015, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1456, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1457, \"height\": 669, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 602, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 845, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1302, \"height\": 1123, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1339, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqcsyobzii/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1448, \"height\": 234, \"label\": \"Table\"}]"
motivation: 原始3DGS的自适应密度控制仅基于梯度大小，导致基元冗余，影响存储和效率。
method: DC4GS在基元分裂时引入梯度方向一致性约束，根据角度相干性决定是否分裂及最优分裂位置。
result: "DC4GS显著减少了高斯基元数量（最多少30%），同时渲染质量与原始方法相当或更优。"
conclusion: 方向一致性驱动策略有效压缩了3DGS模型，提升了其在实际应用中的可部署性。
---

## Abstract
We present a Directional Consistency (DC)-driven Adaptive Density Control (ADC) for 3D Gaussian Splatting (DC4GS). Whereas the conventional ADC bases its primitive splitting on the magnitudes of positional gradients, we further incorporate the DC of the gradients into ADC, and realize it through the angular coherence of the gradients. Our DC better captures local structural complexities in ADC, avoiding redundant splitting. When splitting is required, we again utilize the DC to define optimal split positions so that sub-primitives best align with the local structures than the conventional random placement. As a consequence, our DC4GS greatly reduces the number of primitives (up to 30\% in our experiments) than the existing ADC, and also enhances reconstruction fidelity greatly.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：传统 3D Gaussian Splatting (3DGS) 的自适应密度控制 (ADC) 仅依赖于**位置梯度的幅值（L2 范数）** 来决定是否分裂基元，并**随机**放置分裂出的子基元。这种方式无法区分场景中结构复杂与均质的区域，容易在不需要精细化的地方产生冗余分裂，导致基元数量膨胀、存储与渲染效率降低，同时子基元的随机放置可能引起错位或重叠。
- **整体含义**：论文提出**利用梯度的方向一致性（Directional Consistency, DC）** 作为结构复杂度的指标，将其融入 ADC，实现更智能、更紧凑的基元管理。该方法在显著减少基元数量（最高减少 30%）的同时，保持甚至提升了重建质量，从而提高了 3DGS 模型在实际部署中的存储与渲染效率。

### 2. 论文提出的方法论
- **核心思想**：
  - 将每个高斯基元所覆盖像素的**位置梯度方向一致程度**量化为方向一致性（DC）。
  - 将 DC 与梯度幅值结合，形成新的分裂判定准则（DCC），用于避免在均质区域（高 DC）进行分裂。
  - 在必须分裂时，使用 DC 引导分裂位置选择（DCS），使子基元尽可能落在各自结构均质的区域，从而最大化子基元内部的方向一致性，最小化结构复杂度。

- **关键技术细节与算法流程**：
  - **方向一致性（DC）定义**：  
    对每个高斯基元 \(i\)，收集其影响的像素 \(j\) 的位置梯度 \(g_{i,j}\)，归一化为单位向量。计算这些单位向量的**圆形均值** \(C_i = \frac{1}{N}\sum u_{i,j}\)，方向一致性即为 \(\kappa_i = \|C_i\| \in [0,1]\)。\(\kappa\) 接近 1 表示梯度方向高度一致（均质区域），接近 0 表示方向散乱（复杂区域）。
  - **DC 加权分裂准则（DCC）**：  
    定义新的准则 \(\nabla^{DC}_{\mu_i'}L = \frac{1}{\nu}\sum_{v=1}^{\nu} (1 - \kappa_{i,v}) \cdot \|\hat{g}_{i,v}\|\)，其中 \(\hat{g}_{i,v}\) 为同向梯度累积（采用 AbsGS 的聚合法）。即用 \((1-\kappa)\) 对梯度幅值进行加权：方向越不一致，加权后的值越大，越容易被选中分裂。该准则替代了传统的纯幅值阈值，有效过滤掉已精细化的高斯。
  - **DC 引导的分裂位置选择（DCS）**：
    - 分裂位置限制在基元的**主轴**（尺度最大的轴）方向上。
    - 沿主轴对称采样 \(N=5\) 个候选分裂点，对每个候选点，将基元像素划分为左右两半，分别计算两半区域的DC代价 \(J_l = (1-\kappa_l)\|\hat{g}_l\|\) 和 \(J_r\)，总代价 \(J(x)=J_l+J_r\)。
    - 对离散样本进行**多项式回归**，估计最优分裂位置 \(x_{opt}\)，使得左右子区域均达到高一致性（即代价最小）。
    - 分裂时按比例调整子基元的中心位置、沿主轴方向的尺度以及不透明度。

- **即插即用性**：DC4GS 可以直接集成到现有的 3DGS 及其变体（如 AbsGS、Pixel‑GS）的 ADC 流程中，修改量集中于分裂判定与位置生成部分。

### 3. 实验设计
- **数据集**：
  - Mip‑NeRF 360（7 个室外 + 2 个室内场景）
  - Tanks and Temples（2 个场景）
  - Deep Blending（2 个场景）
  - 动态场景扩展：D‑NeRF 和 DyNeRF 数据集
- **基准方法（Baselines）**：
  - 非 3DGS 方法：Plenoxels, iNGP‑big, Mip‑NeRF360
  - 3DGS 及其改进：原始 3DGS, Scaffold‑GS, GES, LPM, Pixel‑GS, AbsGS
  - 将 DC4GS 分别集成到 3DGS, Scaffold‑GS, GES, LPM, Pixel‑GS, AbsGS 中进行对比
  - 动态场景对比：4DGS 与 4DGS+DC4GS
- **评价指标**：
  - 渲染质量：PSNR, SSIM, LPIPS
  - 存储效率：基元数量 (Primitives) 及内存占用 (Memory)
  - 时间效率：训练总时间、单帧渲染时间 (ms)
- **消融实验**：以 AbsGS 为基线，单独添加 DCC、单独添加 DCS、同时添加两者，分别评估各模块的贡献。

### 4. 资源与算力
- 所有实验均在**单块 NVIDIA A6000 GPU（48 GB 显存）** 上运行。
- 训练时长随方法不同而异，论文表 2 给出了详细对比。例如：
  - 在 Mip‑NeRF360 数据集上，AbsGS 训练约 37 分钟，AbsGS+DC4GS 约 51 分钟。
  - 总体而言，DC4GS 引入的训练开销来自于 DC 计算和分裂代价评估，但该额外开销仅限于训练阶段，推理时因基元数减少反而更快。
- 未明确提及 GPU 数量（已说明单块），也未提及每次训练的重复次数（未报告多次运行的误差棒，仅用箱线图展示了 10,000 次随机采样的 2D 验证结果）。

### 5. 实验数量与充分性
- **实验组数**：
  - 在 3 个真实世界数据集的 13 个场景上，与 6 种 baseline 方法集成对比，合计约 18 组主要定量结果（表 1）。
  - 时间效率对比（表 2）覆盖 3 个数据集、5 种方法的训练/渲染时间。
  - 消融实验在 3 个数据集上测试了 3 种配置（表 3）。
  - 额外的定性结果（图 6、9‑11）、深度图对比（图 12）、挑战性场景对比（透明物体/强纹理，表 8）、动态场景对比（表 9）以及 2D 模拟的统计验证（图 5、图 8）。
  - 还提供了采样方法与分辨率影响的分析（附录 A.2）。
- **充分性与公平性**：
  - 实验设计较为全面，覆盖了主流静态与动态数据集，并与权威 baseline 进行了公平对比（沿用原方法的超参数和训练策略）。
  - 消融实验清晰展示了 DCC 和 DCS 各自的贡献及协同效应。
  - 实验客观性较高，不仅衡量质量，还重点考察了基元数和存储效率，并对比了训练与推理时间。

### 6. 论文的主要结论与发现
- **基元数量显著减少**：DC4GS 与 AbsGS 结合时，基元数量平均减少约 20%，在个别场景（Room）最高减少 30%；与其他 baseline 结合也可减少 11%–18%。
- **渲染质量保持或提升**：所有集成 DC4GS 的方法在 PSNR、SSIM、LPIPS 上均达到与原始方法相当或更优的水平，尤其在保持高频细节和几何边界方面表现更好。
- **良好泛化能力**：方法可即插即用于不同 3DGS 变体及动态场景（4DGS），并同样能提升渲染质量、降低基元数和推理时间。
- **结构感知的分裂策略有效**：方向一致性能够有效识别场景中的均质/复杂区域，引导更精准的分裂决策与子基元布局，从而避免了传统方法的冗余分裂和随机放置带来的伪影。

### 7. 优点
- **创新性度量**：首次将位置梯度的方向一致性引入 3DGS 的密度控制，用简洁的圆形统计量有效量化了局部结构的同质性。
- **双环节赋能**：DC 同时用于分裂判定（DCC）和分裂位置优化（DCS），形成了闭环的逻辑，且两者使用一致的代价公式，理论自洽。
- **显著的效率提升**：在保持质量的前提下大幅压缩基元数量，直接降低了存储需求和渲染延迟，对移动端/实时应用友好。
- **泛用性强**：可轻松嵌入到多种 3DGS 变体中，实验也验证了其对动态场景和透明/强纹理等挑战性区域的鲁棒性。
- **实验详尽**：定量、定性、消融、效率、统计验证等多维度评估，并提供了代码复现。

### 8. 不足与局限
- **训练开销增加**：DC 计算和分裂代价评估带来了约 30%–50% 的额外训练时间（见表 2），虽然训练是一次性的，但对于快速原型迭代仍有影响。
- **超参数敏感性未详细讨论**：方法引入了采样点数 \(N\)、多项式回归阶数等新参数，论文在特定设置下展示了良好性能，但未系统分析这些参数在不同场景下的敏感性和调参策略。
- **分裂方向约束**：DCS 限制了子基元仅沿主轴方向放置，对于某些各向异性极强或主轴方向与结构变化方向不平行的情况，可能产生次优分裂。
- **极端条件下的表现未知**：虽然在透明物体和强纹理区域有改进，但对于极低光照、严重反射或大幅运动模糊等极端场景，仍缺少充分验证。
- **实验重复性**：由于计算资源限制，未进行多次完整训练并报告误差棒，部分结论的统计显著性可进一步加强。

（完）
