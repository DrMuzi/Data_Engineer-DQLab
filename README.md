# Data_Engineer-DQLab
Berisi materi belajar dari DQLab tentang Data Engineer. Bahasa pemprograman Phyton, R, dan SQL.

## Python-Beginner-Part1
Berisi praktek Python menyelesaikan permasalah menggunakan ilmu data, soal sebagai berikut:

Ekspedisi Pamanku

Aku menyambar ponsel di meja dan membuka pesan singkat dari paman tempo hari yang menjelaskan jika paman harus mengeluarkan uang sebesar 1,5 juta per mobil dalam sehari. 
Tapi, beliau selalu kebingungan total pengeluaran per bulan karena adanya aturan ganjil-genap yang membuat pengoperasian mobil yang berbeda.

“Kalau begitu, aku akan masukkan variabel jumlah_hari berisi jumlah hari dalam sebulan dan variabel `list_plat_nomor` berisi seluruh nomor plat mobil milik paman,” gumamku sendiri.
Kalau seperti ini paman hanya perlu mengganti variabel jumlah_hari atau modifikasi variabel `list_plat_nomor` untuk melacak total pengeluaran paman selama sebulan. Ide Cemerlang!

## Python-Beginner-Part2

Harga Rumah di Tangerang

“Terima kasih, Aksara! Akhirnya kelar juga pekerjaan kemarin. Masih semangat, kan? Belum kapok kalau ada proyek baru datang lagi? Hahaha,” goda Senja.
“Asalkan ada bonus, maju terus,” candaku.
“Oke, kali ini serius. Kita diminta untuk mengembangkan model prediksi harga rumah di di Tangerang berdasarkan luas tanah, luas bangunan serta kedekatan lokasi dengan pusat kota. Untuk mengembangkan model prediksi ini, saya telah mengumpulkan beberapa data yang diperlukan. Coba kamu lihat,” jelas Senja.
![p2-1](https://user-images.githubusercontent.com/48518663/112790335-540d2900-9089-11eb-92f5-03c585264afd.png)

“Berarti aku akan memprediksi harga rumah ini berdasarkan kemiripan atribut dari data yang telah ada ini?” tanyaku memastikan. Senja mengangguk.
Aku pun segera menempatkan data tersebut ke dalam file harga_rumah.txt seperti berikut ini:
![p2-2](https://user-images.githubusercontent.com/48518663/112790368-67b88f80-9089-11eb-83b2-ee73fafadf9b.png)

Tugas 1
Aku pun melanjutkan prosesnya dengan membaca file harga_rumah.txt ("https://storage.googleapis.com/dqlab-dataset/harga_rumah.txt") dan merepresentasikan setiap data ke dalam tipe data dictionary dan menampung keseluruhan data dalam sebuah list bernama harga_rumah:

![p2-3](https://user-images.githubusercontent.com/48518663/112790400-7737d880-9089-11eb-99d9-c9731c8c1db0.png)

Setelah selesai memasukkan data dan menemukan jika nilai dari setiap atribut (tanah, bangunan, jarak_ke_pusat) tidak setara, aku mulai agak bingung. Tapi, harus tenang dan jangan panik!
Aku kembali mengecekanya dan memutuskan utnuk melakukan proses transformasi data. Transformasi data dilakukan dengan mengurangi setiap nilai atribut dalam data dengan nilai atribut minimum dan membaginya dengan nilai atribut maksimum yang dikurangi dengan nilai atribut minimum, seperti ini:
Untuk atribut tanah, nilai maksimum adalah 150 dan nilai minimum adalah 70.
Saat nilai atribut tanah 100, proses transformasi akan mengubah nilai atribut ini menjadi 0,375

`nilai_transformasi = 100 - 70 / (150 - 70)`
Aku mulai mendapat solusi untuk mempermudah proses transformasi data.

Tugas 2
Mula-mula,  aku akan membuat sebuah fungsi bernama get_all_specified_attribute yang menerima parameter `list_of_dictionary` (tipe data list yang berisikan sekumpulan tipe data dictionary) dan `specified_key` (tipe data string). Fungsi akan mengembalikan sebuah list yang berisikan seluruh atribut dengan kunci (key) `specified_key`.

Tugas 3
Kemudian, setelah berhasil membuat fungsi  tersebut, aku juga membuat fungsi`min_value` yang menerima parameter `list_attributes` (berupa tipe data list) dan mengembalikan nilai terkecil dalam `list_attributes` dan `max_value` yang menerima parameter `list_attribute` dan mengembalikan nilai terbesar dalam `list_attributes`.

Tugas 4
Selanjutnya aku membuat fungsi `transform_attribute` yang menerima `parameter attr` (sebuah bilangan), `max_attr` (sebuah bilangan) dan `min_attr` (sebuah bilangan) yang mengembalikan nilai transformasi dari sebuah attribute.

Tugas 5
“Sudah cukup, Nja?” tanyaku saat Senja terdiam lama menelusuri hasil kerjaku.
“Menurutku kita masih butuh fungsi baru yaitu fungsi `data_transformation` yang menerima parameter `list_of_dictionary` (sebuah list yang berisikan tipe data dictionary) dan `list_attribute_names` (sebuah list yang berisikan tipe data string) mengembalikan hasil transformasi data dari `list_of_dictionary` berdasarkan `list_attribute_names` telah dispesifikasikan.

Tugas 6
Dari data baru dan `attr_info` ini, Senja menyuruhku membuat fungsi `transform_data` yang menerima parameter data dan `attr_info` dan mengembalikan nilai atribut dari data baru yang telah ditransformasikan.

Tugas 7
Setelah itu, Senja memintaku untuk membuat sistem prediksi harga berdasarkan nilai kemiripan atribut.

Tugas 8
Dan aku menggunakan semua fungsi yang telah aku definisikan dari Step 1 s/d Step 7.

Hitung harga rumah yang telah ditransformasikan ke dalam variabel `harga_rumah` berikut dengan atributnya `attr_info`
Gunakan variabel data untuk memprediksi harga rumah
`data = {'tanah': 110, 'bangunan': 80, 'jarak_ke_pusat': 35}`
transformasikan data tersebut dengan dengan menggunakan `attr_info` yang telah diperoleh yang kembali disimpan ke variabel data.
Hitunglah prediksi harga dari variabel data tersebut. 

## Python-Beginner-Part3

Studi Kasus dari Senja

Di perusahaan ini, seorang analis data yang masuk umumnya berusia 21, memiliki pendapatan senilai 6.500.000 dan insentif lembur senilai 100.000. Kemudian, untuk seorang ilmuwan data yang masuk umumnya berusia 25, memiliki pendapatan senilai 12.000.000, dan insentif lembur senilai 150.000. Di sisi lain, untuk tenaga lepas, hanya terdapat pendapatan umum senilai 4000000 untuk pembersih data dan 2500000 untuk dokumenter teknis. 

Berikut adalah data perusahaan beserta detail karyawan yang bekerja.

Nama Perusahaan: ABC

Alamat                  : Jl. Jendral Sudirman, Blok 11

Telepon                 : (021) 95812XX

![p3-1](https://user-images.githubusercontent.com/48518663/112791010-cc281e80-908a-11eb-8d1f-2ca8bda60ae0.png)


Note: saat usia/pendapatan kosong maka usia/pendapatan mengikuti standar perusahaan.

“Dengan kasus ini, berarti di akhir aku harus mencetak total pengeluaran perusahaan untuk menguji kelancaranku dalam menerapkan OOP dengan Python nih,” gumamku sambil berkutat pada baris-baris code di code editor.

Tugas:
Simulasikan dengan program yang telah dibuat.
Cetak total pengeluaran yang dimiliki perusahaan untuk menguji fungsionalitas konsep dan teknik polymorphism yang diterapkan.

# Case_Study-Data_Quality-Python
Case Study: Data Profiling

Dear Aksara, 

Tolong proses dataset terlampir yang  disimpan dalam bentuk csv bernama 'https://storage.googleapis.com/dqlab-dataset/uncleaned_raw.csv'.

Kamu bisa memprosesnya dengan cara berikut:

Import dataset csv ke variable bernama `uncleaned_raw`
Inspeksi dataframe `uncleaned_raw`
Check kolom yang mengandung missing value, jika ada, kolom apakah itu dan berapa persen missing value pada kolom tersebut?
Mengisi missing value tersebut dengan mean dari kolom tersebut!
Setelah membaca email tersebut, aku pun memulai kode programnya di code editor.

Case Study: Data Cleansing - Part 1

Untuk memprosesnya bisa dilakukan dengan cara berikut:

Mengetahui kolom yang memiliki outliers! Gunakan visualisasi dengan boxplot pada dataframe `uncleaned_raw`.

Case Study: Data Cleansing - Part 2

Langkah selanjutnya bisa dilakukan dengan cara berikut:

Melakukan proses removing outliers pada kolom `UnitPrice`.
Checking duplikasi and melakukan deduplikasi dataset tersebut!

# Data_Manipulation-Pandas-Part1

Project dari Andra

Berikut adalah isi email yang ditugaskan oleh Andra:

 

Diberikan dataset ‘retail_raw_test.csv’

1. Baca dataset
2. Tipe data diubah menjadi tipe yang seharusnya

               `customer_id` dari `string` ke `int64`,
  
                `quantity` dari `string` ke `int64`,
  
                `item_price` dari `string` ke `int64`
 
3. transform `product_value` supaya bentuknya seragam dengan format PXXXX, assign ke kolom baru `"product_id"`, dan drop kolom `"product_value"`, jika terdapat nan gantilah dengan `"unknown"`.
4. tranform `order_date` menjadi value dengan format `YYYY-mm-dd`
5. cek data hilang dari tiap kolom dan kemudian isi missing value

               di brand dengan `"no_brand"`, dan
   
               cek dulu bagaimana missing value di `city` & `province` - isi missing value di city dan province dengan `"unknown"`
   
6. create column `city/province` dari gabungan `city` & `province`
7. membuat index berdasarkan `city_provice`, `order_date`, `customer_id`, `order_id`, `product_id` (cek index)
8. membuat kolom `"total_price"` sebagai hasil perkalian `quantity` dengan `item_price`
9. slice data hanya untuk Jan 2019

Notes :

Dataset :  https://storage.googleapis.com/dqlab-dataset/retail_raw_test.csv

Preview akhir data:


![pd-1](https://user-images.githubusercontent.com/48518663/112792241-4c4f8380-908d-11eb-8886-3eb7fbe9a86c.png)

# Data_Manipulation-Pandas-Part2

Performa Penjualan di Setiap Cabang

Diberikan 4 csv files yang isinya retail data untuk tiap Quarter:

csv (data dari bulan January - March)       --> https://storage.googleapis.com/dqlab-dataset/LO4/retail_data_from_1_until_3.csv

csv (data dari bulan April - June)              --> https://storage.googleapis.com/dqlab-dataset/LO4/retail_data_from_4_until_6.csv

csv (data dari bulan July - September)      --> https://storage.googleapis.com/dqlab-dataset/LO4/retail_data_from_7_until_9.csv

csv (data dari bulan October - December)  --> https://storage.googleapis.com/dqlab-dataset/LO4/retail_data_from_10_until_12.csv
 

Goal: Automation untuk pembuatan grafik dari measurement yang dibutuhkan.

 

Untuk part 1 ini yang perlu dilakukan:

[1]. Load masing-masing data *.csv dengan Pandas

[2]. Pengecekan dan Transformasi Data 

Cek data sekilas (melihat bentuk data biasanya 5 data teratas)

Cek list kolom untuk semua dataframe apakah seluruh kolom dari keempat dataframe yang terpisah itu sama

Jika sama digabungkan.

Cek informasi dataframe yang telah digabungkan

Statistik deskriptif dari dataframe yang telah digabungkan.

Untuk representasi string gunakan kutip satu, misalnya: 'contoh string'.

Melanjutkan penyelesaian persoalan ke langkah berikutnya

[3] Transformasi Data 

Jika ada data yang tidak seharusnya maka dapat dibuang
Jika ada kolom yang seharusnya bertipe datetime64 ubahlah
Cek kembali informasi dataframe 
Tampilkan kembali statistik deskriptif dari dataframe
Untuk representasi string gunakan kutip satu, misalnya: 'contoh string'.

 

Sebagai kontrol, informasi terakhir (baris 22) berikut dengan statistik deskriptif (baris 24) adalah:

![pd-2](https://user-images.githubusercontent.com/48518663/112793065-cf250e00-908e-11eb-9649-c126e525a583.png)

![pd-3](https://user-images.githubusercontent.com/48518663/112793091-d8ae7600-908e-11eb-8e64-ccb74282e687.png)

Mari lanjutkan ke langkah berikutnya

[4]. Filter province yang hanya termasuk 5 provinsi besar di Jawa (DKI Jakarta, Jawa Barat, Jawa Tengah, Jawa Timur, dan Yogyakarta)

[5]. Mengelompokkan data berdasarkan order_date dan province yang sudah difilter dan menghitung order unique count, customer unique count, product unique count, brand unique count, dan GMV (Gross Merchandise Volume = total_price untuk semua penjualan)

[6]. Melakukan unstack untuk mendapatkan order_date di bagian baris dan province di bagian column

 

Untuk string direpresentasikan dengan kutip satu, misalnya 'contoh string'.

 

Sebagai kontrol, bahwa output langkah ke [5]

![pd-4](https://user-images.githubusercontent.com/48518663/112793156-f8de3500-908e-11eb-9482-16a1e69f1eaa.png)


dan output langkah [6] 

![pd-5](https://user-images.githubusercontent.com/48518663/112793184-04c9f700-908f-11eb-8eb2-c5ac8481e002.png)

Ayo lanjutkan ke langkah berikutnya:

[7]. Slicing data untuk masing-masing measurement (kolom), misal: kolom order

[8]. Lakukan resampling pada data tersebut untuk dilakukan perhitungan secara bulanan

 

Untuk string direpresentasikan dengan kutip satu, misalnya 'contoh string'.

Sekarang dilanjutkan untuk langkah #[9] yaitu menampilkan grafik dari langkah #[8] yang telah dilakukan.

[9]. Plot untuk hasil pada langkah #[8]

Untuk string direpresentasikan dengan kutip satu, misalnya 'contoh string'.

 

Output untuk langkah [9]

![pd-6](https://user-images.githubusercontent.com/48518663/112793232-1ca17b00-908f-11eb-8d62-239a3a869cd0.png)

Dapat dilihat bahwa avg order size untuk DKI Jakarta tertinggi dan terus memiliki kenaikan, disusul oleh Jawa Barat dan kemudian 3 sisanya hampir berada dalam angka yang rata-rata sama

Langah 7 s/d 9 yang telah dilakukan baru untuk satu measurement yaitu order. Berarti ada empat kali lagi kode seperti ini harus dibuat. Karena struktur code masih sama, dapat menggunakan perulangan sesuai dengan jumlah measurement yaitu 5, sehingga kelima measurement dapat ditampilkan grafiknya dalam satu canvas figure.

Mari memulai dengan membuat sebuah perulangan dengan dataframe unstack_city_province yang digunakan (hasil dari langkah ke 5 di part 2).

 

Visualisasi yang diharapkan adalah:

![pd-7](https://user-images.githubusercontent.com/48518663/112793336-53779100-908f-11eb-98c8-5af52d556a0f.png)










