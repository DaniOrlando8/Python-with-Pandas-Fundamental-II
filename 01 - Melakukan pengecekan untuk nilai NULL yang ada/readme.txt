Melakukan pengecekan untuk nilai NULL yang ada

Dengan menggunakan fungsi pandas, kita tidak perlu melihat satu persatu baris data untuk mengetahui apakah ada 
nilai kosong atau NULL/NAN pada suatu dataset. Bayangkan jika kita memilki 1000 baris data. Apakah kita harus 
melihat semua baris data tersebut? Tentu saja tidak. Maka dari itu di pandas disediakan fungsi untuk mengecek 
apakah ada data yang kosong. Coba praktikkan kode di bawah ini :

import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data.csv")

print(csv_data.isnull().values.any())

Hasil pada panel console akan keluar seperti berikut :

False

Note : data yang digunakan merupakan data yang lengkap, maka dari itu output yang dihasilkan False. Coba Sekarang 
ganti dengan dataset yang memang terdapat data yang kosong. Coba ketikkan kode di bawah ini :

import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")

print(csv_data.isnull().values.any())

Hasil pada panel console akan keluar seperti berikut :

True

Solusi mengisi Missing Value
Sebelum mengenal lebih banyak mengenai Solusi yang biasa ada pada kasus-kasus data science.

Skema yang biasanya sering dalam pengelolaan data.

perlu diketahui bahwa kasus kehilangan data bisa diatasi dengan berbagai cara. 
Bahkan, melakukan penghapusan data juga merupakan solusi yang bisa menjadi pilihan apabila jika dirasa mengisi 
nilai kosong akan memberikan pengaruh yang kurang bagus terhadap analisa, atau apabila pertimbangan data yang 
dihapus atau data yang hilang sedikit dan tidak memberikan terlalu banyak sumbangsih untuk analisa yang akan 
dilakukan. Penghapusan data bisa langsung pada baris data tersebut atau langsung satu kolom data. Pada solusi kedua 
yaitu menggunakan imputation (pengisian data yang kosong) bisa tergantung dari permasalahannya. Khusus untuk masalah
yang berhubungan forecasting atau peramalan tergantung dari data yang ada (lebih lengkap bisa dilihat pada gambar).
Khusus untuk general problem tergantung jenis datanya. Jika yang hilang data kategorikal atau bersifat string bisa 
menggunakna relasi antar kolom dengan Logistic Regression, jika numerical bisa menggunakan statistik sederhana dan 
linear regression. Pada sesi kali ini kita akan mencoba menangani data hilang dengan statistik sederhana, Mean dan Median.

