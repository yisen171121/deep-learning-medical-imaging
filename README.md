# deep-learning-medical-imaging
A curated collection of papers, code resources, and notes on Deep Learning for Medical Image Analysis.

## 📁 Repository Architecture Overview

The repository is organized to separate conceptual knowledge, practical code, and essential resources, following a clear progression from fundamentals to advanced applications.

### 1、The literature and its Repository 

- **[Segmentation](./01-Papers-Notes/01-Segmentation/)**

| Repository | Description |    Time     |
| :--------: | :---------: | :---------: |
|   Header   |    Title    | Here's this |
| Paragraph  |    Text     |  And more   |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |

- **[Classification](./01-Papers-Notes/01-Segmentation/)**

| literature | Description |     Time    |
| :--------: | :---------: | :---------: |
| Header     |    Title    | Here's this |
| Paragraph  |    Text     |    And more |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |

- **[Detection-Localization](./01-Papers-Notes/01-Segmentation/)**

| literature | Description |    Time     |
| :--------: | :---------: | :---------: |
|   Header   |    Title    | Here's this |
| Paragraph  |    Text     |  And more   |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |

- **[Registration](./01-Papers-Notes/01-Segmentation/)**

| literature | Description |    Time     |
| :--------: | :---------: | :---------: |
|   Header   |    Title    | Here's this |
| Paragraph  |    Text     |  And more   |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |

- **[Reconstruction](./01-Papers-Notes/01-Segmentation/)**

| literature | Description |    Time     |
| :--------: | :---------: | :---------: |
|   Header   |    Title    | Here's this |
| Paragraph  |    Text     |  And more   |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |

- **[Generative](./01-Papers-Notes/01-Segmentation/)**

| literature | Description |    Time     |
| :--------: | :---------: | :---------: |
|   Header   |    Title    | Here's this |
| Paragraph  |    Text     |  And more   |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |
|            |             |             |

### 2、Datasets

|           |       |             |
| :-------: | :---: | :---------: |
|  Header   | Title | Here's this |
| Paragraph | Text  |  And more   |
|           |       |             |
|           |       |             |
|           |       |             |
|           |       |             |
|           |       |             |
|           |       |             |
|           |       |             |

## 📝 Fundamentals

### 1、Preprocessing

|     预处理步骤     |               英文术语                |                        核心目的与说明                        |
| :----------------: | :-----------------------------------: | :----------------------------------------------------------: |
| 图像获取与格式转换 | Image Acquisition & Format Conversion | 从扫描设备（CT, MRI等）获取原始数据，并转换为标准格式（如DICOM转NIFTI）以便计算处理。 |
|       重采样       |              Resampling               | 将图像调整到统一的**体素间距（Voxel Spacing）** 和**图像尺寸（Image Dimension）**，解决不同设备、协议下分辨率差异的问题。 |
|    窗宽窗位调整    |           Windowing (WW/WL)           | 针对CT图像，通过设置**窗宽（Window Width）** 和**窗位（Window Level）**，将原始的HU值映射到显示灰度，以最佳对比度观察特定组织（如肺窗、骨窗）。 |
|       归一化       |             Normalization             | 将图像强度值缩放至特定范围（如[0,1]或[-1,1]），或进行**标准化（Standardization，即Z-score）**，以消除扫描间差异，加速模型训练收敛。 |
|        去噪        |               Denoising               | 减少图像中的随机噪声，提高信噪比。常用方法包括**高斯滤波（Gaussian Filter）**、**中值滤波（Median Filter）** 及更先进的**非局部均值（Non-Local Means）** 算法。 |
|      图像配准      |          Image Registration           | 将不同时间、模态或视角下的图像进行空间对齐，使解剖点一一对应。包括**刚性配准（Rigid）** 和**非线性/弹性配准（Non-rigid/Deformable）**。 |
|      图像分割      |          Image Segmentation           | 将图像划分为多个区域，通常是提取**感兴趣区域（Region of Interest, ROI）**，如器官或病灶。这既是预处理步骤，也是核心分析目标。 |

### 2、Evaluation

- **[Segmentation](./01-Papers-Notes/01-Segmentation/)**

