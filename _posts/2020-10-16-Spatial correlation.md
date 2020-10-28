---
layout: post
title: "空间相关"
subtitle: '基础讲解及其MATLAB代码仿真'
author: "WT"
header-img: "img/post-bg-alitrip.jpg"
catalog: true

tags:
  - MIMO Communications
---

### 前言
在无线通信中，我们可以通过使用多输入多输出 （Multi-input multi-output， MIMO） 来抑制信道衰落效应。虽然假设这些天线使用信道预编码（precoding）后在空间上独立且具有相同的分布，但是在实际情况中，这些天线通常具有空间相关性，使其无法获得理想的潜在的性能。因此我们需要考虑其信道的空间相关性，表现为一个 NxN 的矩阵，该矩阵与信道矩阵是相关的。由于 Rayleigh 信道的均值为 0，即该空间相关矩阵为信道矩阵元素的协方差矩阵。

### 基础理论


![Agoda ST]（https://raw.githubusercontent.com/zhouwt612/zhouwt612.github.io/master/_posts/Photos/2020-10-28/Correlation_matrix.png)

### 代码实现
假设一个 2x2 的 MIMO 信道。
```
clc
clear
close all

h = sqrt(1/2)*(randn(2,2)+1i*randn(2,2));
vech = h(:);
vechh = vech';

R = vech*vechh;
```
R 即该 2x2 MIMO 信道的空间相关矩阵。

### 结尾


### Reference

1. [Spatial Correlation](https://en.wikipedia.org/wiki/Spatial_correlation)
2. [E. Björnson, J. Hoydis, and L. Sanguinetti, "Massive MIMO Networks: Spectral, Energy, and Hardware Efficiency," Foundations and Trends® in Signal Processing: Vol. 11, No. 3-4, pp 154–655.](https://massivemimobook.com/wp/)
