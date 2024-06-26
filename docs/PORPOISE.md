快速发展的计算病理学领域已经展示出从组织学图像中开发客观预后模型的潜力。**然而，大多数预后模型要么仅基于组织学数据，要么仅基于基因组学数据，没有解决如何整合这些数据来源以开发联合图像-基因组预后模型的问题**。此外，从这些模型中识别出解释性的形态学和分子描述符，以确定预后的关键因素也很重要。我们使用多模态深度学习共同研究 14 种癌症类型的病理切片图像和分子谱数据。我们的弱监督的多模态深度学习算法能够融合这些异质模态以预测结果，并发现与不良和良好结果相关的预后特征。我们在一个交互式开放访问的数据库中呈现了关于 14 种癌症类型中患者预后的形态学和分子相关性的所有分析结果，以便进行进一步的探索、生物标记物发现和特征评估。

导言 癌症的定义包括**肿瘤和组织微环境中的典型组织病理、基因组和转录组的异质性**，这些异质性导致了治疗反应率和患者预后的可变性（Marusyk 等，2012）。对于许多癌症类型，目前的临床范式涉及到对**组织病理学特征（如肿瘤侵袭、不典型、坏死和有丝分裂）的手动评估，然后将其作为分级和分期标准，将患者分为不同的风险组别用于治疗决策**。例如，在肿瘤、淋巴结和转移 (TNM) 分期系统中，原发肿瘤根据肿瘤的严重程度（如大小、生长、异形性）被分类为不同的分期，然后用于治疗计划、手术适应症、放射剂量和其他治疗决策（Amin 等，2017）。然而，对组织病理学特征的主观解释已经被证明存在较大的观察者间和观察者内的变异性，同一等级或分期的患者在预后方面仍然存在显著的变异性。尽管已经建立许多组织病理学生物标志物用于诊断任务，但大多数基于肿瘤细胞形态和位置，缺乏对肿瘤微环境中间质、肿瘤和免疫细胞的空间组织如何影响患者风险的细致理解（Marusyk 等，2012; Chang 等，2013; Heindl 等，2015; Kather 等，2018; Tarantino 等，2021）。

最近在计算病理学领域取得的深度学习的进展，使得可以使用全切片图像（WSI）进行自动化癌症诊断和肿瘤微环境形态表型的定量。使用弱监督学习，可以使用切片级别的临床批注来指导深度学习算法重新模拟常规诊断任务，如癌症检测、分级和亚型分型（Campanella 等，2019; Lu 等，2021）。尽管这类算法在狭义定义的问题上可以达到与人类专家相当的性能，**但由于基于主观人类批注进行训练可能无法提取迄今为止未被识别的性质，从而限制了对新的预后形态特征的定量**（Echle 等，2021）。为了捕捉更客观和预后的形态特征，最近的基于深度学习的方法提出使用以结果为基础的标签来进行监督，例如无病生存时间和总生存时间作为参照标准（Harder 等，2019; Courtoil 等，2019; Kather 等，2019a、2019b; Kul karni 等，2020; Wuclzyn 等，2020,2021）。事实上，最近的研究表明，**利用深度学习进行自动生物标志物的发现具有巨大潜力，可以发现新的和预测性的形态学决定因素**（Beck 等，2011; Echleet al.，2021; Diao 等，2021）。

虽然预测性形态学生物标志物可能通过 WSI 中基于结果的标签来解释，但在更广泛的环境中，癌症预后是一个多模式问题，**它由组织学标志物、临床数据和基因组学驱动**（Ludwig 和 Weinstein，2005; Gentzler 等，2014; Fridman 等，2017; Mobadersany 等，2018; Cheerla 和 Gevaert，2019; Vale-Silva 和 Rohr，2021）。**随着下一代测序技术的出现和靶向分子治疗的发展，许多癌症类型的治疗决策过程因预测性分子标志物的包含而变得越来越复杂**（Hyman 等，2015）。例如，表皮生长因子受体（EGFR）外显子 19 缺失和外显子 21 p.Leu858Arg 替代是使用靶向治疗如厄洛替尼治疗 EGFR 突变型肺癌和胰腺癌的指征（Mayekar 和 Bivona，2017; Zhou 等，2021）。结合组织学评估，以及具有 IDH1 突变和 1p/19q 共码的少突胶质瘤和星形胶质瘤组织学，能够对患者进行低风险、中等风险和高风险分层（Louis 等，2016; Bai 等，2016; Cloughesy 等，2019），确定这些综合生物标志物的存在或缺失已经成为病理学家评估脑肿瘤的标准护理方法。**利用深度学习，通过 WSI 中的分子生物标志物和提取的形态学特征进行多模态融合，在改善患者风险分层的精度方面具有潜在的临床应用，并且还可以帮助发现和验证在组织学和基因组生物标志物的复合效应未知的情况下的多模态生物标志物**（Bera 等，2019）。最近在 TCGA 上进行的多模态研究主要集中于通过预测分子异常来学习基因型-表型相关，以帮助决定不进行下一代测序的患者的靶向分子治疗（Coudray 等，2018; Kather 等，2019a, 2019b, 2020; Fu 等，2020）。

基于深度学习的多模态集成为了解决癌症预后中研发联合图像组学生物标志物的挑战，我们提出了一种基于深度学习的多模态融合算法（MMF），**该算法使用 H&E 染色 WSIs 和分子特征（突变状态、拷贝数变异、RNA 测序[RNA-seq]表达）来度量和解释癌症死亡的相对风险**（图 1A）。我们的多模态网络不仅能够在生存预后预测等弱监督学习任务中整合这两种模态，还能解释组织病理学特征、分子特征及其相互作用与低风险和高风险患者的相关性（图 1B-1E）。**在对患者队列进行风险评估后，我们的网络使用注意力和基于归因的可解释性作为一种非定向方法来估计所有患者的预测标志物**（图 1B-1F）。我们的研究使用了来自 TCGA 的 14 种癌症类型的 5,720 个患者样本的 6,592 幅吉格像素的 WSIs（表 S1）。对于每种癌症类型，我们使用弱监督范式进行 5 折交叉验证来训练我们的多模态模型，并进行删除分析，比较单模态和多模态预后模型的性能。在训练和模型评估之后，我们对网络的可解释性进行了广泛的分析，研究了每种癌症类型的局部和全局图像组学解释，量化了与相关形态学对应的组织微观结构，并研究了单模态解释性与多模态解释性相比时特征重要性的变化。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202308162044548.png)

