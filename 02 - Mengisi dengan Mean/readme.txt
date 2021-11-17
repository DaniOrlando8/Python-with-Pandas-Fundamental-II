Mengisi dengan Mean

Salah satu metode yang bisa dikatakan sebagai solusi yang umum pada kasus general data science adalah mengisi data
kosong dengan menggunakan mean dari masing-masing kolom. Pertama kita harus menentukan mean dari masing-masing kolom. 
Pada pandas terdapat fungsi mean() untuk menentukan nilai mean dari masing-masing kolom. Mean sendiri digunakan 
untuk data yang memiliki sedikit sifat outlier/noisy/anomali dalam sebaran datanya maupun isinya.  

Coba ketikkan kode di bawah ini :

import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")

print(csv_data.mean())

Hasil pada panel console akan keluar seperti berikut :

CustomerID                100.500000
Age                        38.939698
Annual Income (k$)         61.005051
Spending Score (1-100)     50.489899
dtype: float64

Fungsi mean sendiri berfungsi untuk menampilkan  nilai mean (rata-rata) dari setiap kolom. Nilai inilah nanti yang 
akan mengisi nilai kosong dari dataset yang mengalami kasus missing value. Untuk mengisi nilai yang kosong 
menggunakan fungsi fillna(), coba ketikkan kode di bawah ini :

import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")
print(csv_data.mean())
print("Dataset yang masih terdapat nilai kosong ! :")
print(csv_data.head(10))

csv_data=csv_data.fillna(csv_data.mean())
print("Dataset yang sudah diproses Handling Missing Values dengan Mean :")
print(csv_data.head(10))

Hasil pada panel console akan keluar seperti berikut :
CustomerID                100.500000
Age                        38.939698
Annual Income (k$)         61.005051
Spending Score (1-100)     50.489899
dtype: float64
Dataset yang masih terdapat nilai kosong ! :
   CustomerID   Genre   Age  Annual Income (k$)  Spending Score (1-100)
0           1    Male  19.0                15.0                    39.0
1           2    Male   NaN                15.0                    81.0
2           3  Female  20.0                 NaN                     6.0
3           4  Female  23.0                16.0                    77.0
4           5  Female  31.0                17.0                     NaN
5           6  Female  22.0                 NaN                    76.0
6           7  Female  35.0                18.0                     6.0
7           8  Female  23.0                18.0                    94.0
8           9    Male  64.0                19.0                     NaN
9          10  Female  30.0                19.0                    72.0
Dataset yang sudah diproses Handling Missing Values dengan Mean :
   CustomerID   Genre        Age  Annual Income (k$)  Spending Score (1-100)
0           1    Male  19.000000           15.000000               39.000000
1           2    Male  38.939698           15.000000               81.000000
2           3  Female  20.000000           61.005051                6.000000
3           4  Female  23.000000           16.000000               77.000000
4           5  Female  31.000000           17.000000               50.489899
5           6  Female  22.000000           61.005051               76.000000
6           7  Female  35.000000           18.000000                6.000000
7           8  Female  23.000000           18.000000               94.000000
8           9    Male  64.000000           19.000000               50.489899
9          10  Female  30.000000           19.000000               72.000000