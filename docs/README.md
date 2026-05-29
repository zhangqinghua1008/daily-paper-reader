<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-04-30 ~ 2026-05-29
- 运行时间：2026-05-29 10:35:29 UTC
- 运行状态：成功
- 本次总论文数：14
- 精读区：3
- 速读区：11

### 今日简报（AI）
本周聚焦医学影像与动态场景重建，精读两篇高分内窥镜仿真论文，速读多篇3D/4D渲染技术。
内窥镜几何估计和手术模拟取得突破：CoGE 实现结肠镜实时位姿推断，EndoGSim 借助多模态大模型生成逼真动态手术场景。
建议关注高斯泼溅在医疗仿真中的落地进展，这可能是手术机器人训练的下一个跳板。
- 详情：[/20260430-20260529/README](/20260430-20260529/README)

### 精读区论文标签
1. [CoGE: Sim-to-Real Online Geometric Estimation for Monocular Colonoscopy](/20260430-20260529/2605.13038v1-coge-sim-to-real-online-geometric-estimation-for-monocular-colonoscopy)  
   标签：评分：9.0/10、query:endo-dgs
   evidence：结肠镜单目在线几何估计，包含深度估计
2. [EndoGSim: Physics-Aware 4D Dynamic Endoscopic Scene Simulations via MLLM-Guided Gaussian Splatting](/20260430-20260529/2605.16022v1-endogsim-physics-aware-4d-dynamic-endoscopic-scene-simulations-via-mllm-guided-gaussian-splatting)  
   标签：评分：9.0/10、query:endo-dgs
   evidence：直接应用4D高斯溅射实现内窥镜场景的物理感知重建与仿真。
3. [SCARED-C: Corrected Camera Poses for Endoscopic Depth Estimation](/20260430-20260529/2605.16628v1-scared-c-corrected-camera-poses-for-endoscopic-depth-estimation)  
   标签：评分：8.0/10、query:endo-dgs
   evidence：纠正SCARED数据集中的相机位姿以改善内窥镜深度估计

### 速读区论文标签
1. [Differentiable Ray Tracing with Gaussians for Unified Radio Propagation Simulation and View Synthesis](/20260430-20260529/2605.07781v1-differentiable-ray-tracing-with-gaussians-for-unified-radio-propagation-simulation-and-view-synthesis)  
   标签：评分：7.0/10、query:endo-dgs
   evidence：基于3D高斯溅射的可微光线追踪用于视图合成
2. [3D Skew-Normal Splatting](/20260430-20260529/2605.15010v2-3d-skew-normal-splatting)  
   标签：评分：7.0/10、query:endo-dgs
   evidence：采用偏正态基元扩展3D高斯溅射以改善表示
3. [R5DGS: Semantic-Aware 4D Gaussian Splatting with Rigid Body Constraints for Efficient Dynamic Scene Reconstruction](/20260430-20260529/2605.25909v1-r5dgs-semantic-aware-4d-gaussian-splatting-with-rigid-body-constraints-for-efficient-dynamic-scene-reconstruction)  
   标签：评分：7.0/10、query:endo-dgs
   evidence：语义感知4D高斯溅射可提升动态内窥镜场景重建。
4. [Softmax-GS: Generalized Gaussians Learning When to Blend or Bound](/20260430-20260529/2604.27437v1-softmax-gs-generalized-gaussians-learning-when-to-blend-or-bound)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：提出Softmax-GS，通过softmax竞争解决3DGS中的视图不一致和模糊边界问题
5. [Faster 3D Gaussian Splatting Convergence via Structure-Aware Densification](/20260430-20260529/2604.28016v1-faster-3d-gaussian-splatting-convergence-via-structure-aware-densification)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：通过基于多尺度频率分析的结构感知致密化改进3DGS收敛
6. [AdpSplit: Error-Driven Adaptive Splitting for Faster Geometry Discovery in 3D Gaussian Splatting](/20260430-20260529/2605.06876v1-adpsplit-error-driven-adaptive-splitting-for-faster-geometry-discovery-in-3d-gaussian-splatting)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：3DGS的自适应分裂算子加速训练，可潜在加速内窥镜三维重建。
7. [High-Fidelity Surface Splatting-Based 3D Reconstruction from Multi-View Images](/20260430-20260529/2605.07254v1-high-fidelity-surface-splatting-based-3d-reconstruction-from-multi-view-images)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：提出多项式核IMLS实现高保真表面抛雪球，改进3DGS网格提取
8. [Focusable Monocular Depth Estimation](/20260430-20260529/2605.11756v1-focusable-monocular-depth-estimation)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：提出区域感知的单目深度估计，聚焦于指定目标区域
9. [HarmoGS: Robust 3D Gaussian Splatting in the Wild via Conflict-Aware Gradient Harmonization](/20260430-20260529/2605.13073v1-harmogs-robust-3d-gaussian-splatting-in-the-wild-via-conflict-aware-gradient-harmonization)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：通过梯度协调实现通用场景的鲁棒3D高斯溅射
10. [HarmoGS: Robust 3D Gaussian Splatting in the Wild via Conflict-Aware Gradient Harmonization](/20260430-20260529/2605.13073v2-harmogs-robust-3d-gaussian-splatting-in-the-wild-via-conflict-aware-gradient-harmonization)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：通过梯度协调提高3DGS对扰动和光照不一致的鲁棒性
11. [Z-Order Transformer for Feed-Forward Gaussian Splatting](/20260430-20260529/2605.13465v1-z-order-transformer-for-feed-forward-gaussian-splatting)  
   标签：评分：6.0/10、query:endo-dgs
   evidence：引入基于Transformer的前馈3DGS方法，实现实时新视角合成


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