> (A) 病人数据以数字化高分辨率福尔马林固定石蜡包埋（FFPE）H&E 组织学玻片（称为 WSI）的形式与相应的分子数据一起作为算法的输入。我们的多模态算法由三个神经网络模块共同组成：(1) 基于注意力的多实例学习（AMIL）网络，用于处理 WSI；(2) 自归一化网络（SNN），用于处理分子数据特征；(3) 多模态融合层，用于计算 Kronecker Product，以模拟组织学特征和分子特征之间的成对特征交互。
>
> (B）对于 WSI，利用基于注意力的可解释性，将每个患者的局部解释可视化为高分辨率注意力热图，其中热图中的高注意力区域（红色）对应于有助于模型预测风险评分的形态学特征。
>
> (C) 通过对低风险和高风险患者队列中的高注意力区域进行细胞量化，提取出整体形态模式。
>
> (D) 对于分子特征，在综合梯度中使用基于归因的可解释性将每个患者的局部解释可视化。
>
> (E) 通过分析所有患者基因归因的方向性、特征值和大小，实现分子特征的全局可解释性。
>
> (F) 通过 Kaplan-Meier 分析，对个别癌症类型的低风险和高风险患者进行可视化分层。

此外，我们还开发了一个研究工具，利用 WSIs 和分子特征数据的模型解释来发现新的预测性生物标志物。使用我们的多模态网络，我们开发了一种名为 Pathology-Omics Research Platform for Integrative Survival Estimation（PORPOISE）的交互式平台，该平台可以为多种癌症类型的成千上万名患者直接提供我们模型学习到的预测标志物，网址为http://pancancer.mahmoodlab.org （交互演示）。具体而言，PORPOISE 允许用户可视化（1）原始的 H&E 图像金字塔 TIFF 与单模态和多模态训练的注意力可解释性重叠，（2）使用归因可解释性对每个患者的分子特征进行局部解释，以及（3）每个疾病模型的形态学和分子特征重要性的全局模式。为了验证 PORPOISE 可用于发现可识别的预测性生物标志物，我们分析了 WSIs 中的高注意力形态学区域，并进一步量化肿瘤微环境以量化高危和低危患者的形态学相关性。

多模态整合改善患者风险分层。我们**首先对 14 种癌症类型的成对 WSI-分子数据集使用 5 折交叉验证评估了我们提出的 MMF 深度学习模型**。我们还将我们的模型与只使用一种模态的单模态深度学习模型进行了比较：一种只使用 WSIs 的基于注意力的多实例学习(AMIL)模型，以及一种只使用分子特征的自归一化网络(SNN)模型。为了比较这些模型的性能，我们使用了交叉验证一致性指数(c-Index)来衡量每个模型的预测性能，使用卡帕兰-迈尔曲线来可视化预测低风险和高风险患者群体之间的质量差异，使用对数秩检验来评估在预测风险得分的 50%百分位上区分低风险和高风险群体的病人分层统计学意义。(图 2A、2B 和 S1; 表 S2)除了 c-Index，我们还报告了动态曲线下面积(AUC；称为生存 AUC)，该指标纠正了计算模型性能时来自审查的乐观偏差(Table S3)。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202308162050979.png)

> (A) 通过 MMF 对所有 14 种癌症类型的低风险和高风险患者进行分层的 Kaplan-Meier 分析。低风险和高风险由通过 MMF 预测的中位 50% 百分位数定义。对数秩检验用于检测低风险和高风险患者生存率分布的统计学意义（p < 0.05）。
>
> (B) 在 5 倍交叉验证中，SNN、AMIL 和 MMF 在每种癌症类型中的 c 指数表现（n = 5,720）。每个模型的横线表示所有癌症类型的平均 c-Index 性能。方框图对应的是对综合风险预测进行 1000 次引导重复的 c 指数。
>
> (C) 14 种癌症类型的 WSI 归因分布。每个点代表与分子特征输入相比，赋予 WSI 模式输入的特征归因比例。归因是根据每个疾病模型中的综合风险预测计算得出的。方框表示四分位值，胡须表示 1.5 倍四分位值范围内的数据点。

在 14 种癌症类型中，MMF 的整体 c-Index 为 0.644，而 AMIL 和 SNN 的整体 c-Index 分别为 0.578 和 0.606。在生存 AUC 上，多模态整合也取得了类似的改善，在整体性能上为 0.662，相比之下 SNN 和 AMIL 分别为 0.615 和 0.588(Table S2)。在单一癌症类型上的一对多模型性能比较中，MMF 在 14 种癌症类型中的 12 种(12/14)上取得了最高的 c-Index，其中 10 种癌症类型的模型在二元病人分层方面显示出统计学意义(Figure 2A-2C)。与仅使用分子特征的 SNN 相比，MMF 在所有癌症类型中的 c-Index 和生存 AUC 都表现出一致的性能。尽管 SNN 在某些癌症类型上具有可比性的性能，但我们观察到在乳腺癌(BRCA)、结直肠腺癌(COADREAD)、肺腺癌(LUAD)、胰腺腺癌(PAAD)和子宫体部子宫内膜癌(UCEC)的模型性能和病人分层中，MMF 显示出了显著的改善，而 SNN 没有显示出统计学意义(Figure 2B；表 S2)。与 AMIL 相比，除了肺鳞状细胞癌(LUSC)和 UCEC 外，MMF 在所有癌症类型上都表现出改善，其中有 7 种癌症类型的病人分层意义得到改善。我们注意到，皮肤切伤性黑色素瘤(SKCM)具有易于区分的疾病形式混合体(例如，包含原发和转移病例)，这可能会对模型性能产生乐观偏差。然而，总的来说，几乎所有癌症类型的模型性能在多模态整合后都得到了改善(Figure 2B)。在检查接近 MMF 性能的单模态模型时，我们发现 SNN 在透明细胞肾细胞癌(KIRC)和乳头状肾细胞癌(KIRP)的分层中显示出统计学意义(尽管在 MMF 中，预测的风险群体更清晰界定)，而 AMIL 则在肝细胞癌(LIHC)、胃腺癌(STAD)和 UCEC 的分层中显示出统计学意义。

在我们的研究中涵盖的所有单一癌症类型中，KIRP 在多模态训练中表现提升最大，达到了 0.816 的 c 指数（95%置信区间[CI]：0.705-0.880，p = 3.83 _ 10^-4，对数秩检验），相比之下，使用 AMIL 的 c 指数为 0.539（95% CI：0.408-0.625，p = 5.86 _ 10^-1，对数秩检验），使用 SNN 的 c 指数为 0.779（95% CI：0.678-0.857，p = 2.27 _ 10^-3，对数秩检验）（表 S2）。通过生存 AUC 评估纠正潜在乐观偏差和高度审查后，我们观察到 MMF 具有类似的模型性能，AUC 为 0.791（SD：0.102），而 AMIL 为 0.530（SD：0.082），SNN 为 0.743（SD：0.095）。PAAD 在多模态训练中表现出明显改进，c 指数为 0.653（95% CI：0.571-0.696，p = 1.69 _ 10^-3，对数秩检验），相比之下，使用 AMIL 的 c 指数为 0.580（95% CI：0.485-0.613，p = 2.30 _ 10^-1，对数秩检验），使用 SNN 的 c 指数为 0.593（95% CI：0.507-0.656，p = 5.59 _ 10^-2，对数秩检验）（表 S2）。对于 PAAD，我们观察到单独使用组织学或基因组学训练单模态模型并没有显示出统计学上的显著性，因为 Kaplan-Meier 生存曲线在预测低风险和高风险患者的身份上显示出较差的分层能力。然而，在多模态整合后，我们观察到这些分组变得有意义，这与我们在 PAAD 中观察到的 MMF 性能改进一致。我们在 BRCA、COADREAD 和 LUAD 中使用 MMF 分别分隔出低生存组，得到类似的分层结果（图 S2、S3、S6 和 S11）。

