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

若矩阵 X 使对称正定的，Cholesky分解将矩阵分解成一个下三角矩阵 R 和一个上三角矩阵 R^T (下三角矩阵 R 的转置)的乘积。

```
R = chol(X)
```
X 非对称正定时，输出错误信息。为使该分解不输出错误信息，我们使用
```
[R,p] = chol(X)
```
对 X 进行分解。X 为对称正定时，p=0。否则 p 为一个正整数。如果 X 为满秩矩阵，则 R 为一个阶数为 q=p-1 的上三角阵，切满足 (R^T)R = X(1:q,1:q)。

#### 4. 任意方阵的Schur分解

任意一个 n 阶方阵 X 可以分解为 X=URU'，其中 U （unitiary）为酉矩阵，R 为上三角 schur 矩阵且其主对角线上的元素为 X 的特征值。
```
[U,R]=schur(X) 
```

#### 5. 任意方阵的Hessenbery分解

任意一个 n 阶方阵 X 可以分解为 X=PHP', 其中 P 为酉矩阵, H 的第一子对角线下的元素均为 0，即 H 为 Hessenberg 矩阵。
```
[P,H]=hess(X) 
```

#### 6. 任意方阵的特征值分解 (Eigenvalue Decomposition)

任意一个 n 阶方阵 X 可以分解为 XV=VD，其中 D 为 X 的特征值对角阵，V 为 X 的特征向量矩阵。
```
[V,D]=eig(X)
```
我们也可以计算广义特征值矩阵 D 和广义特征值向量矩阵 V，使得 XV = YVD。


#### 7. 矩阵的奇异值分解 (Signular Value Decomposition)
任意一个 mxn 维的矩阵 X 可以分解为 X=USV'，U 和 V 均为酉矩阵（unitiary matrix），S 为 mxn 维的对角矩阵，其对角线元素为 X 的从大到小排序的非负奇异值。

```
[U,S,V]=svd(X)
```

#### 8. 矩阵的几何均值分解 (Geometric Mean Decomposition)

任意矩阵 mxn维的矩阵 X 可以分解为 X=QRP', Q 和 P 均为酉矩阵（unitiary matrix），R 为 kxk 维的实正线上三角矩阵，其主对角线元素均等于 X 的所有 K 个正奇异值的几何均值，k=rank(X)。
对于复数的情况，定义则为：一个 nxn 的 Hermitian 矩阵 M 是正定的当且仅当对于每个非零的复向量 z ，都有 z'Mz > 0。其中 z' 表示z的共轭转置。由于 M 是 Hermitian 矩阵，经计算可知，对于任意的复向量 z，z'Mz 必然是实数，从而可以与 0 比较大小。因此这个定义是自洽的。正定方阵M的所有的特征值 λi 都是正的。


### 结尾
在物理层通信学习中，难以避免各种矩阵分解，熟练掌握以上方法可以帮助我们更好的阅读参考文献。祝大家科研顺利！

### Reference

[矩阵分解的Matlab指令大全](https://wenku.baidu.com/view/c952870c76c66137ee0619a1.html#)
