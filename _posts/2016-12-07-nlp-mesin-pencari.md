---
layout: post
title: "nlp pada mesin pencari"
description: ""
date: 2016-12-07
tags: []
comments: true
share: true
---


nlp pada mesin pencari

pada umumnya, web app yang menggunakan fitur pencarian hanya menggunakan klausa `LIKE "%hal%"` dari SQL.
klausa LIKE pada database SQL seperti MySQL sendiri berfungsi seperti grep pada unix,

misal, pada database d terdapat tabel t dengan row r yang berisi nama produk n,
dengan menggunakan pattern matching LIKE, query yang digunakan pada umumnya seperti berikut:

`SELECT n FROM t WHERE n LIKE "%es%"`

query diatas akan bekerja dengan yang diharapkan.

tapi, bagaimana kalau pengguna yang usil memasukkan kalimat? bukan hanya kata kunci tertentu?
seperti "ES JERUK MANG EMAN", dengan query di atas, mysql tidak akan berhasil menemukan dokumen yang tepat.

 
yaitu sebagai pencocok pola. kekurangan dari cara ini adalah pada saat query yang dimasukkan berupa kalimat "ES JERUK DINGIN MANG EMAN",
"mesin pencari" yang menggunakan klausa LIKE tidak akan berhasil mencocokkan pola query dengan dokumen, 
singkatnya, mesin pencari ini gagal.


pendekatan lain selain menggunakan cara diatas yaitu pemrosesan bahasa alami (natural language processing).
misal kita ingin mengetahui kecocokan query q dengan kalimat k. 