除了进行单模态和多模态模型的消融研究之外，我们还使用年龄、性别和肿瘤分级协变量作为基准评估了 Cox 比例风险模型，但这些模型的表现仍然不如 MMF（表 S3）。在仅有分级信息的癌症类型的头对头比较中，AMIL 的平均 c 指数为 0.601，而 Cox 模型为 0.582，这表明当前对癌症预后中肿瘤分级的主观评估可能可以通过客观的基于深度学习的表型特征提供更准确的评估。我们还量化了每种模态的预后重要性，从而能够确定哪些癌症类型需要开发多模态预后模型，以及哪些肿瘤类型只需要组织学或基因组学就足以构建足够的预后模型。通过对所有癌症类型的评估，我们发现 WSI 平均占 MMF 输入归因的 16.8%，这表明分子特征在 MMF 的风险预测中起主导作用（图 2C；表 S3）。这证实了在大多数癌症类型中，比起 WSI，分子特征更具生存预后的预测能力（通过比较 SNN 和 AMIL 的性能）。然而，我们注意到在对 UCEC 评估的 MMF 模型中，WSI 占所有输入归因的 55.1%，这与 AMIL 在该癌症类型中的较高表现相一致。我们还观察到在头颈鳞状细胞癌（HNSC）、胃腺癌（STAD）和肝细胞癌（LIHC）中，平均 WSI 贡献较大，这与 AMIL 优于 SNN 的癌症类型相一致。对于 LUSC，在其中 AMIL 也优于 SNN，我们观察到相对较低的平均 WSI 归因为 5.8%，这可能与 MMF 的表现不佳相一致，因为该模型无法达到足够的预测性能。

文章中的特征重要性在 WSIs 的预后信息中的作用。有趣的是，尽管 AMIL 表现不如 SNN，但 WSIs 在 PAAD 中贡献了 32.4%的输入属性分配，这可能表明 MMF 能够通过 SNN 或 AMIL 进行单模态特征提取，提取出分子标志物中没有捕捉到的预后形态特征。

多模态可解释性用于联合图像-组蛋白组生物标志发现。为了解释和进一步验证我们的模型，我们应用注意力和基于梯度的可解释性到我们训练的 SNN、AMIL 和 MMF 模型上，以解释 WSIs 和分子特征分别如何用于预测预后。对于 WSIs，我们使用了一种自定义可视化工具，将从 AMIL（以及 MMF 中的 AMIL 子网络）计算得到的注意力权重叠加到 H&E 诊断切片上，显示为高分辨率的注意力热图，显示用于预测风险的图像区域的相对预后相关性（图 3、4、5 和 6A）。对于分子特征，我们使用了 Shapley Additive Explanation（SHAP）风格的属性决策图来可视化在 SNN（以及 MMF 中的 SNN 子网络）中由综合梯度计算得到的每个分子特征的属性权重和方向（图 3、4、5 和 6B 以及 3D、4D、5D 和 6D，分别）。然后，我们使用这些解释和可视化技术构建了我们的发现平台 PORPOISE，并将其应用于每个模型和所有患者，得到了所有 6,592 个 WSIs 和 5,720 个患者的注意力热图和属性决策图。在 PORPOISE 中，用于解释单个患者模型的分析被称为局部可解释性，对于整个癌症患者群体进行的分析被称为全局可解释性。图 3、4、5 和 6 显示了 KIRC、KIRP、低级别神经胶质瘤（LGGs）和 PAAD 的局部和全局可解释性。其余癌症类型的全局可解释性结果以及局部可解释性结果在图 S2-S11 中提供。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202308162054998.png)

> (A) 对于 KIRC（n = 345），低风险病例（上图，n = 80）的高度关注往往集中在典型的透明细胞形态上，而对于高风险病例（下图，n = 80），高度关注往往对应于细胞质减少或核与细胞质比率增加的区域。
>
> (B) 相应低危（上图）和高危（下图）病例的局部基因归属。
>
> (C) 仅用 omics（左侧，"SNN"）、仅用组织学（中间，"AMIL"）和多模态融合（右侧，"MMF"）的 Kaplan-Meier 曲线，显示 MMF 改善了分离效果。对数秩检验用于检测低风险和高风险患者生存率分布的统计学意义（如果 p 值 _<_ 0.05，则标记为 ∗）。
>
> (D) 根据单模态可解释性（左侧为 "SNN"）和多模态可解释性（右侧为 "MMF"）对不同患者队列进行全局基因归因。SNN 和 MMF 都能识别 KIRC 中的_CDKN2C_和_VHL_等免疫相关标记物和预后标记物。MMF 还能识别其他免疫相关/预后基因，如 KIRC 中的 _RUNX1_ 和 _NFIB_。
>
> (E)低风险（上）和高风险（下）病例中的高关注斑块示例及相应的细胞标签。
>
> (F)对每种疾病总体高关注斑块中细胞类型的量化，显示肿瘤和 TIL 存在增加。方框表示四分位值，胡须延伸至四分位值范围 1.5 倍以内的数据点。

患者的单模态和多模态预测模型的分层显示在图 3、4、5、6、7C 和 S2–S11 中。为了了解模型如何使用形态特征，**我们评估了在每种癌症类型中，预测患者风险的前 25%（高危组）和后 25%（低危组）的 WSIs 中高关注区域，分别反映了有利和不良的癌症预后**。除了两名病理学家的视觉检查外，我们还同时分割和分类了我们 WSIs 中高关注区域的细胞类型身份。图 3、4、5 和 6A 显示了 KIRC、KIRP、LGGs 和 PAAD 中低和高危情况下注意热图和示例 ROI。图 3E、4E、5E 和 6E 显示了**低和高危情况下高关注区域中细胞类型的语义分割结果**。图 3、4、5 和 6F 比较了这些癌症类型中高危情况下高关注斑块中的定量细胞类型分布。

