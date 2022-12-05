# DogePredict - Fajar Maulana
## Domain Proyek
---
## Business Understanding
---
### Latar Belakang
Kemajuan teknologi sangat berkembang pesat, termasuk kemajuan teknologi dalam bidang ekonomi. Salah satu kemajuan spektakuler teknologi di bidang ekonomi diantaranya cryptocurrency atau uang virtual yang sedang populer. *Cryptocurency* memiliki banyak macam, seperti *Ripple*, *Lisk*, *Ether*, *MaidSafeCoin*, *Litecoin*, *StorjCoinX*, *Ethereum*, *DogeCoin*, *Dash*, *Monero*, *Zcash*, dan *Bitcoin* (BTC) (Brainytutorial, 2018). *Cryptocurrency* mendorong beberapa hal pro dan juga kontra. Banyak sebagian besar pada orang tertarik pada sebuah hal *cryptocurrency* karena dilihat dari aspek teknologi, fungsionalitas, dan juga seberapa besar kesempatan untuk mendapatkan sebuah keuntungan dalam menggunakan mata uang virtual ini. mata uang yang dikeluarkan ini bukan merupakan hasil dari penciptaan dari sebuah negara, melainkan komputer jaringan kriptografi.

Dogecoin merupakan *cryptocurrency* yang diciptakan oleh Billy Markus dari Portland,Oregon dan Jackson Palmer dari Sydney, Australia pada tahun 2013 dengan
menggunakan maskot anjing Shiba Inu yang awalnya hanya dianggap sebagai meme coins (Chohan, 2017). Namun koin ini telah mengalami kenaikan nilai tukar sebanyk 800% pada tahun 2021. Nilai tukar Dogecoin juga sempat mengalami penurunan sebesar 20% yang justru terjadi pada saat Doge Day pada tanggal 20 April 2021 setelah sebelumnya
hype 

Pertumbuhan pasar kripto yang begitu massive membuat volatilitas harga di pasar kripto cukup tinggi sehingga membuat pasar kripto mampu menawarkan potensi keuntungan yang besara namun risiko yang dihadapi juga akan meningkat. Fluktuasi harga yang sangat tinggi menjadikan transaksi perdagangan di pasar kripto tergolong sangat spekulatif dan memiliki risiko yang sangat besar. Terdapat  tiga  faktor  yang berperan  membentuk   volatilitas   harga   kripto,   yang pertama adanya generasi baru traderdan investor yang memasuki pasar. Kedua, trader dan investor baru belum pernah mengalami kejatuhan harga yang biasa terjadi di pasar kripto, sehingga ketika menghadapi situasi seperti ini trader dan investor pemula akan terkejut dan cenderung melakukan transaksi berlebihan.K etiga, investor ritel lebih mudah terpengaruh oleh sensasi, khususnya ketika naiknya *Dogecoin* dan turunnya harga *Bitcoin*. Tiga faktor tersebut menjadikan penyebab terjadinya koreksi yang sangat besara dalam dunia kripto.

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
* Penerapan hyperparameter yang dikombinasikan dengan teknik *Grid Search*. Dengan cara mengkombinasikan nilai yang kita inputkan ke *Hyperparameter*. Hal ini bertujuan untuk model yang kita buat lebih akurat.

## Data Understanding
---
Pada proyek ini menggunakan dataset yang diambil dari Kaggle dengan Judul *Cryptocurrency Historical Prices* https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory
  * Pada dataset ini mengambil file data coin_Dogecoin.csv
  * Tidak ada missing values atau nilai yang kosong pada tiap kolom
  * Data terdiri atas 1 kolom bertipe data integer, 3 kolom bertipe data string, dan 6 kolom bertipe data float.
  * Data berisi 2.760 sample.
  * Data berisi 10 kolom yag terdiri dari kolom *SNo, Name, Symbol, Date, High, Low, Open, Close, Volume, Marketcap*.

Variable yang terdapat pada data :
* Name : Nama uang kripto
* Symbol : Simbol dari mata uang kripto
* Date : Tanggal pencataan data darti setiap mata uang
* High : Nilai harga tertinggi uang kripto dari hari tertentu
* Low : Nilai harga terendah uang kripto dari hari tertentu
* Open : Nilai harga buka uang kripto dari hari tertentu
* Close : Nilai harga tutup uang kripto dari hari tertentu
* Volume : Besaran transaksi di hari tertentu
* Marketcap : Kapitalisai pasar

### Exploratory Data Analytics
Melakukan eksplorasi data dari dataset, sehingga kita dapat mengetahui bagaimana keadaan dataset yang akan kita gunakan.
* Outlier

