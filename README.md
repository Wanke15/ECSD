# E-Commerce Sentiment Dict (ECSD)

**电商情感词典**

本项目介绍苏州大学人类语言研究所构建的电商情感词典，包括通用的情感词条和电商领域特有的情感词条，共计3138条

<br>

## 电商情感词典包含的类别、预置标签、数目以及示例

|类别|预置标签|数目|示例|
|:-:|:-:|:-:|:-:|
|正面观点表达|DoUP|844|...物有所值，实惠，舒服...|
|中性观点表达|DoUM|82|...美中不足，一般，凑合...|
|负面观点表达|DoUN|2084|...伤不起，差评，贵...|
|多极性观点表达|DoP|99|...水水的，大，高...|
|否定词|DoN|29|...不，不怎么，没那么...|

其中，前三种类别的观点表达只反映单一的情感倾向（例如“好吃”）

第四种观点表达反映多种情感倾向（例如“价格  **高**  ”和“性价比  **高**  ”）

否定词的追加是为了进一步扩展观点表达（“不”+“给力”=“不给力”）

<br>

## 文件介绍

* DoUP：放置正面观点表达的词条
* DoUM：放置中性观点表达的词条
* DoUN：放置负面观点表达的词条
* DoP：放置多极性观点表达的词条
* DoN：放置否定词的词条

<br>

## 情感词典参考用法

本文的主要任务是从观点文本（例如用户评论文本等）中获取情感要素（例如观点对象、观点表达、情感倾向等），看作序列标注问题，并使用情感词典来改善挖掘性能

因此，本文使用情感词典词条对生文本进行最大正向匹配，将得到的情感词典标签与原有文本结合起来输入序列标注模型，匹配实例如下：

    设词表为：DoUP={实惠，耐用}，DoN={不}
    生文本为：产品实惠但不耐用
    按照最大正向匹配的结果为：
    
    产   O
    品   O
    实   B-DoUP
    惠   I-DoUP
    但   O
    不   B-DoN
    耐   B-DoUP
    用   I-DoUP

在其他一些情感分析任务中可以有其他用法，但一般都采用匹配的方法

<br>

## 相关论文

**郁圣卫, 卢奇, 陈文亮. 基于领域情感词典特征表示的细粒度意见挖掘. CCL-2018（已录用）**