在所有癌症类型中，我们普遍观察到**低风险患者的高关注区域与更多的免疫细胞存在以及较低的肿瘤分级相对应**，其中 8/14 个癌症类型在高关注区域的淋巴细胞比例上显示出统计学上显著的差异（图 6F 和 S3-S10）。此外，我们还观察到**高风险患者的高关注区域与某些癌症类型中增加的肿瘤细胞存在和侵袭相对应**，其中 6/14 个癌症类型在肿瘤细胞比例上显示出统计学上显著的差异（图 S3、S5、S6、S7、S9 和 S11）。图 6F、S3 和 S7 显示了在肿瘤细胞比例（BRCA p：2.17x10^-9、LUAD p：1.45x10^-3）和淋巴细胞比例（BRCA p：6.79x10^-14、LUAD p：1.06x10^-9、PAAD p：2.04x10^-8，t 检验）之间细胞比例分布的明显差异。图 3E、4E、5E 和 6E 分别显示了低和高危患者中引人注目的区域，基于注意力的解释性分析确定了低风险患者中密集的免疫细胞渗入（绿色）和高风险患者中肿瘤细胞的核形态改变和异型性（红色）。有趣的是，对于 KIRC 和 KIRP，我们没有发现高风险患者的高关注区域中增加的肿瘤细胞含量（图 3 和 4F）。然而，通过视觉检查我们发现高风险患者中皮肤/non-mel 非黄色肿瘤的细胞比例分布与低风险患者相似。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202308162110002.png)

> (A) 就 KIRP（n = 253）而言，低风险病例（上图，n = 36）通常高度关注复杂和弯曲的乳头状结构，而高风险病例（下图，n = 63）则高度关注肿瘤细胞密集的区域。
>
> (B) 相应低危病例（上图）和高危病例（下图）的局部基因归属。
>
> (C) 仅omics（左侧，"SNN"）、仅组织学（中间，"AMIL"）和多模态融合（右侧，"MMF"）的 Kaplan-Meier 曲线，显示 MMF 的分离效果更好。对数秩检验用于检测低风险和高风险患者生存率分布的统计学意义（如果 p 值 _<_ 0.05，则标记为 ∗）。
>
> (D) 根据单模态可解释性（左侧为 "SNN"）和多模态可解释性（右侧为 "MMF"）对不同患者队列进行全局基因归因。SNN 和 MMF 都能识别预后标记，如 KIRP 中的 BAP1。MMF 还能识别其他免疫相关/预后基因，如 KIRP 中的 _PROCR_ 和 _RIOK1_。
>
> (E) 低风险（上）和高风险（下）病例中的高关注斑块示例及相应的细胞标签。
>
> (F)对每种疾病总体高关注斑块中细胞类型的量化，显示上皮细胞和 TIL 存在增加。方框表示四分位值，胡须延伸至四分位值范围 1.5 倍以内的数据点。

**研究发现，低风险患者的肿瘤细胞等级较高风险患者更低**。图 3 和图 4A 是 KIRC 和 KIRP 中低风险和高风险患者的关注热力图示例，高风险患者的关注区域在 KIRC 中对应中央坏死，在 KIRP 中对应肿瘤细胞侵袭肾包膜。为了了解多模式可解释性中条件分子特征时如何转移注意力，我们还让两位病理学家使用 PORPOISE 评估了单模和多模注意力热力图。对于 BRCA 和 KIRC 等某些癌症类型，**多模特性的注意力从仅肿瘤区域转向基底膜和肿瘤区域，这证明了基底膜区域的预后相关性**。与评估 WSI 可解释性同时，我们也调查了分子特性输入中重要的模型解释。图 3、4、5 和 6B 显示了 KIRC、KIRP、LGG 和 PAAD 的局部可解释性，图 3D、4D、5D 和 6D 显示了这些癌症类型中分子特性的全局重要性。在所有癌症类型中，基于梯度的可解释性能够识别出许多在现有生物医学文献中被认可并用于靶向分子治疗的致癌基因和免疫相关基因。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202308162111079.png)

> (A) 对于 LGGs（n = 404），低风险病例（上图，n = 133）的高度关注点往往集中在肿瘤细胞密集区域，而对于高风险病例（下图，n = 68），高度关注点则同时集中在肿瘤细胞密集区域和血管增生区域。
>
> (B) 相应低危（上图）和高危（下图）病例的局部基因归属。
>
> (C)仅用 omics（左侧，"SNN"）、仅用组织学（中间，"AMIL"）和多模态融合（右侧，"MMF"）的 Kaplan-Meier 曲线，显示 MMF 患者分层情况有所改善。对数秩检验用于检测低风险和高风险患者生存率分布的统计学意义（如果 p 值 _<_ 0.05，则标记为 ∗）。
>
> (D) 根据单模态可解释性（左侧为 "SNN"）和多模态可解释性（右侧为 "MMF"）对不同患者队列进行全局基因归因。SNN 和 MMF 都能识别 LGG 中的免疫相关标记物和预后标记物，如 _IDH1_、_ATRX_、_EGFR_ 和 _CDKN2B_。
>
> (E) 低危（上图）和高危（下图）病例的高发斑块与相应的细胞标签，分别显示少突胶质瘤和星形细胞瘤亚型。
>
> (F)高危斑块中各疾病细胞类型的量化，高危患者细胞坏死增加具有统计学意义。方框表示四分位值，胡须延伸至四分位值范围 1.5 倍以内的数据点。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202308162112201.png)

