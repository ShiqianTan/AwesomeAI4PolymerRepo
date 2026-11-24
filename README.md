# AwesomeAI4PolymerRepo

个人收集的 **AI for Polymer / Polymer Informatics** GitHub 项目索引。此 README 根据旧电脑目录 `/Users/shiqian/Documents/github/polymer` 中的本地仓库整理，目的是在换机后快速了解、筛选并重新下载这些项目。

> 盘点日期：2026-11-24。共发现 **59 个带独立 `.git` 的目录**，其中包含上游项目、个人 fork、项目内嵌依赖，以及少量与聚合物相邻的材料信息学项目。项目状态、数据访问方式和许可证可能随上游更新；使用前请再次查看各仓库的 README 和 LICENSE。

## 目录

- [快速恢复](#快速恢复)
- [资源导航与数据集](#资源导航与数据集)
- [表征学习、基础模型与通用预测](#表征学习基础模型与通用预测)
- [生成设计、逆向设计与优化](#生成设计逆向设计与优化)
- [性质预测与具体应用](#性质预测与具体应用)
- [文献挖掘与知识抽取](#文献挖掘与知识抽取)
- [结构生成、模拟与科研工具](#结构生成模拟与科研工具)
- [项目内嵌依赖](#项目内嵌依赖)
- [相邻材料信息学项目](#相邻材料信息学项目)
- [迁移注意事项](#迁移注意事项)

## 快速恢复

### 推荐方式：按需下载

在下面的分类表中点击仓库名称，优先只下载当前研究需要的项目：

```bash
git clone <repository-url>
```

如果使用 SSH，请先在新电脑配置 GitHub SSH key；否则直接使用表格中的 HTTPS 链接。

### 按旧目录结构批量恢复

下面的命令会在当前目录新建 `polymer/`，已存在的目录会自动跳过。两个内嵌依赖和一个相邻材料项目放在后面的可选区，避免不必要的重复下载。

```bash
mkdir -p polymer
cd polymer

clone_to() {
  url="$1"
  target="$2"
  if [ -d "$target/.git" ]; then
    printf 'skip: %s already exists\n' "$target"
  else
    mkdir -p "$(dirname "$target")"
    git clone "$url" "$target"
  fi
}

# 资源导航与数据集
clone_to https://github.com/ShiqianTan/AI4PolymerCommunity.git AI4PolymerCommunity
clone_to https://github.com/ShiqianTan/PolymerDatabaseCollection.git PolymerDatabaseCollection
clone_to https://github.com/Ramprasad-Group/polyVERSE.git Ramprasad-Group/polyVERSE
clone_to https://github.com/Ramprasad-Group/polyVERSE-Structures.git Ramprasad-Group/polyVERSE-Structures

# 表征学习、基础模型与通用预测
clone_to https://github.com/Ramprasad-Group/polyBERT.git Ramprasad-Group/polyBERT
clone_to https://github.com/ShiqianTan/polyBERT.git Ramprasad-Group/PolyBERT_fork/polyBERT.git/polyBERT_fork
clone_to https://github.com/Ramprasad-Group/canonicalize_psmiles.git Ramprasad-Group/canonicalize_psmiles
clone_to https://github.com/ChangwenXu98/TransPolymer.git understanding/TransPolymer
clone_to https://github.com/PchGolden/Uni-Macro.git understanding/Uni-Macro
clone_to https://github.com/hkqiu/PolymerGNN.git hkqiu/PolymerGNN
clone_to https://github.com/crema-lida/PoCo.git contrastive_learning/PoCo
clone_to https://github.com/hkqiu/Unified_ML4Polymers.git hkqiu/Unified_ML4Polymers
clone_to https://github.com/hkqiu/SMILES-vs-BigSMILES.git hkqiu/SMILES-vs-BigSMILES
clone_to https://github.com/sobinalosious/PolyGraphMT.git data/PolyGraphMT
clone_to https://github.com/htang7415/Polymer_UQ.git LiYing/Polymer_UQ
clone_to https://github.com/Ramprasad-Group/Polymer_informatics_beyond_homopolymers.git Ramprasad-Group/Polymer_informatics_beyond_homopolymers

# 生成设计、逆向设计与优化
clone_to https://github.com/ShiqianTan/OMG-MultiProperty-GenML.git generative/OMG-MultiProperty-GenML
clone_to https://github.com/hkqiu/PolymerGenerationPretrainedModel.git hkqiu/PolymerGenerationPretrainedModel
clone_to https://github.com/hkqiu/POLARIS.git hkqiu/POLARIS
clone_to https://github.com/hkqiu/DataAugmentation4SmallData.git hkqiu/DataAugmentation4SmallData
clone_to https://github.com/hkqiu/PolySeek-Plus.git hkqiu/PolySeek-Plus
clone_to https://github.com/Knitua/PolyRL.git RF/PolyRL
clone_to https://github.com/AMETHYST-2025/Multi-Score-RL-for-High-Tg-Polyimide-Design.git RF/Multi-Score-RL-for-High-Tg-Polyimide-Design
clone_to https://github.com/Ramprasad-Group/polyga.git Ramprasad-Group/polyga
clone_to https://github.com/Ramprasad-Group/pvfsga.git Ramprasad-Group/pvfsga
clone_to https://github.com/PEJpOhno/SMiPoly.git SMiPoly
clone_to https://github.com/Ramprasad-Group/bioplastic_design.git Ramprasad-Group/bioplastic_design

# 性质预测与具体应用
clone_to https://github.com/figotj/Copolymer.git Copolymer
clone_to https://github.com/figotj/Fractional-free-volume-of-polymer-membranes.git Fractional-free-volume-of-polymer-membranes
clone_to https://github.com/figotj/Polyimide_explorer.git Polyimide_explorer
clone_to https://github.com/jsunn-y/PolymerGasMembraneML.git PolymerGasMembraneML
clone_to https://github.com/figotj/Polymer_Tg_.git Polymer_Tg_
clone_to https://github.com/figotj/RNN-Tg.git RNN-Tg
clone_to https://github.com/Ramprasad-Group/OPVPerfPredictor.git Ramprasad-Group/OPVPerfPredictor
clone_to https://github.com/Ramprasad-Group/PENN_Melt_Viscosity.git Ramprasad-Group/PENN_Melt_Viscosity
clone_to https://github.com/Ramprasad-Group/PolymerSolarCellsML.git Ramprasad-Group/PolymerSolarCellsML
clone_to https://github.com/Ramprasad-Group/Sublimation_enthalpy_model.git Ramprasad-Group/Sublimation_enthalpy_model
clone_to https://github.com/Ramprasad-Group/copolymer_informatics.git Ramprasad-Group/copolymer_informatics
clone_to https://github.com/Ramprasad-Group/enthalpy_ml_paper_code.git Ramprasad-Group/enthalpy_ml_paper_code
clone_to https://github.com/Ramprasad-Group/green_solvents.git Ramprasad-Group/green_solvents
clone_to https://github.com/Ramprasad-Group/ionic_liquids_nn.git Ramprasad-Group/ionic_liquids_nn
clone_to https://github.com/Ramprasad-Group/polymer-erosion-yield.git Ramprasad-Group/polymer-erosion-yield
clone_to https://github.com/Ramprasad-Group/polymer_in_solvent_solubility_modeling.git Ramprasad-Group/polymer_in_solvent_solubility_modeling
clone_to https://github.com/hkqiu/PPP-1_PredictionTg4Polyimides.git hkqiu/PPP-1_PredictionTg4Polyimides
clone_to https://github.com/hkqiu/ViscosityPredOfEpoxyResin.git hkqiu/ViscosityPredOfEpoxyResin
clone_to https://github.com/Zhilong-Liang/Polymer-Compatibility.git compatability/Polymer-Compatibility
clone_to https://github.com/Elahehkazemi/Descriptor-and-Graph-based-Molecular-Representations-in-Prediction-of-Copolymer-Properties.git copolymer_machine_learning/Descriptor-and-Graph-based-Molecular-Representations-in-Prediction-of-Copolymer-Properties

# 文献挖掘与知识抽取
clone_to https://github.com/Ramprasad-Group/PromptDataExtraction.git Ramprasad-Group/PromptDataExtraction
clone_to https://github.com/Ramprasad-Group/polymerNEN.git Ramprasad-Group/polymerNEN
clone_to https://github.com/Ramprasad-Group/polymer_information_extraction.git Ramprasad-Group/polymer_information_extraction
clone_to https://github.com/Ramprasad-Group/polymer_knowledge_extraction.git Ramprasad-Group/polymer_knowledge_extraction

# 结构生成、模拟与科研工具
clone_to https://github.com/Ramprasad-Group/PSP.git Ramprasad-Group/PSP
clone_to https://github.com/Ramprasad-Group/ML-DFT.git Ramprasad-Group/ML-DFT
clone_to https://github.com/Ramprasad-Group/polyGen.git Ramprasad-Group/polyGen
clone_to https://github.com/Ramprasad-Group/csst_analyzer.git Ramprasad-Group/csst_analyzer
clone_to https://github.com/Ramprasad-Group/LSE.git Ramprasad-Group/LSE
```

可选的内嵌依赖及相邻材料项目：

```bash
clone_to https://github.com/coleygroup/polymer-chemprop.git copolymer_machine_learning/Descriptor-and-Graph-based-Molecular-Representations-in-Prediction-of-Copolymer-Properties/external/polymer-chemprop
clone_to https://github.com/aspuru-guzik-group/group-selfies.git generative/OMG-MultiProperty-GenML/group-selfies
clone_to https://github.com/Ramprasad-Group/spall_strength_prediction.git Ramprasad-Group/spall_strength_prediction
```

## 资源导航与数据集

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [AI4PolymerCommunity](https://github.com/ShiqianTan/AI4PolymerCommunity) | `AI4PolymerCommunity` | 面向 AI 驱动聚合物发现的综合门户，汇总论文、数据库、教程、算法和在线预测工具。个人维护仓库。 |
| [PolymerDatabaseCollection](https://github.com/ShiqianTan/PolymerDatabaseCollection) | `PolymerDatabaseCollection` | 聚合物实验/计算数据库、基准、光谱与数据工具的分类指南。个人维护仓库。 |
| [polyVERSE](https://github.com/Ramprasad-Group/polyVERSE) | `Ramprasad-Group/polyVERSE` | Ramprasad Group 整理的已知/虚拟聚合物及多种性质的 informatics-ready 数据集。 |
| [polyVERSE-Structures](https://github.com/Ramprasad-Group/polyVERSE-Structures) | `Ramprasad-Group/polyVERSE-Structures` | polyVERSE 对应的聚合物分子动力学结构文件集合。通常体积较大，按需下载。 |

## 表征学习、基础模型与通用预测

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [polyBERT](https://github.com/Ramprasad-Group/polyBERT) | `Ramprasad-Group/polyBERT` | 基于 PSMILES 的聚合物化学语言模型，用于快速生成指纹和多性质预测；学术非商业许可。 |
| [polyBERT fork](https://github.com/ShiqianTan/polyBERT) | `Ramprasad-Group/PolyBERT_fork/polyBERT.git/polyBERT_fork` | 上述 polyBERT 的个人 fork；若没有个人修改，可只保留上游仓库。 |
| [canonicalize_psmiles](https://github.com/Ramprasad-Group/canonicalize_psmiles) | `Ramprasad-Group/canonicalize_psmiles` | PSMILES 规范化工具；上游建议新项目优先使用功能更完整的 `psmiles` 包。 |
| [TransPolymer](https://github.com/ChangwenXu98/TransPolymer) | `understanding/TransPolymer` | 在约 500 万聚合物序列上预训练的 Transformer，并通过微调用于下游性质预测。 |
| [Uni-Macro](https://github.com/PchGolden/Uni-Macro) | `understanding/Uni-Macro` | 支持单/多 SMILES 输入的通用大分子数据预处理与下游训练框架。 |
| [PolymerGNN](https://github.com/hkqiu/PolymerGNN) | `hkqiu/PolymerGNN` | 聚合物性质预测 GNN，包含可解释性、数据预处理与训练工具。 |
| [PoCo](https://github.com/crema-lida/PoCo) | `contrastive_learning/PoCo` | 聚合物对比表征学习框架，面向性质预测和模型可解释性。 |
| [Unified_ML4Polymers / PolyNC](https://github.com/hkqiu/Unified_ML4Polymers) | `hkqiu/Unified_ML4Polymers` | 融合自然语言与化学语言的统一聚合物性质预测模型。 |
| [SMILES-vs-BigSMILES](https://github.com/hkqiu/SMILES-vs-BigSMILES) | `hkqiu/SMILES-vs-BigSMILES` | 比较 SMILES 与 BigSMILES 在聚合物机器学习流程中的表现。 |
| [PolyGraphMT](https://github.com/sobinalosious/PolyGraphMT) | `data/PolyGraphMT` | 多任务、多保真聚合物图神经网络，支持多种 PyG 骨干、条件编码和不确定性头。 |
| [Polymer_UQ](https://github.com/htang7415/Polymer_UQ) | `LiYing/Polymer_UQ` | 聚合物 Tg、带隙、熔点和分解温度预测的不确定性量化基准。 |
| [Polymer_informatics_beyond_homopolymers](https://github.com/Ramprasad-Group/Polymer_informatics_beyond_homopolymers) | `Ramprasad-Group/Polymer_informatics_beyond_homopolymers` | 面向均聚物之外体系的多任务分类/回归及元学习 notebook。 |

## 生成设计、逆向设计与优化

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [OMG-MultiProperty-GenML](https://github.com/ShiqianTan/OMG-MultiProperty-GenML) | `generative/OMG-MultiProperty-GenML` | 结合 Group SELFIES、VAE、性质模型与贝叶斯优化的聚合物多性质生成设计流程；个人 fork。 |
| [PolymerGenerationPretrainedModel / PolyTAO](https://github.com/hkqiu/PolymerGenerationPretrainedModel) | `hkqiu/PolymerGenerationPretrainedModel` | 面向按需逆向设计的聚合物生成预训练模型，模型权重托管于 Hugging Face。 |
| [POLARIS](https://github.com/hkqiu/POLARIS) | `hkqiu/POLARIS` | 面向聚合物 mRNA 递送载体发现的门控生成与自适应逆向推断平台。 |
| [DataAugmentation4SmallData](https://github.com/hkqiu/DataAugmentation4SmallData) | `hkqiu/DataAugmentation4SmallData` | 针对小样本耐热聚合物发现的数据增强 GNN、解释与逆向设计流程。 |
| [PolySeek-Plus](https://github.com/hkqiu/PolySeek-Plus) | `hkqiu/PolySeek-Plus` | PolySeek+ 预告/占位仓库；本地 README 尚无实现说明。 |
| [PolyRL](https://github.com/Knitua/PolyRL) | `RF/PolyRL` | 用强化学习生成并多目标优化 CO₂/N₂ 分离聚合物膜。 |
| [Multi-Score-RL-for-High-Tg-Polyimide-Design](https://github.com/AMETHYST-2025/Multi-Score-RL-for-High-Tg-Polyimide-Design) | `RF/Multi-Score-RL-for-High-Tg-Polyimide-Design` | 比较模型分数、Shapley 分数与相似度组合策略的高 Tg 聚酰亚胺强化学习设计。 |
| [polyga](https://github.com/Ramprasad-Group/polyga) | `Ramprasad-Group/polyga` | 用遗传算法直接演化和优化聚合物候选。 |
| [pvfsga](https://github.com/Ramprasad-Group/pvfsga) | `Ramprasad-Group/pvfsga` | 通过反应模板进行虚拟正向合成，再用遗传算法优化可合成聚合物。 |
| [SMiPoly](https://github.com/PEJpOhno/SMiPoly) | `SMiPoly` | 规则驱动的单体分类与聚合物重复单元虚拟库生成工具。 |
| [bioplastic_design](https://github.com/Ramprasad-Group/bioplastic_design) | `Ramprasad-Group/bioplastic_design` | 用多任务神经网络筛选 PHA 生物塑料替代品；预测器本体通过 Polymer Genome 提供。 |

## 性质预测与具体应用

### 热学、流变与热力学

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [Polymer_Tg_](https://github.com/figotj/Polymer_Tg_) | `Polymer_Tg_` | 高温聚合物发现项目，包含基于指纹的 Tg 深度神经网络和数据说明。 |
| [RNN-Tg](https://github.com/figotj/RNN-Tg) | `RNN-Tg` | 把聚合物表示视为化学语言，以 RNN/DNN 预测玻璃化转变温度。 |
| [PPP-1_PredictionTg4Polyimides](https://github.com/hkqiu/PPP-1_PredictionTg4Polyimides) | `hkqiu/PPP-1_PredictionTg4Polyimides` | 使用 GNN 预测和定向设计聚酰亚胺 Tg。 |
| [PENN_Melt_Viscosity](https://github.com/Ramprasad-Group/PENN_Melt_Viscosity) | `Ramprasad-Group/PENN_Melt_Viscosity` | 将物理规律嵌入神经网络的聚合物熔体黏度预测实现。 |
| [ViscosityPredOfEpoxyResin](https://github.com/hkqiu/ViscosityPredOfEpoxyResin) | `hkqiu/ViscosityPredOfEpoxyResin` | 不同温度下环氧树脂与稀释剂黏度预测的数据和补充代码。 |
| [enthalpy_ml_paper_code](https://github.com/Ramprasad-Group/enthalpy_ml_paper_code) | `Ramprasad-Group/enthalpy_ml_paper_code` | 焓机器学习论文分析 notebook；指纹需由用户自行生成。 |
| [Sublimation_enthalpy_model](https://github.com/Ramprasad-Group/Sublimation_enthalpy_model) | `Ramprasad-Group/Sublimation_enthalpy_model` | 小分子升华焓预测模型与 Colab；注意其主要对象不是聚合物。 |

### 膜、溶解度与相容性

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [PolymerGasMembraneML](https://github.com/jsunn-y/PolymerGasMembraneML) | `PolymerGasMembraneML` | 建立聚合物化学结构与气体渗透率之间的可解释模型，用于气体分离膜发现。 |
| [Fractional-free-volume-of-polymer-membranes](https://github.com/figotj/Fractional-free-volume-of-polymer-membranes) | `Fractional-free-volume-of-polymer-membranes` | 用机器学习替代 Bondi 基团贡献法预测聚合物膜自由体积分数。 |
| [Polymer-Compatibility](https://github.com/Zhilong-Liang/Polymer-Compatibility) | `compatability/Polymer-Compatibility` | 结合文本挖掘、HDDN 与 Hansen 溶解度参数研究聚合物相容性。 |
| [polymer_in_solvent_solubility_modeling](https://github.com/Ramprasad-Group/polymer_in_solvent_solubility_modeling) | `Ramprasad-Group/polymer_in_solvent_solubility_modeling` | 用广义化学指纹和机器学习为聚合物选择溶剂。 |

### 共聚物与聚酰亚胺

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [Copolymer](https://github.com/figotj/Copolymer) | `Copolymer` | 同时编码单体组成与随机/嵌段/梯度序列分布的共聚物性质模型。 |
| [copolymer_informatics](https://github.com/Ramprasad-Group/copolymer_informatics) | `Ramprasad-Group/copolymer_informatics` | 用多任务深度神经网络和元学习进行共聚物信息学建模。 |
| [Descriptor-and-Graph-based-Molecular-Representations-in-Prediction-of-Copolymer-Properties](https://github.com/Elahehkazemi/Descriptor-and-Graph-based-Molecular-Representations-in-Prediction-of-Copolymer-Properties) | `copolymer_machine_learning/Descriptor-and-Graph-based-Molecular-Representations-in-Prediction-of-Copolymer-Properties` | 比较分子描述符随机森林与 wD-MPNN 对共聚物热力学性质的预测。 |
| [Polyimide_explorer](https://github.com/figotj/Polyimide_explorer) | `Polyimide_explorer` | 可解释机器学习与高通量筛选聚酰亚胺热学/力学性质，并提供大规模假想候选库。 |

### 能源、电子、可持续与特殊应用

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [PolymerSolarCellsML](https://github.com/Ramprasad-Group/PolymerSolarCellsML) | `Ramprasad-Group/PolymerSolarCellsML` | 从文献抽取并人工整理聚合物太阳能电池数据，预测 PCE 并模拟主动学习。 |
| [OPVPerfPredictor](https://github.com/Ramprasad-Group/OPVPerfPredictor) | `Ramprasad-Group/OPVPerfPredictor` | 基于 TinyLlama 微调适配器，从有机太阳能电池文本描述预测 PCE、JSC、VOC 和 FF。 |
| [ionic_liquids_nn](https://github.com/Ramprasad-Group/ionic_liquids_nn) | `Ramprasad-Group/ionic_liquids_nn` | 用深度神经网络预测纯组分/二元离子液体电导率。 |
| [green_solvents](https://github.com/Ramprasad-Group/green_solvents) | `Ramprasad-Group/green_solvents` | 预测溶剂综合绿色评分，并结合 HSP/RED 推荐更可持续的替代溶剂。 |
| [polymer-erosion-yield](https://github.com/Ramprasad-Group/polymer-erosion-yield) | `Ramprasad-Group/polymer-erosion-yield` | 低地球轨道原子氧环境下的聚合物侵蚀产额数据集及 LLM 预测器。 |

## 文献挖掘与知识抽取

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [PromptDataExtraction](https://github.com/Ramprasad-Group/PromptDataExtraction) | `Ramprasad-Group/PromptDataExtraction` | 使用 MaterialsBERT、GPT-3.5 和 Llama 2 从聚合物文献自动抽取数据。 |
| [polymerNEN](https://github.com/Ramprasad-Group/polymerNEN) | `Ramprasad-Group/polymerNEN` | 聚合物命名实体归一化，用于把文献中的多种名称映射到一致实体。 |
| [polymer_information_extraction](https://github.com/Ramprasad-Group/polymer_information_extraction) | `Ramprasad-Group/polymer_information_extraction` | 面向大规模聚合物语料的通用材料性质抽取流水线。 |
| [polymer_knowledge_extraction](https://github.com/Ramprasad-Group/polymer_knowledge_extraction) | `Ramprasad-Group/polymer_knowledge_extraction` | 早期聚合物文献自动知识抽取项目的代码、数据与训练示例。 |

## 结构生成、模拟与科研工具

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [PSP](https://github.com/Ramprasad-Group/PSP) | `Ramprasad-Group/PSP` | 从聚合物 SMILES 构建单体、低聚物、无限链、晶体和无定形三维结构，并生成力场参数。 |
| [ML-DFT](https://github.com/Ramprasad-Group/ML-DFT) | `Ramprasad-Group/ML-DFT` | 从 POSCAR 预测电子密度、态密度、势能、力和应力等 DFT 级性质；学术非商业许可。 |
| [polyGen](https://github.com/Ramprasad-Group/polyGen) | `Ramprasad-Group/polyGen` | 以分子图为条件，在联合潜空间中用自编码器和扩散模型生成原子级聚合物结构。 |
| [csst_analyzer](https://github.com/Ramprasad-Group/csst_analyzer) | `Ramprasad-Group/csst_analyzer` | 自动加载、处理和分析 Crystal 16 溶解/溶解度实验数据。 |
| [LSE](https://github.com/Ramprasad-Group/LSE) | `Ramprasad-Group/LSE` | 从 MOF 的 CIF 结构中提取连接体 SMILES；属于相邻化学信息学工具。 |

## 项目内嵌依赖

这些目录本身带 `.git`，但位于另一个项目内部。恢复父项目后先检查是否已经通过 submodule、安装脚本或 vendoring 获得，再决定是否单独克隆。

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [polymer-chemprop](https://github.com/coleygroup/polymer-chemprop) | `copolymer_machine_learning/.../external/polymer-chemprop` | 支持聚合物加权图表示的 wD-MPNN/Chemprop 分支，是共聚物描述符/GNN 项目的外部依赖。 |
| [group-selfies](https://github.com/aspuru-guzik-group/group-selfies) | `generative/OMG-MultiProperty-GenML/group-selfies` | 基团级 SELFIES 表示工具，是 OMG 多性质生成项目中的外部依赖。 |

## 相邻材料信息学项目

| 项目 | 原目录 | 内容概要 |
| --- | --- | --- |
| [spall_strength_prediction](https://github.com/Ramprasad-Group/spall_strength_prediction) | `Ramprasad-Group/spall_strength_prediction` | 金属与合金剥落强度数据集及 GPR 模型；不是聚合物项目，但保留以免迁移时遗漏。 |

## 迁移注意事项

1. **先检查许可证。** 多个 Ramprasad Group 仓库明确限制为学术、非商业使用，数据也可能有单独条款。
2. **代码仓库不等于完整数据。** PolyInfo、Khazana、Zenodo、Hugging Face、Polymer Genome 等外部数据/权重通常需要另外下载。
3. **大文件要单独核对。** 如果仓库使用 Git LFS，安装 `git-lfs` 后执行 `git lfs pull`；大型数据库和结构库建议按需恢复。
4. **保留个人 fork 的修改。** `ShiqianTan/*` 仓库优先从自己的远端下载；确认与上游一致后再决定是否删除重复副本。
5. **记录运行环境。** 这些项目跨越 Python 3.6–3.11、不同 RDKit/PyTorch 版本，最好每个仓库独立创建 Conda/uv/Poetry 环境。
6. **检查子模块。** 对包含 `.gitmodules` 的仓库，使用 `git clone --recurse-submodules <url>` 或在克隆后执行 `git submodule update --init --recursive`。
7. **避免盲目批量安装依赖。** 先读项目 README，再选择需要复现的项目；老项目的锁定版本可能与新电脑或新 CUDA 不兼容。

## 维护建议

- 新增项目时记录：仓库链接、用途、核心方法、数据来源、许可证、最后验证日期。
- 每隔一段时间运行 `git remote -v` 和 `git status`，确认 fork 中是否存在未推送修改。
- 如果某个仓库只作为另一个项目的依赖，把它放进“项目内嵌依赖”，避免重复统计。
- 对真正需要长期复现的项目，额外保存环境文件、数据 DOI、模型权重链接和论文引用。
