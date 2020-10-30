---
layout: post
title: "正交导频序列"
subtitle: 'Walsh-Hadamard matrix and Discrete Fourier Transform matrix'
author: "WT"
header-img: "img/post-bg-alitrip.jpg"
catalog: true

tags:
  - MIMO Communications
---

### 前言
在无线通信中，我们需要在每个 Coherence block 中的起始位置添加导频来估计信道。在固定情况下，coherence block 的大小是固定的。在 TDD 模式下，每个 block 的顺序为 [导频，UL data，DL data]。因此导频的长度应该小于等于 coherence clock 的长度。即更长的导频长度会降低每个 block 中的信号样本的数量。因此通常导频的长度小于 block 长度的一半。
我们通常使用正交导频来做信道估计。

### 正交导频序列
在