> (A）对于 PAAD（n = 160），低风险病例（上图，n = 40）的高度关注点往往集中在含有分散腺体和淋巴细胞聚集的基质上，而对于高风险病例（下图，n = 40），高度关注点则集中在肿瘤相关基质和肌样基质上。
>
> (B) (A)和(G)中相应低危（上）和高危（下）病例的局部基因归属。
>
> (C) 仅omics（左，"SNN"）、仅组织学（中，"AMIL"）和多模态融合（右，"MMF"）的Kaplan-Meier曲线，显示SNN和AMIL对低生存率患者的分离效果较差，而多模态融合后的分层效果更好。对数秩检验用于检测低风险和高风险患者生存率分布的统计学意义（如果 p 值 _<_ 0.05，则标记为 ∗）。
>
> (D) 根据单模态可解释性（左侧为 "SNN"）和多模态可解释性（右侧为 "MMF"）对不同患者队列进行全局基因归因。SNN 和 MMF 都能识别 PAAD 中的免疫相关标记物和预后标记物，如 _IL8_、_EGFR_ 和 _MET_。MMF 还将归因转移到其他免疫相关/预后基因，如 _CD81_、_CDK1_ 和 _IL9_。
>
> (E）低风险（上）和高风险（下）病例的高关注斑块及相应的细胞标签。
>
> (F)对每种疾病总体高发斑块中细胞类型的量化，显示低风险患者淋巴细胞和 TIL 存在增加，以及 PAAD 中坏死存在增加。方框表示四分位值，胡须表示四分位值范围 1.5 倍以内的数据点。

文章治疗（Uhlen 等人，2017 年）。**在具有明显分子特征的 LGG 队列中，基于梯度的可解释性确定 IDH1 突变（p 值：2.31 _ 10^-89，T 检验）状态作为最具影响力的基因特征**，该基因在细胞代谢、表观遗传调控和 DNA 修复方面具有重要功能，并定义了 IDH1 野生型星形细胞瘤、IDH1 突变型星形细胞瘤和 IDH1 突变型少突胶质瘤的分子亚型（Louis 等人，2016 年）。此外，**IDH1 突变与 LGGs 相关，因此与 IDH1 野生型胶质瘤相比，预后较为有利，与 IDH1 突变在归因决策图中的归因方向相吻合**，**其中 IDH1 突变的分布具有负向的归因值（低风险）（图 5D）**。模型还使用了其他几个在其他癌症类型中的关键致癌基因，例如在 BRCA 中的 PIK3CA 突变（p：4.04 _ 10^-118，T 检验），COADREAD 中的 SOX9 突变（p：7.56 _ 10^-64，T 检验）和 SOX11 突变（p：1.65 _ 10^-58，T 检验）；LUAD（p：1.98 _ 10^-63，T 检验）和 PAAD（p：9.00 _ 10^-12，T 检验）中的 KRAS 突变；以及 KIRC 中的 VHL（p：1.76 _ 10^-62，T 检验）和 BAP1（p：5.57 _ 10^-18，T 检验）突变（图 3D、5D、S3 和 S6）。**在 PAAD 中，我们还观察到与免疫相关的基因（如 CD81、CDK1、IL8 和 IL9）的归因，其 RNA 测序表达被认为是最高的，这与它们在先天免疫和炎症细胞信号转导中的作用相吻合**（癌基因组图谱研究网络，2013 年；Uhlen 等人，2015 年；Chevrier 等人，2017；Uhlen 等人，2017，2019 年）（图 6D）。此外，我们注意到，在 WSI 的条件下，对于 PAAD 的 MMF 模型中的许多基因，归因相对减少，这与我们之前观察到的 PAAD 中 WSI 归因较高的情况相吻合，用于 MMF 患者分层。**在大多数癌症类型中，编码极大蛋白质的基因突变（例如 TTN、OBSCN、RYR3 和 DNA5）通常被认为具有很高的归因。尽管许多这些基因并非明确与癌症相关且具有预后，但这些大型编码区域的基因组不稳定性可能是肿瘤突变负荷的间接衡量指标**（Lawrence 等人，2013 年；Rizvi 等人，2015 年；Shi 等人，2021 年；Oh 等人，2020 年）。 SNN 和 MMF 的所有基因特征的归因可在表 S4 中找到。 免疫反应作为预后标志 另外，**我们使用 PORPOISE 的解释性作为一种机制来测试肿瘤浸润淋巴细胞（TIL）存在与良好的癌症预后相一致的假设**。图 7 展示了先前定义的风险组内所有 14 种癌症类型的**高注意区域中 TIL 的分数分布**。在比较低风险患者和高风险患者之间的 TIL 存在性时，**我们发现 14 种癌症类型中有 9 种在预测低风险患者中 TIL 存在性显著增加，表明模型的注意力集中在更多免疫活跃区域**。对于我们数据集中常用 FDA 批准的免疫检查点抑制剂疗法治疗的癌症类型，TILs 存在被用作有利预后的模型解释，例如在 BRCA（p：5.17 _ 10^-11，T 检验）；HNSC（p：1.97 _ 10^-18，T 检验）；KIRC（p：1.86 _ 10^-3，T 检验）；LIHC（p：2.54 _ 10^-17，T 检验）；LUAD（p：1.54 _ 10^-21，T 检验）；LUSC（p：2.92 _ 10^-12，T 检验）；PAAD（p：3.77 _ 10^-6，T 检验）；STAD（p：1.09 _ 10^-9，T 检验）；以及 SKCM（p：6.29 \* 10^-10，T 检验）。这表明我们的训练模型将形态结构特征作为免疫反应的标记来预测癌症预后，并支持越来越多的证据表明 TILs 在许多癌症类型中具有预后作用（Thorsson 等人，2018 年；Saltz 等人，2018 年；Shaban 等人，2019 年；AbdulJabbar 等人，2020 年）。在 BRCA 中，Maley 等人对 WSI 中免疫癌细胞的共定位进行了热点分析，显示免疫癌共定位是长期生存的显著预测因子（Maley 等人，2015 年）。在口腔鳞状细胞癌中，Shaban 等人提出了一个共定位评分来量化 TIL 密度，得到了类似的发现（Shaban 等人，2019 年）。在肺癌中，AbdulJabbar 等人提出了一个深度学习框架来预测 TILs 的存在性。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202308162115447.png)

> 在预测的低风险（BLCA n = 90、BRCA n = 220、COADREAD n = 74、HNSC n = 96、KIRC n = 80、KIRP n = 36、LGG n = 133、LIHC n = 85、LUAD n = 105、LUSC n = 97、PAAD n = 40、SKCM n = 29、STAD n = 53）和高风险患者病例（BLCA n = 93、BRCA n = 223、COADREAD n = 80、HNSC n = 103、KIRC n = 80、UCEC = 104）的高关注区域进行 TIL 定量、UCEC = 104）和高危患者病例（BLCA n = 93、BRCA n = 223、COADREAD n = 80、HNSC n = 103、KIRC n = 80、KIRP n = 63、LGG n = 68、LIHC n = 84、LUAD n = 89、LUSC n = 103、PAAD n = 40、SKCM n = 55、STAD n = 78、UCEC = 125），涉及 14 种癌症类型。对每位患者得分最高的 1%高关注区域（512 × 512 40_×_ 图像斑块）进行分割，并分析肿瘤和免疫细胞的存在情况。肿瘤与免疫细胞高度共聚焦的图像斑块表示 TIL 阳性（否则为阴性）。在所有患者中，计算出含有 TIL 的高关注度斑块的比例，并在方框图中显示出来。对每种癌症类型进行双样本 t 检验，以检测低风险和高风险患者的 TIL 分数分布的平均值是否有显著的统计学差异（∗p < 0.05）。方框表示四分位值，胡须延伸至四分位值范围 1.5 倍以内的数据点。

文章对组织病理学图像（H&E）和免疫组织化学图像（IHC）中的免疫浸润进行了空间分析，**并发现具有超过一个免疫冷区的肿瘤复发风险更高**（AbdulJabbar 等人，2020）。Saltz 等人在 TCGA 上对 TILs 的空间分布进行了全癌症分析，并展示了不同表型的 TILs 浸润与生存的相关性（Saltz 等人，2018）。**与这些分析的区别在于，我们的方法并没有专门训练用于识别 TILs 并将其与结局相关联。相反，模型的可解释性揭示出 TILs 的存在是用作低风险和高风险患者分层的预后形态学特征**。

讨论部分指出，将计算机衍生的组织形态学生物标志物纳入临床分期系统中有望实现更好的患者风险分层（Echle 等人，2021；Bera 等人，2019）。目前的癌症分期系统（如 TNM 分类系统）在精确性和一致性上存在困难，导致患者管理和结果的差异（Nicholson 等人，2001；Novara 等人，2007；Rabe 等人，2019）。在本研究中，我们提出了一种解释性的、弱监督的、多模态深度学习方法，将 WSIs 和分子特征数据整合用于癌症预后。我们在 14 种癌症类型的 5,720 名患者的 6,592 个 WSIs 上进行了训练和验证，并将我们的方法与单模态深度学习模型以及具有临床协变量的 Cox 模型进行了比较，在 14 种癌症类型中有 12 种的 c-Index 表现最好。我们的方法还通过解释 WSIs 和分子特征的特征如何对风险做出贡献，探索了多模态可解释性。我们开发了一个名为 PORPOISE 的交互式、免费可用的平台，直接提供我们模型在这 14 种癌症类型中产生的 WSI 和分子特征解释。我们的目标是使计算病理学中的当前黑盒最先进方法，尤其是新兴的多模态方法，对更广泛的生物医学研究社区更加透明、可解释和可用。通过提供每种癌症类型的热图和决策图，我们希望我们的工具能够让临床医生和研究人员制定自己的假设，并通过深度学习来探索解释的发现。尽管我们发现多模态整合有助于大多数癌症类型的患者风险分层，但我们的结果也表明，对于某些癌症类型，使用仅基于 WSIs 或分子特征训练的单模态算法可能会达到可比较的分层性能，因为癌症结果的变异在任何一种模态中都可以被捕捉到。许多实际设置可能缺乏对同一组织标本的配对诊断切片或高通量测序数据，在这种情况下，单模态的基于深度学习的癌症预后算法可能具有较低的临床应用障碍。虽然多模态学习在技术领域（如音频、视觉和语言模态的融合）取得了成功，但在临床转化任务中，我们注意到多模态整合的改进基础需要建立在每种癌症类型的生物学基础上，因为完全由基因型贡献解释的肿瘤微环境中的表型表现具有高的互信息（Kather 等人，2020）。通过为 14 种不同的癌症类型建立单模态和多模态基准线，我们的结果支持应根据每种癌症的情况确定多模态整合的应用，这有助于检视单一疾病模型上的单模态或多模态生物标志物的临床问题。

**我们方法的一个限制是，虽然我们的方法可以指出“是什么”和“在哪里”，但它并不能总是解释为什么需要基于人类知识进一步量化和内省发现的特征**。例如，虽然在大多数癌症类型中发现了肿瘤浸润淋巴细胞（TILs）来区分低风险和高风险患者，**但仍需进行事后分析以量化 TIL 的存在并评估两个风险组之间的统计显著性**。在 WSI 中进行特征转变的分析中，我们观察到在某些癌症类型中，高关注度经常从肿瘤区域转移到基质、正常组织和其他形态区域。我们推测这种观察结果是 WSI 和分子谱数据之间固有差异的结果，训练动态可能倾向于使用更简单模态（Wang 等人，2020 年）的更多信息。**在分子特征中，来自基因突变、拷贝数变异和 RNA-seq 丰度等的基因型信息在肿瘤活检中的细胞中进行了平均，而 WSI 中则以空间方式表示了正常组织、肿瘤细胞和其他形态学决定因素等表型信息**。因此，当我们的多模态算法已经使用与肿瘤相关的特征（如 TP53 突变状态、PTEN 缺失）来进行条件训练时，它可以关注具有非肿瘤信息的形态区域（如基质）来解释生存结果的微小差异（Beck 等人，2011 年）。换句话说，**特征的重要性不需要归因于分子特征中的癌基因和 WSI 中的肿瘤区域，这两者具有高共线性**，这使得多模态网络能够学习超出肿瘤分级的其他组织学特异性预后信息。除了表征已知的癌症中可识别的现象特征（如肿瘤浸润淋巴细胞），PORPOISE 还可以**通过对细胞类型比例和组织结构进行稳健定量，进一步表征目前尚不太了解的表现型特征**，并由研究界用于指导治疗决策（Diao 等人，2021 年）。此外，针对更大规模且精心策划的临床试验数据进行调整的多模态网络，可用于辅助发现和验证人类可解释的图像组学生物标志物，以指导治疗决策。类似追求该目标的相关研究方向是从 WSI 和其他基因型-表型相关性中预测分子生物标志物，这将减少需要分子检测用于治疗决策的常规临床工作流程的复杂性。虽然这种方法有潜力阐明预测分子异常的形态学标记，但可能存在与分子特征无相关性但具有预后价值的正交形态学标志。正如我们在 PAAD 中观察到的，虽然 AMIL 对生存结果没有预测价值且性能比 SNN 差，但我们证明了多模态集成不仅可以提高性能，而且对 WSI 给予相对较高的归因，这表明存在尚未捕获的预后信息（Coudray 等人，2018 年；Kather 等人，2019a，2019b，2020 年；Gamble 等人，2021 年）。为了开发用于辅助治疗决策的计算支持系统，基于基因型-表型相关分析的进一步工作将在理解多模态集成方法中的共享和模态特定预后信息的形成直觉方面发展更加正式的认识，这可能导致对单模态或联合图像-组学计算生物标志物进行临床验证（每种癌症类型）作为下游预后的发展。总的来说，这项研究是一个概念验证，展示了使用弱监督深度学习从正交数据流开发多模态预后模型，并随后识别驱动这种预测的相关特征。未来的工作将专注于通过策划更大规模的多模态数据集来开发更专注的预后模型，将模型调整到大型独立的多模态测试队列，并使用多模态深度学习预测对治疗的响应和耐药性。随着定序技术（如单细胞 RNA-seq、质谱细胞学和空间转录组学）的研究进展，这些技术持续发展并在临床上应用，在整个切片成像中结合使用，以及我们对分子生物学的理解方法将变得越来越具有空间解析力和多模态性（Abdelmoula 等人，2016 年；Berglund 等人，2018 年；Giesen 等人，2014 年；Jackson 等人，2020 年；Schapiro 等人，2017 年；He 等人，2020 年）。在使用批量分子特征数据时，我们的多模态学习算法被视为“后期融合”架构，其中单模态的 WSI 和分子特征在网络的输出端附近进行融合（Baltru�saitis 等人，2018 年）。然而，组合具有空间解析的基因组学和转录组学数据与整片成像，有潜力实现“早期融合”的深度学习技术，将局部组织病理学图像区域和具有精确空间对应关系的分子特征一起集成，这将导致更稳健的介绍和空间组织映射，显示肿瘤内异质性、免疫细胞存在以及其他形态学决定因素。

STAR+METHODS

详细方法在本文的在线版本中提供，包括以下内容：

d 关键资源表
d 资源可用性
B 联系负责人
B 材料可用性
B 数据和代码可用性
d 方法细节
B 数据集描述
B WSI 处理
B 基于深度学习的整体幻灯片图像和基因组特征的生存分析
B 多模态可解释性和可视化
B 计算硬件和软件
d 量化和统计分析

STAR+METHODS

关键资源表

资源可用性

联系负责人

如需进一步了解和请求有关本手稿的信息，请发送给并由主要研究者 Faisal Mahmood（faisalmahmood@bwh.harvard.edu）负责解决。

材料可用性

本研究未生成任何独特试剂。

数据和代码可用性

所有诊断性全切片图像（WSIs）及其相应的分子和临床数据均来自癌症基因组图谱（The Cancer Genome Atlas），并可通过 NIH 基因组数据共享数据门户（https://portal.gdc.cancer.gov/）公开访问。所有代码都是使用Python编写的，并使用PyTorch作为主要的深度学习包。本文中用于重现实验的所有代码和脚本均可在以下网址找到：https://github.com/mahmoodlab/PORPOISE。

### 方法细节

数据集描述

通过 NIH 基因组数据共享数据门户，收集了来自 TCGA 的 14 种癌症类型中的 5,720 名患者的 6,592 个带有相应分子和临床数据的 H&E 诊断 WSIs。数据集收集的样本纳入标准是

学术论文的定义包括以下两个方面：1）数据集大小以及每个 TCGA 项目中被审查和未审查患者的分布，2）每个 WSI（WSI-CNV-MUT-RNA）具有匹配的 CNV、突变和 RNA-Seq 丰度。为了减少过拟合问题，该研究排除了 TCGA 项目中患者少于 150 人（在 WSI 和分子数据对齐之后）且未审查率低（未审查患者比例低于 5%）的项目。对于消化道肿瘤，将这些组织中的癌症类型分别分组，形成组合的 TCGA 项目 COADREAD（结肠（COAD）和直肠（READ）腺癌）。对于 LGG，TCGA 胶质瘤队列中的其他病例（如胶质母细胞瘤）在模型训练中进行了包含，仅对 LGG 病例进行了评估和解释。对于存在大量数据缺失的皮肤切除性黑色素瘤（TCGA SKCM）和子宫体内膜癌（TCGA-UCEC），数据对齐的标准被放宽，仅包括仅具有匹配的 WSI-MUT-RNA 和 WSI-CNV-MUT 的样本。我们注意到，在 TCGA SKCM 中，我们还包括了转移病例，因为很少有原发肿瘤具有匹配的分子特征信息。为了减少分子特征数据中特征的稀疏性，采用了在每个癌症研究中具有大于 10% CNV 或 5%突变频率的基因。在 TCGA-SKCM 和 TCGA-UCEC 中，我们使用了 10%的突变频率作为阈值，因为对其他癌症类型使用该阈值得到的基因特征很少或者为零。为了限制来自 RNA-Seq 的特征数量，我们使用了 Molecular Signatures 数据库（Subramanian et al., 2005）中的基因家族类别的基因集。分子和临床数据是从 cBioPortal 的质量控制文件中获取的。队列特征、审查统计和特征对齐的摘要表格可以在表 S1 和 S3 中找到。

WSI 处理对于每个 WSI，使用公共的 CLAM（Lu et al., 2021）存储库进行 WSI 分析，执行组织的自动分割。在分割完成后，从所有已识别的组织区域提取 2563256 大小的图像块，无重叠。随后，使用在 ImageNet 上预训练的 ResNet50 模型作为编码器，通过在第 3 个残差块之后进行空间平均池化，将每个 2563256 图像块转换为 1024 维的特征向量。为了加快处理速度，多个 GPU 并行计算，每个 GPU 的批处理大小为 128。基于深度学习的综合全幻灯片图像和基因组特征的生存分析 PORPOISE（Integrated Survival Estimation 的病理-组学研究平台）采用了一种高吞吐量、可解释性弱监督多模态深度学习算法（MMF），旨在集成全幻灯片图像和分子特征数据，用于进行弱监督学习任务，如通过生存分析进行患者级别的癌症预后。给定诊断的金字塔文件和单个患者的处理过的基因组和转录组特征，MMF 学习以共同表示这两种异构数据模态。尽管任务是生存分析，我们的算法适用于任何模态组合，并且灵活解决计算病理学中具有患者级别标签的任何学习任务。我们的算法由三个部分组成：1）基于注意力的多实例学习（AMIL）用于处理 WSI，2）自正则化网络（SNN）用于处理分子特征数据，3）融合 WSI 和分子特征数据的多模态融合层（扩展自 Pathomic Fusion）（Chen et al., 2020; Ilse et al., 2018; Klambauer et al., 2017; Lu et al., 2021）。

为了从 WSIs（全扫描图像）进行生存预测，我们扩展了基于注意力的多示例学习算法，该算法最初用于弱监督分类。在多示例学习框架下，每个亿像素 WSI 被分成较小的区域，并被视为一组（包）具有相应滑动级别标签的补丁（实例）用于训练。相应地，在 WSI 处理后，每个 WSI 包由 Mi3C 矩阵张量表示，其中 Mi 是补丁的数量（包大小），在不同幻灯片之间变化，而 C 是特征维度，并且对于我们使用的 ResNet50 编码器而言等于 1024.由于生存结果信息是在患者层面而不是针对单个幻灯片，因此我们在训练和评估期间将与患者病例对应的所有 WSIs 以单个 WSI 包的形式一起处理。换句话说，对于具有 N 个 WSIs 和包大小分别为 M1; /; MN 的患者病例，与该患者对应的 WSI 包由所有 N 个包连接而成，其维度为 M×1024，其中 M =ΣN。模型可以由三个组件描述，投影层 fp、注意力模块 fattn 和预测层 fpred。每个 WSI 包的入场级别嵌入，H ∈ R^M×1024，首先通过具有权重 Wproj ∈ R^512×1024 和偏差 bbias ∈ R^512 的全连接层 fp 映射到更紧凑的 512 维特征空间中。为简洁起见，从现在开始，我们只使用层的权重来引用层（偏差项隐含在内）。随后，注意力模块 fattn 学习将每个区域评分以确定其与患者级别预测的相关性。具有高注意力分数的区域相对于具有低注意力分数的区域在聚合患者 WSIs 中的所有区域的信息中对患者级别特征表示的贡献更大，这一操作被称为注意力池化（Ilse et al., 2018）。具体而言，fattn 由三个具有权重 Ua ∈ R^256×512、Va ∈ R^256×512 和 Wa ∈ R^13×256 的全连接层组成。给定一个补丁嵌入 hm ∈ R^512（H 的第 m 行条目），其注意力分数 am 通过以下计算得出：am = exp(Wa _ tanh(Va _ hu + 1 _ sigm(Ua _ hu))) / Σm{exp(Wa _ tanh(Va _ hu + 1 _ sigm(Ua _ hu)))}。

注意力池化操作然后将补丁级特征表示聚合为患者表示 hpatient ∈ R^512，使用计算得到的注意力分数作为权重系数，其中 A ∈ R^M 是注意力得分的向量：hpatient = Attnpool(A, H) = Σm{am \* hm}。最终的患者级预测分数 s 通过使用具有权重 Wpred ∈ R^4×3512 和 sigmoid 激活的预测层 fpred 来计算：s = fpred(hbag)。这种体系结构选择和离散时间生存建模的负对数似然函数在之前的章节中详细描述。最后的全连接层用于学习表示 hWSI ∈ R^32×31，然后将其用作我们的多模态融合层的输入。

为了使用分子特征进行生存预测，我们采用了先前在高维低样本情况下表现良好的自标准化网络(Self-Normalizing Network, SNN) (Klambauer et al., 2017)。在拥有相对较少训练样本但有数百到数千个特征的基因组学等学习场景中，传统的前馈网络容易出现过拟合问题，以及目前深度学习正则化技术(如随机梯度下降和 Dropout)的训练不稳定性。为了在高维低样本基因组学数据上使用更稳健的正则化技术，我们采用了 SNN 架构中的归一化激活和丢弃层：1) 缩放指数线性单元 (Scaled Exponential Linear Units, SeLU) 和 2) Alpha Dropout。与当前前馈网络中常见的修正线性单元 (Rectified Linear Units, ReLU) 激活相比，SeLU 激活在传播时会使每层的输出趋近于零均值和单位方差。SeLU 激活的定义如下：SeLU(x) = λx (if x > 0) aexp(x) − a (if x ≤ 0)，其中 λ=1.67，a=1.05。为了在丢弃层之后保持归一化，我们将激活值设置为 limx→−∞SeLU(x) = -λ/a，这确保了具有更新均值和方差的自标准化属性：E(x_d + a(1 - d)) = qm + (1 - q)a，Var(x_d + a(1 - d)) = q(1 - q)(a - m)^2 + n。在用于分子特征输入的 SNN 架构中，我们使用了每层 256 个神经元的 2 个隐藏层，每层都应用了 SeLU 激活和 Alpha Dropout。最后的全连接层用于学习一个表示 hmolecular ∈ R^{3231}，然后将其作为输入传递给我们的多模态融合层。我们通过去除自标准化和 L1 正则化的全连接层对多模态融合性能进行了分析，发现自标准化和 L1 正则化对多模态训练很重要 (表 S3)。

