引言：肿瘤浸润性 B 细胞已成为癌症免疫中的重要因素，并作为对免疫治疗反应的预测指标。这些 B 细胞展示了多种功能，主要通过其分化成浆细胞来产生抗体，但在不同癌症类型中的空间和时间分布各不相同。解析不同癌症类型中 B 细胞的丰度和分化状态，对于提高免疫治疗反应具有重要意义。

理由：为了编制全面的泛癌症 B 细胞图谱，我们对各种癌症类型患者的配对肿瘤、淋巴结转移、邻近正常组织以及外周血进行了单细胞 RNA 测序（scRNA-seq），并整合了大量已发表的 scRNA-seq 数据集。在校正批次效应后，这一图谱包含来自 269 名患者的 20 种癌症类型的 scRNA-seq 数据。我们结合了单个 B 细胞的 B 细胞受体（BCR）测序与基因表达谱，以表征 B 细胞与抗体分泌细胞（ASCs）之间的动态转换。我们整合了来自不同癌症的 B 细胞的单细胞染色质可及性景观，以解析在微调 B 细胞发育中起作用的表观遗传调控网络。我们在成熟与未成熟的第三方淋巴结构（TLSs）中定位了 B 细胞，并研究了指导 B 细胞产生特定反应的潜在调节因子。

B 细胞是适应性免疫系统的重要组成部分，在体液免疫反应和抗体生成中发挥核心作用。在肿瘤微环境（TME）中，肿瘤浸润 B 细胞（TIBs）表现出显著的功能异质性，涵盖从初级 B 细胞、记忆 B 细胞（Bm）、生发中心（GC）B 细胞到抗体分泌细胞（ASCs，包括浆母细胞和浆细胞），主要基于它们的免疫表型。然而，当前的 B 细胞研究范式大多是假设驱动的，可能无法无偏见地捕捉肿瘤环境中 B 细胞状态的全谱。最近的报告指出，B 细胞在产生针对肿瘤相关抗原的抗体、促进吞噬作用以及向 CD8+ T 细胞呈递抗原方面具有抗肿瘤能力，表明 B 细胞可用于下一代免疫疗法。空间上，这些细胞在第三方淋巴结构（TLS）中与 T 细胞密集相互作用，这与多种癌症中生存率提高和热肿瘤环境相关。然而，TIBs 也显示出通过释放细胞因子、形成免疫复合体和参与免疫检查点的肿瘤促进属性。这些观察结果强调了 B 细胞的阴阳作用，并突显了需要对人类癌症中 B 细胞进行全面的数据驱动分析的必要性。

历史上，长期以来认为 ASCs 源自 GC 反应。在这种情况下，B 细胞遇到抗原，经历体细胞高频突变、类转换重组（CSR）和克隆扩增，最终分化成长寿命的浆细胞并产生高亲和力抗体。另外，最近发现的外滤泡（EF）分化途径揭示了短寿命的 ASCs，产生低亲和力和多反应性抗体。EF 相关 B 细胞在老龄化小鼠、自身免疫疾病和慢性感染模型中被记录为年龄相关 B 细胞（ABCs）、双阴性 B 细胞（BDN）或非典型记忆（AtM）B 细胞，其特征为 CD21-CD11c+，并表达 T-box 转录因子（T-bet）。我们和其他独立研究组也报告了如 Toll 样受体 7/9（TLR7/9）、干扰素 γ（IFNg）、白细胞介素 -21（IL-21）和 CD40 等信号在自身免疫疾病中驱动 EF 相关 B 细胞状态发展的作用。这些数据提出了一个关键问题：B 细胞的命运由什么组成，以及如何在癌症生态系统中精确调控。因此，系统地解码癌症中 B 细胞的发展层级可能会揭示肿瘤特异性模式以及克隆谱系。

在这项研究中，我们编制了涵盖 20 种不同人类癌症的 TIBs 图谱。我们系统地表征了 15 种 B 细胞亚群，并识别了之前未被认识的 AtM B 细胞以及 TME 中 EF 途径的存在。我们的数据揭示了两种不同的 ASC 分化途径—GC 和 EF 路径—显示出癌症类型偏好。我们特别描述了与常规 GC B 细胞相比的 AtM B 细胞的独特表型、功能、TLS 定位和临床意义。特别是，肿瘤浸润的 AtM B 细胞，EF 来源 ASCs 的祖细胞，表现出耗竭和旁观者表型，并独立于 GC 发展。我们将这些发现与特定的转录因子和表观遗传调控相关联，并展示了代谢微环境的影响，其中谷氨酰胺在调节 AtM B 细胞分化和采纳免疫调节功能中起作用。我们的研究提供了前所未有的大规模 B 细胞转录组数据，作为研究 TIBs 并可能指导有效的 B 细胞导向癌症免疫治疗策略的宝贵资源。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101517199.png)

> 图 1. 跨不同人类癌症的 B 细胞单细胞分析。
> (A) 泛癌症单细胞转录组、B 细胞受体（BCR）复合体以及 B 细胞染色质可及性的示意图。
> (B) 15 种 B 细胞亚群的均匀流形逼近和投影（UMAP）可视化。
> (C) B 细胞亚群中标志基因表达的点图。颜色代表标志基因的最大归一化平均表达，大小表示表达这些基因的细胞百分比。
> (D) 堆叠条形图显示相应组织中总 B 细胞的同种型分布。
> (E) 热图显示各组织中 B 细胞亚群分布的比率（ORs）。OR 值表示在相应组织中的偏好分布。
> (F) 不同组织中总 B 细胞的免疫球蛋白 H（IgH）链上超突变频率的箱形图。数据显示中位数及四分位数范围（IQR），须线表示最小和最大测量值。 \*\*\*\*P < 0.0001。P 值由双侧 Wilcoxon 检验确定。

### 结果

#### 跨人类癌症的单个 B 细胞转录组蓝图

B 细胞浸润在不同的人类癌症类型中高度变异。为了理解 B 细胞的总体浸润模式，我们基于六种现有去卷积算法的共识，评估了癌症基因组图谱（TCGA）泛癌症数据集（包括 8863 个肿瘤样本，涵盖 31 种癌症类型）中 B 细胞浸润的丰度（图 S1A）。我们选取了具有高和中等肿瘤内 B 细胞得分的癌症类型进行进一步采样。从 15 种人类癌症类型的 66 名患者的 153 个样本中分选出 CD19+ B 细胞，包括匹配的肿瘤、淋巴结转移（LN_Mets）、邻近正常组织和外周血，随后进行了配对的单细胞 RNA 测序（scRNA-seq）和单细胞 B 细胞受体测序（scBCR-seq）（图 1A 和图 S1B）。我们还整合了包含 TIBs 的多种已发表数据集，使用 Harmony 算法（25）校正批次效应，并最终在 20 种癌症类型的 269 名捐献者的 477 个样本中建立了单细胞转录组图谱。经过严格的质量控制，我们获得了总共 474,718 个单 B 细胞转录组，其中 69.24% 是在本研究中新生成的（图 S1C 和表 S1）。对于 scBCR-seq，共产生了 166,733 个细胞，来自 150,949 个克隆型，涵盖 15 种癌症类型的 61 名捐献者，每个克隆型至少携带一对生产性重链和轻链，其中 12.76% 为克隆型（≥ 两个 B 细胞含有相同的 BCR 对），对应 21,268 个扩展克隆型。总体而言，我们的单细胞图谱为 B 细胞研究创建了一个泛癌症蓝图（可在 http://pancancer.cn/B/ 获取）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101600701.png)

> 图 S1. 患者队列和 B 细胞亚群信息。
> (A) 癌症基因组图谱（TCGA）泛癌种肿瘤样本的 B 细胞一致性浸润水平。
> (B) 代表性流式图显示在一个宫颈鳞状细胞癌（CESC）样本中（B 细胞浸润水平为中等）的分选策略。
> (C) 泛癌 B 细胞研究包括的患者和细胞数量。详细的样本信息在表 S1 中提供。
> (D) 条形图显示癌症类型（左侧）和 B 细胞亚群的组织分布（右侧）。
> (E) 条形图显示主要组织群中 15 种 B 细胞亚群的相对细胞比例。
> (F) UMAP 图显示 B 细胞亚群的典型标记基因的表达。

#### B 细胞的转录多样性

无监督聚类分析鉴定出 15 个独特的 B 细胞亚群，这些亚群在各种癌症类型中均可重复观察到，并表现出明显的组织和癌症类型偏好（图 1B；图 S1, D 和 E；表 S2）。其中，典型的 B 细胞亚群代表了不同的 B 细胞成熟阶段，包括一个初级 B 细胞（TCL1A、FCER2 和 IGHD）、三个活化 B 细胞（ACBs；CD69 和 CD83）、一个记忆 B 细胞（Bm；CRIP2 和 ITGB1）、三个生发中心 B 细胞（LMO2+ 轻带、CXCR4+ 暗带和 MKI67+ 周期性），以及两个抗体分泌细胞（包括 TXNDC5+ 浆母细胞和 MZB1+ 浆细胞）（图 1C 和图 S1F）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101604465.png)

> 图 S2. B 细胞亚群的转录和 BCR 特征
> (A) 我们研究中的 B 细胞亚群和注释（行）与五项先前研究中的注释（列）进行比较，这些研究分别是 Xue 等人（26），Pelka 等人（27），Wieland 等人（28），Laughney 等人（30）和 Kim 等人（29）。比较是根据使用我们的数据作为参考的 CellTypist（135）训练的逻辑回归模型进行的。颜色标尺代表预测特定细胞类型的平均概率，点的大小代表被预测为特定细胞类型的细胞百分比。
> (B) 肺癌（LC）患者配对的血液和肿瘤浸润 B 细胞中 HSP70 和 HSP90 表达的代表性流式图。这些数据展示了不同解离方法的影响。
> (C) 多重免疫组化（IHC）染色的代表性图像显示结直肠腺癌（COAD）、食管癌（ESCA）和肝细胞癌（LIHC）中 HSP70+ 受压 B 细胞。白色箭头表示 HSP70+ 受压 B 细胞。
> (D) 小提琴图显示在初级和受压 B 细胞间低氧相关基因表达的差异。
> (E) 左侧面板：UMAP 图显示自身免疫疾病数据集（顶部）的 12 个 B 细胞簇和 HBV 感染数据集（底部）的 11 个 B 细胞簇。中间面板：自身免疫疾病数据集（顶部）和 HBV 感染数据集（底部）中 AtM B 细胞的特征得分。右侧面板：自身免疫疾病数据集（顶部）和 HBV 感染数据集（底部）中 AtM B 细胞特征基因表达的点图。颜色代表标记基因的最大标准化平均表达，大小代表表达这些基因的细胞百分比。簇 9 富含 AtM B 细胞特征。
> (F) 火山图显示肿瘤与自身免疫疾病（左侧）或 HBV 感染（右侧）衍生的 AtM B 细胞之间差异表达的基因。每个红点表示具有 Benjamini-Hochberg 调整后 P 值<0.05 的单个基因，使用双侧 t 检验。标记了 Top15 基因。
> (G) 通过 GSVA 分析，肿瘤与自身免疫疾病（顶部）或 HBV 感染（底部）衍生的 AtM B 细胞之间富集的差异通路。使用双侧未配对 limma-moderated t 检验。
> (H) 条形图堆叠显示 15 个 B 细胞亚群中癌症特异性扩展克隆的频率（顶部）和密度（底部）。
> (I) 盒形图显示癌症与邻近正常组织、癌症与血液或淋巴结转移与血液之间的双向迁移指数（pMigr）的分布。每个点代表一个捐赠者。
> (J) 三角热图显示 Bm、AtM 和浆细胞在四种组织类型中扩展的 BCR 克隆类型的重叠。数据为每个患者组内汇总。数字表示每对组织类型共享的扩展 BCR 克隆类型的标准化 Jaccard 指数。
> (K) 热图显示癌症与邻近正常组织、癌症与血液或淋巴结转移与血液之间的 pMigr 得分，按癌症类型分层。颜色代表按行缩放的 pMigr 值的 z 分数。