|  核心评估指标  |        英文术语        |                        指标含义与用途                        |
| :------------: | :--------------------: | :----------------------------------------------------------: |
|  戴斯相似系数  |       Dice Score       |  衡量预测分割区域与真实标注（金标准）的重叠度，最常用指标。  |
|     交并比     |  IoU / Jaccard Index   |            类似Dice，计算重叠区域占合并区域的比例            |
|  豪斯多夫距离  |   Hausdorff Distance   |       衡量两个分割边界之间的最大距离，对轮廓误差敏感。       |
| 精确率与召回率 |   Precision & Recall   | **精确率**：预测为正的像素中实际为正的比例；**召回率**：实际为正的像素中被预测出的比例。 |
|  体积相关误差  | Volumetric Correlation |               计算预测体积与真实体积的相关性。               |

- **[Classification](./01-Papers-Notes/01-Segmentation/)**

|       核心评估指标       |         英文术语          |                        指标含义与用途                        |
| :----------------------: | :-----------------------: | :----------------------------------------------------------: |
| 受试者工作特征曲线下面积 |          AUC-ROC          |     综合衡量分类器在不同阈值下的性能，对类别不平衡稳健。     |
|          准确率          |         Accuracy          |                   总体分类正确的样本比例。                   |
|      敏感度与特异度      | Sensitivity & Specificity | **敏感度**（召回率）：正确识别正例的能力；**特异度**：正确识别负例的能力。 |
|          F1分数          |         F1-Score          |            精确率与召回率的调和平均数，兼顾两者。            |
|         混淆矩阵         |     Confusion Matrix      |      展示分类结果详细分布的表格，可计算出以上所有指标。      |

- **[Detection-Localization](./01-Papers-Notes/01-Segmentation/)**

| 核心评估指标 |       英文术语        |                    指标含义与用途                     |
| :----------: | :-------------------: | :---------------------------------------------------: |
|   平均精度   | Average Precision, AP | 综合精确率-召回率曲线下的面积，是检测任务的核心指标。 |
| 平均精度均值 |          mAP          |                 多个类别AP的平均值。                  |

- **[Registration](./01-Papers-Notes/01-Segmentation/)**

| 核心评估指标 | 英文术语 |              指标含义与用途              |
| :----------: | :------: | :--------------------------------------: |
| 目标配准误差 |   TRE    | 测量配准后对应解剖标志点之间的平均距离。 |
|  均方根误差  |   RMSE   |  计算配准后图像对之间强度差异的均方根。  |

- **[Reconstruction](./01-Papers-Notes/01-Segmentation/)**

|  核心评估指标  |        英文术语        |                        指标含义与用途                        |
| :------------: | :--------------------: | :----------------------------------------------------------: |
|   峰值信噪比   |          PSNR          |     衡量生成图像与目标图像之间的像素级误差，值越高越好。     |
| 结构相似性指数 |          SSIM          | 从亮度、对比度、结构三方面评估两幅图像的相似性，更符合人眼感知。 |
|   均方根误差   |          RMSE          |            计算配准后图像对之间强度差异的均方根。            |
| 基于任务的性能 | Task-based Performance | 评估重建图像在**下游任务**（如分割、检测）中的效用，是更临床化的评估。 |
|   噪声功率谱   |          NPS           | 描述图像噪声的**强度**随**空间频率**的分布。不同重建算法会产生不同特性的噪声（如白噪声、纹理状噪声）。NPS可以量化这些差异。 |
|  调制传递函数  |          MTF           | 描述成像系统传递**不同空间频率**的**对比度**的能力。MTF曲线下降得越慢，系统分辨率越高，细节保留越好。 |
|  对比度噪声比  |          CNR           | 衡量图像中**特定目标区域**与**背景区域**之间的信号强度差异，相对于图像背景噪声的水平。 |
|    主观评分    |   Subjective Scoring   | 由经验丰富的放射科医生或临床专家，根据其专业知识和临床需求，对医学图像的**质量**和**适用性**进行系统性、结构化的视觉评价和打分。 |
|                |                        |                                                              |

基于参考的图像质量 (PSNR, SSIM, RMSE)当存在“金标准”参考图像时，用于衡量重建的保真度。

- **[Generative](./01-Papers-Notes/01-Segmentation/)**

|  核心评估指标  | 英文术语 |                        指标含义与用途                        |
| :------------: | :------: | :----------------------------------------------------------: |
|   峰值信噪比   |   PSNR   |     衡量生成图像与目标图像之间的像素级误差，值越高越好。     |
| 结构相似性指数 |   SSIM   | 从亮度、对比度、结构三方面评估两幅图像的相似性，更符合人眼感知。 |
| 弗雷歇起始距离 |   FID    | 衡量生成图像与真实图像在特征空间的分布距离，值越低表示生成质量越真实。 |
|   感知相似性   |  LPIPS   |    使用深度学习特征计算图像差异，与人类视觉判断相关性高。    |