多模态融合层。在构建来自 AMIL 和 SNN 子网络的单模态特征表示之后，我们使用 Kronecker 乘积融合学习一个多模态特征表示，以捕捉这两种模态之间的重要交互 (Chen et al., 2020; Zadeh et al., 2017)。我们的联合多模态张量是通过 hWSI 和 hmolecular 的 Kronecker 乘积计算得到的，其中 hmolecular 中的每个神经元都与 hWSI 中的每个神经元相乘，以捕捉所有双模态交互。为了保留单模态特征，我们在融合之前向每个单模态特征表示附加"1"，如下所示：= 5，其中 5 表示 Kronecker 乘积，hfusion ∈ R^{33333} 是一个可微分的多模态张量，用 O(1)的计算模型建模了所有单模态和双模态的交互。为了减少噪声单模态特征的影响，并减少 WSI 和分子特征模态之间的特征共线性，我们使用了一个基于门控的注意机制，另外控制了每个模态的表达能力：= zi · hi，其中 chi ∈ {hWSI, hmolecular}，hi = ReLU(Wi, hi)，zi = s(Wj, [hWSI, hmolecular])。对于具有学习的单模态特征 hi 的模态 i，我们学习一个权重矩阵 Wj，用于评分模态 i 中每个特征的相对重要性。在执行 Softmax 之后，zi 可以解释为 hWSI 和 hmolecular 对 hi 中每个特征的注意得分。我们通过将原始的单模态特征 hi 和注意得分 zi 进行逐元素乘积，得到门控表示 hi;gated。在我们实现的基于门控的注意机制中，我们在融合之前对两个模态都应用了门控，同时在多模态网络的倒数第二个隐藏层添加了额外的跳跃连接。在 Kronecker 乘积融合之后，我们将多模态张量传递到两个大小为 256 的隐藏层，并使用基于交叉熵的损失函数对生存分析进行监督。表 S3 展示了使用多模态门控进行病理和基因组门控，以及在 Kronecker 乘积融合之前的消融研究。为了评估与其他融合机制的多模态表现，我们比较了向量串联和 Kronecker 乘积融合的低秩实现，这些方法同样优于单模态方法 (表 S3) (Liu et al., 2018)。