我们接下来鉴定了四个以前大多未被描述的亚群（26-30）（图 S2A）。第一个是干扰素刺激基因阳性的初级 B 细胞亚群（B_02），它高表达 IFIT3、IFI44L 和 ISG15，与受伤相关，并在粘膜愈合期间扩展（31）。第二个亚群是应激 B 细胞（B_03），在肿瘤中占主导地位，高表达热休克蛋白，经 37°C 胶原酶和 4°C 机械分离以及多重免疫组化（mIHC）验证（图 S2，B 和 C）。与应激 T 细胞相比（32），应激 B 细胞也位于 TLS 中心，高表达与缺氧相关的基因，如 HIF1A、NFE2L2、RELB、NFKB1 和 NFKB2（图 S2D）。第三个亚群是前生发中心 B 细胞（B_10），与邻近正常组织和血液相比，在淋巴结转移和肿瘤中高度富集，表达 PSME2、NME1 和 ENO1。前生发中心 B 细胞在转录上类似于初级 B 细胞、生发中心 B 细胞和浆母细胞，表明它们的过渡阶段（图 1C）。

我们鉴定的第四个亚群是此前未知的非典型记忆 B 细胞亚群（B_09），表达 DUSP4、ITGAX（CD11c）、FCRL5、ZEB2 和 FGR。此前，这种亚群被记录为年龄相关 B 细胞、CD27−IgD− 双阴性 B 细胞、FCRL4+ B 细胞或在老龄化小鼠、自身免疫疾病、扁桃体和慢性感染中报告的耗竭 Bm 细胞（16, 19, 23, 24），现在显示它们在 TME 中广泛存在（图 1C）。我们收集并分离了自身免疫疾病和乙型肝炎病毒（HBV）感染数据集中已发表的 scRNA-seq AtM B 细胞（表 S1），并进行了差异表达基因分析，显示肿瘤浸润的 AtM B 细胞高表达与应激相关的基因（FOSB 和 HSPA1A）、干扰素诱导的基因（IFITM1 和 IFI30）和激活相关的基因（CD83、NR4A1 和 CD69），而与初级相关的基因（TXNIP 和 IGHD）和代谢相关的基因（MT-ATP6 和 NDUFB1）在自身免疫疾病和 HBV 感染中富集（图 S2，E 和 F 及表 S2）。同样，肿瘤中的 AtM B 细胞在炎症反应和缺氧途径中富集，而自身免疫疾病和 HBV 感染中则主要是血管生成和代谢途径（图 S2G）。这些数据强调，在 TME 中的 AtM B 细胞在功能上可能有所不同，尽管它们在表型上与自身免疫疾病和病毒感染中的细胞一致。

综合分析组织分布、转录和复合体特征突出了来自不同组织源的潜在肿瘤反应性 B 细胞。TIBs 含有比非肿瘤组织的 B 细胞更多的 IGHG 和 IGHA，而血液中的 B 细胞富含 IGHD 和 IGHM，表明 TIBs 经历了抗原体验并进行了类转换重组（CSR）（图 1D）。通过比率（OR）分析（33），HSP+ B 细胞、EGR1+ACBs 和浆母细胞在肿瘤中有强烈偏好；MT1X+ B 细胞、周期性 GC B 细胞、前生发中心 B 细胞、GCLZ、GCDZ 和 IFIT3+ B 细胞在淋巴结转移中显著富集；TCL1A+ 初级 B 细胞和 DUSP4+ AtM B 细胞在血液中最高；而 MZB1+ 浆细胞在邻近正常组织中占主导（图 1E）。再次，与其他组织中的相比，TIBs 的 IGH 突变显著增多，GC B 细胞和两个 ASC 亚群显示出肿瘤特异的克隆扩张，表明它们具有强烈的抗原驱动的抗体亲和力（图 1F 和图 S2H）。此外，ITGB1+ Bm 和 DUSP4+ AtM B 细胞在肿瘤、淋巴结转移和血液中的富集程度相当，略高于邻近正常组织，暗示了跨组织迁移潜力。实际上，STARTRAC 迁移指数（pMigr）（34），用于量化组织间迁移的可能性，以及 Jaccard 指数（35），显示了不同组织间共享 BCR 克隆的数量，表明 ITGB1+ Bm 和 AtM B 细胞在血液与淋巴结转移或肿瘤之间有适度的流动性，在大约一半的癌症中观察到（图 S2，I 至 K）。

#### 肿瘤浸润的抗体分泌细胞（ASCs）的异质性

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101605209.png)

> 图 S3. 肿瘤浸润的浆细胞显示出增加的异质性和独特的发展路径。
> (A) 盒形图显示主要组织群中 B 细胞和 ASC 组成的多样性分布，通过 Shannon 多样性指数测量。
> (B) B 细胞受体（BCR）克隆型多样性（左）和血液、邻近正常组织、淋巴结转移（LN_Met）和癌症之间的克隆大小分布（右）。分析了前 150 个 BCR 克隆型。中心线表示线性拟合，阴影区域表示通过 1000 次自助法得到的 95％置信区间。
> (C) 盒形图显示血液、邻近正常、淋巴结转移和癌症中 PB 和 MZB1+rASC 的频率。
> (D) 盒形图显示不同癌症类型中肿瘤内 PB（左）和 MZB1+PC（右）的频率。
> (E) 盒形图比较两个浆细胞亚群与其余亚群的转录细胞纯度，通过 ROGUE 指数测量。每个点代表一个样本。
> (F) UMAP 视图显示四个主要组织群中浆细胞亚群（顶部）和细胞密度（底部）。对四个组织群进行了降采样。高相对细胞密度显示为明亮的岩浆色。
> (G) Monocle3 分析描绘了 B 细胞的发展轨迹（黑色骨架线）（左）。细胞根据 Monocle3 伪时间着色（右）。
> (H) 三角热图显示四种组织类型中所有 B 细胞亚群间扩展的 BCR 克隆型的重叠。数据从每个组内的每个患者聚合。数字表示每对亚群共享的扩展 BCR 克隆型的标准化 Jaccard 指数。
> (I) 条形图显示 PB 或 MZB1+rASC 与其他 B 细胞亚群之间的双向过渡指数（pTrans）。
> (J) UpSet 图描绘 B 细胞与 ASCs 共享的扩展克隆数量。条形图显示浆细胞和指示的 B 细胞之间共享的克隆数量。每个 B 细胞亚群的总克隆数量由左侧的条形显示。
> (K) 热图显示 ASC 与非 ASC 亚群之间的克隆型共享。行代表克隆型，列代表不同的组织类型。通过共享细胞数量着色。
> (L) 共享克隆型的系统发育谱系树，包括 EF 途径中 ASC 细胞与 AtM 或其他 B 细胞之间的关系，包括 IFIT3+B、EGR1+ACB1 和 HSP+B（顶部），以及 ASC 细胞与 Bm 或 GCB 细胞在 GC 途径中的关系（底部）。体细胞突变的获得由分支上的数字表示，表示突变数量和分枝。假定的未突变的共同祖先由白圈显示。数据显示中位数及四分位范围，须表示最小和最大测量值（A, C, D 和 E）。 \*P<0.05； **P<0.01； \***P<0.001； \*\*\*\*P<0.0001；ns 表示无显著性。 P 值通过双侧 Wilcoxon 检验（A, C, E）和双向 ANOVA（D）计算。

ASCs 是终末分化的 B 细胞，通过产生抗体执行效应功能（36）。与将 ASCs 归类为同质亚群的现有数据相比（14, 28, 37, 38），我们的高分辨率图谱显示，肿瘤浸润的 ASCs 在组织分布、癌症类型偏好、BCR 复合体和转录组特征上表现出多面性的多样性。首先，根据 Shannon 均等性指数（39），ASCs 的比例显示出很大的变化，其中肿瘤浸润的 ASCs 比邻近正常组织和血液中的 ASCs 显示出更高的多样性（P < 0.01），而非 ASCs 在淋巴结转移（LN_Mets）中的多样性最高（图 S3A）。其次，我们观察到 BCR 克隆型的多样性增加以及扩展 BCR 克隆型数量的增加。然而，在肿瘤中观察到较低的克隆频率，表明与其他组织相比，肿瘤中的克隆大小更为同质，其中少数扩展克隆主导了复合体（图 S3B）。第三，癌症类型对 ASCs 的频率产生了强烈的影响（图 S1D）。在两个 ASC 亚群中，肿瘤浸润的 MZB1+ 浆细胞的中位频率为 TIBs 的 12.52%，在结肠腺癌（COAD）中高达 70.18%，而在胆管癌（CHOL）和胃腺癌（STAD）中几乎无法检测到（1.85% 和 3.32%）[方差分析（ANOVA），P < 2e−16]（图 S3，C 和 D）。肿瘤浸润的 TXNDC5+ 浆母细胞的中位频率为 0.13%，但在不同癌症类型中仍有变化（P = 1.1e−5）。最后，ROGUE 分析（40），用于量化识别的细胞类型的转录组纯度，进一步确认在 15 种 B 细胞亚群中，2 个 ASC 亚群展示了最高的基因表达异质性（图 S3E）。对 ASC 部分的亚群分析（移除 TXNDC5+ 浆母细胞）揭示了 10 个具有特定基因标记和组织分布的不同浆细胞亚群（图 2，A 和 B；图 S3F；表 S2）。其中，PC04.HSPA1A、PC05.NEAT1 和 PC08.IFI6 在肿瘤中占主导，PC09.RGS13 和 PC10.SPINK2 在邻近正常组织中积累，PC02.RGS13 在 LN_Mets 中普遍存在。同时，PC01.NME2 和 PC07.CD83 在 LN_Mets 和血液中富集相当，PC03.DUSP5 在 LN_Mets 和肿瘤中分布均匀，PC06.SLC3A2 在肿瘤和邻近正常组织中分布类似（图 2C）。这些发现有助于解释 PCs 在患者预后中的争议性角色（5, 41, 42），这可能归因于不同 PC 亚群和癌症类型的可变性。总体来说，这些数据表明癌症起源对 ASCs 的频率有重大影响，并暗示 ASCs 可能有不同的 B 细胞起源。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101529466.png)

