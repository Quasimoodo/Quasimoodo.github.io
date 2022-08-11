---
layout: post
title: emnlp-2018-九歌-多风格无监督诗歌生成
date: 2022-07-25 17:22:36
tags:
- NLP
- note
categories:
- Substance
---

本文是emnlp`18 Stylistic Chinese Poetry Generation via Unsupervised Style Disentanglement 的阅读笔记



<!--more-->

# Abs

* Contribution： 

  Fully unsupervised to generate stylistic poetry with same imagery, by incorporating mutual information

# Intro



Automatic poetry generation, Chinese quatrain:

Early Work: rule-based and template-based methods

 Recent : neural machine translation



**Previous Target**: coherency and conformity between theme and lines

A relevant work try to improve novelty

All need pre-defined topics





**Now target:** multiple generations in diverse styles under same input



**Model:** sequence-to-sequence model with attention mechanism



Use the mutual information for unsupervised style disentanglement and style-specific generation

还得学信息论……

 

In Relevant work , the author mentioned that with LDA applied ， only 10% sentences in a poem have the same largest topics components.



so , sentences in one poem can share different styles



so the author want to disentangle the poem from different kinds of styles, without  labels

**disentangled representation learning**

# Method





### 互信息Mutual Information





### Seq2seq with attention





数学水平不够 看不懂 怎么推到KL散度的

草





