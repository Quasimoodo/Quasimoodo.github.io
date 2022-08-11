---
layout: post
title: 论文笔记 Highway OCL & Informal to Formal Specications in UML
date: 2022-06-28 19:49:50
tags:
- Code generation
- OCL
categories:
- Substance
---
这篇笔记是文章 From Informal to Formal Specications in UML 和 Automating Utility Permitting within Highway Right-of-Way via a Generic UML/OCL Model and Natural Language Processing的不完全笔记
<!--more-->
# Abstract

Purpose :

 informal requirements,use cases => formal specifications ,OCL

# Summary

**how to obtain formal specications from informal ones**

formal ones can also help to improve informal ones.

# Introduction

在intro中讲故事的这一部分很有意思 可能是因为是04年的文章 他的引入视角是——UML在OO建模很猛——有了OCL才能足够精确——不知道应该在什么环节集成OCL——还是应该customer来做，毕竟对系统行为清晰——期望所有人都有能力不现实



用例——describe system behaviors



研究了 文字用例中的前后置条件 与 类图中OCL写的操作的前后置条件 的**关系**



从分析阶段的用例图——到设计阶段的时序图和类图



## 用例图

非正式的本质 可以用在更多的上下文本经当中，但寻求正确的抽象层次和确保一致性困难

在他们的工作中 书写用例描述的风格不太重要 只要他们能够展现出需求与开发设计者的共识，获得前后置条件

考虑了关于替代流的问题 本来想掰开成为别的用例 但觉得违背了为用户满足目标的愿景



# 状态图

考虑了用例的所有路径



# 从用例到操作后置条件

只讨论用例的后置条件 因为觉得前置差不多 而且有点迷惑——比方说满足了前置条件就相当于进入某些流’

所以就当所有的前置条件都是空

讨论系统中的唯一对象就是系统本身



客户给的自然语言描述后置条件可能不光和终态有关，还可能和事件序列有关 比如输错三次密码

——使用状态图来捕获条件









# Automating Utility Permitting within Highway Right-of-Way via a Generic UML/OCL Model and Natural Language Processing

OCL用来表达一些方位上的约束





implies的作用：只有前面的条件是真，后面的东西才会被评估



采用了扩展的OCL 增添了一些对空间语义的描述的函数 如不相交 相当 包含等





要将这样的文本约束转化为OCL——首先可以先变成较为形式化的元组

the 6-inch mechanical joint inlet shall be located 5 feet 6 inches below the ground

——》

<mechanical joint inlet (6-inch), below (5 ft 6 in.), ground>.





方位约束使用双层或多层语言层次来提取多种的方位信息



想要自动从方位约束中提取结构化的信息





1. 预处理：tokenize 句子划分和语法标注
2. 特殊标注 增添了额外三个词表 城市产品，方位词和比较关系的词会被识别标出
3. 逐级向上归纳 生成句子树
4. 从树型结构中寻找目标信息，生成结构化的元组
5. 从元组中生成所需OCL 不同层次有不同转换方法，主要是针对类不变量——x.allInstances->forAll ——implies这样的结构



NLP的方法：

使用某个NLTK实施标注和句子树的构建，从裸文本生成出对应元组，作为构造OCL约束的输入



UML/OCL的方法：

应用：

写在某种对象关系型数据库里 当有数据库的改动时触发触发器，检查是否符合约束