> 图 2. 人类癌症中浆细胞的两种发展路径。
> (A) 10 种浆细胞亚群的 UMAP 可视化。
> (B) 已识别浆细胞亚群的标志基因的点图。颜色代表表达标志基因的细胞的最大归一化平均表达量，大小代表表达这些基因的细胞百分比。
> (C) 热图显示各组织中浆细胞亚群分布的比率（ORs）。OR 值表示在相应组织中的偏好分布。
> (D) 配对转换指数（pTrans）显示非 ASCs 与 ASCs 之间的 BCR 重叠。高度连接到 ASCs 的前两个亚群被突出显示。
> (E 和 F) 通过 FACS 分离肝细胞癌（LIHC）患者肿瘤浸润的初级（Bn）、记忆（Bm）和非典型记忆（AtM）B 细胞，并在体外用 R848、IL-2、IL-10 和 IL-21 刺激 11 天（捐赠者数量=3 至 7）。代表性流式细胞图（E）和通过 FACS 检测的 CD19+ B 细胞中 ASCs 的频率（F）。数据显示中位数及四分位数范围，须线表示最小和最大测量值。
> (G)（顶部）ASC 细胞与 AtM B 细胞之间共享的克隆型的系统发育谱系树，（底部）ASCs 与 Bm 或 GC B 细胞之间的。树枝上的数字表示突变数和分支数，假设的未突变的共同祖先由白色圆圈表示。
> (H) 热图显示 ASCs 与其他 B 细胞亚群之间的 pTrans 值，按不同癌症类型分类。颜色代表按行缩放的 z 分数 pTrans 值。
> (I) 箱形图显示不同组织中 EF 和 GC 来源 ASCs 的体细胞超突变（SHM）频率。数据显示中位数及四分位数范围，须线表示最小和最大测量值。
> (J) 堆叠柱状图显示不同组织中 EF 和 GC 来源 ASCs 的 IGH 同位型频率。
> (K) 癌症中 EF 来源（上）和 GC 来源（下）ASCs 的类转换重组（CSR）频率。线条粗细表示两种 Ig 同位型之间共享克隆型的数量，点的大小表示每种同位型的克隆扩展。
> (L) UMAP 图显示识别 EF 和 GC 来源 ASCs（左上角）、通过 CytoTRACE 确定发展顺序（右上角）、通过 scTour 推断的分化状态（左下角）、以及通过 Monocle3 推断的分化状态（右下角）。
> (M) 草图显示 EF 与 GC 反应的分化路径。中间表格总结了 TME 中 EF 和 GC 的特征。
> 对于 (F) 和 (I), \*P < 0.05, \*\*P < 0.01, \*\*\*\*P < 0.0001。P 值由双侧 Wilcoxon 检验确定。

#### 肿瘤劫持了生发中心和外滤泡路径

尽管生发中心（GC）和外滤泡（EF）反应源自 B 细胞的途径在自身免疫疾病和慢性感染中常见（21, 43, 44），但肿瘤生态系统影响不同 B 细胞进化轨迹的潜力尚未得到充分探索。因此，我们利用基因表达推断 ASCs 分化的轨迹，并观察到 ASCs 主要源自 GC B 细胞（图 S3G），这与以前的研究一致（2, 45）。然而，鉴于通过无监督聚类基于 PC 标记基因的高表达显著区分 ASC 亚群与其他亚群，传统的基于转录组的轨迹分析可能无法准确反映真实的分化状态。为了解决这个问题，我们使用 BCR 克隆共享策略和无监督聚类，通过 STARTRAC [通过 RNA 测序和 T 细胞受体（TCR）跟踪的单 T 细胞分析] 配对转换指数（pTrans）、Jaccard 指数（35）和体细胞超突变（SHM）鉴定 ASCs 的祖先，因为 BCR 复合体是追踪 ASCs 谱系的可靠分子标签。我们发现 AtM 和 Bm 细胞是与 ASCs 有克隆共享的两种主要 B 细胞，表明 ASCs 可能源自肿瘤微环境中的典型 GC 和替代 EF 途径（图 2D 和图 S3，H 和 I）。为了验证这一点，从肝细胞癌（LIHC）患者中分选出肿瘤浸润的初级 B、Bm 和 AtM B 细胞，并使用体外 B 细胞分化方法进行刺激。事实上，AtM B 细胞比初级 B 细胞（P = 0.035）更有效地分化为 ASCs，但比 Bm 细胞（P = 0.0027）分化能力弱（图 2，E 和 F）。除了 AtM 和 Bm 细胞外，我们还识别了与浆母细胞共享 BCR 的前 GC、循环 GC 和 GCLZ B 细胞，以及与浆细胞共享 BCR 的 IFIT3+ B、HSP+ B 和 EGR1+ACBs，这些通过共享克隆的系统发育谱系树得到验证（图 2G 和图 S3，J 到 L）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101608930.png)

> 图 S5. EF 来源和 GC 来源的 ASCs 在转录和 BCR 特征上的差异。
> (A) 盒形图显示肿瘤浸润的 EF 来源和 GC 来源的 ASCs 的频率。
> (B) 盒形图显示通过 ROGUE 指数测量的 EF 来源和 GC 来源 ASCs 的纯度。每个点代表一个样本。
> (C) BCR 克隆型多样性（左）（q=0，q=1 和 q=2，相当于物种丰富度、香农熵和辛普森指数）和 EF 来源和 GC 来源 ASCs 的克隆大小分布（右）。显示前 150 个 BCR 克隆型。中心线表示线性拟合，阴影区域表示通过 1000 次自助法得到的 95％置信区间。
> (D) 盒形图显示不同组织中 EF 来源和 GC 来源 ASCs 的同种型频率。
> (E) 血液、邻近正常组织和 LN_mets 中 GC 来源 ASCs 的类换位重组频率。EF 来源的 ASCs 在这些组织中缺乏 CSR。线的厚度表示两种 Ig 同种型之间共享的克隆型数量，点的大小代表每种同种型的克隆扩张。
> (F) 火山图显示 EF 和 GC 来源的 ASCs 之间差异表达的基因。每个红点表示一个单独的基因，其调整后的 P 值<0.05 且|log2（倍数变化）|>0.25，双侧 t 检验。
> (G) GSVA 分析显示 EF 来源和 GC 来源的 ASCs 之间富集的差异通路。使用双侧未配对 limma-moderated t 检验。
> (H) UMAP 视图显示 EF 和 GC 途径之间的浆细胞亚群（顶部）和细胞密度（底部）。高相对细胞密度显示为明亮的岩浆色。
> (I) 条形图显示 EF 和 GC 主导癌症中不同组织的 PC 亚群频率。
> (J) 堆积柱形图显示 10 个浆细胞亚群中 IGH 同种型的频率。
> (K) 我们研究中的浆细胞亚群和注释（行）与骨髓浆细胞的注释（列）（48）进行比较。比较是根据使用我们的数据作为参考的 CellTypist（135）训练的逻辑回归模型进行的。颜色标尺代表预测特定细胞类型的平均概率，点的大小代表被预测为特定细胞类型的细胞百分比。
> (L 和 M) 代表性直方图（L）和 MFI（M）显示 LIHC（n=4）和 COAD（n=4）浸润的 ASC 中 EF 来源 ASCs 特异性基因，包括 CD37、CD74、CD83、CD20、HLADR 和 IRF8，通过 FACS 检测。
> (N) 代表性多重免疫组化（IHC）染色显示 IRF8+ASCs 和 HLADR+ASCs 在 EF（RCC 和 LIHC）和 GC 主导（STAD 和 COAD）癌症组织中。青色、绿色、红色和黄色箭头分别代表 IRF8+ASCs、IRF8-ASCs、HLADR+ASCs 和 HLADR-ASCs。
> (O) 多重 IHC 揭示的 EF（n=49）和 GC 主导（n=23）癌症中 CD20-CD79a+ASCs 中 IRF8+ASCs 和 HLADR+ASCs 的频率。
> (P) EF 和 GC 来源 ASCs 之间 BCR SHM 靶向模型。两行顶部的“刺猬”图表展示了 EF 来源 ASCs 的靶向热点和冷点序列基序，底部两行展示了 GC 来源 ASCs 的。WRC/GYW（红色）、SYC/GRS（蓝色）、WA/TW（绿色）和中性（灰色）突变的频率可视化。WRC/GYW 和 WA/TW 是突变热点，SYC/GRS 是突变冷点。图表中央的 ATCG 核苷酸代表特定的突变碱基。图上棒的长度对应于给定 5-mer 中给定碱基被突变的可能性。
> (Q) 盒形图显示不同 SHM 包括中性、热点和冷点突变频率，来自 EF 和 GC 来源 ASCs 的不同同种型。
> (R) BASELINE 选择分析在 EF 和 GC 来源 ASCs 中 CDR 和 FWR 选择，按同种型分组。条形表示组中的 95％置信区间。
> (S) EF 与 GC 来源 ASCs 和癌症与邻近正常组织浸润 ASCs 之间的 IGHV 家族使用偏好推断。使用 log2（倍数变化）值绘制图表，每个点按 IGHV 使用量大小和颜色编码表示组特异性。红色、蓝色、绿色和紫色分别代表癌症浸润的 EF 来源 ASCs、癌症浸润的 GC 来源 ASCs、邻近浸润的 GC 来源 ASCs 和邻近浸润的 EF 来源 ASCs 富含 IGHV 基因。数据显示中位数及四分位范围（M 和 O），须表示最小和最大测量值（A、B 和 D）。\*P<0.05；**P<0.01；\***P<0.001；\*\*\*\*P<0.0001；ns 表示无显著性。

我们接下来评估了两种路径的普遍性，并将与典型 Bm（GC 来源 ASCs 的 66%）、循环 GC（13%）、GCLZ（12%）和 GCDZ（7%）共享 BCR 的 ASCs 分类为 GC 来源的 ASCs，而那些与其他 B 细胞亚群重叠的 ASCs，包括 AtM（EF 来源 ASCs 的 47%）、ACB（29%）、IFIT3+ B（8%）、HSP+ B（6%）、前 GC（5%）和 MT1X+ B（3%）细胞，被归类为细胞层面的 EF 来源 ASCs（图 S4A）。随后，我们使用标签转移获得更多基于已分类 ASCs 的基因表达轮廓的 EF 和 GC 来源 ASCs，然后验证了标签转移的准确性（图 S4B）。有了定义的 EF 来源和 GC 来源的 ASCs，我们进一步计算了 EF 指数，并结合 SHM 将患者分类为 EF 占主导或 GC 占主导的两个不同组，此分类进一步通过 pTrans 得分得到验证和精细化（图 S4，C 至 E）。尽管存在明显的患者和癌症类型偏好，但两条路径都可以在单个患者和癌症中观察到，表明 GC 和 EF 反应是 ASC 分化的普遍路径（图 2H）。结肠腺癌（COAD）和甲状腺癌（THCA）使用 GCDZ、GCLZ 和循环 GC B 细胞，而胆囊癌（GBC）、胃腺癌（STAD）、肺癌（LC）和胸腺瘤（THYM）倾向于使用 Bm 细胞作为 GC 途径。相反，AtM B 细胞占主导的 EF 路径在肝细胞癌（LIHC）、胰腺腺癌（PAAD）、宫颈鳞状细胞癌及宫颈腺癌（CESC）和头颈部鳞状细胞癌（HNSC）中富集，而前 GC、ACB 和 IFIT3+ 占主导的 EF 路径在肾细胞癌（RCC）、膀胱尿路上皮癌（BLCA）和胃肠道间质瘤（GIST）中丰富（图 2H 和图 S4F）。在卵巢癌（OV）和乳腺癌（BRCA）中，AtM B 细胞的 pTrans 得分与循环 GC 和 Bm 细胞相当，表明这些癌症中两条路径的同等存在（图 S4G）。除了亚群之间的 BCR 共享外，GC 和 EF 途径的发育潜力也可以通过非 ASC 亚群在 ASCs 中的表达特征得到验证（图 S4H）。例如，PC01.NME2 表达前 GC 特征基因，包括 PSME2 和 ENO1，并且这些前 GC B 细胞在 BLCA 和 RCC 中与 TXNDC5+ 浆母细胞和 MZB1+ 浆细胞共享 BCR。类似地，PC04.HSPA1A 表达 HSPA1A 和 HSPA1B，HSP+ B 细胞倾向于与 BLCA 中的 MZB1+ 浆细胞共享 BCR，表明通向 ASCs 的异质分化路径。总体来说，这些数据表明，两种进化路径（GC 和 EF）被不同的癌症生态系统劫持。

