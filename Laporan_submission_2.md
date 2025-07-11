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
Sumber dataset yang digunakan [Kaggle](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset).

Daftar file dalam dataset : 
Archive:  book-recommendation-dataset.zip
  inflating: Books.csv               
  inflating: DeepRec.png             
  inflating: Ratings.csv             
  inflating: Users.csv               
  inflating: classicRec.png          
  inflating: recsys_taxonomy2.png  

Hanya menggunakan dataset Books.csv dan Ratings.csv 

Variabel-variabel pada dataset yang digunakan adalah sebagai berikut:
- ISBN(books) : Id unik buku
- Book-Title: Judul buku
- Book-Author: Nama penulis
- Year-Of-Publication: Tahun terbit
- Publisher: Nama penerbit
- Image-URL-S : Link cover buku
- Image-URL-M : Link cover buku
- Image-URL-L : Link cover buku
- User-ID: ID unik pengguna
- ISBN(ratings) : Id unik buku
- Book-Rating: Nilai rating yang diberikan pengguna ke buku

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menggunakan dataset books dan ratings
- Dataset berjumlah 271360 baris untuk dataset books dengan tipe data object
- Dataset berjumlah 1149780 baris untuk data ratings dengan tipe data int dan object
- Dataset books memiliki missing value pada fitur publisher, book-author dan image-url-l
- Dataset ratings tidak memiliki missing value
- Dataset books tidak memiliki duplikat pada fitur ISBN
- Dataset books memiliki jumlah duplikat sebanyak 29225 pada fitur Book-Title
- Dataset books memiliki jumlah duplikat sebanyak 169337 pada fitur Book-Author
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
- Pemisahan fitur(x) dan target(y)
- Menormalisasi fitur rating
- Split dataset

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Merge fitur 'ISBN', 'Book-Author', 'Book-Title' pada dataset books dengan ratings, dilakukan agar data lebih rapih
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
- Pemisahan fitur dan target
- Normalisasi fitur targer(rating) menjadi rentang 0 dan 1
- membagi data menjadi 80% train dan 20% validasi

## Modeling
- Menggunakan Content based filtering
- Menggunakan User based collaborative

**Rubrik/Kriteria Tambahan (Opsional)**: 

- Content base filtering bekerja dengan merekomendasikan item berdasarkan kemiripan konten antara item yang disukai pengguna dengan item lain. 
- Cosine digunakan untuk melihat kemiripan antar vektor
- User base collaborative bekerja dengan merekomendasikan item berdasarkan kesamaan antar pengguna.
- RecommenderNet adalah model neural network sederhana berbasis embedding yang belajar dari interaksi (rating) antara user dan item.

**Top-N Rekomendasi**
- Content base filtering :

          Rekomendasi:
                                               title                author
          0  the minority report and other classic stories ...   philip k. dick
          1                                     substance mort   philip k. dick
          2                           el hombre en el castillo   philip k. dick
          3                        dr. bloodmoney (p. k. dick)   philip k. dick
          4                          clans of the alphane moon   philip k. dick
          5                                   a scanner darkly   philip k. dick
          6                             auã?â?enseiter. roman.     dick francis
          7                                             reflex     dick francis
          8                                        second wind     dick francis
          9                  funny stories (walker treasuries)  dick king-smith


- User base collaborative :

          Rekomendasi Buku untuk User 127539
          Total rekomendasi ditampilkan: 10
          --------------------------------------------------------------------------------------------------------------
          No   Judul                                              Penulis                        Rating Prediksi
          --------------------------------------------------------------------------------------------------------------
          1    sacred choices: the right to contraception and a   daniel c. maguire              0.71           
          2    adolphe                                            benjamin constant              0.70           
          3    unknown woman: a journey to self-discovery         alice koller                   0.69           
          4    jamestown's american portraits: corn raid: a sto   james lincoln collier          0.69           
          5    blackwood farm (rice, anne, vampire chronicles.)   anne rice                      0.68           
          6    the russian revolution (opus s.)                   sheila fitzpatrick             0.68           
          7    words for murder perhaps                           edward candy                   0.68           
          8    cruising for murder                                susan sussman                  0.68           
          9    rightfully mine                                    doris mortman                  0.68           
          10   pas de deux.                                       philippe djian                 0.68   


## Evaluation
- Content based filltering Menggunakan : 
Precision@K

- User Based Collaborative menggunakan : 
Loss dan RMSE

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Content based filltering :
- Precision@K adalah metrik evaluasi yang digunakan untuk mengukur ketepatan sistem rekomendasi pada K item teratas yang direkomendasikan.
- Akurasi = Jumlah buku yang direkomendasikan dari penulis tersebut / Total buku oleh penulis tersebut
  
              Hasil evaluasi Precision@K: 0.60


- User based collaborative : 
- Loss mengukur seberapa jauh prediksi model dari nilai sebenarnya.
- Root Mean Squared Error adalah akar dari MSE (loss).
  
              Hasil nya sebesar : 
              loss: 0.0401
              root_mean_squared_error: 0.1689
              val_loss: 0.1720
              val_root_mean_squared_error: 0.3987
  

  Dari hasil Precision@k dan loss, RMSE tidak ada hasil terbaik, karena mengukur hal yang berbeda
  - loss dan RMSE mengukur seberapa akurat model dalam memprediksi skor, sedangkan
  - Precision@k mengukur seberapa baik model dalam memilih item yang revelan.

 
   **Hubungan dengan business understanding**
- Menggunakan Content base filtering dan User base collaborative berhasil menjawab setiap problem statements, goals.
- Berhasil membuat atau mengembangkan sistem rekomendasi buku untuk pemula berdasarkan referensi pengguna dan pengguna lain.

