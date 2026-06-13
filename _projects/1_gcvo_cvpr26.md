---
layout: page
title: Generalized-CVO
description: Fast and correspondence-free point cloud registration in RKHS with second-order Riemannian optimization
img: assets/img/gcvo/kitti_00_gcvo_2nd_order.png
importance: 1
category: work
---

CVPR 2026 Highlight

Authors: Ray Zhang, Marcus Greiff, Thomas Lew, John Subosits

Links:
<a href="https://arxiv.org/abs/2606.10019">Paper</a> |
<a href="https://github.com/ToyotaResearchInstitute/gcvo">Code</a> |
<a href="https://www.youtube.com/watch?v=D7dJ3j6qx7g">Demo video</a>

Generalized-CVO estimates rigid SE(3) transforms between point clouds by maximizing a inner product with anisotropic kernels in a reproducing kernel Hilbert space. The method avoids explicit correspondences and combines geometric and appearance features with second-order Riemannian optimization on the SE(3) manifold.

Note: The original project website at `sites.google.com/tri.global/gcvo` is no longer maintained; this page now serves as the project page.

<div class="row">
        {% include figure.html path="assets/img/gcvo/gcvo_teaser.png" alt="overview" title="overview" class="img-fluid rounded z-depth-1" %}
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/gcvo/kitti_00_gcvo_2nd_order.png" alt="KITTI sequence 00 GCVO second-order trajectory compared with ground truth" title="KITTI seq 00 GCVO 2nd-order trajectory" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/gcvo/eth3d_table_3_gcvo_2nd_order.png" alt="ETH3D table_3 GCVO second-order tracking result" title="ETH3D table_3 GCVO 2nd-order tracking" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Frame-to-frame registration examples from the GCVO repository: KITTI Seq 00 LiDAR odometry and ETH3D table_3 RGB-D tracking, both without local mapping or loop closure.
</div>

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-3">
  <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/D7dJ3j6qx7g" title="Generalized-CVO demo video" allowfullscreen></iframe>
</div>