我们进一步探讨了这两种进化路径的 BCR 复合体和匹配的转录特征。EF 来源 ASCs 在肿瘤中的中位频率为 1.52%（四分位数范围 0.35 至 4.37%），显著高于 GC 来源 ASCs 的 0.45%（四分位数范围 0.13 至 2.29%）（图 S5A）。相比之下，EF 来源 ASCs 的基因表达和 BCR 克隆型多样性降低（图 S5，B 和 C）。这些细胞特征为寡克隆扩展，前五个克隆型占总复合体的 11.51%，而 GC 来源 ASCs 为 3.20%。实际上，GC 来源 ASCs 表现出高多样性和相对均匀的克隆大小（图 S5C）。与先前在自身免疫疾病中的发现一致（43, 46），肿瘤中的 EF 来源 ASCs 的体细胞超突变（SHM）显著低于 GC 来源的 ASCs（图 2I 和图 S5D）。同位型分析表明，EF 来源 ASCs 含有高干扰素诱导的免疫球蛋白 G（IgG）同位型和相对于 IGHG1 的类转换重组（CSR），在肿瘤中以及高 IGHM 富集，而在邻近正常组织和血液中没有发生 CSR（图 2J）。相比之下，GC 来源 ASCs 在肿瘤、邻近正常组织和血液中显示出显著更高的扩展和 CSR 相对于 IGHA1 和 IGHA2，这与肿瘤抗原特异性识别和抗肿瘤免疫相关（47）（图 2K 和图 S5E）。

这些差异可能源于 EF 和 GC 来源 ASCs 之间的内在区别，EF 来源 ASCs 高表达 IRF8、CD83 和 HLA-DR，表现出较早的免疫反应表型（48）并富集在缺氧和炎症反应途径中。相反，GC 来源 ASCs 表现出更高的免疫球蛋白基因表达，并表现出更成熟的浆细胞表型——这与它们在免疫反应后期阶段出现一致——并富集在多个代谢途径中，包括糖酵解、氧化磷酸化和脂肪酸代谢，突出显示了 CSR 和 GC 反应期间广泛的能量和生物合成需求（图 S5，F 和 G，以及表 S2）。为了比较 EF 和 GC 来源 ASCs 的早期和晚期分化阶段，我们使用了三种方法推断分化状态，包括 cytoTRACE（49）、scTour（50）和 Monocle3（51），并显示 EF 来源 ASCs 处于早期阶段，与 GC 来源 ASCs 的末端分化相比，表明 EF 反应早期和 GC 反应延迟（52）（图 2L 和图 S5H）。这些结果进一步得到验证，因为 EF 来源 ASCs 富集了 PC07.CD83，高表达 HLA-DR 和 FOXP1，已显示抑制生发中心（GC）形成和抑制人类浆细胞分化（53, 54）（图 S5I）。此外，PC07.CD83 中 IGHM 同位型的富集进一步与骨髓中早期免疫球蛋白 M（IgM）ASCs 的特征一致（48）（图 S5，J 和 K）。

GC 来源 ASCs 富集了 PC03.DUSP5、PC04.HSPA1A 和 PC10.SPINK2。LIHC 浸润 ASCs 显著高表达 EF 来源 ASC 标记物，如 CD20、HLA-DR、CD37、CD74、CD83 和 IRF8，与 COAD 中的表达相比（图 S5，L 和 M）。这些结果还通过使用组织微阵列（TMA）对 IRF8 和 HLA-DR 进行 mIHC 染色进行了验证，该微阵列包括 EF 占主导的癌症（BLCA, CESC, GIST, LIHC, PAAD, RCC; n = 49）和 GC 占主导的癌症（COAD, STAD, 和 LC; n = 23）（图 S5N）。EF 占主导癌症中 IRF8+ ASCs 的频率（中位数在 EF = 13.67%，中位数在 GC = 6.58%；P=0.0315）和 HLA-DR+ ASCs 的频率（中位数在 EF = 50%，中位数在 GC = 34.09%；P = 0.0066）在 CD79+CD20− ASCs 中显著高于 GC 占主导癌症（图 S5O）。总的来说，这些结果进一步支持了 EF 来源 ASCs 的早期反应与 GC 来源 ASCs 的延迟反应的观念。

GC 来源的 ASCs 在激活诱导的胞苷脱氨酶（AID）WRC/GYW 和 WA/TW 热点区域的突变频率高于 EF 来源的 ASCs（图 S5，P 和 Q）。具体来说，GC 来源 ASCs 在 AID 热点区域的突变频率为 IGHA 的 6.05%（4.37 至 8.44%）和 IGHM 的 4.61%（1.05 至 7.07%）。这些频率显著高于 EF 来源的 ASCs，后者为 IGHA 的 4.65%（2.63 至 6.95%）（P = 2.5e−12）和 IGHM 的 0%（0 至 2.93%）（P < 2.2e−16）。GC 来源的 ASCs 显示出对 IGHA2 和 IGHG2 的互补性决定区（CDR）中替换突变的正选择，进一步支持它们增加的类转换重组（CSR）（图 S5R）。相比之下，与 GC 来源的 ASCs 相比，EF 来源的 ASCs 中 IGHG4 增加，这与最近一份报告一致，该报告显示 IgG4 相关的自身免疫病中 EF 反应增强（57）。同样，比较肿瘤中 EF 和 GC 来源 ASCs 的 IGHV 基因使用情况显示，GC 来源的 ASCs 过度表达 IGHV1-8 和 IGHV1-24（图 S5S），其中 IGHV1-8 的偏好与更高的 SHM 率相关（58），表明它们具有强烈的抗原特异性亲和力。EF 来源的 ASCs 上调了一组 IGHV 基因（IGHV3-15、IGHV3-23、IGHV3-33、IGHV3-49、IGHV4-34 和 IGHV4-59），这些基因的增加使用已与 COVID-19、病毒感染和自身免疫病相关（43, 46, 59, 60），暗示一个多反应性 BCR 复合体。总的来说，我们的数据表明，不同的癌症生态系统劫持了两条进化路径（EF 和 GC），揭示了 EF 和 GC 来源 ASCs 之间在 BCR 复合体和转录特征上的差异，突出显示它们在抗肿瘤反应中的独特作用（图 2M）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101536240.png)

> 图 3. 人类癌症中 EF 和 GC 反应的单细胞表观基因组特征。
> (A) scATAC-seq 标注的 B 细胞亚群（顶部）和癌症类型（底部）的 UMAP 可视化。
> (B) 基于 scATAC-seq 的所有亚群标记基因的基因活性评分热图。颜色代表 z 分数缩放的基因表达。
> (C) 在 B 细胞亚群中指示的特征基因位点的基因组可访问性轨迹。
> (D) SCENIC 分析的 TF 活性热图（左侧）和在标注的 B 细胞亚群的特定开放染色质区域的 TF 基序富集（右侧）。
> (E) RNA 表达（顶部）和 B 细胞亚群特定 TF 的基序偏差评分（底部）的 UMAP 可视化。
> (F) EF 主导和 GC 主导癌症来源的 MZB1+ 浆细胞之间的差异表达 TF 偏差评分计算 [对数 2 倍变化 (FC)>0.5，Benjamini-Hochberg 调整后 P 值<0.05，双侧 Wilcoxon 检验]。TF 偏差评分按调整后 P 值排名，(红色) EF 主导相对于 (蓝色) GC 主导癌症来源的 MZB1+ 浆细胞。
> (G) 不同假定调节 TF 驱动 B 细胞分化从初级 B 细胞到浆细胞的示意图，左侧为 GC 主导癌症，右侧为 EF 主导癌症。

#### 调控元件通过表观遗传学授权外滤泡和生发中心的平衡

转录调控是决定和维持 B 细胞身份的基础（61-64），但肿瘤特异性的调控网络和对 TIBs 身份有贡献的分子驱动因素尚未明确定义。为了解决这一挑战，我们应用了配对的单细胞 RNA 测序（scRNA-seq）和单细胞转座酶可访问染色质测序（scATAC-seq），来表征 TIBs 的表观基因组，并为来自五种癌症类型的九名患者的 53,428 个 TIBs 获得了染色质可访问性图谱，包括 GC 途径主导的癌症（COAD、THCA、LC 和 STAD）和 EF 途径主导的癌症（LIHC），中位数为 11,853 个独特对齐片段，约 67.87% 的 Tn5 插入位于 ATAC-seq 峰中（图 3A 和图 S6, A 至 C）。通过整合 scATAC-seq 和 scRNA-seq 数据，我们观察到八个类似的 B 细胞亚群，涵盖初级、两个 ACB、Bm、AtM、GC（DZ 和 LZ）和 PC 亚群（图 3A 和表 S3）。因此，亚群身份和亚群特异性标记在 scRNA-seq 和 scATAC-seq 中都有强烈一致性（图 3B 和图 S6D）。开放染色质可访问性确认了 B 细胞亚群的特征基因，如 TCL1A、RGS13、ITGAX 和 XBP1，进一步确认了它们的细胞身份（图 3C 和图 S6E）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101613541.png)

> 图 S6. 单细胞 ATAC 测序（scATAC-seq）数据质量控制与整合。
> (A) UMAP 图显示无监督 scATAC-seq 聚类（左侧）、患者（中间）和每个单细胞独特核片段数量的对数（log10）（右侧）。
> (B) 条形图显示 scATAC-seq B 细胞亚群的数量（左侧）和独特核片段的中位数（右侧）。
> (C) 按患者的 scATAC-seq 数据集的质量控制指标，包括每个细胞条形码的片段数量、转录起始位点富集评分、核小体与非核小体片段大小的比率，以及基因组黑名单区域中片段的比率。
> (D) 热图揭示无监督 scATAC-seq 聚类（左侧）或转移 scATAC-seq 亚群身份（右侧）与 scRNA-seq 细胞类型的重叠。颜色代表 scRNA-seq 聚类或亚群与 scRNA-seq 亚群之间的重叠率。
> (E) scATAC-seq B 细胞亚群中 41,643 个顺式调控元件的热图。颜色代表按行缩放的峰值评分的 z 分数。
> (F) 转录因子（TF）表达评分（x 轴）与平均 TF 基序偏差评分（y 轴）的相关性，用于预测 B 细胞亚群中的正向 TF 调节因子。相关性大于 0.5 的以红色表示。
> (G) 选定的 B 细胞谱系 TF 的 RNA 表达（顶部）和基序偏差评分（底部）。
> (H) 在不同 B 细胞亚群中对选定的特定细胞类型 TF 进行足迹分析。

为了定义参与修改不同 B 细胞亚群染色质可访问性的转录因子（TFs），我们识别了染色质可访问活性与其基因表达显著正相关的 TFs。这种分析产生了一整套富集的 TFs，包括已知的 B 细胞系 TFs，如 PAX5、EBF1 和 SPIB（65）（图 S6, F 和 G）。通过结合 TFs 的足迹和特征（66），我们识别出 B 细胞亚群间共享和独特的调控模式（图 3D）。例如，类似细胞状态之间的共享模式的调节 TF 活动，如初级、ACB 和 Bm 中活跃的 BCL11A、ELF2、SPIB 和 STAT6，或在 GCDZ 和 GCLZ B 细胞中的 CTCFL、EBF1、HMGA1 和 POU2F1（图 3D）。相反，广泛的 TFs 在特定 B 细胞亚群中特别富集（例如，ETS1 在初级 B 细胞中；TBX21 和 FOSL2 在 AtM 中；POU2F1、MEF2B 和 BCL6 在 GC B 细胞中；IRF2/3/4/5/6/7/8、PRDM1 和 ZNF652 在 PCs 中）（图 3, D 和 E, 和图 S6H）。总体而言，我们的数据不仅无偏见地揭示了已知和未知的 TFs 在控制 B 细胞身份中的作用，还提供了跨癌症中主要 B 细胞亚群基因调控网络的全面资源。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101615830.png)

