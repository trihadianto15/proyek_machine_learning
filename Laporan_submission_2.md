 # Laporan Proyek Machine Learning - Tri Hadianto

## Project Overview

Banyak orang ingin mulai membaca buku untuk menambah wawasan atau sebagai kegiatan positif di waktu luang. Namun, tidak sedikit yang justru merasa kebingungan saat harus memilih buku pertama yang sesuai dengan minat mereka. Tanpa referensi yang jelas atau pengalaman sebelumnya, proses memilih buku bisa menjadi hambatan awal yang membuat semangat membaca menurun.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Masalah yang harus diselesaikan :
  Tanpa rekomendasi atau panduan yang tepat, mereka cenderung merasa tidak yakin, berujung pada kehilangan minat untuk mulai membaca. Hal ini menjadi tantangan besar dalam upaya meningkatkan budaya literasi, terutama di kalangan generasi muda.
  
- bagaimana cara menyelesaikannya :
  Membuat sistem rekomendasi berdasarkan buku atau author dan dengan sistem rekomendasi berdasarkan rating buku

## Business Understanding

### Problem Statements

Menjelaskan pernyataan masalah:
- Tidak adanya pengalaman atau referensi membuat pembaca pemula kesulitan menentukan buku yang tepat untuk dibaca.
- Belum tersedia sistem rekomendasi yang dirancang khusus untuk membantu pembaca pemula menemukan buku yang cocok secara personal.

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Untuk membantu pembaca pemula yang tidak memiliki pengalaman atau referensi dalam memilih buku, dapat dikembangkan sistem rekomendasi yang memberikan saran buku berdasarkan preferensi awal yang sederhana.
- Mengembangkan sistem rekomendasi buku untuk pembaca pemula dengan menggunakan dua pendekatan berbeda, yaitu berdasarkan referensi pengguna dan referensi pengguna lain.  

**Rubrik/Kriteria Tambahan (Opsional)**:
### Solution statements
- Menggunakan content based filtering dan user based collaborative filtering
      
## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [Kaggle]([https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset]).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada dataset adalah sebagai berikut:
- ISBN : Id unik buku
- Book-Title: Judul buku
- Book-Author: Nama penulis
- Year-Of-Publication: Tahun terbit
- Publisher: Nama penerbit
- Image-URL-S : Link cover buku
- Image-URL-M : Link cover buku
- Image-URL-L : Link cover buku
- User-ID: ID unik pengguna
- Book-Rating: Nilai rating yang diberikan pengguna ke buku

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menggunakan dataset books dan ratings
- Dataset berjumlah 271360 baris untuk dataset books dengan tipe data object
- Dataset berjumlah 1149780 baris untuk data ratings dengan tipe data int dan object
- Dataset books memiliki missing value pada fitur publisher, book-author dan image-url-l
- Dataset ratings tidak memiliki missing value
- Dataset books memiliki jumlah duplikat sebanyak 29225 pada fitur Book-Title
- Dataset books memiliki jumlah duplikat sebanyak 169337 pada fitur Book-Rating
- Dataset books memiliki jumlah duplikat sebanyak 271158 pada fitur Year-Of-Publication
- Dataset books memiliki jumlah duplikat sebanyak 254552 pada fitur Publisher
- Dataset ratings memiliki jumlah duplikat sebanyak 1044497 pada fitur User-ID
- Dataset ratings memiliki jumlah duplikat sebanyak 809224 pada fitur ISBN
- Dataset ratings memiliki jumlah duplikat sebanyak 1149769 pada fitur Book-Rating

## Data Preparation
- Merge dataset Books dan Ratings
- Menghapus missing value
- Menghapus duplikat
- mengubah nama header 
- Mengubah dataset menjadi lowercase
- Mengambil 10000 data dari dataset 
- Memasukan fitur ke dalam list
- Mengubah jadi dataframe
- Proses TF-IDF Vectorization
- encoding fitur user_id dan ISBN dalam indeks integer
- Membuat kolom baru 'user' dan 'book' berdasarkan data yang sudah di encode
- Menghitung jumlah user, book, nilai min max pada data dan mengubah fitur rating menjadi float
- Mengacak data
- Pemisahan fitur(x) dan target(y) dan Split dataset

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Merge fitur 'ISBN', 'Book-Author', 'Book-Title', 'Year-Of-Publication' pada dataset books dengan ratings, dilakukan agar data lebih rapih
- Menghapus missing value menggunakan perintah 'dropna'
- Menghapus duplikat dari beberapa fitur seperti User-ID, ISBN, dan Book-Title dengan perintah 'drop-duplicates'
- Mengubah nama header dari tanda hubung seperti, 'User-ID' menjadi 'user_id' atau 'Book-Title' menjadi 'book_title' dan lain-lain. 
- Mengubah fitur book_author dan book_title menjadi lowercase
- Karena data terlalu banyak, jadi saya hanya mengambil 10000 data
- Memasukan fitur ISBN, book_author, book_rating, book_title, publication ke dalam list
- Mengubah fitur dalam list menjadi dataframe untuk digunakan dalam penelitian
- Melakukan Proses TF-IDF pada fitur 'author'
- Melakukan proses encoding pada fitur user_id dan ISBN
- Membuat kolom baru 'user' dan 'book' berdasarkan data yang di encoding pada fitur user_id dan ISBN
- Mengubah fitur rating menjadi float
- Mengacak data sebelum pemisahan antara fitur dan target dan split dataset
- Pemisahan fitur dan target dan membagi data menjadi 80% train dan 20% validasi

## Modeling
- Menggunakan Content based filtering
- Menggunakan User based collaborative

**Rubrik/Kriteria Tambahan (Opsional)**: 
Untuk Content base filtering Menggunakan : 
- Cosine digunakan untuk melihat kemiripan antar vektor



Untuk User based collaborative menggunakan :
- RecommenderNet adalah model neural network sederhana berbasis embedding yang belajar dari interaksi (rating) antara user dan item. 

## Evaluation
- Content based filltering Menggunakan : 
Akurasi

- User Based Collaborative menggunakan : 
Loss dan RMSE

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Content based filltering :
- Akurasi = Jumlah buku yang direkomendasikan dari penulis tersebut / Total buku oleh penulis tersebut
  
              Hasil akurasi rekomendasi berdasarkan author: 0.20

- User based collaborative : 
- Loss mengukur seberapa jauh prediksi model dari nilai sebenarnya.
- Root Mean Squared Error adalah akar dari MSE (loss).
  
              Hasil nya sebesar : 
              loss: 0.0269
              root_mean_squared_error: 0.0962
              val_loss: 0.1759
              val_root_mean_squared_error: 0.3970