### 3、Clinical-Concepts

|          概念           |                  英文术语                  |                      核心用途与临床意义                      |
| :---------------------: | :----------------------------------------: | :----------------------------------------------------------: |
|     标准化扫描方案      |              Imaging Protocol              | 包括设备参数、序列、剂量等。确保图像质量一致、可比，是后续一切分析的基础。**临床意义**：错误的协议会导致诊断信息丢失或辐射浪费。 |
|        临床指征         |            Clinical Indication             | 进行此次检查的**具体临床原因或问题**（如“筛查肺癌”、“评估中风”）。它直接决定了应采用何种协议、观察哪些结构、以及如何撰写报告。 |
|      解剖标志/结构      |     Anatomical Landmarks / Structures      | 识别图像中的正常器官、组织、边界。是定位病灶、描述其位置（如“肝右叶后段”）的**空间参考系**。 |
|   病理改变/病灶/发现    |        Pathology / Lesion / Finding        | 指图像上异常的区域或模式。对其进行**检测、分割、分类**是医学图像AI的核心任务。 |
| 影像组学/影像生物标志物 |       Radiomics / Imaging Biomarkers       | 从图像中高通量提取的定量特征（如纹理、形状）。用于预测肿瘤基因型、治疗反应或预后，实现**精准医疗**。 |
|        窗宽窗位         |            Window Width & Level            | 整图像显示对比度的工具，是放射科医生**主观优化**图像以观察不同组织（如肺窗、纵隔窗、骨窗）的关键操作。 |
|     影像学征象/模式     |        Radiological Sign / Pattern         | 特定的图像表现与疾病病理之间的关联（如“毛刺征”提示肺癌，“黑洞征”提示急性脑卒中）。是诊断推理的**词汇库**。 |
|        报告指南         |            Reporting Guidelines            | 结构化报告模板（如LI-RADS用于肝，BI-RADS用于乳腺）。确保报告**全面、标准化**，减少歧义，便于随访和沟通。 |
|        鉴别诊断         |           Differential Diagnosis           | 根据影像表现，列出所有可能的疾病列表，并按可能性排序。AI可辅助提供基于大数据支持的鉴别清单。 |
|     诊断信心/确定性     |     Diagnostic Confidence / Certainty      | 医生对诊断结论的把握程度（常以概率表示）。AI可作为一个“第二意见”来增强或校准医生的信心。 |
|   临床金标准/参考标准   | Clinical Ground Truth / Reference Standard | 诊断的最终依据，如**病理活检结果、外科手术发现、长期临床随访结局**。这是评估任何AI模型性能的**终极标尺**。 |
|     临床工作流集成      |       Clinical Workflow Integration        | AI工具如何嵌入到现有的医院信息系统和医生工作习惯中（如与PACS集成）。决定其**可用性和采纳度**。 |
|      可行动的发现       |             Actionable Finding             | 指那些需要临床干预或改变治疗计划的影像发现。AI应优先识别和提示此类发现。 |
|      治疗反应评估       |       Treatment Response Assessment        | 使用影像（如RECIST标准用于肿瘤）定量测量病灶对治疗的变化。AI可自动化此过程，提高评估的客观性和效率。 |

## 🧭Challenges-Competitions