# 文章计算硬件和软件

PORPOISE 使用 OpenSeaDragon API 构建，并托管在 Google Cloud 上。PORPOISE 使用 Python（版本 3.7.7）的软件包包括 PyTorch（版本 1.3.0），Lifelines（版本 0.24.6），NumPy（版本 1.18.1），Pandas（版本 1.1.3），PIL（版本 7.0.0）和 OpenSlide（版本 1.1.1）。所有的 WSIs 都是在 Intel Xeon 多核 CPU 和总共 16 个 2080 Ti GPU 上处理的，使用我们自定义的公开可用的 CLAM（Lu 等人，2021 年）全尺寸处理流程。用于集成 WSIs 和分子谱的多模态融合层采用我们自定义的公开可用的 Pathomic Fusion（Chen 等人，2020 年）软件在 Python 中实现。深度学习模型使用 Nvidia 软件 CUDA 11.0 和 cuDNN 7.5 进行训练。Integrated Gradients 使用 Captum（版本 0.2.0）实现（Kokhlikyan 等人，2020 年）。细胞实例分割和分类使用 HoVerNet 软件实现（Graham 等人，2019 年）。统计分析，如双样本 t 检验和 Log-Rank 检验，分别使用 SciPy（1.4.1）和 Lifelines（版本 0.24.6）进行实现。绘图和可视化软件使用 Seaborn（0.9.0），Matplotlib（版本 3.1.1）和 Shap（0.35.0）生成。

