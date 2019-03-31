---
title: Short explanation of graph by PCA
author: Geebbon
date: '2019-03-31'
slug: short-explanation-of-graph-by-pca
categories: 
  - plot
tags:   
  - R
  - data visualization
header:
  caption: ''
  image: ''
  preview: yes
summary:
  "Explanation of PCA graphs"
---

一般来说，PCA分析2个图够了，以iris数据为例，在经过PCA分析后，我们可以得到第一章碎石图，表示PC1，2，3，4的特征向量值，可以据此选择保留的主成分（通常选择特征向量值超过2的变量），此图显示出1个主成分可以保留。

![image.png](https://upload-images.jianshu.io/upload_images/1817671-f39056b2a8a39add.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

此外，可以有另外2个基于特征向量值选择主成分的标准，即 Kaiser-Guttman 标准和 Broken Stick 标准，这些标准可以反应主成分对于解释原始数据的贡献程度

![image.png](https://upload-images.jianshu.io/upload_images/1817671-f115189a5c07d722.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

依据Kaiser-Guttman 标准，仅应该保留主成分1，上图中仅PC1超过了平均值，下图中仅PC1超过了红色柱形图。

在选择了PC后，需要考虑变量对于PC的贡献，下图中，Petal Length，Width， Sepal Length对于PC1的贡献大，即方向偏向x轴方向；而Sepal width对PC2的贡献大，方向偏向y轴。长度越长，相对影响越大。

![image.png](https://upload-images.jianshu.io/upload_images/1817671-e3c1851faab033ca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


附简易代码

```

head(iris)

ir.pca <- prcomp(iris[,1:4], center=TRUE, scale. = TRUE) 

summary(ir.pca)

loadings <- ir.pca$rotation

scores <- ir.pca$x

plot(ir.pca, type = "l",main="")

ev <- ir.pca$sdev^2

source ('http://www.davidzeleny.net/anadatr/doku.php/en:numecolr:evplot?do=export_code&codeblock=1') 
evplot(ev)

library("ggbiplot")

ggbiplot(ir.pca, choices=c(1,2), obs.scale = 1, var.scale = 1)

ggbiplot(ir.pca,choices=c(1,2), groups=iris[,5], obs.scale = 1, var.scale = 1, ellipse = TRUE)
              
```
