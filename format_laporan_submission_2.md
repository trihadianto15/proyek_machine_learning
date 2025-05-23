# Laporan Proyek Machine Learning - Tri Hadianto

## Project Overview

Banyak orang ingin mulai membaca buku untuk menambah wawasan atau sebagai kegiatan positif di waktu luang. Namun, tidak sedikit yang justru merasa kebingungan saat harus memilih buku pertama yang sesuai dengan minat mereka. Tanpa referensi yang jelas atau pengalaman sebelumnya, proses memilih buku bisa menjadi hambatan awal yang membuat semangat membaca menurun.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Masalah yang harus diselesaikan :
  Tanpa rekomendasi atau panduan yang tepat, mereka cenderung merasa tidak yakin, berujung pada kehilangan minat untuk mulai membaca. Hal ini menjadi tantangan besar dalam upaya meningkatkan budaya literasi, terutama di kalangan generasi muda.
  
- bagaimana cara menyelesaikannya :
  Mengumpulkan data minat pengguna dan Menganalisis karakteristik buku

## Business Understanding

Pada bagian ini, Anda perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah:
- Tidak adanya pengalaman atau referensi membuat pembaca pemula kesulitan menentukan buku yang tepat untuk dibaca.
- Belum tersedia sistem rekomendasi yang dirancang khusus untuk membantu pembaca pemula menemukan buku yang cocok secara personal.

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Untuk membantu pembaca pemula yang tidak memiliki pengalaman atau referensi dalam memilih buku, dapat dikembangkan sistem rekomendasi yang memberikan saran buku berdasarkan preferensi awal yang sederhana.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Menggunakan content based filtering dan user based collaborative filtering
      
## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [Kaggle](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset)).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- ISBN : Id unik buku
- Book-Title: Judul buku
- Book-Author: Nama penulis
- Year-Of-Publication: Tahun terbit
- Publisher: Nama penerbit
- User-ID: ID unik pengguna
- Book-Rating: Nilai rating yang diberikan pengguna ke buku
- Location: Lokasi pengguna
- Age: Usia pengguna

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
