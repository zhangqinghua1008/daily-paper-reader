<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-06-10
- 运行时间：2026-06-10 22:46:09 UTC
- 运行状态：成功
- 本次总论文数：8
- 精读区：5
- 速读区：3

### 今日简报（AI）
今日精读两篇9分论文：卫星遥感Gaussian Splatting与可变形结肠镜3D数据集，并速览高效FPS采样、多相机VIO最小求解器等三篇工作。  
最值得关注的是RPC-GS首次将卫星专用RPC渲染直接融入3D高斯泼溅，大幅提升遥感场景重建精度，而C3VD-DEFCOL则填补了动态内窥镜下真实外观与密集时空真值的空白。  
建议对遥感三维重建或医学动态重建感兴趣的读者重点跟进RPC-GS的光度配准思路，并关注Sphere Voxel裁剪在点云采样加速中的实际部署潜力。
- 详情：[/202606/10/README](/202606/10/README)

### 精读区论文标签
1. [RPC-GS: Gaussian Splatting with native RPC Rendering for Satellite Imagery](/202606/10/2606.06690v1-rpc-gs-gaussian-splatting-with-native-rpc-rendering-for-satellite-imagery)  
   标签：评分：9.0/10、query:gs-slam
   evidence：使用RPC模型的高斯泼溅进行卫星场景重建与渲染
2. [C3VD-DEFCOL: A Deformable Colonoscopy Dataset with Time-Resolved 3D Ground Truth and Realistic Appearance](/202606/10/2606.07891v1-c3vd-defcol-a-deformable-colonoscopy-dataset-with-time-resolved-3d-ground-truth-and-realistic-appearance)  
   标签：评分：9.0/10、query:endo-dgs
   evidence：提供带有密集时序三维真值（深度、表面法线）的变形结肠镜数据集，直接支持深度估计和重建评估。
3. [G2G: Exploiting Intra-Group Geometry for Inter-Group Pose Estimation](/202606/10/2606.08284v1-g2g-exploiting-intra-group-geometry-for-inter-group-pose-estimation)  
   标签：评分：8.0/10、query:gs-slam
   evidence：利用组内几何估计图像组间的相对六自由度位姿，用于重定位和里程计。
4. [Efficient Minimal Solvers for Relative Pose Estimation in Autonomous Driving Applications](/202606/10/2606.09569v1-efficient-minimal-solvers-for-relative-pose-estimation-in-autonomous-driving-applications)  
   标签：评分：8.0/10、query:gs-slam
   evidence：多相机系统的高效相对姿态最小求解器
5. [Generalized-CVO: Fast and Correspondence-Free Local Point Cloud Registration with Second Order Riemannian Optimization](/202606/10/2606.10019v1-generalized-cvo-fast-and-correspondence-free-local-point-cloud-registration-with-second-order-riemannian-optimization)  
   标签：评分：8.0/10、query:gs-slam
   evidence：使用各向异性核的无对应点云配准

### 速读区论文标签
1. [RadiusFPS: Efficient Farthest Point Sampling on CPUs and GPUs via Spherical Voxel Pruning](/202606/10/2606.06255v1-radiusfps-efficient-farthest-point-sampling-on-cpus-and-gpus-via-spherical-voxel-pruning)  
   标签：评分：7.0/10、query:gs-slam
   evidence：通过球形体素剪枝加速FPS支持实时SLAM
2. [Efficient Minimal Solvers for Visual-Inertial Relative Pose Estimation in Multi-Camera Systems](/202606/10/2606.09477v1-efficient-minimal-solvers-for-visual-inertial-relative-pose-estimation-in-multi-camera-systems)  
   标签：评分：7.0/10、query:gs-slam
   evidence：提出视觉惯性相对位姿的高效最小求解器，适用于多相机SLAM
3. [Information-Preserving Continuous Occupancy Mapping with Variance-Weighted Submap Joining](/202606/10/2606.10442v1-information-preserving-continuous-occupancy-mapping-with-variance-weighted-submap-joining)  
   标签：评分：6.0/10、query:gs-slam
   evidence：提出一种用于SLAM占据地图的连续概率子图融合方法，改善全局一致性和不确定性处理。


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
