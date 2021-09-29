# Personalize Workshop


## 准备环境

创建Sagemaker Notebook 实例：
* Name: PersonalizeWorkshop
* Notebook instance type: ml.m5.xlarge
* Volume size: 20GB


点击“Open JupyterLab" 进入Jupyter Notebook 
* Clone a repo: https://github.com/leejianwei/amazon-personalize-workshop.git
* 进入“amazon-personalize-workshop”文件夹


1. 验证和导入user-item-interaction 数据 - 
`01_Validating_and_Importing_User_Item_Interaction_Data.ipynb`
1. 验证和导入item-metadata数据 - 
`02_Validating_and_Importing_Item_Metadata.ipynb`
1. 创建和评估你的第一个方案 - 
`03_Creating_and_Evaluating_Solutions.ipynb`
1. 部署活动（campaign）和筛选器 -
`04_Deploying_Campaigns_and_Filters.ipynb`
1. 与活动（campaigns）和筛选器交互 -
`05_Interacting_with_Campaigns_and_Filters.ipynb`
1. 清空你的AWS账号中用到的资源 - `06_Clean_Up_Resources.ipynb`

以上为本POC过程的一般顺序。但是，如果你是参加一个两天的现场POC，建议你在到达实验现场之前事先导入user-item-interaction 和item-metadata数据。


## 实验步骤

### 验证和导入User-Item-Interaction 数据

用于Amazon Personalize中每个算法的核心数据都是用户项交互数据user-item-interaction；本notebook将指导你识别这些数据，然后格式化这些数据使之可以用在Personalize服务中，并且定义你的数据模式（schema），最后导入这些数据. 

打开 `01_Validating_and_Importing_User_Item_Interaction_Data.ipynb` 并执行其中的步骤.

在你完成以后，继续执行下一步，导入元数据.

### 验证和导入 Item Metadata

Amazon Personalize有几种算法可以给你一个没有元数据的结果。但是，User Personalization和HRNN-Metadata算法可能是有趣的资源可用于部署，视你的数据集而定. 

打开 `02_Validating_and_Importing_Item_Metadata.ipynb` 并执行其中的步骤.

在你完成以后，继续执行下一步，创建和评估你的第一个解决方案.

它类似于处理用户数据的过程，只有User Personalization和HRNN-Metadata算法可以支持两种数据类型中的任意一种.

### 创建和评估你的第一个方案Solution

在Amazon Personalize中，有一个方案（Solution）的概念，它包含了一个基于你提供数据的经过训练的模型。所有模型都是私有的，帐户之间甚至数据集组之间都没有数据共享。本notebook将指导你完成训练模型的过程；也就是为以下各算法构建方案:

* HRNN
* SIMS
* Personalized-Ranking

你可能会注意到，每一个算法或配方都解决了一个截然不同的问题。这个目的是向你展示如何从一个相对简单的数据集构建解决大量问题的东西.

打开 `03_Creating_and_Evaluating_Solutions.ipynb` 并且执行构建这些解决方案的步骤并查看其结果.

### 部署你的活动（Campaigns）和筛选器

当你有了许多训练好的的方案后，下一步就是部署它们。这在下面的notebook中完成 `04_Deploying_Campaigns_and_Filters.ipynb`

在这里你可以学到:
1. 部署和能力的规划
1. 如何创建项目和事件筛选器


### 和Personalize进行交互

下一步是你部署的方案进行交互。 这在下面的notebook中完成 `05_Interacting_with_Campaigns_and_Filters.ipynb`. 在这里你可以学到:

1. 如何与部署的解决方案交互（各种方法）
1. 实时交互
1. 使用campaign和过滤器
1. 批量导出

### 下一步

完成这些Notebook后， 你会留下许多可工作的模型将来用于你的客户项目。从这里开始，你将考虑如何让客户按照他们的目标（覆盖，点击等）完成AB测试，然后发送数据流量到这些模型，并且监测模型指标。随着时间的推移，这样的构建将帮助你建立信心，并且也是你通向生产规模化的路径。

更多关于AB测试的内容即将推出。



### 清理

完成POC了？如果你想删除在你的AWS帐户中使用这些Notebook时创建的所有资源，请参阅 `06_Clean_Up_Resources.ipynb` notebook. 它将帮助你识别出你的账户中部署的所有Personalize资源，并告诉你如何删除它们。
