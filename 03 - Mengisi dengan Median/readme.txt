Mengisi dengan Median

Berbeda dengan mean pada sesi sebelumnya, median digunakan untuk data-data yang memiliki sifat 
outlier yang kuat. Kenapa median dipilih? Median merupakan nilai tengah yang artinya bukan hasil 
dari perhitungan yang melibatkan data outlier. Pada beberapa kasus, data outlier dianggap 
mengganggu dan sering dianggap noisy karena bisa mempengaruhi distribusi kelas dan mengganggu 
analisa pada klasterisasi (clustering).

import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")

print(csv_data.median())

Hasil pada panel console akan keluar seperti berikut :

CustomerID                100.5
Age                        36.0
Annual Income (k$)         62.0
Spending Score (1-100)     50.0
dtype: float64

Sama dengan sesi sebelumnya dengan mean(), gunakan kode di bawah ini untuk mengisi nilai yang kosong menggunakan fungsi fillna() :

import pandas as pd

csv_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/shopping_data_missingvalue.csv")
print("Dataset yang masih terdapat nilai kosong ! :")
print(csv_data.head(10))

csv_data=csv_data.fillna(csv_data.median())
print("Dataset yang sudah diproses Handling Missing Values dengan Median :")
print(csv_data.head(10))

Hasil pada panel console akan keluar seperti berikut :

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
Dataset yang sudah diproses Handling Missing Values dengan Median :
   CustomerID   Genre   Age  Annual Income (k$)  Spending Score (1-100)
0           1    Male  19.0                15.0                    39.0
1           2    Male  36.0                15.0                    81.0
2           3  Female  20.0                62.0                     6.0
3           4  Female  23.0                16.0                    77.0
4           5  Female  31.0                17.0                    50.0
5           6  Female  22.0                62.0                    76.0
6           7  Female  35.0                18.0                     6.0
7           8  Female  23.0                18.0                    94.0
8           9    Male  64.0                19.0                    50.0
9          10  Female  30.0                19.0                    72.0