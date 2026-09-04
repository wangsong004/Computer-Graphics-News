# Computer-Graphics-News

## 2026-08-26

### ExMesh++：从多视图图像生成可重新打光的 UV-PBR 网格资产

- 类型：论文（Graphics，cs.GR）
- 核心进展：ExMesh++ 将多视图重建分成两个阶段：先通过自适应顶点拆分和合并优化显式网格拓扑，同时保持 UV 一致性；再固定网格与 UV，优化 UV 空间中的 PBR 材质和环境光，并用次级光线追踪建模一次漫反射间接光。
- 值得关注：它面向可编辑、可重新打光的生产级网格资产，减少从神经/多视图重建结果进入 Blender、Maya 等 DCC 流程时常见的表面提取和纹理烘焙工作。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2608.24109)

## 2026-08-27

### GLOSS：基于几何局部自相似性的参考引导纹理填充

- 类型：论文与 Blender 插件（Graphics，cs.GR；SIGGRAPH Asia 2026）
- 核心进展：GLOSS 利用形状的局部几何自相似性和几何-纹理相关性，只用单个 3D 形状与现成图像模型先验，训练几何感知的局部纹理生成/补全模型。艺术家可以选择参考纹理并以 patch 级方式交互式填充目标网格；方法还支持局部几何条件修补、PBR 材质迁移和未见网格的纹理转移。
- 值得关注：它把生成式纹理从“整物体自动生成”推进到更可控的局部创作流程，并已作为 Blender 插件由 5 位专业 3D 纹理艺术家试用；项目页报告其在 LPIPS、DreamSim 和 CMMD 等指标上相对多种基线具有竞争力。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2608.25461) · [项目主页](https://chenyuecai.github.io/gloss-page/) · [官方代码库](https://github.com/ChenyueCai/GLOSS)

## 2026-08-28

### Procedura：带程序化控制的智能体 3D 建模

- 类型：论文与开源项目（Graphics，cs.GR）
- 核心进展：Procedura 将文本生成的 3D 形状表示为由命名部件组成的程序化装配，而不是不可编辑的稠密网格。智能体先规划装配图，再逐部件生成参数化程序；每个部件必须通过编译、配合（mate）和连通性检查，视觉 critic 再逐项修正，同时保留部件材质和可验证关节。
- 值得关注：这种“3D shape as code”路线直接产出可编辑、带部件结构的模型，并在 P3D-Bench 与 MechBench-36 上报告优于已有原生 3D 生成器和 3D-code agent，尤其适合机械/硬表面建模与后续 CAD、仿真流程。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2608.26238) · [项目主页](https://spatiaos.github.io/projects/procedura/) · [官方代码库](https://github.com/SpatiaOS/Procedura)

## 2026-08-29

### RefracGS：面向折射水面的 3D Gaussian 光线追踪新视图合成

- 类型：论文与开源项目（ECCV 2026；Graphics，cs.GR）
- 核心进展：RefracGS 将折射水面建模为神经高度场，将水下场景表示为 3D Gaussian 场，并用遵循 Snell 定律的折射感知 Gaussian 光线追踪计算非直线光路。水面和场景表示进行端到端联合优化，从而同时恢复波面与水下场景的新视图。
- 值得关注：它针对 NeRF/3DGS 假设光线直线传播在非平面水面下产生严重伪影的问题；项目页报告在复杂波面场景上实现更高视觉质量、约 15 倍更快训练和约 200 FPS 实时渲染，并提供代码与数据集。
- 来源：[arXiv 修订版论文页面](https://arxiv.org/abs/2603.21695) · [项目主页](https://yimgshao.github.io/refracgs/) · [官方代码库](https://github.com/yimgshao/refracgs) · [数据集](https://huggingface.co/datasets/yimingshao1/refracgs_dataset)

## 2026-08-30

### Hamiltonian Two-Way Coupling：非线性波浪与 3D 流体的双向耦合

- 类型：论文（ACM TOG / SIGGRAPH Asia 2026；Graphics，cs.GR）
- 核心进展：该工作基于经典 Zakharov 形式构建兼具非线性与色散效应的 2D 波浪模型，并利用其 Hamiltonian 结构，将水面高度和势函数作为正则变量，与局部 3D Navier-Stokes 流体求解器进行一致的双向耦合。信息能够更平滑地穿过 2D/3D 接口，从而抑制反射与接缝伪影。
- 值得关注：论文报告其 2D 求解器的平均波高误差比 SWE、BEM 和 Airy 基线低 1.7-5 倍，同时比 BEM 快超过 1000 倍；完整耦合系统在同一域上比纯 GPU NB-FLIP 仿真快 4 倍以上，为大尺度海面中局部高细节流体模拟提供了实用路线。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2608.25203) · [ACM DOI](https://doi.org/10.1145/3842540)

## 2026-09-01

### Domain-Varying 2D Green's Functions：用于笼式变形的域变化 Green 函数

- 类型：论文（SIGGRAPH Asia 2026；Graphics，cs.GR）
- 核心进展：该工作用 domain-varying Green's functions 重新理解 cage-based deformation，统一 Harmonic Coordinates 与 Green Coordinates。通过控制 Green 函数的定义域，变形可在 cage-consistent 与 shape-preserving 两种性质之间连续调节；圆形和矩形域还支持解析或半解析表达式，圆形域中的 2D simplicial cage 可避免数值积分。
- 值得关注：它为笼式变形提供了一个可调的统一框架，既保留控制笼的一致性，又能按需要减少形状失真；解析/半解析形式也有助于构建更快、更稳定的交互式几何处理工具。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2608.31003) · [ACM DOI](https://doi.org/10.1145/3829340.3842236)

## 2026-09-02

### ARAP Gaussian Radiance Fields：高斯辐射场的尽可能刚性变形

- 类型：论文与开源项目（IEEE TVCG；Graphics，cs.GR）
- 核心进展：该方法面向 3D Gaussian Splatting 的交互式尽可能刚性（ARAP）变形。完成高斯几何编辑后，它进一步优化高斯，使光栅化结果与目标辐射场保持一致；径向特征用于描述变形前后的辐射差异，自适应各向异性空间低通滤波器则抑制采样混叠并适应非均匀采样间隔。
- 值得关注：传统 3DGS 变形往往只移动高斯中心、尺度和方向，几何与最终渲染的辐射场不一致时容易出现伪影。该工作把辐射场一致性纳入变形过程，在保持 3DGS 高质量和实时渲染效率的同时支持大幅交互式编辑，并提供可运行的官方实现。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2608.29538) · [官方代码库](https://github.com/XinhaoT/ARAP-Deformation-of-Gaussian-Radiance-Fields) · [IEEE DOI](https://doi.org/10.1109/TVCG.2025.3555404)

## 2026-09-03

### WildFab：面向真实世界模型的多轴 3D 打印

- 类型：论文（Graphics，cs.GR；同时涉及 Robotics，cs.RO）
- 核心进展：WildFab 用混合查询表示直接处理设计流程、拓扑优化、隐式模型、扫描点云和非流形/非封闭网格。神经无符号距离场（UDF）提供可微表面距离与方向查询，正则化广义绕数场（reg-GWN）负责可靠的表面定位和实体/空腔判别；在此基础上，方法联合计算高精度多轴空间刀路，并以由粗到细的策略规划全局无碰运动。
- 值得关注：传统多轴打印通常要求先修复网格，修复过程可能改变设计意图。WildFab 把几何查询、刀路生成和碰撞检查连成端到端流程，目标是让真实世界的复杂输入更直接地进入设计到制造（design-to-3DP）工作流，并通过多类输入和实体打印结果验证鲁棒性。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2609.02413)

## 2026-09-04

### TileGS：面向 3D Gaussian Splatting 的局部深度分箱光栅化

- 类型：论文（Graphics，cs.GR）
- 核心进展：TileGS 将传统全局排序的长 tile 流重组为多个更短的局部深度区间，在前到后顺序下进行光栅化，并在粗粒度排序不足时执行选择性修复。论文在 9 个场景和 Ada GPU 上评测，默认 No-GW 版本在 RTX 4090 上实现平均 1.44 倍光栅内核加速，端到端帧率相对 gsplat 在 RTX 4090 和 RTX 1000 Ada 上分别提升 1.069 倍和 1.094 倍。
- 值得关注：它把 3DGS 性能瓶颈定位到 tile 遍历和几何属性访问，而不是简单追求更高占用率或更少字节流量；在几乎不改变画质（相对 gsplat 的 PSNR、SSIM、LPIPS 差异均小于 0.001）的前提下减少线程指令，为实时 Gaussian Splatting 渲染器优化提供了可复现的系统方向。
- 来源：[arXiv 原始论文页面](https://arxiv.org/abs/2609.03613)