> 图 S7. EF 和 GC 源浆细胞谱系轨迹。(A-C) 幼稚 B 细胞通过 AtM (A)、GC B (B) 和 Bm 细胞 (C) 分化成浆细胞的伪时间热图排序，分别显示基因评分 (左) 和转录因子 motif 可及性 (右)。(D) 计算了 EF 和 GC 来源的癌症衍生 Bm 和 AtM B 细胞之间差异表达的转录因子 (log2 FC > 0.5，Benjamini-Hochberg 校正的 P 值 < 0.05，双侧 Wilcoxon 秩和检验)。EF 来源的癌症 (红色) 和 GC 来源的癌症 (蓝色) 衍生的 Bm (顶部) 和 AtM B 细胞 (底部) 中按 P 值调整的富集排名。(E) 山脊图显示了 EF 和 GC 来源的癌症中不同 B 细胞亚群中指示的阳性转录因子调节因子的偏差评分。(F 和 G) 代表性 FACS 检测的 LIHC (n = 4) 和 COAD (n = 4) 浸润性 ASCs 中 IRF4 和 RUNX2 的柱状图 (F) 和 MFI (G)。数据显示 IQR 的中位数 (G)。(H) IRF4+ ASCs 和 RUNX2+ ASCs 在 EF (LIHC) 和 GC 来源 (COAD) 癌组织中的 CD20、CD79a、IRF4 和 RUNX2 的代表性多重 IHC 染色。红色、绿色、黄色和粉色分别代表 IRF4+ ASCs、IRF4- ASCs、RUNX2+ ASCs 和 RUNX2- ASCs。(I) 多重 IHC 显示的 EF (n = 49) 和 GC 来源 (n = 23) 癌症之间 CD20-CD79a+ ASCs 中 IRF4+ ASCs 和 RUNX2+ ASCs 的频率。数据显示 IQR 的中位数，P < 0.05；\_\*\*\*，P < 0.0001；P 值通过双侧 Wilcoxon 检验计算 (G 和 I)。

仔细检查 Bm、AtM 和 PCs 时，我们发现它们主要由特定 EF 和 GC 癌症类型的细胞组成，促使我们调查 Bm、AtM 和 PCs 的染色质景观中潜在的癌症实体特异性差异（图 3A）。因此，我们研究了来自 EF 和 GC 主导癌症的 B 细胞系谱系轨迹（图 S7, A 至 C）。我们识别了正向 TF 调节器的顺序活动，包括 PAX5、BCL11A、POU2F2、EBF1、REL、TBX21、PRDM1、IRF4、RORA、RUNX2 和 XBP1，它们促进 B 细胞系的特化、维持、CSR 和分化（62, 64, 65, 67）。这些活动在 EF 和 GC 主导癌症中沿着 B 细胞分化呈现变化。随后，我们评估了 TF 偏差分数以确定 EF 和 GC 主导癌症之间差异性正向 TF 调节器。EF 主导癌症中的 Bm 和 AtM 富含 AP-1 因子，包括 FOS 和 JUN，这些因子涉及 BCR 信号传导途径，并标志 B 细胞激活和分化（68）（图 S7, D 和 E）。相比之下，GC 主导癌症中的 Bm 和 AtM 富含核因子 κB（NF-κB）亚单位，包括 REL、RELA 和 RELB，这与它们在 GC B 细胞维持和稳态中的报道功能一致（69）。与 GC 主导癌症中的 PCs 显示高 RUNX1-3 偏差分数相比，EF 主导癌症中的 PCs 显示高活性的调节快速诱导干扰素 -β（IFN-β）和炎症性 TME 的 TFs，包括 IRF1/3/4/5/8 和 STAT2（70）（图 3F）。为了验证这一点，我们确认了 IRF4 和 RUNX2 在肿瘤浸润 ASCs 中比其他 B 细胞富集，并且 IRF4 在与 LIHC 相关的 ASCs 中比与 COAD 相关的 ASCs 表达上调，而 RUNX2 显示相反趋势（图 S7, F 和 G）。这些结果通过 mIHC 染色 IRF4 和 RUNX2 在 ASCs 的组织微阵列中得到证实，包括 EF 主导（n=49）和 GC 主导癌症（n=23）（图 S7H）。在 CD79a+CD20− ASCs 中，EF 主导癌症中 IRF4+ 的频率（中位数在 EF = 55.09%，中位数在 GC = 50%；P = 0.0416）显著高于 GC 主导癌症，而 RUNX2+ ASCs 的频率显示相反趋势（中位数在 EF = 26.11%，中位数在 GC = 56.89%；P < 0.0001）（图 S7I）。总的来说，这些数据突出了一个动态的表观遗传调控网络的功能，在癌症生态系统中精细调节 B 细胞的分化和选择，并强调了系谱 TFs 在管理 EF 和 GC 途径之间平衡的基本作用（图 3G）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101541942.png)

> 图 4. 人类癌症中 AtM B 细胞的 GC 独立发展。
> (A) 热图显示初级、Bm 和 AtM B 细胞中代表性基因的相对表达。颜色标尺代表按行缩放的 z 分数基因表达值，每一列代表一个病人。
> (B) 通过 FACS 检测的来自肝细胞癌（LIHC）患者的肿瘤浸润初级、Bm 和 AtM B 细胞的代表性标记物（n = 3）。
> (C) 热图显示了在体外刺激 11 天后，来自 LIHC 患者的肿瘤浸润初级、Bm 和 AtM B 细胞的上清液中检测到的自身抗原和肿瘤相关抗原特异性 IgA（n = 4）。
> (D) （左）Monocle3 轨迹分析描绘了非 ASC 的发展轨迹，显示（右）两条主要的发散轨迹（从灰色骨架线：红色，路径 1；蓝色，路径 2）。（右下）细胞按其对应的伪时间进行颜色编码。
> (E) 二维图显示了沿着推断的伪时间，路径 1（红色）和路径 2（蓝色）的细胞中高亲和力、低亲和力、耗竭和 CSR 特征的动态表达得分。中心线表示线性拟合，阴影线表示 95% 置信区间。

#### 外滤泡非典型记忆 B 细胞（AtM B 细胞）表现出耗竭表型，独立于生发中心发展

认识到作为肿瘤微环境（TME）中 EF 途径的主要祖先的 AtM B 细胞的关键作用，我们全面检查了它们的表型和功能。与非肿瘤环境中先前定义的标志性标记物相比（21, 22, 24），肿瘤浸润的 AtMB 细胞也显示出 CD27、CD38、IRF8 和 SDC1 的表达降低，与 Bm 细胞相比，PRDM1、IRF4 和 XBP1 的表达增加，Bm 细胞是 GC 来源 ASCs 的经典祖先（1）。已知 XBP1 抑制 B 细胞增殖并促进向 ASCs 的分化（71），支持 AtM 向 ASCs 分化的潜力（图 4A）。AtM B 细胞表现出耗竭和驻留记忆表型，不同于 Bm 的效应表型。简而言之，AtM B 细胞上调了免疫检查点（PDCD1、CD274、CTLA4、ENTPD1、LAG3 和 HAVCR2）、与耗竭相关的转录因子（TOX、TOX2、ZBED2、BATF、RBPJ 和 VDR）（33, 72），以及涉及免疫球蛋白和免疫复合物结合的 Fc 受体家族（FCRL2/3/4/5 和 CD32A/B）（图 4A）。其中，FCRL4 与可能抑制 BCR 信号的组织驻留记忆细胞相关。CD32B 作为低亲和力抑制性受体，抑制抗体依赖的细胞毒性（ADCC）、抗体依赖的细胞吞噬（ADCP）和 B 细胞激活（73）。与过度激活 TCR 信号的耗竭 T 细胞类似，AtM B 细胞也高表达 BCR 信号基因（SYK）、免疫调节和激活基因（TLR7/9、CD80、CD86 和 CD72）。这些独特的表型通过流式细胞术进一步得到证实（图 4B 和图 S8A）。这些数据综合展示了外滤泡 AtM B 细胞的独特免疫表型和分子特征。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101616412.png)

> 图 S8. AtM 细胞与 Bm 或 GC B 细胞之间的表型和 BCR 库的差异。(A) 代表性的流式图，显示来自 LIHC 患者 (n = 3) 的 CD20+ B 细胞中肿瘤浸润的幼稚 B 细胞、Bm 细胞和 AtM 细胞。(B) 堆叠条形图显示了来自不同组织的幼稚 B 细胞、Bm 细胞、AtM 细胞、GC_D 区、GC_L 区和循环 GC B 细胞的类型分布。(C) 箱型图显示了不同组织中 Bm 细胞和 AtM 细胞之间类型频率的差异。(D) 从 LIHC 患者中分离出肿瘤浸润的幼稚 B 细胞、Bm 细胞和 AtM 细胞，并用 R848、IL2、IL10 和 IL21 刺激 11 天。收集上清液，通过 ELISA 测定 IgG、IgA 和 IgM 的浓度 (n = 4)。(E) 热图显示了 LIHC 患者肿瘤浸润的幼稚 B 细胞、Bm 细胞和 AtM 细胞的上清液中自身抗原和肿瘤相关抗原特异性 IgG 和 IgM 的检测，如 (D) 所述，体外刺激 11 天后 (n = 4)。(F 和 G) 不同组织中幼稚 B 细胞、Bm 细胞、AtM 细胞、GC_D 区、GC_L 区和循环 GC B 细胞的 IgH 链 (F) 体细胞超突变频率和 CDR3 氨基酸长度 (G) 的箱型图。(H) 来自肿瘤浸润的幼稚 B 细胞、Bm 细胞、AtM 细胞、GC_D 区、GC_L 区和循环 GC 细胞的框内序列的 CDR3 长度 (以氨基酸计) 通过 scBCR-seq 数据集进行量化。(I) 代表 LIHC 和 COAD 中 AtM (左) 和 GC B 细胞 (右) 最大克隆的系统发育谱系树。分支上的数字显示体细胞突变的获得，表示突变和分支的数量。推定的未突变共同祖先用白色圆圈表示。(J) 箱型图显示了从幼稚 B 细胞到 AtM 或 GC B 细胞的非 ASC 亚群中推断的伪时间的分布。箱型图代表每个子集伪时间值的中间值、第 25 个百分位数和第 75 个百分位数。(K) 二维图显示了 B 细胞发育过程中沿着伪时间耗竭和 CSR 相关标记的动态表达。中心线表示线性拟合，阴影线表示 95% 置信区间。数据显示 IQR 的中位数 (E 和 H)，须线表示最小值和最大测量值 (C、D、F、G 和 J)。\*, P < 0.05; **, P < 0.01; \***, P < 0.001; \*\*\*\*, P < 0.0001; ns，不显著。P 值通过双侧 Wilcoxon 检验计算 (C、D、F 和 G)。

