---
layout: post
title: "矩阵分解及其MATLAB代码"
subtitle: 'A few method for Matrix decomposition.'
author: "WT"
header-img: "img/post-bg-alitrip.jpg"
catalog: true

tags:
  - MIMO Communications
---

### 前言
在通信物理层学习中，时常会遇到信道矩阵分解。因此在这里将矩阵分解的种类及其MATLAB代码列出，以备不时之需。

### 分解方法

#### 1. 可逆矩阵的LU分解
```
A = LU
```

矩阵的LU分解即将任意矩阵（方阵） X 分解为一个下三角矩阵 L 和一个上三角矩阵 U。当方阵 A 是非奇异矩阵，LU 分解总是存在的。

MATLAB代码：

```
[L,U] = LU(X)
```

存在一个置换矩阵，使 PX = LU。

```
[L,U,P] = lu(X)
```

#### 2. 满秩矩阵的QR分解

将矩阵 X （方阵）分解成一个正交矩阵 Q 和一个上三角矩阵 R 的乘积形式。

```
[Q,R] = qr(X)
```
存在一个矩阵 Q，使 XE = QR。
```
[Q,R,E] = qr(X)
```

#### 3. 对称正定矩阵的Cholesky分解




#### 4. 任意方阵的Schur分解

#### 5. 任意方阵的Hessenbery分解

#### 6. 任意方阵的特征值分解 (Eigenvalue Decomposition)

#### 7. 矩阵的奇异值分解 (Signular Value Decomposition)

#### 8. 矩阵的几何均值分解 (Geometric Mean Decomposition)


### 结尾
在物理层通信学习中，难以避免各种矩阵分解，熟练掌握以上方法可以帮助我们更好的阅读参考文献。祝大家科研顺利！

### Reference

[矩阵分解的Matlab指令大全](https://wenku.baidu.com/view/c952870c76c66137ee0619a1.html#)