|  中文名称  | 英文名字 | 主办方/所属会议 | 核心任务与简要介绍 | 时间 |
| :--------------: | :--: | :--: | :---: | :---: |
| 脑肿瘤分割“灯塔”挑战赛 | BraTS (Brain Tumor Segmentation) Lighthouse Challenge | MICCAI | **任务**：在多模态脑部MRI上，对胶质瘤的不同亚区（如增强肿瘤、非增强肿瘤核心、瘤周水肿）进行自动分割。<br/>**介绍**：自2012年起举办，是医学影像分割领域**影响力最大、历史最悠久**的基准测试。其数据集规模大、标注精细，旨在解决脑肿瘤诊断、手术规划和疗效评估中的核心分割难题。2025年升级为“灯塔挑战”，涵盖术前/术后等多场景。 | 2025年9月 |
| 头颈部肿瘤分割、诊断与预后挑战赛 | HECKTOR (Head and neCK TumOR segmentation, diagnosis and prognosis) | MICCAI | **任务**：基于PET/CT图像，完成**头颈部原发肿瘤和淋巴结的自动分割**、**HPV状态分类**以及**无复发生存期预测**。<br/>**介绍**：聚焦头颈部癌症，任务结合了**图像分割**与**临床预后预测**，极具临床价值，旨在辅助放疗靶区勾画和个性化治疗决策。 | 2025年9月 |
| 真实世界医学图像综合分析与计算挑战赛 | CARE (Comprehensive Analysis & computing of REal-world medical images) | MICCAI | **任务**：处理真实世界临床数据中的复杂问题，如**少样本、跨中心、跨设备、模态缺失**等场景下的分割任务（如肝脏、心脏分割）。<br/>**介绍**：旨在推动AI算法从“理想实验室数据”走向“复杂临床环境”，考验算法在数据异构、标注稀缺等真实挑战下的**泛化能力**。 | 2025年9月 |
| 口腔影像智能分析挑战赛 | ToothFairy & STSR | MICCAI | **任务**：**ToothFairy** 专注于CBCT影像中的牙齿、神经管等多结构分割；**STSR** 专注于牙齿、牙髓根管分割以及口内扫描与CBCT的配准。<br/>**介绍**：推动AI在**数字化口腔诊疗**中的应用，解决正畸、种植、根管治疗中的精准测量和手术规划问题。 | 2025年9月 |
| 通用超声图像挑战赛 | UUSIC (Universal Ultrasound Image Challenge) | MICCAI | **任务**：开发一个能处理**跨多个器官、多种病理、多种任务**（分类、分割、检测、回归）的通用超声分析模型。<br/>**介绍**：旨在突破当前超声AI“一病一模型”的局限，推动构建适应复杂临床环境的、鲁棒的**超声基础模型**。 | 2025年9月 |
| 分娩期超声大挑战赛 | IUGC (Intrapartum Ultrasound Grand Challenge) | MICCAI | **任务**：在产程超声图像中自动检测关键解剖标志点，并测量如**产程角**等重要临床参数。<br/>**介绍**：直击产科超声临床痛点，通过自动化测量减少操作者依赖性，提高产程评估的标准化和效率。 | 2025年9月 |
| RSNA颅内动脉瘤AI挑战赛 | RSNA Intracranial Aneurysm AI Challenge | RSNA | **任务**：在CTA、MRA等多模态影像中，同时完成**动脉瘤的有无判断和多个部位的精准定位**。<br/>**介绍**：由全球顶级放射学会主办，基于大规模、多中心、多模态的真实临床数据，旨在开发能用于动脉瘤筛查和诊断的高精度AI工具，竞赛竞争极其激烈。 | 2025年11-12月 |
| 统一医学影像与语言基准挑战赛 | UNICORN (Unified Benchmark for Imaging in Computational Pathology, Radiology and Natural Language) | MICCAI Lighthouse | **任务**：构建和评估能在**病理、放射影像和文本**多个模态和任务上通用的**医学基础模型**。<br/>**介绍**：是评估医学AI基础模型最全面的基准之一，涵盖11项影像任务，推动迈向通用医学人工智能。 | 2025年9月 |
| ISBI胎儿超声大挑战赛 | ISBI Fetal Ultrasound Grand Challenge (FUGC) | ISBI | **任务**：采用**半监督学习**范式，在仅有少量标注的宫颈超声图像上实现宫颈前唇和后唇的自动分割，用于早产预测。<br/>**介绍**：聚焦产科临床重要问题，旨在降低标注成本，推动自动化宫颈超声图像分割技术的发展。 | 2025年3-4月 |
| 医学分割基础模型挑战赛 | MedSegFM Challenge | CVPR | **任务**：开发**通用型3D医学分割基座模型**，要求能处理CT、MRI、PET、超声、显微镜等多种模态，分割243类解剖结构及病灶。<br/>**介绍**：旨在推动突破“一病一模型”局限的通用医学分割模型发展，是CVPR在医疗AI领域的重要赛事。 | 2025年6月 |
| 广义眼底血管分析挑战赛 | GAVE (Generalized Analysis of VEssels in fundus images) | MICCAI | **任务**：在眼底图像中实现**动静脉分类分割**、血管分割及泛化分析。<br/>**介绍**：推动糖尿病视网膜病变、高血压眼底病变等常见眼科疾病的智能诊疗技术发展，对心血管疾病智能预警研究有重要意义。 | 2025年9月 |

