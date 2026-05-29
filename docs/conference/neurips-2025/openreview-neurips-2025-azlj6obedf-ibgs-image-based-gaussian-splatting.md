---
title: "IBGS: Image-Based Gaussian Splatting"
title_zh: "IBGS: 基于图像的3D高斯泼溅"
authors: "Hoang Chuong Nguyen, Wei Mao, Jose M. Alvarez, Miaomiao Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=AZLj6ObEDF"
tags: ["query:gs-slam"]
score: 7.0
evidence: 利用源图像增强3DGS新视角合成的颜色建模
tldr: IBGS针对3D高斯泼溅（3DGS）仅使用低阶球谐函数难以捕捉空间变化颜色和视角相关效果的问题，提出基于图像的高斯泼溅方法，从邻近训练图像中学习残差颜色，与基础3DGS渲染结合，有效恢复高光及细节，提升新视角合成的真实感。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-azlj6obedf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-azlj6obedf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1411, \"height\": 2215, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-azlj6obedf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1380, \"height\": 550, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-azlj6obedf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-azlj6obedf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-azlj6obedf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1270, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-azlj6obedf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 240, \"label\": \"Table\"}]"
motivation: 3DGS的低阶球谐无法充分表达视角相关的高光和空间变化的颜色细节。
method: 提出IBGS，将3DGS基础颜色与从源图像学习的残差组合，以丰富颜色表达。
result: 在复杂场景中，新视角合成质量优于标准3DGS，高光和细节更逼真。
conclusion: IBGS通过直接利用源图像信息，简单有效地增强了3DGS的视觉质量。
---

## Abstract
3D Gaussian Splatting (3DGS) has recently emerged as a fast, high-quality method for novel view synthesis (NVS). However, its use of low-degree spherical harmonics limits its ability to capture spatially varying color and view-dependent effects such as specular highlights. Existing works augment Gaussians with either a global texture map, which struggles with complex scenes, or per-Gaussian texture maps, which introduces high storage overhead. We propose Image-Based Gaussian Splatting, an efficient alternative that leverages high-resolution source images for fine details and view-specific color modeling. Specifically, we model each pixel color as a combination of a base color from standard 3DGS rendering and a learned residual inferred from neighboring training images. This promotes accurate surface alignment and enables rendering images of high-frequency details and accurate view-dependent effects. Experiments on standard NVS benchmarks show that our method significantly outperforms prior Gaussian Splatting approaches in rendering quality, without increasing the storage footprint. Our project page is available at https://hoangchuongnguyen.github.io/ibgs.

---

## 论文详细总结（自动生成）

## 论文总结

### 1. 核心问题与整体含义
- **研究背景**：3D Gaussian Splatting (3DGS) 是一种快速、高质量的新视角合成方法，但其**低阶球谐函数**难以捕捉复杂的**空间变化颜色**和**视角相关效果**（如镜面高光、反射）。
- **现有方法局限**：此前工作尝试引入纹理贴图来增强颜色表达，但全局纹理贴图难以处理多物体复杂场景，而逐高斯纹理贴图则会带来巨大的存储开销，且仍然无法很好地建模视角相关效果。
- **整体含义**：本文提出**基于图像的高斯泼溅 (IBGS)**，利用高分辨率训练图像来补充细节和视角相关信息，通过预测颜色残差与3DGS基础渲染相结合，在**不增加存储**的前提下，显著提升渲染质量，尤其是对高频细节和复杂光照效果的重建能力。

### 2. 方法论
- **核心思想**：将每个像素的最终颜色建模为两部分之和：
  - **基础颜色**：由标准3DGS渲染管线得到的颜色（基于球谐函数）。
  - **颜色残差**：一个由邻近源图像推断出来的补充项，用以捕捉基础颜色所缺失的高频细节和视角相关效果。
