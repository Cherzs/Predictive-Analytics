# Laporan Proyek Machine Learning - Nama Anda

## Domain Proyek

Saya memilih domain Ekonomi dan bisnis untuk proyek kali ini dengan judul **Predictive Analytics of Bank BNI(BBNI) stock**

### Latar Belakang
Investasi Saham adalah salah satu investasi yang dipilih oleh
seseorang untuk menginvestasikan kekayaannya selain asset rill yang
berupa emas, berlian ataupun tanah. Saham merupakan surat berharga yang
menunjukkan bukti kepemilikan invidu maupun institusi dalam suatu
perusahaan. Seorang investor dapat memilih jenis investasi ini karena dapat
memberikan keuntungan ekonomis dan non ekonomis bagi pemegang
saham.

Sejalan dengan berkembangnya perekonomian, banyak perusahaan
yang melakukan ekspansi usaha. Untuk tujuan tersebut maka perusahaan
memerlukan dana yang relatif besar. Untuk memenuhi kebutuhan dana
tersebut tentunya diperlukan usaha untuk mencari tambahan dana untuk di
suntikkan ke dalam perusahaan sebagai pengganti ataupun sebagai
penambah dana yang sedang dijalankan ataupun untuk pengembangan dan
perluasan bidang usaha. Salah satu aspek yang di nilai oleh masyarakat
dalam ivestasi adalah kinerja keuangan perusahaan yang diukur dari laporan
keuangan perusahaan. Oleh karena itu perusahaan akan selalu
mempublikasikan laporan keuangannya agar para calon investor dapat
mengetahui bagaimana kinerja dan prospek perusahaan tersebut ke depan. Namun dengan untuk kemudahan investor ini maka saya membuat Predictive Analytics of Bank BNI(BBNI) stock yang akan membantu investor yang baru terjun kedalam dunia saham untuk menjadi patokan berinvestasi dengan menggunakan Machine Learning secara berkelanjutan atau Time Series Forecasting/Regression

Metode Forecasting adalah salah satu metode untuk melakukan perencanaan serta pengendalian produksi dalam dunia akuntansi. Selain itu, forecasting juga didefinisikan sebagai alat bantu untuk melakukan perencanaan yang efektif dan efisien. Dalam Machine Learning Forecasting adalah bagian dari teknik yang dapat digunakan untuk mengkalkulasi apa yang akan terjadi dalam 1 bulan kedepan bahkan beberapa tahun kedepan
## Business Understanding
### Problem Statements
Berikut permasalahan yang didapat da:
- Apakah Predictive analytics ini bisa menjadi acuan untuk investasi, kemudian bagaimana cara analisis harga dari Bank BNI(BBNI)?
- Bagaimana memilih algoritma yang sesuai dan melatih model untuk hasil yang terbaik untuk data ini?
- Bagaimana menganalisis dan memprediksi harga pada Bank BNI(BBNI) menggunakan teknik Forecasting dalam Time Series?
- Apakah hanya Bank BNI(BBNI) yang dapat diprediksi dalam kasus ini?

### Goals

Tujuan:
- Predictive analytics ini dapat menjadi acuan untuk para investor yang baru maupun yang sudah bisa menguasai teknikal anilisis.
- Dengan melakukan training model pada beberapa algoritma yang digunakan dan kita akan mendapat hasil dan kemudian memilih yang terbaik
- Setelah mendapatkan hasil Training yang diinginkan, maka kita bisa menerapkannya pada Bank BNI yang akan kita investasikan dan memliki acuan untuk berinvestasi pada perusahaan tersebut.
- Bukan hanya Bank BNI(BBNI), semua bank/perusahaan bisa kita analisis dan prediksikan jika kita ingin menganalisis market yang ada di dunia ataupun di dalam region kita.


### Solution statements
Solusi yang bisa dilakukan agar goals dapat terpenuhi sebagai berikut :
* Melakukan analisa dan eksplorasi lebih jauh pada dataset kemudian memvisualisasikanya agar mendapat gambaran/hasil yang kuat. Berikut merupakan tahapan yang bisa mewakili solution statement:
  - Menangani missing value/data hilang pada dataset yang digunakan.
  - Jika terdapat outliner kita dapat menganganinya dengan metode IQR dimana outliner yang ada akan hilang.
  - Melakukan Normalization pada dataset sehingga dipastikan bahwa dataset yang kita gunakan berkualitas baik.
  - Membuat model regresi untuk prediksi bilangan kontinua pada saham.

* Berikut merupakan list algortima yang dicoba dalam model:
  - K-Nearest Neighbors (KNN)
  - Support Vector Machine (Support Vector Regression)
  - Boosting Algorithm (Gradient Boosting Regression)

* Seletah semua dilalui kita bisa menambahkan Hyperparameter tuning agar model dapat berjalan dalam performa terbaiknya.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

