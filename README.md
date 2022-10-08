# Laporan Proyek Machine Learning - Muhammad Zhafran Ghaly

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
- Predictive analytics ini dapat menjadi acuan untuk para investor yang baru maupun yang sudah expert dalam bidang investasi.
- Dengan melakukan training model pada beberapa algoritma yang digunakan dan kita akan mendapat hasil dan kemudian memilih yang terbaik.
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

* Seletah semua dilalui kita bisa menambahkan Hyperparameter tuning menggunakan teknik Grid Search agar model dapat berjalan dalam performa terbaik dan mendapatkan hasil yang terbaik pula.

## Data Understanding
Pada proyek ini saya mengambil dataset publik dari Kaggle yang berjudul Dataset Saham Indonesia / Indonesia Stock Dataset didalam dataset tersebut saya mengambil pada folder /daily/BBNI.csv 
(https://www.kaggle.com/datasets/muamkh/ihsgstockdata/code).

Dataset yang digunakan memiliki format .csv, mempunyai total 4431 data dengan 7 kolom diantaranya (Date, Open, High, Low, Close, Adj Close dan Volume), berikut merupakan penjelasan masing masing kolom:
- **timestamp**: tanggal mulai dari open, low, high, close dan volume
- **open** : opening price per day
- **low** : Lowest price per day
- **high** : Highest price per day
- **close** : Closing price per day
- **volume** : Volume Transaction price per day

### Eksploratory Data Analysis
Berikut adalah data seperti korelasi, outliner, dan analisis Univariate dan Multivariate anailisis
- Menangani Outliner
Dibawah ini adalah visualisasi dari data numerik yang menampilkan outliner hanya pada fitur ***volume***.

![outliner_before](https://github.com/Cherzs/Predictive-Analytics/blob/c95401a7c391a8921a0531ee5582aa3054303760/Image/before%20Outliner.png)
Untuk menangani outlier dengan menggunakan IQR Method yaitu dengan menghapus data yang berada diluar IQR yaitu antara **25%** dan **75%**. Sampel data yang sudah clean adalah (4444, 5).
Berikut proses penanganan outliner

![outliner_after](https://github.com/Cherzs/Predictive-Analytics/blob/c95401a7c391a8921a0531ee5582aa3054303760/Image/after%20Outliner.png)

- Unvariate Analysis
Kita fokus pada kolom close

![unvariate](https://github.com/Cherzs/Predictive-Analytics/blob/c95401a7c391a8921a0531ee5582aa3054303760/Image/U.png)

- Multivariate Analysis
Berikut adalah hasil dari multivariate analisis. Bisa kita lihat pada kolom Close dengan kolom lainya, bisa disimpulkan bahwa close memiliki korelasi yang cukup kuat terhadap kolom**High, Open, Low, dan Close**. Sementara Close terhadap kolom **Volume** memiliki korelasi yang kurang kuat. 

![multivariate](https://github.com/Cherzs/Predictive-Analytics/blob/c95401a7c391a8921a0531ee5582aa3054303760/Image/M.png)

- Korelasi Heatmap
Untuk memperjelas korelasi kita menggunakan heatmap dengan menggunakan library Seaborn. Disini kolom Close memiliki korelasi positif yang kuat terhadap setiap fitur yang ditandakan dengan angka **1** yang berarti kuat dan bisa kita gunakan sebagai Dependent variable terkecuali pada fitur **Volume**.

![heatmap](https://github.com/Cherzs/Predictive-Analytics/blob/c95401a7c391a8921a0531ee5582aa3054303760/Image/Heatm.png)

## Data Preparation
Tahap berikutnya dalam pemrosesan data:

### Melakukan Penanganan Missing Value
Tahapan yang paling awal adalah menghilangkan Missing value pada dataset. Kebetulan dataset yang digunakan tidak memiliki nilai yang hilang/missing value. Namun jika anda memilki missing value, maka penanganan yang digunakan adalah menghapus atau mengisisi nilai hilang dengan nilai rata rata menggunakan library Simpleimputer.

### Splitting dataset
Pada tahap ini dataset yang tadi kita sudah diolah kemudian kita bagi menjadi data train dan data test. Dengan ratio yang bisa kita atur sendiri sesuai kebutuhan, ratio yang digunakan pada proyek ini sebesar **80:20**, dimana **80%** merupakan data train dan **20%** merupakan data test yang sudah dibagi menggunakan librari train_test_split dari Sklearn.

### Menghapus fitur yang tidak diperlukan 
setelah diolah ternyata kita hanya memerlukan kolom **high, low, ope dan close**. Maka drop  kolom **Volume** untuk kasus ini.

### Normalization Data
Pada tahap ini kita menggunakan MinMaxScaler supaya hasil yang maximal dan mentransformasi data dalam rentan angka **0** hingga **1**.

## Modeling
Pada tahap ini kita menggunakan 3 algoritma  yaitu _Support Vector Regression, Gradient Boost dan KNN_.

### Support Vector Regression 

Support Vector Machines (SVMs) terkenal dalam masalah klasifikasi. Namun, penggunaan SVM dalam regresi tidak didokumentasikan dengan baik. Jenis model ini dikenal sebagai Support Vector Regression (SVR). Pada SVM, algoritma tersebut berusaha mencari jalan terbesar yang bisa memisahkan sampel dari kelas berbeda, sedangkan SVR mencari jalan yang dapat menampung sebanyak mungkin sampel di jalan. Berikut merupakan Hyper Parameter yang digunakan dalam model: 
 - kernel : Hyperparameter ini biasa digunakan untuk menghitung kernel pada matriks sebelumnya, pada model ini menggunakan kernel **"rbf"** dikarenakan konsep dari kernel ini yang paling banyak digunakan dalam klasifikasi data yang tidak dapat dipisahkan secara linier. 
 - C : Hyperparameter ini biasa digunakan untuk menukar klasifikasi yang benar dari contoh training terhadap maksimalisasi margin fungsi keputusan, pada model ini kita gunakan nilai **1000**.
 - gamma : Hyperparameter ini biasa digunakan untk menetukan seberapa jauh pengaruh satu contoh pelatihan mencapai, dengan nilai rendah berarti jauh dan nilai tinggi berarti dekat, dalam model ini kita berikan nilai gamma **0.003**.

#### kelebihan
- Lebih efektif pada data dimensi tinggi (data dengan jumlah fitur yang banyak)
- Memori lebih efisien karena menggunakan subset poin pelatihan

#### Kekurangan 
- Sulit dipakai pada data skala besar

### Gradient Boost

Gradient Boosting adalah algoritma boosting yang populer. Dalam peningkatan gradien, setiap prediktor mengoreksi kesalahan pendahulunya. Berbeda dengan Adaboost, bobot instance pelatihan tidak diubah, sebagai gantinya, setiap prediktor dilatih menggunakan kesalahan residual dari pendahulunya sebagai label. Untuk hyperparameter yang digunakan pada model ini ada 3 yaitu: 
- learning_rate : Hyperparameter training yang digunakan untuk menghitung nilai koreksi bobot padded pada waktu proses training. Umumnya nilai learning rate berkisar antara **0** hingga **1**, dalam fitting model ini menggunakan nilai **0.01**.
- n_estimators : Jumlah tahapan boosting yang akan dilakukan pada model, pada model ini menggunakan nilai **1000** tahapan.
- criterion : Hyperparameter yang biasanya digunakan untuk menemukan fitur dan ambang batas optimal dalam membagi data, pada model ini menggunakan "**squared_error**" dimana untuk kesalahan kuadrat rata rata.

#### kelebihan
- Hasil pemodelan yang lebih akurat
- Model yang stabil dan lebih kuat (robust)
- Dapat digunakan untuk menangkap hubungan linear maupun non linear pada data

#### Kekurangan 
- Pengurangan kemampuan interpretasi model
- Waktu komputasi dan desain tinggi
- Tingkat kesulitan yang tinggi dalam pemilihan model

### K-Nearest Neighbors (KNN)

Algoritma KNN merupakan algoritma klasifikasi yang bekerja dengan mengambil sejumlah K data terdekat (tetangganya) sebagai acuan untuk menentukan kelas dari data baru. Algoritma ini mengklasifikasikan data berdasarkan similarity atau kemiripan atau kedekatannya terhadap data lainnya. Algoritma ini dapat digunakan untuk klasifikasi dan regresi. Untuk hyperparameter yang digunakan pada model ini hanya 1 yaitu :

- n_neighbors : Parameter yang menunjukan Jumlah tetangga untuk yang diperlukan untuk menentukan letak data baru, pada model ini kita gunakan nilai **6** pada hyperparameter n_neighbour karena kita hanya ingin 6 titik yang akan digunakan untuk menentukan letak baru.

#### kelebihan
- Dapat menerima data yang masih noisy
- Sangat efektif apabila jumlah datanya banyak
- Mudah diimplementasikan

#### Kekurangan 
- Sensitif pada outlier
- Rentan pada fitur yang kurang informatif

#### Pemakaian Algortima 
Untuk proyek kali ini kita akan menggunakan model K-Nearest Neighbors karena memiliki error (0.00001) yang paling sedikit daripada model yang lain. Namun tidak bisa dipungkiri model dari Gradient Boosting juga memiliki error (0.000011) yang hampir seperti KNN.

## Evaluation
Pada tahap evaluasi ini metrik yang digunakan adalah Mean Squared Error (MSE), dimana dia akan mengukur seberapa dekat garis pas dengan titik pada data. 

![mse_rumus](https://github.com/Cherzs/Predictive-Analytics/blob/87300f46f089ad222576eb4e58c1fe4299137b79/Image/Rumus%20MSE.jpg)

Perhitungan dari MSE dimana penjelasan dari variablenya:
- Y ' = Nilai Prediksi 
- Y   = Nilai Sebenarnya
- n   = Jumlah Data

Berikut hasil dari MSE model, dimana semakin kecil MSE yang diperoleh oleh model maka akan semakin optimal algortima yang digunakan.

|index|train\_mse|test\_mse|
|---|---|---|
|SVR|20\.238573880982816|55\.52692278397914|
|KNN|16\.68136160714286|51\.30848214285714|
|GradientBoosting|9\.669640985095231|36\.33649890753796|

Plot Visualisasi MSE pada model
Berikut hasil plot dari model terhadap beberapa algoritma yang digunakan, terlihat algoritma yang sangat cocok untuk digunakan adalah Gradient Boosting.

![mse_plot](https://github.com/Cherzs/Predictive-Analytics/blob/87300f46f089ad222576eb4e58c1fe4299137b79/Image/MSE.png)

Hasil akurasi MSE model
Kita bisa melihat akurasi dari setiap algortima yagn digunakan dan kita bisa simpulkan bahwa KNN atau Gradient Boost merupakan algortma paling optimal untuk model. 

|index|Accuracy \(%\)|
|---|---|
|SVR|99\.61126168219803|
|KNN|99\.64079455447617|
|Gradient Boost|99\.74561188065324|

Pada proyek ini semua model berjalan dengan sangat baik dan maksimal dan hanya terdapat selisih sangat kecil diantara ketiganya akan tetapi kita akan memilih model yang paling tinggi akurasinya, alhasil Gradient Boost adalah algortima yang memiliki nilai tertinggi.

### Forecasting
Pada tahap ini saya akan mencoba memprediksi menggunakan algoritma yang kita pili diatas yaitu Gradient Boost dalam kurun waktu 30 hari kedepan.
Berikut prediksi harga yang akan datang dalam kurun waktu 30 hari kedepan yang sudah diprediksi menggunakan Gradient Boost yang telah kita pilih sebagai algoritma yang paling optimal.

|index|close|Forecast|
|---|---|---|
|2022-09-26 00:00:00|264\.0|NaN|
|2022-09-27 00:00:00|262\.0|NaN|
|2022-09-28 00:00:00|264\.0|NaN|
|2022-09-29 00:00:00|260\.0|NaN|
|2022-09-30 00:00:00|256\.0|NaN|
|0|NaN|847\.0|
|1|NaN|847\.0|
|2|NaN|847\.0|
|3|NaN|847\.0|
|4|NaN|847\.0|
|5|NaN|847\.0|
|6|NaN|847\.0|
|7|NaN|847\.0|
|8|NaN|847\.0|
|9|NaN|847\.0|
|10|NaN|847\.0|
|11|NaN|847\.0|
|12|NaN|847\.0|
|13|NaN|847\.0|
|14|NaN|847\.0|
|15|NaN|847\.0|
|16|NaN|847\.0|
|17|NaN|847\.0|
|18|NaN|847\.0|
|19|NaN|847\.0|
|20|NaN|847\.0|
|21|NaN|847\.0|
|22|NaN|847\.0|
|23|NaN|847\.0|
|24|NaN|848\.6666666666666|
|25|NaN|847\.0|
|26|NaN|847\.0|
|27|NaN|847\.0|
|28|NaN|847\.0|
|29|NaN|847\.0|


### Referensi :
* Adipta Martulandi(Oct 6, 2019).Tuning Hyperparameters Logistic Regression Menggunakan Grid Search #UcupStory, from https://medium.com/@adiptamartulandi/tuning-hyperparameters-logistic-regression-menggunakan-grid-search-ucupstory-fb1ab9db082a
* Mekari (2022). Mengenal Metode Forecasting Untuk Kepentingan Bisnis Anda from https://www.jurnal.id/id/blog/mengenal-metode-forecasting-untuk-kepentingan-bisnis-anda/.
* Fakultas Hukum Universitas Medan Area (June 15, 2020),Normalisasi Database from https://hukum.uma.ac.id/2022/06/15/normalisasi-database/#:~:text=Atau%20pengertian%20singkatny%2C%20Normalisasi%20Databse,database%20yang%20dibuat%20berkualitas%20baik.
* Tom Sharp(Mar 4, 2020), An Introduction to Support Vector Regression (SVR) from https://towardsdatascience.com/an-introduction-to-support-vector-regression-svr-a3ebc1672c2
* Abdul Muiz Khalimi(January, 2021) Cara Hitung RMSE , MSE, MAPE, dan MAE Dengan Excel from https://www.pengalaman-edukasi.com/2021/01/cara-menghitung-rmse-root-mean-square.html
* ngodingdata, Python Pandas : Cara Menangani Missing Value, from https://ngodingdata.com/python-pandas-cara-menangani-missing-value/
* GeeksForGeeks(2 Sep, 2020) ML – Gradient Boosting from https://www.geeksforgeeks.org/ml-gradient-boosting/
* Lutfia Afifah, Algoritma K-Nearest Neighbor (KNN) untuk Klasifikasi from https://ilmudatapy.com/algoritma-k-nearest-neighbor-knn-untuk-klasifikasi/

