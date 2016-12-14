---
layout: post
title: "nlp pada mesin pencari"
description: "catatan penelitian mesin pencari dan nlp"
date: 2016-12-07
tags: [nlp, search engine]
share: true
---

pada umumnya, web app yang menggunakan fitur pencarian hanya menggunakan klausa `LIKE "%hal%"` dari SQL.
klausa LIKE pada database SQL seperti MySQL sendiri berfungsi seperti grep pada unix,


misal, pada database d terdapat tabel t dengan row r yang berisi nama produk n,
dengan menggunakan pattern matching LIKE, query yang digunakan pada umumnya seperti berikut:

`SELECT n FROM t WHERE n LIKE "%es%"`

query diatas akan bekerja dengan yang diharapkan.

tapi, bagaimana kalau pengguna yang usil memasukkan kalimat? bukan hanya kata kunci tertentu?
seperti "ES JERUK MANG EMAN", dengan query di atas, MySQL tidak akan berhasil menemukan dokumen yang tepat.

ini dikarenakan klausa LIKE hanya berfungsi sebagai pencocok pola. kelemahan dari cara ini adalah pada saat query yang dimasukkan berupa kalimat "ES JERUK DINGIN MANG EMAN",
"mesin pencari" yang menggunakan klausa LIKE tidak akan berhasil mencocokkan pola query dengan dokumen,
singkatnya, metode pencarian dokumen dengan cara ini gagal.


selain menggunakan klausa LIKE, kita sebenarnya bisa menggunakan teknik informatin retreival dan natural language processing pada mesin pencari.
misal kita ingin mengetahui kecocokan query q dengan kalimat k. kita ingin mengetahui seberapa cocok
teks "ini ibu budi" dengan "ini budi".

---

tulisan ini belum selesai :)