为了进一步探索外滤泡 AtM B 细胞的免疫复合体，同位型分析表明，与 Bm 细胞相比，肿瘤浸润的 AtM B 细胞转换较少，含有更高的 IGHD 和 IGHM（P < 0.01），而 IGHA1、IGHA2 和 IGHG2 在 Bm 中较为普遍（P < 0.01）（图 S8, B 和 C）。此外，在体外激活和分化 11 天后收集的肝细胞癌（LIHC）患者肿瘤 AtMB 细胞的上清液中，IgG、IgA 和 IgM 的含量低于 Bm（图 S8D）。再次，通过抗原微阵列测试这些上清液抗体的反应性显示，从 AtM B 细胞衍生的 ASCs 产生了更高水平的自身抗体，而从 Bm 衍生的 ASCs 产生了更高水平的与肿瘤相关抗原反应的抗体（图 4C），涵盖了 IgG、IgA 和 IgM 所有三种类型（图 S8E）。与这些发现一致，我们观察到 Bm 中 SHM 较高，而 AtM B 细胞中 SHM 水平较低或中等（图 S8F）。总的来说，我们的数据显示，耗竭的 AtM B 细胞表现出受损的抗体产生能力、旁观者激活和弱肿瘤反应性。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101618761.png)

> Fig.S9. AtM B 细胞的发育轨迹。(A) 分别在 COAD、LC、LIHC 和 RCC 中的非 ASC 细胞分化的 Monocle3 轨迹分析。细胞的颜色与其对应的伪时间相对应。(B) 使用 scATAC-seq 数据集，对来自幼稚 B 细胞经活化 B 细胞分化的 AtM B 细胞分化过程中的基因评分 (左) 和转录因子 motif 可及性 (右) 的伪时间热图排序。(C) 沿 AtM B 细胞分化轨迹转录因子偏差评分的动态变化。每个点代表 AtM B 细胞分化伪时间排序的 scATAC-seq 谱文件中偏差评分。线代表伪时间上的平滑拟合和指示的 TF 偏差评分。(D) 不同 B 细胞亚群中 TBX21 和 BATF 的转录因子足印。Tn5 插入偏差轨道显示在下方。(E) 热图显示了不同癌症类型的 AtM B 细胞和其他 B 细胞亚群之间的 pTrans。彩色表示按行缩放的 pTrans 值的 z 分数。(F) UpSet 图描绘了 B 细胞与 AtM B 细胞共享的扩增克隆数量。条形图显示了 AtM 和指示的 B 细胞之间共享的克隆数量。每个 B 细胞亚群的总克隆数由左侧的条形图显示。(G) 热图显示了 AtM B 细胞和非 AtM 亚群之间的克隆型共享。行代表克隆型，列代表不同的组织类型。按共享细胞数量着色。

另一个关键问题是 AtMB 细胞是否能进入 GC 或源自真正的 GC B 细胞（19, 74-76）。为了解决这一问题，我们共同分析了 BCR 复合体、发育轨迹、表观基因组调控和基因表达特征。我们观察到 AtM 和三个 GC B 细胞之间的 IGHV 使用、CDR3 氨基酸长度和 SHM 相当。这些数据支持 AtM 和 GC B 克隆通常是独立的而不是可互换的观点（图 S8, G 和 H）。因此，我们为 AtM 和 GC B 细胞最扩展的克隆重建了系谱树，显示克隆谱系主要源自 AtM 或 GC B 细胞（图 S8I）。伪时间轨迹分析确认了 AtM 和 GC B 细胞在两个独立分支上完全分离，以初级 B 细胞开始，终端分支为 AtM（路径 1）加循环 GC B 细胞（路径 2）（图 4D）。沿着轨迹，高亲和力特征得分和 CD24、CD38 和 SELL 逐渐在路径 2 中上调，而低亲和力和与耗竭相关的特征得分相关基因（即 PDCD1、ENTPD1 和 HAVCR2）相应地在路径 1 中上调，再现了 B 细胞从初级状态通过激活状态最终到 AtM 状态的发展（图 4E 和图 S8, J 和 K）。在这个过程中，耗竭的程度逐渐加剧。这一发展轨迹在不同癌症类型中均一致观察到（图 S9A），并通过 scATAC-seq 数据得到确认（图 S9B）。我们进一步识别了 AtM 的动态表达、染色质活性和足迹。与 Bm 和 GC B 细胞相比，AtM B 细胞表现出参与 CSR 和耗竭表型的 TFs 的高活性，并增强了特异同位型 IgG+ Bm 的免疫功能（33, 67, 77, 78），包括 TBX21 和 BATF（图 S9, C 和 D），表明独特的调控程序（图 3D）。CSR 相关的特征得分和基因（APEX1, APEX2, XRCC5, XRCC6, POLD2 和 AICDA）沿轨迹逐渐上调，表明 AtM B 细胞可能在不经历 GC 反应的情况下经历 CSR（图 4E 和图 S8K）。同样，AtM 在 EF 主导的癌症中与 IFIT3+ B 共享 BCR，包括 HNSC、OV、GIST、BRCA 和 CESC，表明由干扰素诱导的初级 B 细胞可能定向分化为 AtM 而不进入 GC（图 S9, E 至 G）。总的来说，这些发现表明 AtM 和 GC B 细胞经历了分别导致 EF 和 GC 来源 ASCs 的独立发展过程。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101548368.png)

> 图 5. AtM B 细胞在不成熟的 TLS 中聚集，并通过 IL-21–IL-21R 轴由 Tph 细胞诱导。
> (A) 结直肠腺癌（COAD）病例中，用于 TLS 成熟度的代表性多重免疫组化（mIHC）染色，显示 CD20, CD3, 和 fDC [CD21（长异构体），CD23, 和 CD35]（第一行），B 细胞亚群的 CD20, CD27, T-bet, 和 CD79a（第二行），AtM B 细胞（第三行），以及 TLS 的浸润带（第四行）。黄色、绿色、紫色、棕色、红色和青色箭头分别代表 fDC、CD3+ T 细胞、CD20+ B 细胞、CD20+CD27+ Bm、CD20+T-bet+ AtM B 细胞和 CD20-CD79a+ ASCs。
> (B 和 C) 通过 mIHC 揭示的结直肠腺癌（COAD）[(B), n = 6] 和肝细胞癌（LIHC）[(C), n = 17] 中不成熟和成熟 TLS 之间 Bm 和 AtM B 细胞的密度。
> (D) 在结直肠腺癌（COAD）（顶部，n = 6）和肝细胞癌（LIHC）（底部，n = 17）中不成熟和成熟 TLS 中 AtM B 细胞的密度序列带。虚线指示界面线。线图代表中位数与四分位范围（IQR）。
> (E) 在结直肠腺癌（COAD）（左侧，n = 6）和肝细胞癌（LIHC）组织（右侧，n = 17）中，AtM 到不成熟和成熟 TLS 界面的中位距离。虚线指示界面线。
> (F) 通过流式细胞术确定肝细胞癌（LIHC）患者中肿瘤浸润的主要免疫亚群与 AtM B 细胞的相关性（n = 46）。PCC, 皮尔逊相关系数。
> (G) AtM B 细胞和 T 细胞之间上调的配体 - 受体交流。y 轴代表亚群，x 轴代表配体和受体名称。圆圈大小代表对数标准化 P 值，颜色深度代表配体和受体的平均表达。
> (H 和 I) 空间共定位相关性（H）和代表性图像（I）显示 AtM B 细胞特征与 TLS 或 PD1HiCD4+ Tph 在 81 个空间转录组学数据集中的关系，这些数据集来自九种癌症类型。相关性通过 Spearman rho 计算。数据来源和获取信息总结在表 S4 中。
> (J) 代表性的多重免疫组化（mIHC）染色显示肝细胞癌（LIHC）肿瘤组织中 PD1HiCD4+ Tph 和 AtM B 细胞的共定位。绿色、黄色、红色和青色箭头分别代表 PD1HiCD4+ Tph、CD20+T-bet+ AtM B 细胞和 CD20-CD138+ PCs。
> (K) （左侧）AtM B 细胞周围 20 毫米半径内 PD1HiCD4+ Tph 细胞的浸润密度和（右侧）频率，分别在肿瘤和邻近区域的 TLS 和非 TLS 区域中，来自肝细胞癌（LIHC）TMA（n = 180）。
> (L 和 M) 肿瘤浸润的 Treg、Th 和 PD1HiCD4+ Tph 细胞被分选并与健康供者的外周全 B 或分选的初级 B 细胞以 1:5 的比例共培养，在有或无同种型和抗 IL-21R 的情况下培养 7 天。代表性流式图（L）和 AtM B 细胞的频率（M）通过 FACS 确定（n = 6 至 8）。数据在 (B) 至 (D)，(E)，和 (K) 中显示中位数与 IQR，在 (H) 和 (M) 中显示最小和最大测量值。\*\*P < 0.01，\*\*\*P < 0.001，\*\*\*\*P < 0.0001；ns, 无显著性。P 值通过双侧未配对 Wilcoxon 检验确定 (B 和 C)，双侧配对 Wilcoxon 检验确定 (K)，以及双侧配对学生 t 检验确定 (M)。

#### 外滤泡 B 细胞空间上位于不成熟的第三方淋巴结构（TLS）

TLS 通常由具有不同大小和细胞组成的 B 细胞形成。然而，TLS 与肿瘤浸润 B 细胞（TIBs），特别是 AtM B 细胞之间的空间结构和关系仍然不清楚。我们发现 AtM B 细胞高表达 TLS 特征性特征（7），并在泛癌症 TCGA 数据中得到确认，表明它们可能定位于 TLS 中（图 S10, A 和 B）。因此，我们对包含 EF 主导癌症 [肝细胞癌（LIHC）（n=358; n=180）和胰腺腺癌（PAAD）（n=48）] 以及 GC 主导癌症 [结直肠腺癌（COAD）（n=98）、胃腺癌（STAD）（n=52）、和肺癌（LC）（n=90）] 的组织微阵列（TMA）进行了多重免疫组化（mIHC）染色，以表征 TLS 和 AtM B 细胞（表 S1）。通过使用我们建立的 TLS 量化管道（8），我们将肿瘤组织划分为 TLS 和非 TLS 区域，并观察到 AtM B 细胞与 TLS 之间存在显著相关性，表明 AtM B 细胞在 TLS 形成中可能发挥作用（图 S10, C 和 D）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101619148.png)

> Fig.S10. AtM B 细胞与 TLS 呈正相关。(A) 框图显示了 B 细胞亚群的 TLS 评分，通过先前描述的 B 细胞亚群和 TLS 标志基因的平均表达进行计算 (7)。(B) TLS 标志基因 (7) 和 B 细胞亚群标志基因 (调整后的 P 值 < 0.05 和 log2 (fold change) > 0.5) 用于计算 ssGSEA 的标志评分。TLS 评分与 14 个 B 细胞亚群 (左) 或 AtM B 细胞 (右) 评分在不同 TCGA 癌症类型中的相关性通过 Spearman 相关系数计算 (n = 6256)。(C) LIHC 中不同 B 细胞亚群的 CD20、Tbet、IgD 和 CD11c 多重 IHC 染色代表。(红色、青色和黄色箭头分别代表 CD20+、幼稚和 AtM B 细胞。) 组织根据先前描述的方式分为 TLS 和非 TLS 区域 (8)。(D) 框图显示了 GC (STAD、COAD 和 LC) 和 EF 来源优势 (PAAD 和 LIHC) 癌症中 TLS 和非 TLS 区域的 AtM 频率。(E) 不同癌症类型揭示了 COAD (n = 6) 和 LIHC (n = 17) 中未成熟和成熟 TLS 之间 ASCs 的密度。(G) 不同成熟阶段 TLS 中 AtM、Bm 和 ASC 的表型图。红色、青色和黄色点分别代表 CD20 CD79a+ ASCs。(H) COAD (n = 6) 和 LIHC (n = 17) 中未成熟和成熟 TLS 系列条带内 AtM B 细胞的绝对数量。虚线表示界面线。折线图显示的是 IQR 的中位数。数据显示 IQR 的中位数 (E 和 H)，须线表示最小值和最大测量值 (A、D 和 F)。\*, P < 0.05; **, P < 0.01; \*\***, P < 0.0001; ns，不显著。P 值由双侧配对 Wilcoxon 检验 (D)、双侧非配对 Wilcoxon 检验 (E) 和双向方差分析 (F) 确定。

