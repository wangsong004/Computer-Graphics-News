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
