# DogePredict - Fajar Maulana
## Domain Proyek
---
## Business Understanding
---
### Latar Belakang
Kemajuan teknologi sangat berkembang pesat, termasuk kemajuan teknologi dalam bidang ekonomi. Salah satu kemajuan spektakuler teknologi di bidang ekonomi diantaranya cryptocurrency atau uang virtual yang sedang populer. Cryptocurency memiliki banyak macam, seperto Ripple, Lisk, Ether,MaidSafeCoin, Litecoin, StorjCoinX, Ethereum, DogeCoin,Dash, Monero, Zcash, dan Bitcoin (BTC) (Brainytutorial, 2018).cryptocurrency mendorong beberapa hal pro dan juga kontra. 

Banyak sebagian besar pada orang tertarik pada sebuah hal cryptocurrency karena dilihat dari aspek teknologi, fungsionalitas, dan juga seberapa besar kesempatan untuk mendapatkan sebuah keuntungan dalam menggunakan mata uang virtual ini. mata uang yang dikeluarkan ini bukan merupakan hasil dari penciptaan dari sebuah negara, melainkan komputer jaringan kriptografi.

Dogecoin merupakan cryptocurrency yang diciptakan oleh Billy Markus dari Portland,Oregon dan Jackson Palmer dari Sydney, Australia pada tahun 2013 dengan
menggunakan maskot anjing Shiba Inu yang awalnya hanya dianggap sebagai meme coins (Chohan, 2017). Namun koin ini telah mengalami kenaikan nilai tukar sebanyk 800% pada tahun 2021. Nilai tukar Dogecoin juga sempat mengalami penurunan sebesar 20% yang justru terjadi pada saat Doge Day pada tanggal 20 April 2021 setelah sebelumnya
hype 

Pertumbuhan pasar kripto yang begitu massive membuat volatilitas harga di pasar kripto cukup tinggi sehingga membuat pasar kripto mampu menawarkan potensi keuntungan yang besara namun risiko yang dihadapi juga akan meningkat. Fluktuasi harga yang sangat tinggi menjadikan transaksi perdagangan di pasar kripto tergolong sangat spekulatif dan memiliki risiko yang sangat besar. 

Dengan berdasarkan uraian yang telah digambarkan, dengan menerapkan deep learning pada penelitian ini diharapkan dapat memprediksi harga pada pasar kripto dogecoin di masa mendatang. Sehingga mampu sebagai bahan acuan atau bahan pertimbangan para trader dalam melakukan investasi mata uang kripto.

## Business Understanding
---
### Problem Statement
* Bagaimana cara menganalisa uang kripto dogecoin di masa mendatang?
* Bagaimana cara mengolah data uang kripto sehingga dapat diolah scara baik oleh model?
* Cara membuat model deep learning sehingga dapat memprediksi harga kripto yang baik?

### Goals
* Mendapatkan analisa yang terbaik mengenai harga kripto sehingga dapat dimengerti
* Data dapat diolah dengan optimal oleh model yang telah dibuat
* Membantu para trader dalam melakukan investasi mata uang kripto dari segi analisa harga.

### Solution Statement
* Melakukan analisa pemahaman data dengan penerapan data visualisation
    * menganalisa missing value pada dataset yang digunakan
    * menganalisa korelasi antar kolom yang terdapat di dalam data
    * mengatasi outlier yang apabila terjadi pada kolom di dalam dataset
    * melakukan normalisasi data
* Membuat model regresi untuk memprediksi target yang dituju.
    * K-Nearest Neigbours
    * Support Vector Machine (SVR)
    * Random Forest
* Penerapan hyperparameter yang dikombinasikan Grid Search. Dengan cara mengkombinasikan nilai yang kita inputkan ke Hyperparameter. Hal ini bertujuan untuk model yang kita buat lebih akurat.

## Data Understanding
---

Pada proyek ini menggunakan dataset yang diambil dari Kaggle dengan Judul Cryptocurrency Historical Prices https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory
  * Pada dataset ini mengambil file data coin_Dogecoin.csv
  * Tidak ada missing values atau nilai yang kosong pada tiap kolom
  * Data terdiri atas 1 kolom bertipe data integer, 3 kolom bertipe data string, dan 6 kolom bertipe data float.
  * Data berisi 2.760 sample dan 10 kolom.

