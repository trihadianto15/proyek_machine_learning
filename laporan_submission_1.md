# Laporan Proyek Machine Learning - Tri Hadianto

## Domain Proyek

Kanker adalah penyakit di mana sel-sel tubuh berkembang
secara abnormal dan tidak terkendali. Tubuh kita terdiri dari
milyaran sel-sel, seperti batu bata yang menyusun struktur rumah.
Setiap organ tubuh, seperti jantung, paru-paru, otot, tulang dan
kulit memiliki struktur sel yang berbeda-beda

**Rubrik/Kriteria Tambahan (Opsional)**:
- Jelaskan mengapa dan bagaimana masalah tersebut harus diselesaikan
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
- Format Referensi dapat mengacu pada penulisan sitasi [IEEE](https://journals.ieeeauthorcenter.ieee.org/wp-content/uploads/sites/7/IEEE_Reference_Guide.pdf), [APA](https://www.mendeley.com/guides/apa-citation-guide/) atau secara umum seperti [di sini](https://penerbitdeepublish.com/menulis-buku-membuat-sitasi-dengan-mudah/)
- Sumber yang bisa digunakan [Scholar](https://scholar.google.com/)

## Business Understanding
Pada bagian ini, kamu perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements
Menjelaskan pernyataan masalah latar belakang:

- Bagaimana pengaruh faktor gaya hidup terhadap tingkat keparahan kanker pasien? 
- Apakah faktor genetik dan lingkungan memiliki hubungan yang signifikan terhadap risiko kanker?

### Goals
Menjelaskan tujuan dari pernyataan masalah:

- Melihat faktor gaya hidup apa yang menyebabkan keparahan pada kanker 
- Seberapa berpengaruh genetik dan lingkungan terhadap risiko kanker

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Menggunakan 3 algoritma yaitu, RandomForest, K-NN, dan AdaBoost

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [Kaggle](https://www.kaggle.com/datasets/rishidamarla/cancer-patients-data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- index: Nomor urut dari data.
- Patient Id: ID unik setiap pasien
- Age: Usia pasien.
- Gender: Jenis kelamin pasien.
- Air Pollution: Paparan terhadap polusi udara.
- Alcohol use: Konsumsi alkohol.
- Dust Allergy: Riwayat alergi debu.
- OccuPational Hazards: Risiko yang terkait dengan pekerjaan.
- Genetic Risk: Risiko genetik yang diturunkan dari keluarga.
- chronic Lung Disease: Riwayat penyakit paru-paru kronis.
- Balanced Diet: Pola makan sehat atau tidak.
- Obesity: Kondisi berat badan berlebih.
- Smoking: Riwayat merokok aktif.
- Passive Smoker: Paparan asap rokok secara pasif (perokok pasif).
- Chest Pain: Nyeri dada.
- Coughing of Blood: Batuk berdarah.
- Fatigue: Kelelahan.
- Weight Loss: Penurunan berat badan.
- Shortness of Breath: Sesak napas.
- Wheezing: Bunyi mengi saat bernapas.
- Swallowing Difficulty: Kesulitan menelan.
- Clubbing of Finger Nails: Perubahan bentuk kuku jari (tanda penyakit paru).
- Frequent Cold: Sering mengalami flu/pilek.
- Dry Cough: Batuk kering.
- Snoring: Mendengkur saat tidur.
- Level: Tingkat keparahan kanker (misalnya: Low, Medium, High).

**Rubrik/Kriteria Tambahan (Opsional)**:
- Dataset berjumlah 1000 baris dan 26 kolom dengan tipe data int dan object.
- Dataset tidak memiliki missing value dan duplikat, jadi dataset bisa langsung digunakan untuk penelitian.
- Dataset tidak mempunyai data oulier
- Melihat distribusi tingkat keparahan kanker dengan variabel lain. 

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.
- Menghapus fitur 
- Encoding
- Data split

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menghapus fitur patient Id dan index karena tidak terlalu relevan dengan apa yang ingin saya capai 
- Menghapus fitur level(tingkat keparahan kanker) karena akan dilakukan encoding dengan mengubah data menjadi numerik.
- Kolom level diubah menggunakan label encoder, karena nilai dari kolom tersebut lebih dari 2, yaitu low, medium, high dan diubah menjadi 1 = low, 2 = medium, dan 0 = high.
- Kemudian, dataset dibagi menjadi 80% data latih dan 20% data validasi.
  

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.
- Menggunakan Random Forest
- Menggunakan KNN
- Menggunakan Ada Boost

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Random Forest adalah algoritma ensemble berbasis pohon keputusan yang membangun banyak decision tree dan menggabungkan hasilnya (melalui voting atau rata-rata) untuk membuat prediksi yang lebih akurat dan stabil. Menggunakan 50 n_estimators dan random state 42.
- KNN adalah algoritma yang mengklasifikasikan data berdasarkan kemiripan dengan data tetangga terdekatnya. Menggunakan 50 n_neighbors.
- AdaBoost adalah algoritma boosting yang membentuk model kuat dari banyak model lemah, dengan menyesuaikan bobot data yang sulit diklasifikasikan secara benar oleh model sebelumnya. Menggunakan learning_rate 0.05 dan random_state 42.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.
Menggunakan metrik **akurasi, precision, recall, dan F1 score** dan **Confusion metrik**.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- **Akurasi** adalah ukuran dari berapa banyak prediksi model yang benar, baik itu positif maupun negatif, dibandingkan dengan total jumlah data.
- **Precision** mengukur seberapa banyak dari prediksi positif yang benar-benar positif. Jadi, ini menunjukkan keakuratan prediksi positif.
- **Recall** mengukur seberapa banyak data yang sebenarnya positif berhasil ditemukan oleh model. Ini menunjukkan kemampuan model dalam menangkap kasus positif.
- **F1 Score** adalah rata-rata harmonik dari presisi dan recall. Ini digunakan untuk menyeimbangkan keduanya, apalagi jika datamu tidak seimbang.
- **Confusion matrix** adalah tabel yang digunakan untuk mengevaluasi kinerja model klasifikasi. Tabel ini menunjukkan jumlah prediksi yang benar dan salah yang dibuat oleh model.
- 
- Menjelaskan hasil proyek berdasarkan metrik evaluasi
- Akurasi dari evaluasi model random forest menunjukan hasil sebesar 1.00
- Akurasi dari evaluasi model Knn menunjukan hasil sebesar 0.95
- Akurasi dari evaluasi model Ada Boost menunjukan hasil sebesar 0.99

- Dari hasil akurasi tersebut random forest menjadi model yang paling terbaik dengan akurasi mencapai 1.00
  
- **Hubungkan dengan business understanding**
Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.