考虑到 TLS 成熟的临床意义（成熟的 TLS：III 和 IV 阶段的类 GC 结构，包含滤泡树突细胞（fDCs）；不成熟的 TLS：I 和 II 阶段的淋巴聚集体）以及 TME 中类 GC 的 TLS 稀少性（8, 79-82），我们进一步筛选了来自 LIHC（n=17）和 COAD（n=6）的不同 TLS 阶段的整个组织切片。根据 T 和 B 细胞的数量以及 fDC 染色，将 TLS 分类为四个阶段（8）（图 5A）。AtM B 细胞在不成熟的 TLS 中显著富集，而 Bm 主要位于 COAD 和 LIHC 的成熟 TLS 中（图 5, B 和 C）。在不同 TLS 阶段之间没有观察到 ASC 密度的差异（图 S10E）。正如预期的那样，AtM B 细胞主要富集在 EF 主导的癌症中，如胃肠道间质瘤（GIST）、宫颈鳞状细胞癌和宫颈腺癌（CESC）、肝细胞癌（LIHC）和头颈部鳞状细胞癌（HNSC），而 GC B 细胞在 GC 主导的癌症中高度丰富，如结直肠腺癌（COAD）、甲状腺癌（THCA）和肺癌（LC）（图 S10F），表明 GC 主导癌症主要包含成熟的 TLS，而 EF 主导癌症中的 TLS 不成熟。如卵巢癌（OV）这样 EF 和 GC 路径同等存在的癌症，与其他癌症相比，AtM 和 GCLZ B 细胞的浸润中等。在空间上，我们计算了 AtM B 细胞在 TLS 或滤泡的内外边缘 200 毫米内的密度以及 AtM B 细胞到界面的距离。我们观察到 AtMB 细胞主要位于不成熟 TLS 的中心，这与早期 EF 反应和促进 TLS 形成一致（图 5, D 和 E 以及图 S10, G 和 H）。随着 TLS 的成熟，AtM B 细胞迁移到外围，而初级 B 细胞始终位于 TLS 的中心（图 S10C）。这些数据验证了 AtM B 细胞的 GC 独立发展，并表明 TLS 成熟阶段驱动 EF 和 GC 主导癌症中不同的 B 细胞分化。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101620387.png)

> Fig.S11. PD1<sup>Hi</sup>CD4<sup>+</sup> Tph 细胞可通过 IL21-IL21R 诱导 AtM B 细胞分化。(A) UMAP 图分别显示了四种主要免疫细胞类型 (左上)、髓细胞、NK、CD4 和 CD8 T 细胞亚群 (右上)、组织类型 (左下) 和癌症类型 (右下)。(B) 免疫细胞亚群中标记基因表达的点图。颜色代表标记基因的最大归一化平均表达，大小代表表达这些基因的细胞百分比。(C) 代表性流式图显示了肿瘤浸润性中性粒细胞、巨噬细胞、Treg、PD1<sup>Hi</sup>CD8 T<sub>ex</sub> 和 PD1<sup>Hi</sup>CD4 Tph 細胞的划门策略。(D) 热图显示了 TCGA pan-cancer 数据集中肿瘤中 B 细胞亚群和其他免疫亚群之间的相关性 (n = 6256)。免疫细胞亚群的频率由 BayesPrism 模型估计 (85)。颜色代表 Spearman 相关系数。(E) 热图显示了 B 细胞和其他免疫亚群之间使用 scRNA-seq 数据的相互作用。颜色代表配体 - 受体相互作用的缩放强度。(F) 使用我们匹配的 CD45<sup>+</sup> scRNA-seq 数据显示 CD4_PDCD1 和 Bm 或 AtM B 细胞之间的配体 - 受体 (L-R) 相互作用。(G 和 H) 对 LIHC 浸润的 Treg、Th 和 PD1<sup>Hi</sup>CD4 Tph 细胞进行排序，并与健康供血者的 Bn 细胞以 1:2 的比例共培养 5 天，同时加入 CD3/CD28 珠。FACS 测定代表性流式图 (G) 和 AtM B 细胞频率 (H) (n = 10)。数据显示 IQR 的中位数，须线表示最小值和最大测量值 (H)。**, P < 0.01; \***, P < 0.001; \*\*\*\*, P < 0.0001; ns，不显着。P 值由双侧配对 Wilcoxon 检验确定。

这种 AtM B 细胞的特定位置通过上调 CCR7、CXCR3 和 EBI2（编码 GPR183）等归巢受体得到响应，这些受体可以将 AtM B 细胞驱动到 B 区 -T 区边界等待 T 细胞帮助（52, 83）。事实上，AtM B 细胞与 T 滤泡辅助细胞（Tfh）或 I 型 T 辅助细胞（Th1）之间的强相关性，后者在病毒感染中分泌 IFNg、IL-21 和 CD40L（76, 84），指向这些 T 细胞类型与 AtM B 细胞发展之间的潜在交流。流式细胞术和通过 BayesPrism（85）解卷积的泛癌症 TCGA 数据表明，AtM B 细胞与 PD1Hi 耗竭 T 细胞呈正相关（图 5F 和图 S11, A 至 D），尤其是表现出 PD1HiCXCL13+CXCR5- 表型的 PD1HiCD4+ T 细胞（称为外周辅助 T 细胞，Tph），这些细胞可以促进 TLS 形成和自身免疫病中 B 细胞的终末分化（86, 87）。配体 - 受体分析提供了额外证据支持 PD1HiCD4+ Tph 细胞与 AtM B 细胞之间的交流，特别是通过 IL-21R–IL-21 轴，与 Bm 细胞相比。这种相互作用暗示 PD1HiCD4+ Tph 细胞在促进 AtM B 细胞分化中可能发挥作用（图 5G 和图 S11E），这也通过另一个独立算法 CellChat（88）得到验证（图 S11F）。通过已发表的空间转录组学数据集（81 个数据集来自九种癌症类型，包括乳腺癌（BRCA）、宫颈鳞状细胞癌和宫颈腺癌（CESC）、结直肠腺癌（COAD）、肝细胞癌（LIHC）、低级别胶质瘤（LGG）、卵巢癌（OV）、前列腺腺癌（PRAD）、肾细胞癌（RCC）和皮肤黑色素瘤（SKCM））可视化 CD4+PD1Hi Tph 和 AtM B 细胞，揭示了它们在 TLS 中的正相关（图 5, H 和 I 及表 S4），这进一步得到了在 LIHC TMA（n=180）上进行的 mIHC 染色的支持，显示在 TLS 中与 AtM B 细胞紧密相邻的区域中，CD4+PD1Hi Tph 细胞密度和频率显著更高，无论是在肿瘤还是邻近组织的非 TLS 区域（图 5, J 和 K）。为了验证这一点，分选的 LIHC 浸润的 PD1HiCD4+ Tph、Th 和调节性 T（Treg）细胞与健康捐赠者的外周总 B 或分选的初级 B 细胞共培养（图 5L 和图 S11G）。结果显示，Tph 细胞比 Th 和 Treg 细胞更有效地诱导 AtM B 细胞分化，这通过 IL-21R 阻断显著减弱（图 5M 和图 S11H）。总的来说，这些数据表明，肿瘤浸润的 Tph 细胞显著促进了 AtM B 细胞的分化。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101554062.png)

> 图 6. 谷氨酸促进 AtM B 细胞分化并获得免疫调节功能。
> (A) Bm 和 AtM B 细胞的代谢途径中位得分（左）和不同组织的平均代谢基因表达的热图（右）。圆圈大小和颜色均代表缩放的代谢得分（左）。热图的颜色代表平均代谢基因表达（右）。
> (B 和 C) 健康人血液 B 细胞被 R848 单独或与 IFNg 或谷氨酸或谷氨酸和 CB839 一起刺激 4 天。 (B) 通过 FACS 检测的 AtM（顶部）和 Bm（底部）细胞的代表性流式图。 (C) (左) CD20+ B 细胞中 Bm 和 AtM 的频率，（右）Bm 或 AtM B 细胞中三甲基化组蛋白 H3（K27）的频率，通过 FACS 检测（n = 6 至 10）。
> (D) 在健康人血液 B 细胞中，使用磷酸盐缓冲液（PBS）（对照）或与 R848 以及有无谷氨酸刺激 24 小时后，再加入橄榄霉素、FCCP 和 Rot/AA（Rot/AA）（n = 4）检测的实时氧消耗率（OCR）。图示为均值 ± 标准差。
> (E) 在健康人血液 B 细胞中，使用 R848 刺激 24 小时的 13C 标记谷氨酸的代谢追踪分析（n = 4）。通过质谱（MS）检测 R848 和谷氨酸刺激的 B 细胞中指示的标记代谢物。
> (F) 健康人血液 B 细胞被 R848 单独或与 IFNg 或谷氨酸刺激；或谷氨酸和 CB839；或谷氨酸、CB839 和 DMaKG；或 DMaKG 刺激 4 天。通过 FACS 检测 CD20+ B 细胞中 AtM 的频率（n = 3 至 5）。
> (G) 在 DPBS 或 R848 单独或 R848 和谷氨酸刺激 4 天的健康人血液 B 细胞中，显示染色质可及性热图（n = 3）。颜色代表我们的 scATAC-seq 数据集中识别的 AtM 身份峰的强度。
> (H) 对 R848 单独或与 R848 存在下处理的谷氨酸的健康人血液 B 细胞的通路富集分析热图 4 天（n = 3）。颜色代表缩放的通路富集得分。
> (I 和 J) 肿瘤浸润的初级、Bm 和 AtM B 细胞中与 mTOR 信号相关的磷酸化蛋白的代表性流式图 (I) 和箱形图 (J)，来自肝细胞癌患者（n = 7 至 9）。
> (K 和 L) 健康人血液 B 细胞被 R848 单独或与谷氨酸或谷氨酸和雷帕霉素刺激 4 天。 (K) 显示来自 FMO（荧光减一）（顶部）和实验组（底部）的代表性流式图，(L) 通过 FACS 确定 CD20+ B 细胞中 AtM 的频率（n = 12）。
> (M) 健康人血液 B 细胞被 R848 单独或与谷氨酸刺激 4 天。刺激后的 B 细胞被收集并与 CFSE 标记的健康人血液 T 细胞以 2:1 的比例共培养，在 CD3/CD28 珠子存在下培养 3 天。通过流式细胞术确定增殖的 CD4+ 和 CD8+ T 细胞的频率（n = 12）。
> (N) 健康人血液 B 细胞被 R848 单独或与谷氨酸刺激 4 天。刺激后的 B 细胞被收集并与健康人血液 T 细胞以 2:1 的比例共培养，在 CD3/CD28 珠子存在下培养 5 天。通过流式细胞术确定细胞毒性 CD4+ 和 CD8+ T 细胞的频率以及 CD4+ T 细胞中 Tregs 的频率（n = 13）。
> (O) 根据结直肠腺癌（COAD）（n = 98，顶部）和肝细胞癌（LIHC）（n = 358，底部）患者 CD20+ B 细胞中 Bm 和 AtM B 细胞的频率的 Kaplan-Meier 总生存曲线。
> (P) 根据 Bm 和 AtM B 细胞的特征得分，分层治疗的皮肤黑色素瘤（SKCM）患者（n = 26）的反应率（左）和总生存（右）的情况。CR，完全缓解；PR，部分缓解；PD，进展性疾病；SD，稳定疾病。
> (Q) 根据 Bm 和 AtM B 细胞的特征得分分层的肺癌（LC）患者（n = 26）接受抗 PD1 治疗的无进展生存 Kaplan-Meier 曲线。数据显示中位数和 IQR 在 (C) 和 (M) 中；在 (J)，(L) 和 (N) 中显示最小和最大测量值。\*P < 0.05，\*\*P < 0.01，\*\*\*P < 0.001，\*\*\*\*P < 0.0001；ns, 无显著性。P 值由双侧 Wilcoxon 检验确定 (C)，(D) 和 (F)；Mann-Whitney 检验确定 (D) 和 (N)；双侧配对学生 t 检验确定 (L) 至 (N)；双侧对数秩检验确定 (O)（右侧），(P) 和 (Q)，以及 χ² 检验确定 (P)（左侧）。

