---
layout: post
title: "catatan mesin perekomendasi"
description: "penerapan konsep words of mouth pada mesin perekomendasi"
date: 2016-10-02
tags: [machine learning]
comments: false
share: true
---

pada dunia offline (nyata), rekomendasi suatu produk dilakukan dari mulut ke mulut (*words of mouth*),   namun, pada dunia online, konsep words of mouth ditirukan oleh mesin, caranya adalah mencari kemiripan antara 2 pengguna, semakin mirip 1 pengguna dengan pengguna yang lain, maka kemungkinan besar barang yang akan mereka cari di suatu e-comerce akan sama. 

####Similarity score 

ada beberapa cara yang bisa kita lakukan untuk mengetahui seberapa besar kesamaan satu pengguna dengan pengguna yang lain, salah satunya adalah dengan menggunakan *Euclidean distance*.  

![euclidean distance](https://wikimedia.org/api/rest_v1/media/math/render/svg/dc0281a964ec758cca02ab9ef91a7f54ac00d4b7)

> In mathematics, the Euclidean distance or Euclidean metric is the "ordinary" (i.e. straight-line) distance between two points in Euclidean space [1]


pada mesin perekomendasi yang akan kita kembangkan kali ini, kita akan menggunakan euclidian similarity pada 1 dimensi.

![euclidean distance pada bidang 1 dimensi](https://wikimedia.org/api/rest_v1/media/math/render/svg/40acb4e3dca881674b97303ffabfae6f28e3952e)

atau dalam bentuk kode:

```
from math import (
   sqrt,
   pow
)

def euclidean_distance(a, b):
   """
   :type a: int
   :type b: int
   :rtype: float
   """
   return sqrt(pow(a-b, 2)+pow(b-a, 2))
```
-----------------
```
In [34]: euclidean_distance(2,1)
Out[34]: 1.4142135623730951
```
(bersambung)

referensi:

* [1] [wikipedia](https://en.wikipedia.org/wiki/Euclidean_distance#Squared_Euclidean_distance)

kode: [github.com/vickydasta/ahdh](http://github.com/vickydasta/ahdh)