QUANTIFICATION AND STATISTICAL ANALYSIS
为了绘制 Kaplan-Meier 曲线，我们将验证折叠中的样本风险预测聚合起来，并将其绘制为生存时间（Mobadersany 等人，2018 年）。对于 Kaplan-Meier 分析中患者分层的显著性测试，我们使用 log-rank 测试来测量两个生存分布之间的差异是否具有统计学意义（P 值<0.05）（Bland 和 Altman，2004 年）。交叉验证的 c-Index 性能报告为 5 折交叉验证的平均 c-Index。为了估计交叉验证中的 95%置信区间，我们对验证折叠中的样本进行非参数自助法（bootstrapping）重复 1000 次，生成外样本预测结果（LeDell 等人，2015 年；Tsamardinos 等人，2018 年）。除了 c-Index 之外，我们还报告了累积/动态 AUC（称为生存 AUC），这是一种时间相关的模型性能度量，评估模型在不同时间点上对患者风险的划分情况，并通过计算逆概率权重来校正对审查的乐观偏差。对于评估个体细胞类型存在的全局形态特征的显著性，我们在低风险和高风险患者的前 1%最关注区域的平均细胞比例分布中执行双样本 t 检验（P 值<0.05）。对于评估个体基因特征的全局分子特征显著性，我们在低和高基因特征值（低于和高于基因特征值中位数）的归因分布中执行双样本 t 检验。对于所有的箱线图，箱体表示数据分布的第 1、中位数和第 3 个四分位数，而须线延伸到 1.5 个四分位距之内的数据点。