### Exploratory Data Analytics
Melakukan eksplorasi data dari dataset, sehingga kita dapat mengetahui bagaimana keadaan dataset yang akan kita gunakan.
* Outlier
Dari dataset yang digunakan, ada beberapa kolom yang memiliki outlier yang cukup banyak. seperti pada kolom High, Low, Open, Close, Volume, dan Marketcap. 
* Univariate Analysis
Berfokus pada satu variable dengan tujuan dapat diidentifikasi dan diketahui karakteristik yang dimiliki. disini kita memilih fitur/kolom Close sebagai acuan dasar dari aspek Univariate Analysis.
* Multivariate Analysis
Jika pada aspek sebelumnya kita hanya berfokus pada satu kolom saja, pada aspek ini kita akan berfokus dengan cara membandingkan dan juga mencari korelasi dari beberapa kolom dengan kolom yang menjadi acuan dasar yang sudan kita tentukan yaitu kolom Close.

# Data Preparation
---
Untuk mempermudah pelatihan pada model sehingga bisa didapatkan hasil yang baik. selanjutnya kita akan melakukan langkah - langkah sebagai berikut.
* Menghapus kolom yang tidak digunakan
Penghapusan ini diperlukan karena agar tidak menganggu proses permodelan saat dilakukan training.
* Split Dataset
Membagi dataset menjadi 2 bagian
* Data Normalization
Dalam proses ini, diperlukan transformasi data atau dengan kata lain mengubah data asli menjadi format data yang lebih efisien. Hal ini dilakukan untuk menghilangkan redundasi data.

# Modeling
Model atau Algoritma yang digunakan pada proyek ini.
## K-Nearest NEighbours
Algoritma KNN merupakan algoritma klasifikasi yang bekerja dengan mengambil sejumlah K data terdekat (tetangganya) sebagai acuan untuk menentukan kelas dari data baru. Algoritma ini mengklasifikasikan data berdasarkan kesamaan atau kemiripan atau kedekatannya terhadap data ainnya. 
    Cara kerja Algoritma KNN secara umum :
      * Tentukan jumlah tetangga (K) yang akan digunakan untuk pertimbangan penentuan kelas.
      * Hitung jarak dari data baru ke masing-masing data point pada dataset.
      * Ambil sejumlah K data dengan jarak terdekat, kemudian tentukan kelas dari data baru tersebut.
## SVM (SVR)
Algoritma supervised learning yang berguna untuk memprediksi dari nilai kontinu. tujuan dasarnya digunakan untuk menentukan garis keputusan yang sesuai.
SVR akan mencoba menyesuaikan garis yang paling baik dalam nilai ambang batas.
		Kelebihan : 
			* Model keputusan mudah untuk diperbarui.
			* SVR melakukan komputasi yang lebih rendah
			* Memiliki kemampuan generalisasi yang sangat baik, dengan akurasi prediksi yang tinggi
			* Implementasi yang mudah
		Kekurangan	:
			* Tidak cocok diimplementasikan untuk data yang besar.
			* Jika jumlah fitur untuk setiap titik data melebihi jumlah sampel data pelatihan, SVR berperforma buruk.
			* Model keputusan tidak berkinerja sangat baik ketika kumpulan data memiliki lebih banyak noise
## Random Forest. 
Merupakan Algoritma yang fleksibel dan mudah untuk digunakan. “Forest” yang dibangunnya adalah kumpulan decision tree, biasanya dilatih dengan metode “bagging”. Ide umum dari metode bagging adalah kombinasi model pembelajaran meningkatkan hasil keseluruhan.

Untuk proyek inilebih dominan menggunakan model KNN dan/atau Random Forest, karena memiliki error paling kecil (bahkan tidak error) daripada model SVR.

# Evaluasi
---
Evaluasi untuk proyek machine learning kali ini akan menggunakan metrik evaluasi Mean Squared Error(MSE). MSE terdiri atas 2 komponen yaitu bias dan varians. Untuk menentukan uji kebenaran, maka dilakukan dengan mengukur error. Analisis yang menghasilkan nilai MSE terkecil akan menghasilkan model terbaik.
