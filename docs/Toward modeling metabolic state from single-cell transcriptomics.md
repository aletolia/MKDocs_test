### 摘要

#### 背景

单细胞代谢研究为细胞功能带来了新的见解，这些见解通常无法在其他组学层面上捕捉到。代谢信息具有广泛的应用，例如研究细胞异质性、理解药物机制和生物标志物开发。然而，单细胞水平的代谢测量受到不足的可扩展性和灵敏度以及资源密集性的限制，目前无法与常用于识别细胞类型的转录状态测量同时进行。然而，由于组学层面紧密交织在一起，可以基于更易测量的组学层面的数据以及先前的代谢网络知识进行代谢预测。

#### 综述范围

我们总结了当前单细胞代谢测量和建模方法的现状，强调了使用计算技术的动机。我们回顾了用于单细胞代谢预测的三大类计算方法：路径级分析、基于约束的建模和动力学建模。我们描述了从整体到单细胞建模时出现的独特挑战。最后，我们提出了可能的模型扩展和可以利用的计算方法，以实现这些目标。

#### 主要结论

单细胞代谢建模是一个新兴领域，为理解细胞功能提供了新的视角。所提出的建模方法在输入要求和假设、可扩展性、建模的代谢层面和新获得的见解方面有所不同。我们相信，使用先前的代谢知识将导致更稳健的预测，并将为机械和可解释的机器学习模型铺平道路。

