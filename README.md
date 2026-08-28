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
