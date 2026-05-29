<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-05-20 ~ 2026-05-29
- 运行时间：2026-05-29 08:29:01 UTC
- 运行状态：成功
- 本次总论文数：16
- 精读区：8
- 速读区：8

### 今日简报（AI）
本期精读高斯泼溅新作一篇满分、一篇9分，速读则聚焦视觉里程计与重建。
最值得关注《Depth Peeling for Gaussian-Enhanced Surfel Rendering》的透明层剥离与高保真渲染，以及《TWINGS》在少视图场景下的薄板样条对齐初始化方法。
建议结合事件相机与全局SfM的速读新进展，交叉审视高斯增强渲染和鲁棒定位的落地潜力。
- 详情：[/20260520-20260529/README](/20260520-20260529/README)

### 精读区论文标签
1. [Depth Peeling for High-Fidelity Gaussian-Enhanced Surfel Rendering](/20260520-20260529/2605.25345v1-depth-peeling-for-high-fidelity-gaussian-enhanced-surfel-rendering)  
   标签：评分：10.0/10、query:gs-slam
   evidence：提出DP-GES，通过深度剥层改进高斯增强面元渲染，用于基于3D高斯泼溅的高保真新视图合成
2. [TWINGS: Thin Plate Splines Warp-aligned Initialization for Sparse-View Gaussian Splatting](/20260520-20260529/2605.22069v1-twings-thin-plate-splines-warp-aligned-initialization-for-sparse-view-gaussian-splatting)  
   标签：评分：9.0/10、query:gs-slam
   evidence：通过翘曲对齐初始化增强稀疏视角下的3D高斯泼溅新视角合成
3. [No Pose, No Problem in 4D: Feed-Forward Dynamic Gaussians from Unposed Multi-View Videos](/20260520-20260529/2605.22190v1-no-pose-no-problem-in-4d-feed-forward-dynamic-gaussians-from-unposed-multi-view-videos)  
   标签：评分：9.0/10、query:gs-slam
   evidence：利用3D高斯泼溅从无标定多视角视频中同时实现场景重建与相机位姿估计
4. [LangFlash: Feed-forward 3D Language Gaussian Splatting from Sparse Unposed Images](/20260520-20260529/2605.23287v1-langflash-feed-forward-3d-language-gaussian-splatting-from-sparse-unposed-images)  
   标签：评分：9.0/10、query:gs-slam
   evidence：前馈三维语言高斯泼溅框架
5. [FusionCore: A 23-State Unscented Kalman Filter for IMU, Wheel Encoder, GPS, and Visual SLAM Fusion in ROS 2](/20260520-20260529/2605.25239v1-fusioncore-a-23-state-unscented-kalman-filter-for-imu-wheel-encoder-gps-and-visual-slam-fusion-in-ros-2)  
   标签：评分：9.0/10、query:gs-slam
   evidence：融合视觉SLAM位姿与IMU、轮式编码器和GPS以获得精确里程计
6. [DelowlightSplat: Feed-Forward Gaussian Splatting for Lowlight 3D Scene Reconstruction](/20260520-20260529/2605.26629v1-delowlightsplat-feed-forward-gaussian-splatting-for-lowlight-3d-scene-reconstruction)  
   标签：评分：9.0/10、query:gs-slam
   evidence：使用前馈3D高斯泼溅从稀疏姿态图像进行新视角合成
7. [Con-DSO: Learning Short-Horizon Consistency Priors for RGB-D Direct Sparse Odometry](/20260520-20260529/2605.27952v1-con-dso-learning-short-horizon-consistency-priors-for-rgb-d-direct-sparse-odometry)  
   标签：评分：9.0/10、query:gs-slam
   evidence：提出Con-DSO，通过学习短时一致性先验提升RGB-D直接稀疏里程计，直接提高相机位姿跟踪精度
8. [Eulerian Gaussian Splatting using Hashed Probability Pyramids](/20260520-20260529/2605.29136v1-eulerian-gaussian-splatting-using-hashed-probability-pyramids)  
   标签：评分：9.0/10、query:gs-slam
   evidence：提出基于概率密度优化的3D高斯泼溅框架用于新视角合成

### 速读区论文标签
1. [Extending Deep Event Visual Odometry with Sparse Point-Cloud Export](/20260520-20260529/2605.22890v1-extending-deep-event-visual-odometry-with-sparse-point-cloud-export)  
   标签：评分：8.0/10、query:gs-slam
   evidence：单目事件相机视觉里程计与稀疏点云导出，实现相机追踪
2. [Global Structure-from-Motion Meets Feedforward Reconstruction](/20260520-20260529/2605.26103v1-global-structure-from-motion-meets-feedforward-reconstruction)  
   标签：评分：8.0/10、query:gs-slam
   evidence：同时估计相机姿态和3D场景结构
3. [Provably Guaranteed Polytopic Uncertainty Quantification for SLAM](/20260520-20260529/2605.28172v1-provably-guaranteed-polytopic-uncertainty-quantification-for-slam)  
   标签：评分：8.0/10、query:gs-slam
   evidence：SLAM算法提供可证明的不确定性量化，涵盖位姿跟踪与建图
4. [ForeSplat: Optimization-Aware Foresight for Feed-Forward 3D Gaussian Splatting](/20260520-20260529/2605.22020v1-foresplat-optimization-aware-foresight-for-feed-forward-3d-gaussian-splatting)  
   标签：评分：7.0/10、query:gs-slam
   evidence：提出优化感知训练方法提升前馈3DGS的快速有效场景重建
5. [RiGS: Rigid-aware 4D Gaussian Splatting from a Single Monocular Video](/20260520-20260529/2605.23672v1-rigs-rigid-aware-4d-gaussian-splatting-from-a-single-monocular-video)  
   标签：评分：7.0/10、query:gs-slam
   evidence：利用4D高斯泼溅从单目视频进行动态场景重建
6. [CodecSplat: Ultra-Compact Latent Coding for Feed-Forward 3D Gaussian Splatting](/20260520-20260529/2605.25563v1-codecsplat-ultra-compact-latent-coding-for-feed-forward-3d-gaussian-splatting)  
   标签：评分：7.0/10、query:gs-slam
   evidence：为前馈三维高斯泼溅提供超紧凑潜在编码
7. [Underwater360: Reconstructing Underwater Scenes from Panoramic Images with Omnidirectional Gaussian Splatting](/20260520-20260529/2605.26447v1-underwater360-reconstructing-underwater-scenes-from-panoramic-images-with-omnidirectional-gaussian-splatting)  
   标签：评分：6.0/10、query:gs-slam
   evidence：使用3D高斯泼溅进行水下场景重建和新视角合成
8. [SAFEVPR: Patch-Based Conformal Verification for Safe Cross-Condition Sequence Visual Place Recognition](/20260520-20260529/2605.28048v1-safevpr-patch-based-conformal-verification-for-safe-cross-condition-sequence-visual-place-recognition)  
   标签：评分：6.0/10、query:gs-slam
   evidence：基于DINOv2特征与保形预测的视觉地点识别用于SLAM安全重定位


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