![](https://ars.els-cdn.com/content/image/1-s2.0-S2212877821002532-ga1_lrg.jpg)

### 1. Introduction

多模态单细胞分析可以通过不同的组学层面对单个细胞进行稳健研究，这些组学层面描述了特定的细胞过程：DNA 测序可以揭示谱系结构，染色质可及性测量用于研究表观基因组事件，RNA 测序和蛋白质测量揭示了细胞在刺激和发育过程中出现的分子状态。所有这些细胞的分子视图都可以通过使用特定的化学程序在高通量中直接观察到；因此，单细胞生物学的许多最新进展集中在这些组学层面上。我们想要关注一个研究较少的领域，即观察单细胞代谢。它包括生产和降解细胞构建成分以及提供能量所需的代谢反应。代谢位于其他组学的下游，因此总结了表观基因组、基因组和转录组的上游层面的影响，以及营养耗竭等细胞外影响。因此，它提供了细胞表型的非常有意义的读数，并且已被证明与疾病状态密切相关或用于开发有效的生物标志物。

单细胞代谢分析主要包括对单个细胞或其部分（代谢组）中代谢物浓度的研究，代谢物流量（通量组）的研究，这些通量描述了代谢物浓度变化的速率，以及由酶活性控制的单个反应的通量。所有这些都与现代单细胞生物学相关，其核心是细胞类型多样性和细胞状态转变。首先，代谢差异可以识别细胞状态异质性，这是理解组织功能和微生物群体的关键，因为代谢变化可能在其他组学层面上无法观察到。其次，代谢测量可以用于解析个体细胞类型的代谢机制，细化目前可用的全生物体代谢网络。这可以应用于理解跨细胞群体的药物靶标和副作用，类似于以前在整体组织水平上所做的研究，或理解个体细胞中药物抗性的产生。第三，代谢物交换是组织中细胞依赖的关键机制，邻近细胞之间的相互作用在组织形成和功能中起着至关重要的作用。

代谢组学技术的最新进展使得单细胞水平的测量成为可能，最近的综述中也有重点介绍实验应用、空间代谢组学和蛋白质组学以及多组学分析。然而，单细胞代谢组学技术仍然有限，需要进一步改进才能广泛应用。代谢组学测量费用高、技术要求高，需要在测量灵敏度和样品及代谢物通量方面进行改进。相比之下，广泛使用的单细胞 RNA 测序（scRNA-seq）数据集通常包括数千个细胞和基因，而代谢组学数据集通常包括几十到几百个代谢物和细胞。因此，它们仅覆盖了细胞代谢的一小部分，可能会错过稀有细胞类型，由于细胞数量少，每个细胞提供的代谢视图噪声大，导致稳健性较低。缺乏同时测量代谢组和转录组的成熟技术可能会在先前转录组研究的背景下复杂化，并阻碍细胞类型的注释，这通常在转录组数据上完成。然而，方法改进正在进行中。

由于组学层面紧密交织，关于可以在单个细胞中更容易测量的组学层面的知识，如 mRNA，加上关于代谢的先前知识，使得能够预测细胞的通量组、代谢组和反应通量，提供了单细胞代谢组学测量的有前途的替代方案。这可以用来识别导致不同代谢状态的代谢机制的变化。代谢建模依赖于已建立的代谢网络模型，这些模型提供了关于可行代谢转化的先前信息，以及用于定义特定生物学背景约束的大量单细胞测序测量。概念上，单细胞代谢建模而不是整体建模（图 1）带来了额外的挑战，导致了新的代谢建模范式的发展。首先，模型需要扩展到大量细胞。其次，联合建模多个相似或潜在相邻且通信的细胞，使得参数可以在细胞之间共享。这可能会增加稳健性，这在使用噪声大的 scRNA-seq 数据时尤为重要；然而，已知细胞具有不同的代谢功能，必须在建模假设中考虑到这一点。第三，代谢物交换在细胞群体中起重要作用，这导致细胞之间代谢物可用性依赖，并违反了单细胞建模其他分支中常见的独立性假设。我们回顾并比较了主要基于转录组数据的单细胞代谢计算建模方法。

![](https://ars.els-cdn.com/content/image/1-s2.0-S2212877821002532-gr1_lrg.jpg)

> 图 1. 整体分析与单细胞分析。整体分析假设细胞是相同的，并且可以建模细胞与环境之间的交换。单细胞分析考虑了细胞异质性，并且可以建模不同细胞之间以及单个细胞与环境之间的交换。

### 2. Resources for Metabolic Modeling

代谢建模的先前知识包括基因组规模的代谢模型（GEM）和代谢通路集合，这些都可以在大型、经过整理的数据库中获取。代谢通路集合将反应汇总到路径中。基因组规模的代谢模型提供了基因 - 蛋白质 - 反应 - 代谢物和基因 - 蛋白质 - 运输 - 代谢物关联的系统编码，描述了生物体的整个代谢。虽然路径数据库主要用于解释，GEMs 则允许在系统范围内预测代谢。然而，这两者通常涵盖了可能的代谢转化的整个范围，这些转化并不共同发生在单个细胞中。

最广泛使用的路径库是 KEGG，Reactome 和 MetaCyc。可以从 BiGG，BioModels 和其他库中获取基因组规模的代谢模型。人类代谢的建模通常依赖于来自 Recon 和 Human Metabolic Reaction 系列的 GEMs，这些资源正在不断改进。GEMs 还可以从 KEGG 或其他资源中重新构建，通常会进行人工整理。为了在资源之间实现比较和知识整合，需要进行标准化工作。为了利用可用资源，代谢建模工具应能够接受不同模型作为输入，使用标准格式，如 GEMs 的 MAT（mat）或 SBML（xml）。

从特定参考组织测量的代谢物浓度可以用作计算模型的验证数据。这些数据集可以从专门的数据库中获得，包括 MetaboLights 和 Metabolomics Workbench。由于测量细胞水平代谢异质性可能存在困难，另一种验证选项是来自具有已知代谢效应的环境或遗传扰动系统的整体表达或代谢数据集。

### 3. Modelling Approaches

我们确定了用于单细胞水平代谢预测的三大类方法（图 2）：（A）路径级分析，从关联基因的基因表达信息中推导路径表型关联或活动，在某些情况下包括路径拓扑，（B）基于约束的建模，旨在根据 GEMs 中的基因表达和反应化学计量信息预测完整的细胞代谢组和反应活动，以及（C）动力学模型，使用高参数化的微分方程系统，结合测量数据来预测已知系统的代谢物浓度。

![](https://ars.els-cdn.com/content/image/1-s2.0-S2212877821002532-gr2_lrg.jpg)

> 图 2. 代谢建模方法
>
> (A) 路径级分析假设基因表达直接映射到酶浓度或反应活性。它可用于定义在差异表达基因中富集的路径，或通过传播活动计算单个路径的活动（机械路径分析）。
>
> (B) 基于约束的分析假设代谢物浓度是恒定的，并基于此定义可能的通量，这些通量会导致这样的系统，如在主文中进一步描述的那样。即，通过将反应通量与定义每个反应中代谢物转换的化学计量矩阵相乘获得被约束为零的代谢物流量。这给出了一个未定方程系统，定义了可能的反应通量分布。然后基于优化目标（例如基因表达与酶活性之间的一致性）选择最佳通量配置。
>
> (C) 动力学模型基于详细的先前代谢知识和关于代谢物和酶可用性的信息预测代谢变化。基因表达可用于预测酶浓度。

#### 3.1. Pathway-level Analysis

路径级分析（图 2A）通过差异表达或偶尔的标准化表达信息直接预测路径活性或表型关联，有时包括路径拓扑。它侧重于单个路径而不是整个代谢，并且不考虑反应机制，如化学计量或代谢物丰度。现有许多用于路径分析的工具，大多数情况下为整体数据设计的方法可以直接应用于单细胞数据。为了依赖整体数据工作流程并减少稀疏性，分析通常在伪整体数据上进行。在这篇综述中，我们重点介绍了为 scRNA-seq 数据开发的方法。

目前，基于 scRNA-seq 数据的代谢分析最常用的方法是差异表达分析和路径富集分析，并使用通用富集方法。另一种方法是从路径相关基因的基因表达推断路径活性。

如上所述，路径级分析存在一些缺点。首先，经过整理的路径定义旨在捕捉不同生物学背景下的整个生物过程，而不考虑复杂的调控相互作用，因此包含的基因比任何特定细胞状态或类型所涉及的基因更多。预定义路径可能由响应不同方向扰动的基因组成，导致富集分析中的假阴性，这可以通过定义上下文特定路径来解决。其次，路径富集不考虑跨多个路径的生物变化，也不利用调控和反应相互作用的信息。例如，整个路径的活性取决于链中所有酶的活性，中间酶的下调可能导致代谢瓶颈，即使其他酶高度活跃也会导致路径活性降低。已开发的方法包括路径拓扑信息或启用数据驱动的路径发现。例如，为了确定关键基因和代谢物，scMetNet 基于 KEGG 构建代谢网络，然后找到在细胞群体中显著差异表达的子模块。同样，scPPIN 用于基于 scRNA-seq 数据识别蛋白质 - 蛋白质相互作用网络中差异活跃的模块，但也可能适用于代谢网络。另一种选择是报告代谢物分析，如 perturb-Met，旨在通过分析代谢物相关基因表达的变化来识别受影响的代谢物。

#### 3.2. Constraint-based Modelling

##### 3.2.1. Background

稳态约束模型是用于大规模系统最广泛使用的代谢建模方法组。它们假设，由于组学层时间尺度的分离，代谢处于准稳态相对于表达和其他长期过程，然后搜索所有产生该稳态系统的反应通量配置，选择一个基于关于系统的先前生物学知识最大化某个目标函数的配置（图 2B）。准稳态假设的支持理由如下：传统观点认为，细胞代谢系统中的代谢物处于质量平衡，这意味着代谢物相互转化使所有分子质量得到计算。为了维持这个系统，细胞需要外部能源和起始产物以及终产物的处置机制。由于代谢反应非常快，发生在毫秒级别，相比之下酶基因表达在几十分钟的时间尺度上运行，反应在大多数情况下相对迅速地达到平衡，导致代谢稳态。

基于约束的方法依赖于系统范围内的化学计量、热力学和基因关联信息，这些信息由 GEMs 提供 [27]。在最广泛使用的基于约束的代谢建模方法中，通量平衡分析（FBA）最为常见，其中代谢网络由代谢物（行）和反应（列）的化学计量矩阵（ $S$ ）编码。反应通量（ $v$ ）通过假设系统处于稳态，即代谢物浓度（ $d x / d t$ ）不变，得到：

$$
S v = d x / d t = 0
$$

由于 $S v = 0$ 系统中方程数（代谢物数量，人在 8000 个以上）少于变量数（反应通量数量，人在 13000 个以上），该方法导致欠定系统，具有可能的通量分布的整个子空间。在许多情况下，可以基于优化目标使用线性规划恢复单一解，这依赖于系统的先验知识 [68,69,72,73]

基于约束的方法依赖于系统范围内的化学计量、热力学和反应的基因关联信息，这些信息由 GEMs 提供 [27]。在最广泛使用的基于约束的代谢建模方法中，通量平衡分析（FBA）最为常见，其中代谢网络由代谢物（行）和反应（列）的化学计量矩阵（ $S$ ）编码。反应通量（ $v$ ）通过假设系统处于稳态，即代谢物浓度（ $d x / d t$ ）不变，得到：

$$
S v = d x / d t = 0
$$

由于 $S v = 0$ 系统中方程数（代谢物数量，人在 8000 个以上 [49]）少于变量数（反应通量数量，人在 13000 个以上 [49]），该方法导致欠定系统，具有可能的通量分布的整个子空间。在许多情况下，可以基于优化目标使用线性规划恢复单一解，这依赖于系统的先验知识 [68,69,72,73]。

建模目标用于选择单一反应通量配置，分为两类。一方面，一些目标基于关于细胞目的的一般假设，例如最大生长速率、ATP 生产或它们的组合，这可能更好地对应于细胞行为 [38,46,68]。另一方面，一些模型依赖于系统特定数据，例如 RNA 测序、部分代谢组学测量或文献中的信息。当基于理论的生物学目标未知或由于系统复杂性而不适用如生长最大化等简单目标时，基于测量的目标非常有用 [45,46,69,72,74]。整合如 scRNA-seq 等测量数据，可以实现特定上下文的预测，例如特定细胞类型、发育阶段或患者 [27,38]。这些约束可以通过不同方式在线性规划中考虑，包括通过调整 GEMs 或反应速率边界、强制通量遵循组学测量或通过将通量从低组学活动支持的反应重新分配到高组学活动支持的反应 [50,69,72]。

#### 3.2.2. 约束建模应用于 scRNA-seq 数据

目前有两种主要方法用于 scRNA-seq 约束建模，即 FBA 和 GEM 指导的深度神经网络（DNN）模型。已提出多种方法将 FBA 适应于单细胞推断。最简单的方法是基于 scRNA-seq 数据构建上下文特定的 GEMs，然后在每个上下文特定的 GEM 上进行经典的 FBA，如 [75] 所提议，使用特定代谢物生产作为优化目标。另一种选择是 MERGE，它优化低表达基因承载较少通量的反应，反之亦然，并优化整体低通量 [50]。此外，Compass[45] 首先计算每个反应的最大理论可能通量，然后选择减少反应惩罚的通量配置，惩罚与基因表达成反比。scFBA 计算最大理论可能通量，使用 scRNA-seq 数据为可能的通量分布增加一个额外约束，并基于最大生物量生产选择最佳通量分布 [46]。

另一种补充方法在 scFEA 中实现，它使用图神经网络对代谢图进行建模。GEM 被编码为一个有向因子图，反应模块作为变量（未知量或随机变量），中间代谢物作为因子（变量函数），有向边表示底物和产物关系。scFEA 训练网络从 scRNA-seq 输入中学习反应通量，以最小化代谢物通量不平衡。添加了额外的损失组件以抑制负反应通量，并促进反应通量与基因表达之间的一致性，以避免零反应通量的简单解决方案。可解释的 DNN 结构和预测可以直接用于推理细胞代谢。基因的较高权重表明基因表达变化对预测反应通量的影响较大，对应于速率限制反应。此外，高代谢物通量不平衡的路径可能表明代谢压力。

所提出的模型对细胞代谢做出不同的假设。例如，一些方法使用 RNA-seq 数据作为约束并优化细胞生长最大化，而另一些方法仅基于与 scRNA-seq 数据的一致性进行优化。在基于 FBA 的方法中，代谢稳态假设被强制执行，而在 scFEA 中，它被用作优化目标的一个组成部分。此外，scFEA 和 scFBA 假设细胞交换代谢物，处于一个混合良好的环境中，从而为所有细胞共同解决代谢模型 [20,46]。

一个关键挑战是从基因表达到酶活性的映射，各方法对此处理不同。首先，由于不同的基因翻译和酶动力学速率，这种映射理想情况下应该是基因特定的，并且由于细胞内环境对酶动力学的影响，应该是细胞状态特定的。这些挑战可以通过 DNN 模型解决，例如在 scFEA 中所做的那样，并通过整合额外的细胞状态特定的先验知识。其次，映射应建模为符合 Michaelis–Menten 动力学的非线性函数，这在 scFEA 中通过多个神经网络层近似。酶同工酶（或关系）和复合物（与关系）使映射复杂化。第三，由于技术伪影和组学层之间半衰期的差异，基因表达和酶活性可能不对应。因此，通过低表达基因的反应的通量最小化比基于固定表达阈值修剪 GEM 更不容易出现假阴性。如果高度表达的基因在底物可用性低的反应中具有低通量，则不应惩罚这些基因。

与整体相比，单细胞代谢建模的一个重要方面是克服 scRNA-seq 输入的噪声和稀疏性，这可以通过多种方式实现。最常见的方法是共享细胞间的信息，或者通过使用伪整体数据，通过共享相似细胞之间的通量分布信息，或者通过联合建模所有细胞的代谢。数据也可以在基因之间汇集，通过建模汇集的反应模块而不是单个反应，或者假设相邻基因相互影响，从而在它们之间共享表达变化的信息。用于 GEM 修剪的未表达基因的定义受到 scRNA-seq 数据中脱落引起的假阳性的影响。这可以使用统计方法或匹配的整体表达数据来缓解。

由于数据集规模不断增长，这些方法必须具有计算效率。计算效率的两个核心范式出现了。首先，代谢状态的数量可以从全部代谢物和隔室减少到更粗略的代谢网络，通过反应汇集，移除基于表达数据预测为不活跃的反应，或仅建模反应子集，如核心代谢。其次，推理过程必须扩展到许多观测，因为通常有成千上万个细胞，这比整体考虑的数量大几个数量级。常见的加速技术是汇集和类似细胞的每组建模。

总体而言，单细胞基于约束的建模领域正在迅速扩展，需要系统的基准测试来推荐最佳建模选择。在基于 FBA 的方法中，Compass 因其建模选择和用户友好性而脱颖而出。DNN 方法承诺更大的模型灵活性和理想的扩展特性，因此 scFEA 代表了一个有趣的替代方案。

#### 3.3. 动力学模型

动力学模型有不同的应用。首先，动力学模型可用于定量而非相对预测环境和参数值扰动的效应。它们从预定义的初始代谢状态开始，解决具有详细动力学和调控信息的一组微分方程，该状态以定义的酶和代谢物浓度为特征。这与 FBA 形成对比，后者不需要任何代谢物浓度输入。然而，浓度和动力学参数信息稀缺，这使得动力学模型在大系统的建模中基本不可用。这在单细胞系统中更加复杂，因为动力学参数可能因细胞内环境不同（如 pH 值和辅因子可用性）而异。其次，动力学模型上的模型选择和协变量建模可以用于理解导致特定代谢状态的代谢机制。例如，基因变异引起的酶活性细微变化可以在这种动力学模型中考虑，但在基于约束的模型中无法检测到。第三，许多情况下，对刺激响应的时间分辨代谢物浓度建模是有兴趣的。与通常间隔数小时或数天的单细胞时间序列测量可获得的时间洞察形成对比，动力学建模能够从初始测量的代谢状态开始，在更快的代谢时间尺度上进行预测。此外，动力学模型在时间上解决微分方程系统，因此不依赖于稳态假设。因此，当稳态假设不成立时，它们是基于约束建模的替代方法。

提出了一种利用 scRNA-seq 数据估计酶浓度的动力学模型。该方法基于动力学参数变化的变化高效预测代谢变化。他们使用高斯混合模型对产物浓度进行建模。模型由反应催化项组成，条件是可以通过单细胞测量通知的酶浓度。动力学模型和测量数据的组合也可用于推断确定反应动力学的样本特异性动力学参数。这样的样本特异性动力学参数可用于理解跨组织的动力学异质性，从而通过细胞图谱扩展通过单细胞表型表征组织异质性的努力。这种组织水平表型的一个例子是代谢物在细胞之间的交换，缓解了 X 失活相关酶杂合性在女性中的受影响细胞的疾病表型。最近在 RNA 速度的背景下，直接在 RNA-seq 数据上拟合了 RNA 剪接的动力学模型。该 RNA 速度模型通过测量不同基因表达状态下单细胞的未剪接和剪接读数丰度推断转录、剪接和降解的动力学参数。

#### 3.4. 讨论

##### 3.4.1. 方法比较

这三类代谢建模方法旨在回答不同的问题，因此使用不同的技术（表 1）。它们的预测范围从单一反应到整个代谢，以及粗细程度，从测量的基因表达和预测的酶活性之间的直接映射到整个系统的详细代谢表征。动力学建模侧重于小系统的稳健表征，能够进行机械、定量和通常动态预测。相比之下，路径级分析比较不同条件下多个路径的活动。它不考虑反应机制，如化学计量或代谢物丰度，因此通常被认为不那么稳健。反应网络的分析也可以作为其他代谢建模方法（如基于约束的模型）的结果解释方法。基于约束的模型根据 GEMs 提供完整的细胞代谢表征。。

表 1. 代谢建模方法的比较

|                      | 路径级分析                                                       | 基于约束的分析                                                         | 动力学模型                                                   |
| -------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------ |
| 获得的见解           | 富集路径列表或数据定义路径；路径活性                             | 全系统反应通量的代谢预测，有时包括代谢物浓度                           | 代谢物和反应通量的时间预测或在不同参数设置下的预测；模型选择 |
| 适用于整个代谢       | 是                                                               | 是，但通常简化以减少必要的计算资源                                     | 通常不适用                                                   |
| 适用于个别路径或反应 | 是                                                               | 否                                                                     | 是                                                           |
| 代谢层               | 反应，很少代谢物                                                 | 反应和代谢物                                                           | 反应和代谢物                                                 |
| 假设                 | 通常忽略路径内的反应关联或假设路径是独立的；有时大致考虑质量平衡 | 代谢物稳态和质量平衡；可能假设所有底物的可用性                         | 质量平衡和 Michaelis-Menten 动力学；可能假设所有底物的可用性 |
| 结果需要后处理总结   | 通常不需要，因为路径级信息已经可用                               | 是；在探索性分析中，因为结果在反应或代谢物层面，因此通常应用路径级分析 | 否，由于系统较小                                             |
这些方法在资源需求（图 3）和假设方面也有所不同。就复杂性增加而言，通常按以下顺序看待这些方法：路径级分析，然后是基于约束的建模，最后是动力学建模。首先，路径级分析依赖于经过整理的路径 - 基因关联集或网络。因此，它通常适用于特征较少的生物体，在这些生物体中，完整的 GEMs 或动力学参数可能不可用，而且可能需要较少的计算资源。为整体水平开发的路径分析方法通常可以应用于单细胞数据，从而产生大量可用的方法。其次，基于约束的建模需要 GEMs，尽管其数量正在增加。我们预计，基于约束的深度学习模型将在未来实现对大数据集的扩展，整合更多的代谢和多组学约束，并扩展到动态或组织水平模型。基于约束的模型依赖于稳态假设，当这一假设不成立时，它们是不适用的。第三，动力学建模需要详细的动力学信息，使其不适用于大系统。基于约束和动力学建模的方法通常不能直接从整体水平转移到单细胞水平，需要开发新方法或适应现有方法。

![](https://ars.els-cdn.com/content/image/1-s2.0-S2212877821002532-gr3_lrg.jpg)

> 图 3. 不同建模方法的输入
> 建模方法需要不同的信息，包括基因 - 反应关联、反应机制和测量数据。此图仅显示最常用的输入，尽管不同的输入信息也可能被整合到模型中。

#### 3.4.2. 代谢建模的优缺点

代谢建模受欢迎的主要原因是它比代谢测量更容易获得，以及与基因调控模型相比，生化知识的明确可用性。例如，单细胞代谢组学主要集中在测量代谢物浓度，而大规模通量组测量主要是难以实现的。然而，计算方法可以预测代谢通量，与代谢物浓度信息相比，代谢通量可以识别导致特定代谢表型的细胞机制。随着单细胞数据集的日益普及，科学界已经意识到跨研究分析的重要性，从而从分析单个数据集转向分析综合细胞图谱。然而，由于缺乏成熟的分析方法，代谢组学测量在不同研究中仍然很难比较。相比之下，代谢建模主要依赖于 scRNA-seq 数据，该数据的标准化和整合技术已经成熟，提高了跨研究的可比性。新的单细胞代谢组学数据集的生成将导致分析技术的发展，类似于整体代谢组学中发生的情况。

相比于原始的代谢测量，计算建模中使用的经过整理的代谢资源的先验知识可以带来对代谢机制和因果关系的新见解。首先，代谢建模可以提供对扰动效应的机械见解。在单细胞应用方面，这可以用于理解导致疾病发展的分子机制。这些信息可以用于设计靶向特定代谢步骤的药物。此外，跨细胞类型和组织理解单细胞代谢对于预测药物副作用非常有用。代谢建模还可以用于识别可以通过代谢工程靶向以增加产量的基因。其次，代谢建模可以用于预测细胞、机体和环境之间的相互作用。这包括营养物的可用性和交换以及信号分子的生产。第三，代谢建模可以用于预测必需酶和基因组的功能注释。它可以提供对细胞、菌株和生物体的代谢适应和能力的见解。上述推理同样适用于理解更高组学层次的测量，其变化可能难以解释，因为它们影响代谢网络的远端部分，或者由于不同基因的改变导致相同的表型。这些效应可以通过整合代谢网络中的先验信息来更好地理解。

然而，代谢建模受到输入的转录组水平和目标预测的代谢水平之间不一致的限制。例如，由于其较短的半衰期，代谢变化可能无法通过 RNA 测序捕捉到，或由于转录后的随机性。同样，代谢功能可能受到翻译后或转录后调控、降解效应和外源性因素（如营养物可用性）的影响，这些都不会在转录组水平上反映出来。然而，与单独的转录组分析相比，整合代谢网络中的先验信息可能会减轻这些负面影响。例如，scRNA-seq 稀疏性可能导致低表达基因的随机捕获，导致假阳性。然而，通过整合代谢网络的先验知识，RNA 测序计数噪声可能会被克服，提供一个去噪的代谢视图。

### 4. 展望

尽管已经提出了一系列用于建模细胞代谢状态的方法，但一些限制因素限制了它们的更广泛应用。以下是解决这些问题的一些潜在扩展方向。

#### 4.1. 多组学整合

目前，单细胞代谢模型主要基于 mRNA 浓度。测量和建模与代谢物浓度更直接相关的分子实体可以改进当前模型。例如，这些信息可以用来使 RNA 到酶活性的映射更可靠，或通知反应活性约束和动力学。单细胞蛋白质组学测量可以代替转录组数据，因为它们对于预测酶活性更具信息性。它们直接对应于酶的可用性，并能检测决定酶功能的翻译后修饰。然而，尽管单细胞蛋白质组学最近取得了进展，但在可用性、通量和灵敏度方面仍存在限制，这在很大程度上禁止了单细胞蛋白质组学在单细胞代谢建模中的使用。所使用的输入数据类型决定了不同建模方法的适用性。即，如果可以通过酶浓度（例如从基因表达数据）量化反应速率，则基于约束的系统是相关的。另一方面，直接观察代谢物种可能会导致更类似于数据插补算法的模型。更复杂的先验知识可能需要对模型进行强大的算法更改。例如，通量平衡分析主要基于线性程序。对这一线性程序固有的数学假设的偏离将需要转向完全不同的参数系统和优化器。

同样，包含调控机制将导致更可靠的预测。这在配对多组学数据（如联合 scRNA-seq 和 scATAC-seq）的可用性增加的情况下尤为重要。为了整合调控信息，模型可能需要考虑实体之间的复杂相互作用，例如反馈回路。在尚未提供包含额外调控信息的 GEMs 的情况下，可以尝试利用机器学习来识别基因之间的相互作用，这可能以数据驱动的方式近似复杂的调控模式。

#### 4.2. 跨尺度的代谢模型扩展

另一种新型基于约束的模型的发展方向是适应不同的系统。例如，真核细胞被划分为代谢不同的隔室，这些隔室之间有不同的代谢物交换途径，可以将其包括在模型中。必要的关于隔室特定和交换反应的信息已经包含在一些 GEMs 中。此外，具有亚细胞分辨率的蛋白质组学测量可以进一步帮助提高亚细胞水平的预测。同样，细胞不是独立的，在组织或微生物群体内交换代谢物。因此，模型可以扩展到组织水平、微生物群体范围和环境感知系统。一些目前可用的方法已经尝试朝这个方向发展，通过建模细胞外代谢物的可用性或假设细胞间的代谢物共享。在这方面，注意力 -DNN 或在空间数据的情况下，图 -DNN 可以用于跨细胞传递信息。然而，大多数为其他单细胞数据模式开发的深度学习框架将细胞独立对待，因为模型的可扩展性通常关键地依赖于这种独立假设。许多常见的深度学习方法在反映细胞之间的依赖关系方面能力有限。

通过时间的细胞代谢变化非常有趣，因为它们涉及发育、疾病进展、环境响应和周期性行为等。就代谢变化而言，这些表型在不同的时间尺度上实现。首先，发育和疾病进展发生在数小时或数月内，导致细胞状态或细胞类型组成的变化。这些过程与常见单细胞实验的时间分辨率相匹配，然而，在单细胞数据中进行时间序列建模构成了挑战，因为个体细胞不是通过时间测量的。相反，通过在不同时间点获取独立的群体快照生成数据，这些快照通常用于推断细胞进程的典型轨迹并匹配伪时间。然而，这一轨迹并未揭示个体细胞的动态行为。这一时间轨迹数据的静态特征与动态 FBA 建模很好地对应，动态 FBA 建模基于时间点特定的测量为每个时间点解决稳态系统，从而生成与转录组匹配的代谢快照。相反，动力学模型可以用于预测个体细胞的命运，类似于动态 RNA 速度模型所做的预测。最后，DNN 架构，如递归 -DNN，可以用于时间依赖模型。其次，代谢水平对刺激的反应几乎是瞬时发生的，这无法通过常用的单细胞方法（如 scRNA-seq）捕捉。在这方面，动力学模型可以用于从初始测量状态预测个体细胞的短期代谢变化。

#### 4.3. 基于深度学习的模型

代谢物浓度和通量可以被视为细胞多组学分子系统的潜在状态（图 4）。在潜变量建模方面，DNN（深度神经网络）最近作为一组模型出现，它们可以灵活处理约束、整合不同的数据模式和定量预测，使它们成为开发新代谢建模工具的有希望的候选者。首先，DNN 可以扩展到当前在单细胞领域生成的大数据集。此外，使用大数据集将有助于模型正则化，从而提供更可靠的预测。其次，DNN 结构的灵活性使其能够整合多样的生物先验知识，这对于上述代谢建模方法的扩展是必要的。第三，DNN 能够从数据中学习模式，即使用于约束模型的生物机制尚未完全定义时，也可能导致改进的模型。最后，深度学习框架提供了一种方便的方式来构建新的 DNN 模型，通过抽象数学和技术细节，显著改进了目前在 FBA 中使用的线性规划库。

![](https://ars.els-cdn.com/content/image/1-s2.0-S2212877821002532-gr4_lrg.jpg)

> 图 4. 以知识为基础的神经网络
> 
> (A) 关于编码酶的基因和催化代谢物转化的酶的先验知识。
> 
> (B) 神经网络架构可以基于代谢知识。不同的组学层可以由神经网络的不同组件或层表示，以便节点之间的连接对应于先前的代谢知识。

#### 4.4. 代谢数据的解释

单细胞代谢组学测量技术和计算预测方法的出现将需要发展下游分析和解释方法来处理代谢组学和通量组学数据。许多分析理念可以从当前单细胞组学分析工作流程中转移过来，例如为scRNA-seq开发的工作流程。然而，与其他组学相比，代谢数据的一个独特特点是代谢网络的先验知识应被利用来进行解释，从而导致新的分析方法的发展。目前，由于单细胞分辨研究中缺乏对组织的代谢特征描述，组织领域专家对代谢活动的跨研究背景化往往具有挑战性。因此，从基因转向反应的重点转移将有助于代谢解释。

### 5. 结论

在许多信号级联中，代谢是汇集上层组学层次效应的最后一个组学层次，从而直接定义了细胞表型。代谢分析在生物学的各个领域都有广泛的应用，从医学到生物过程工程。由于代谢测量尚未广泛可用，需要其他方法来理解细胞代谢。在这里，代谢建模通过广泛可用的反应网络和scRNA-seq数据来推断潜在的分子状态，以预测反应活动和代谢物浓度。

由于单细胞数据与整体数据具有不同的特性，并提供了对特定背景行为的额外见解，因此需要期待新的单细胞代谢组学建模方法。各种代谢建模方法，正如本文所述，已经应用于单细胞数据。我们相信，新的计算方法，如深度学习，可能能够在单细胞和多组学层次上实现高效建模。

单细胞代谢组学建模将从现有的单细胞测序数据中获得新的见解。首先，已经整合到建模方法中的代谢网络信息使得可以根据代谢途径或分子功能解释结果。其次，关于分子网络的先验知识的使用提高了预测的稳健性，因此可以用于生成更可靠的单细胞嵌入。第三，动力学模型可以用于预测无法通过单细胞测序技术直接捕捉的快速扰动响应。

用于代谢分析的计算方法受益于广泛且高保真的代谢网络先验知识，这是代谢模式的一个独特特征。为单细胞代谢分析开发的机器学习模型可以为进一步的分子数据可解释机器学习方法的发展奠定基础。