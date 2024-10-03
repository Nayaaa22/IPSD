Welcome to the IPSD wiki!


# Teknik EDA (Exploratory Data Analysis)

## Teknik EDA
Teknik EDA dibagi menjadi dua, yakni:
1. **Graphical/Visual** --> lebih dominan digunakan untuk analisis.
   - Teknik ini berfokus pada visualisasi data, seperti grafik dan diagram, yang membantu dalam memahami pola, tren, dan outliers (nilai yang menyimpang) secara intuitif.
2. **Teknik Kuantitatif** --> metode analisis yang menggunakan angka dan statistik untuk memahami karakteristik dan hubungan dalam data.
   - Teknik ini menggunakan statistik seperti mean, median, korelasi, dan lainnya untuk mengeksplorasi data secara numerik.

## Visualisasi Grafis
Visualisasi adalah konversi data menjadi bentuk gambar atau tabel sehingga karakteristik data dan hubungan antar item data atau atribut dapat dianalisis atau dilaporkan.
- Visualisasi merupakan salah satu teknik eksplorasi data yang paling powerful.
- Manusia lebih mudah menganalisis data dengan jumlah besar melalui representasi visual seperti diagram batang, scatter plots, dan heatmaps.
- Dapat mendeteksi pola umum dan tren yang tidak mudah terlihat dalam data mentah.
- Dapat mendeteksi outliers dan pola khusus (unusual).

## Langkah-langkah Umum EDA pada Python

### 1. Import Libraries
Untuk melakukan EDA, kita membutuhkan pustaka seperti `pandas` untuk manipulasi data, `numpy` untuk operasi numerik, `matplotlib` dan `seaborn` untuk visualisasi.
*/

```kotlin
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load Data
Langkah pertama dalam EDA adalah memuat dataset ke dalam pandas DataFrame menggunakan fungsi seperti `pd.read_csv()` atau `pd.read_excel()`.

```kotlin
// Membaca data dari file CSV
val df = pd.read_csv("data.csv")
```
### 3. Data Overview
Langkah selanjutnya adalah memahami data melalui pemeriksaan properti dasar seperti jumlah baris, kolom, tipe data, dan statistik deskriptif.

```kotlin
// Mendapatkan informasi umum tentang dataset (jumlah kolom, tipe data, dll.)
println(df.info())  // Menampilkan informasi dasar tentang DataFrame

#Statistik deskriptif untuk kolom numerik
println(df.describe())  #Menampilkan statistik deskriptif
```

### 4. Data Cleaning
Langkah ini penting untuk membersihkan data dari anomali seperti missing values, duplikat, dan outliers. Data yang bersih sangat penting untuk mendapatkan hasil analisis yang akurat.

#### Cek dan Hapus Duplikat
Mengidentifikasi data duplikat dan menghapusnya agar tidak mempengaruhi hasil analisis.

```kotlin
// Mengecek jumlah duplikat
println(df.duplicated().sum())  // Mengecek jumlah baris duplikat

// Menghapus duplikat
val df_clean = df.drop_duplicates()  // Menghapus duplikat
```

### 5. Visualisasi Data
Visualisasi digunakan untuk mendeteksi pola, tren, outliers, dan hubungan antar variabel dengan lebih mudah. Dengan representasi visual, analisis data menjadi lebih intuitif dan informatif.

#### Box Plot untuk Outliers
Box plot adalah cara yang efektif untuk mendeteksi outliers (nilai yang menyimpang) dalam dataset.

```kotlin
// Membuat box plot untuk mendeteksi outliers
sns.boxplot(data = df_filled)  // Membuat box plot
plt.title("Box Plot untuk Mendeteksi Outliers")  // Menambahkan judul
plt.show()  // Menampilkan grafik
```
### 6. Kesimpulan
Setelah melakukan EDA (Exploratory Data Analysis), kita dapat menarik beberapa kesimpulan dari hasil analisis yang telah dilakukan. EDA membantu kita untuk:

1. **Memahami Struktur Data**: Melalui proses import dan overview data, kita dapat memahami struktur dataset, termasuk jumlah kolom, tipe data, dan nilai-nilai yang hilang.

2. **Mendeteksi Anomali**: Dengan melakukan data cleaning, kita dapat mengidentifikasi dan menangani anomali dalam data, seperti duplikat dan missing values, yang dapat mempengaruhi hasil analisis.

3. **Menemukan Pola dan Hubungan**: Dengan menggunakan visualisasi data, kita dapat mendeteksi pola, tren, dan hubungan antara variabel. Box plot dan histogram membantu dalam mendeteksi outliers dan memahami distribusi data, sedangkan scatter plot dan heatmap memberikan wawasan tentang hubungan antar variabel.

4. **Mendukung Pengambilan Keputusan**: Hasil dari EDA dapat digunakan untuk membuat keputusan yang lebih baik dalam analisis data selanjutnya, membantu dalam pengembangan model prediktif, atau dalam perencanaan bisnis yang lebih baik.

Secara keseluruhan, EDA adalah langkah penting dalam proses analisis data yang membantu peneliti atau analis untuk mendapatkan wawasan yang lebih dalam dan memahami data sebelum melanjutkan ke analisis yang lebih kompleks.