#### 谷氨酸代谢建立外滤泡 AtM B 细胞的表观遗传身份

我们接下来研究了在肿瘤微环境（TME）中机械性地推动对 EF 与 GC 路径的主要反应的因素。对 B 细胞进行的通路分析揭示了人类癌症类型间代谢途径的显著差异，暗示潜在的 B 细胞身份代谢调控（图 S12A）。我们使用 scMetabolism（89）计算了 Bm 和 AtM B 细胞的代谢途径得分，并对代谢相关基因进行了无监督聚类（图 6A）。在肿瘤浸润的 AtM B 细胞中，谷氨酸、谷氨酰胺和鞘磷脂代谢被上调，而花生四烯酸代谢在 Bm 细胞中显著上调。这些途径的核心基因，如谷氨酰胺酶（GLS）、GLA 和 PTGES3，显示了类似的趋势（图 S12B）。这些结果在不同类型的癌症中观察到，没有癌症类型偏好（图 S12C）。

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101621505.png)

> Fig.S12. AtM B 细胞的代谢-表观遗传特征。(A) 使用四个通路方差指数估计 B 细胞亚群的通路活性方差，并且无监督聚类显示代谢通路在 scRNA-seq 数据集中排名高于非代谢通路。(B) 不同组织中富集于 Bm 和 AtM B 细胞的选定代谢基因的表达 (顶部)，以及它们在推断的伪时间 (底部) 沿着 path1 (红色) 和 path2 (蓝色) 细胞中的动态表达。中心线表示线性拟合，阴影线表示 95% 置信区间。(C) 箱型图显示了使用 scMetabolism 计算的 scRNA-seq 数据集中不同癌症类型中 Bm 和 AtM B cells 中选定代谢途径的富集。(D) 非靶向代谢组学检测的 EF 和 GC 来源优势癌中的谷氨酰胺。(E) 非靶向代谢组学检测的 LIHC (n = 109) 配对癌组织和邻近正常组织中的谷氨酰胺。(F) 健康血 B 细胞用 R848 连续五天刺激，使用不同的谷氨酰胺生理血浆浓度 (DPBS，1x、5x、10x 和 20x)。FACS 检测 CD20 B 细胞中 AtM B 细胞的频率 (n = 4)。(G) 健康血 B 细胞单独用 R848 刺激或与 R848 在 10 倍谷氨酰胺或 10 倍谷氨酰胺和 CD839 存在下刺激 24 小时。提取细胞内代谢物并通过质谱检测 (n = 5)。(H) ATAC-seq 轨迹显示健康血 B 细胞用 R848 单独刺激或在 10 倍谷氨酰胺存在下用 R848 刺激 4 天后 TBX21 和 BATF 位点的染色质可及性。(I 和 J) 过表达 TBX21 的健康血 B 细胞用 R848 和谷氨酰胺刺激 4 天。FACS 检测代表性流式图 (I) 和 AtM B 细胞的频率 (J) (n = 6)。(K 和 L) 用 DPBS (对照) 或单独用 R848 或用 R848 和 10 倍谷氨酰胺刺激 4 天的健康血 B 细胞中 mTORC1 通路 (K) 和 CSR 相关基因 (L) 的相对基因表达 (n = 4)。数据显示 IQR 的中位数 (G 和 J)，须线表示最小值和最大测量值 (B、C、D 和 E)。\*, P < 0.05; **, P < 0.01; \***, P < 0.001; ns，不显着。P 值由双侧 Wilcoxon 检验 (D)、双侧配对 Student t 检验 (F、G、J 和 K) 确定。

考虑到谷氨酸在 TME 中的基本作用和大量存在（90-92），我们研究了谷氨酸与我们队列中 B 细胞免疫表型的关联。通过基于质谱的非靶向代谢组学，我们的数据表明，以 EF 反应为主的癌症（肝细胞癌、宫颈鳞状细胞癌和肾细胞癌）的谷氨酸显著高于 GC 主导的癌症（胃腺癌和肺癌）（图 S12D）。此外，肝细胞癌中的肿瘤与邻近正常组织相比，谷氨酸显著更高（n=109）（图 S12E），而结直肠腺癌和胃腺癌这两种 GC 主导的癌症，其谷氨酸水平低于邻近正常组织（93）。因此，我们假设谷氨酸代谢可能在 TME 中启动 EF 反应中发挥潜在作用。

为了验证这一假设，我们收集了健康血液中的 B 细胞，并用 R848（TLR7 激动剂）、IFNg 和谷氨酸刺激它们。类似于 IFNg 在自身免疫疾病中的作用（21, 22），与单独 R848 相比，谷氨酸显著诱导了 AtM 分化，而 GLS 抑制剂（CB839）显著减弱了这一效应（图 6, B 和 C）。作为对照，Bm 细胞对 IFNg 和谷氨酸的刺激反应显著减少，表明谷氨酸通过对立的调节机制影响 AtM 和 Bm 细胞。此外，在体外谷氨酸刺激下，AtM 逐渐增加，并在第 4 天左右达到高峰，剂量依赖性最大化约为生理浓度的 10 倍（图 S12F）。我们监测了 B 细胞在谷氨酸刺激下的氧消耗率和三磷酸腺苷（ATP）产量，并观察到线粒体呼吸加上糖酵解的全球降低（图 6D）。这表明谷氨酸可能重塑 B 细胞的代谢特征，导致我们假设谷氨酸抑制了 B 细胞的克隆扩张或正选择，从而将 B 细胞分化转向 AtM B 细胞（94）。

#### 外滤泡 B 细胞培育免疫调节微环境，并与人类癌症的不良预后相关

![image.png](https://raw.githubusercontent.com/aletolia/Pictures/main/202405101622666.png)

> Fig.S13. AtM B 细胞的免疫调节功能与更差的预后相关。(A) 从 LIHC 患者中分离出肿瘤浸润的 AtM 和非 AtM B 细胞，并用 PMA 和离子霉素 (PI) 刺激 5 小时。收集上清液，通过 ELISA 测定 IL10 (左) 和 TGF β (右) 的浓度 (n = 3-5)。(B) LIHC 患者肿瘤浸润的幼稚 B 细胞、Bm 细胞和 AtM B 细胞中 PDL1 的代表性图 (左)。LIHC 患者肿瘤浸润的幼稚 B 细胞、Bm 细胞和 AtM B 细胞中 PDL1 的 MFI 箱型图 (右，n = 7)。(C) 健康血 B 细胞单独用 R848 刺激或在谷氨酰胺存在下用 R848 刺激 4 天。收集刺激的 B 细胞并用 PI 刺激 5 小时。收集上清液，通过 ELISA 测定 IL10、PDL1 和 TGF β 的浓度 (n = 4)。(D 和 E) 健康血 B 细胞单独用 R848 刺激或在谷氨酰胺存在下用 R848 刺激 4 天。收集刺激的 B 细胞，并与 CFSE 标记的健康血 T 细胞以 2:1 的比例共培养 3 天，同时加入 CD3/CD28 珠。通过流式细胞术测定增殖的 CD4+、CD8+ 和 CD3+ T 细胞的代表性图 (D) 和增殖的 CD4+ T 细胞的频率 (E) (n = 12)。(F-H) 健康血 B 细胞单独用 R848 刺激 (顶部) 或在谷氨酰胺存在下用 R848 刺激 (底部) 4 天。收集刺激的 B 细胞，并与健康血 T 细胞以 2:1 的比例共培养 5 天，同时加入 CD3/CD28 珠。CD4+ (F) 和 CD8+ (G) T 细胞中表达的功能标记物的代表性流式图。通过流式细胞术测定 CD4+ 和 CD8+ T 细胞的 Ki67、TNFα、IFNγ 和 PD1 的频率 (H) (n = 13)。(I) 来自 STAD (n = 52) 和 LC (n = 90) 患者的 CD20+ B 细胞中 Bm 和 AtM B 细胞频率的 OS 的 Kaplan-Meier 生存曲线。数据显示 IQR 的中位数 (E) 和须线表示最小值和最大测量值 (A、B、C 和 H)。\*, P < 0.05; **, P < 0.01; \***, P < 0.001; \*\*\*\*, P < 0.0001. P 值通过双侧配对 Wilcoxon 检验 (A、C)、双侧配对 Student t 检验 (E 和 H) 和双侧 log-rank 检验 (L) 测量。

鉴于外滤泡 AtM B 细胞与 T 细胞在 TLS 内的空间共定位，我们探讨了 AtM B 细胞对 T 细胞的潜在影响（图 5A）。经刺激后，分选的肝细胞癌浸润的 AtM B 细胞分泌的 IL-10 和转化生长因子 -β（TGF-β）较多，并表达的 PDL-1 高于非 AtM B 细胞，这一结果与对照相比，通过谷氨酸诱导的 B 细胞也得到了验证（图 S13, A 至 C）。接下来，我们用谷氨酸诱导外周 B 细胞转化为 AtM，并与外周 CD3+ T 细胞共培养体外。AtM B 细胞能够减少 CD4+ 和 CD8+ T 细胞的增殖（图 6M 及图 S13, D 和 E），并损害 T 细胞产生 IFNγ、肿瘤坏死因子 -α（TNF-α）和颗粒酶 B 的能力（图 6N 及图 S13, F 和 G）。AtM B 细胞促进了向调节性 T 细胞（Treg）和耗竭 T 细胞的分化（图 S13H），==这与先前的研究相似==，这些研究显示 CD27− 耗竭 B 细胞和位于不成熟 TLS 中的 B 细胞与 Treg 相关并共定位（41, 97）。

最后，我们探讨了 Bm 和 AtM B 细胞在癌症中的预后价值。在四个独立队列（结直肠腺癌、胃腺癌、肺癌和肝细胞癌）中，无论是 EF 或 GC 主导的癌症，Bm 细胞与良好的预后相关，而 AtM B 细胞与更差的生存率相关（图 6O 和图 S13I）。此外，在接受抗 PD1 治疗的黑色素瘤（n = 26）（98）和肺癌（n = 21）（99）的已发布队列中，AtM B 细胞的丰度显著与治疗抗性相关，而 Bm 细胞则与改善的反应和更长的生存期相关（图 6, P 和 Q）。总体来说，这些观察结果表明，EF 来源的 B 细胞与不成熟的 TLS 和耗竭的 T 细胞相关，导致免疫治疗抗性和某些癌症的预后不良。====