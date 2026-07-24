---
title: "Model Prediksi Harga Penutupan di Bursa Efek Indonesia dengan Menggunakan Bidirectional LSTM dan HIVE-COTE"
collection: publications
category: manuscripts
permalink: # none
excerpt: "Penelitian ini membandingkan model Bi-LSTM dan HIVE-COTE 2.0 dalam memprediksi klasifikasi harga penutupan saham menggunakan fitur-fitur hasil feature engineering, dan menyimpulkan bahwa HIVE-COTE 2.0 lebih unggul dengan $$F_1$$-score 98,7% serta merekomendasikan persentase perubahan harga sebagai fitur paling berpengaruh."
date: 2025-01-01
venue: 'Jurnal Tekno Kompak'
paperurl: 'https://doi.org/10.33365/jtk.v19i1.4599'
citation: # none
bibtexurl: "https://maranathaedu-my.sharepoint.com/:u:/g/personal/hendra_bunyamin_it_maranatha_edu/Ect9Lx0hiBVIqNpUGE0_KdcBq0ouo0Nf8LthdRxRHZdxtQ?e=VxhKdC"
---

Memprediksi harga penutupan saham merupakan masalah yang menantang karena natur bursa saham yang volatil dan tidak linier. Adanya teknologi machine learning telah mendorong metode prediksi yang lebih akurat untuk data deret waktu, terutama dalam konteks prediksi harga saham. Prediksi yang akurat memberikan manfaat dalam bidang finansial, yaitu memudahkan investor dalam menganalisis pasar dan meminimalisir risiko. Model Bidirectional Long Short-Term Memory (Bi-LSTM) yang merupakan perkembangan dari Long Short-Term Memory (LSTM) dan Hierarchical Vote Collective of Transformation-based Ensembles 2.0 (HIVE-COTE 2.0) merupakan dua pendekatan yang digunakan dalam penelitian untuk memprediksi klasifikasi harga penutupan saham. Dataset yang digunakan adalah dataset harga saham yang berisikan informasi-informasi, seperti tanggal, harga pembukaan, harga tertinggi, harga terendah, harga penutupan, harga penutupan yang disesuaikan, dan volume penjualan. Kemudian, informasi-informasi ini dikenakan proses features engineering untuk memperoleh date/time features, lag features, rolling-window features, dan expanding-window features. Training model Bi-LSTM dan HIVE-COTE 2.0 dari fitur-fitur tersebut dan proses hyperparameter tuning dua model tersebut memberikan hasil evaluasi bahwa model HIVE-COTE 2.0 dengan performa $$F_1$$-score 98,7% lebih baik dalam memprediksi klasifikasi harga saham dibandingkan dengan Bi-LSTM. Selanjutnya, analisis model untuk mencari fitur yang paling berpengaruh dengan dan tanpa feature engineering dilakukan  dan fitur yang paling berpengaruh adalah persentase perubahan harga pada akhir transaksi pada satu hari. Hasil penelitian ini merekomendasikan HIVE-COTE 2.0 sebagai model prediksi karena keakuratannya dan fitur persentase perubahan harga sebagai fitur yang paling mempengaruhi hasil prediksi.