Dari dataset yang digunakan, ada beberapa kolom yang memiliki outlier yang cukup banyak. seperti pada kolom *High, Low, Open, Close, Volume, dan Marketcap*. 
![outlier](https://user-images.githubusercontent.com/75149615/205506145-75af8f24-75a5-4f98-922c-57a439d1fc91.png)

* Univariate Analysis. 

Berfokus pada satu variable dengan tujuan dapat diidentifikasi dan diketahui karakteristik yang dimiliki. disini kita memilih fitur/kolom Close sebagai acuan dasar dari aspek *Univariate Analysis*.
![Univariate](https://user-images.githubusercontent.com/75149615/205506171-49561124-1bf9-4154-8895-8768509c4554.png)

* Multivariate Analysis

Jika pada aspek sebelumnya hanya berfokus pada satu kolom saja, pada aspek ini lebih akan berfokus dengan cara membandingkan dan juga mencari korelasi dari beberapa kolom dengan kolom yang menjadi acuan dasar yang sudan kita tentukan yaitu kolom Close.
![multivariate](https://user-images.githubusercontent.com/75149615/205506179-2013a388-d59d-459a-9904-a54d70c4f85f.png)

Visualiasi dibawah ini menunjukkan beberapa hasil nilai korelasi pada tiap kolom. dihasilkan bahwa kolom *Volume* memiliki niali korelasi yang rendah dibanding kolom yang lain terhadap kolom yang sudah kita jadikan sebagai acuan, yaitu kolom *Close*. dengan demikian kita dapat melakukan drop pada kolom *Volume*

![image](https://user-images.githubusercontent.com/75149615/205510455-2023ca89-bdcc-44c1-86f3-44e76912866c.png)


# Data Preparation
---
Untuk mempermudah pelatihan pada model sehingga bisa didapatkan hasil yang baik. Selanjutnya dapat melakukan langkah - langkah sebagai berikut.
* Mengatasi Outlier
Untuk mengatasi outlier, dapat ditangani dengan menggunakan sebuah method yang bernama IQR method, yaitu dengan cara menghapus data yang berada dikuar IQR sebesar 25% sampai dengan 75% 

* Menghapus kolom yang tidak digunakan
Penghapusan ini diperlukan karena agar tidak menganggu proses permodelan saat dilakukan training. Menghapus kolom *Sno, Name, Symbol, Date, Marketcap* sehingga menjadi 

| High     | Low      | Open     | Close    |
|----------|----------|----------|----------|
| 0.000866 | 0.000150 | 0.000299 | 0.000205 |
| 0.000289 | 0.000116 | 0.000207 | 0.000269 |
| 0.000362 | 0.000205 | 0.000267 | 0.000362 |
| 0.001520 | 0.000328 | 0.000395 | 0.001162 |
| 0.001143 | 0.000662 | 0.001143 | 0.000704 |

* Split Dataset
Membagi dataset menjadi 2 bagian, sebagai test data dan train data. Untuk pembagiannya masing - masing memiliki porsi senilai 80% untuk *train* data dan 20% sebagai *test* data
* Data Normalization
Dalam proses ini, diperlukan transformasi data atau dengan kata lain mengubah data asli menjadi format data yang lebih efisien. Hal ini dilakukan untuk menghilangkan redundasi data. Untuk menormalisasikan data, dapat menggunakan library *MinMaxScaller*. *Library* in akan mengubah fitur dengan cara menskalakan setiap fitur ke rentang terentu. *range default* yang digunakan pada *Library* ini yaitu antara 0 sampai 1.

# Modeling
Model atau Algoritma yang digunakan pada proyek ini.
## K-Nearest Neighbours
Algoritma KNN merupakan algoritma klasifikasi yang bekerja dengan mengambil sejumlah K data terdekat (tetangganya) sebagai acuan untuk menentukan kelas dari data baru. Algoritma ini mengklasifikasikan data berdasarkan kesamaan atau kemiripan atau kedekatannya terhadap data lainnya. Algoritma KNN digunakan untuk klasifikasi dan regresi. Pada pembuatan model ini akan menggunaka modul KNN yang terlah di sediakan oleh *library scikit-learn*.  
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

![image](https://user-images.githubusercontent.com/75149615/205509058-451df508-0557-4443-af76-0ef7ce763de9.png)

Dimana : 
* Yi = Data Sebenarnya
* Ýi = Nilai prediksi dari variabel Y
* n = banyaknya observasi

Setelah melakukan evaluasi menggunakan metrik mean squared error pada model dengan menggunakan data uji didapatkan hasil sebagai berikut:

![image](https://user-images.githubusercontent.com/75149615/205545524-2f5ea65f-f82c-4b85-9a74-b01181a55315.png)

Diantara 3 model yang telah dijalankan, dapat disimpulkan bahwa KNN dan RandomForest yang memiliki hasil yang optimal. Demikian, hasil ini dapat digunakan untuk membantu para trader bertransaksi di dalam dunia kripto.

---
# Refences
---
Moch Farryz Rizkilloh, & Sri Widiyanesti. (2022). Prediksi Harga Cryptocurrency Menggunakan Algoritma Long Short Term Memory (LSTM). Jurnal RESTI (Rekayasa Sistem Dan Teknologi Informasi), 6(1), 25 - 31.

Tjahyana, L.J. (no date) Studi Netnografi Pola komunikasi jaringan komunitas cryptocurrency Dogecoin Pada Twitter, KOMUNIKATIF : Jurnal Ilmiah Komunikasi. Available at: https://doi.org/10.33508/jk.v10i1.3188 (Accessed: December 1, 2022). 