- **关键技术细节**：
  - **特征提取**：针对目标像素射线，选取射线与高斯体相交的前*K*个深度中值点（透射率接近0.5），将这些交点投影到*M*个邻近源视图上，获得扭曲像素颜色；加权平均后计算其与基础颜色的差值，作为**颜色特征**；同时，计算目标视图与各源视图之间的相机位置与方向差异，作为**相机特征**。
  - **残差预测网络**：采用轻量级网络。首先由PointNet风格的提取器处理每个视图的“颜色特征 + 相机特征”，经最大池化得到聚合特征图；然后将该特征图与基础渲染图、射线方向图拼接，输入一个9层卷积解码器，预测残差图。
  - **曝光校正**：为处理训练视图间的曝光不一致，通过求解一个最小二乘仿射变换，使基础颜色模仿最近源视图的曝光设置。该校正可泛化到任意新视角。
  - **优化项**：在训练损失中加入**多视图颜色一致性损失**（约束扭曲图像与真实图像一致）和**法线一致性损失**，以促进几何精度。源视图选择时还会进行深度一致性检查，剔除被遮挡视图。

### 3. 实验设计
- **数据集与场景**：
  - Tanks & Temples (TNT): 2个场景
  - Deep Blending: 2个场景
  - Mip-NeRF 360: 9个场景
  - Shiny 数据集: 3个场景（专门用于检验镜面高光、反射等挑战性视角相关效果）
- **对比基准**：与Mip-NeRF 360、Instant-NGP、3DGS、SuperGauss、TexturedGauss 等方法进行全面比较。
- **评价指标**：PSNR、SSIM、LPIPS，以及高斯体数量 (`#Gauss`) 和存储占用 (`Mem`)。

### 4. 资源与算力
- **硬件配置**：论文明确指出所有实验均使用 **单块 RTX 4090 GPU** 进行。
- **训练设置**：优化迭代30,000次，使用Adam优化器训练残差预测网络，并给出了学习率调整策略。
- **计算负载**：文中在局限性部分指出，由于渲染过程中增加了额外计算，其渲染速度和运行时内存消耗**不及**标准3DGS，但未提供具体的训练总时长和具体速度对比数据。

### 5. 实验数量与充分性
- **实验总量**：覆盖4个标准基准数据集，与至少5种主流或前沿方法进行了定量和定性对比，实验较为丰富。
- **消融研究**：设计了多组消融实验，以验证关键组件的有效性：
  - 仅使用基础颜色（移除残差预测）
  - 移除多视图颜色一致性损失
  - 改变网络输入（使用完整颜色而非颜色差值）
  - 移除曝光校正
  - 比较不同不透明度剪枝阈值下的鲁棒性
- **充分性与公平性**：实验设置充分，对比方法涵盖经典和最新的GS变体，指标全面，消融实验清晰证明了各模块的作用，整体评估客观、公正。

### 6. 主要结论与发现
- IBGS在所有基准数据集上均取得了**最优**的新视角合成性能（PSNR、SSIM、LPIPS全面领先）。
- 与先前的纹理增强GS方法相比，IBGS在显著提升质量的同时，**大幅降低了高斯体数量和存储空间**（例如在Mip-NeRF 360上存储减少62%，高斯数减少42%）。
- 在具有挑战性视角相关效果的Shiny数据集上，IBGS的PSNR比3DGS和SuperGauss提高了超过5 dB，展现出卓越的视角相关颜色建模能力。
- 提出的曝光校正策略能有效处理训练视图曝光不一致的问题，并能泛化至新视角。

### 7. 优点
- **性能优越**：在保持低存储占用的同时，实现了对高频细节和复杂视角相关效果的高质量渲染，性能表现达到新SOTA。
- **设计巧妙**：通过“基础颜色+图像残差”的分解式建模，巧妙地利用了源图像信息，网络结构轻量，不引入大型Transformer。
- **几何与外观联合优化**：多视图颜色一致性损失和法线一致性损失有效地促进了精确的表面对齐，允许剪枝更多低透明度高斯体。
- **曝光校正泛化**：提出了一种可泛化到新视图的曝光校正方法，解决了实际场景中常见的曝光不一致问题。

### 8. 不足与局限
- **稀疏视图性能**：该方法依赖邻近视图间的稠密像素对应关系，在稀疏视图设置下可能面临挑战，难以准确预测颜色残差。
- **渲染效率**：由于需要从源视图提取特征并运行残差预测网络，其渲染速度和运行时的显存需求均劣于原生3DGS，无法实现实时渲染。
- **曝光校正假设**：曝光校正策略基于“邻近视图光照条件相似”的假设，在光照变化剧烈或视点跨度较大的场景中可能失效。
- **未提供具体计算开销**：文中未给出训练总时长、推理帧率等具体数据，与标准3DGS的效率差距缺乏量化对比。

（完）
