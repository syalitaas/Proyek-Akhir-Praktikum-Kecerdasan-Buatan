# Laporan Ujian Akhir Semester Praktikum Mata Kuliah Kecerdasan Buatan (AI)



**Anggota Kelompok :**

1. Raihana Khalika Putri  (3.34.21.3.20)

2. Syalita Widyandini       (3.34.21.3.23)

   

## Domain Proyek

**Cosmetic (Kosmetik)** merupakan salah satu kebutuhan primer yang menjadi bagian penting dalam rutinitas perawatan diri sehari-hari. Penggunaan **cosmetic (kosmetik)** dapat meningkatkan rasa percaya diri dan membantu seseorang merasa lebih baik tentang penampilan mereka. Rata-rata  **cosmetic (kosmetik)**  digunakan oleh wanita (sebagian besar). **Cosmetic (Kosmetik)** digunakan untuk meningkatkan penampilan fisik, merawat dan memperbaiki kondisi kulit, rambut, dan kuku, serta mengekspresikan diri melalui riasan wajah dan perawatan tubuh. Namun, karena  **cosmetic (kosmetik)** merupakan suatu produk yang mengandung resiko penggunaan bagi konsumen di samping manfaat sosialnya, konsumen cenderung untuk mempertimbangkan faktor-faktor ketika ingin memilih suatu produk dalam rangka mengurangi resiko yang mungkin dihadapinya. Oleh karena itu kemampuan *machine learning* dalam memprediksi harga dan tipe kulit pada **cosmetic (kosmetik)** menjadi sangat penting bagi masyarakat yang ingin mencari **cosmetic (kosmetik)** sesuai kebutuhannya. Dalam proyek ini, kami akan menggunakan dataset tentang penjualan **cosmetic (kosmetik)** berdasarkan harga dan tipe kulit. Dataset ini mencakup informasi tentang label, brand, name, price, rank, ingredients, tipe kulit (combination, dry, normal, dan oily) mengenai produk **cosmetic (kosmetik)**. Proyek ini bertujuan untuk menganalisis preferensi konsumen dalam memilih **cosmetic (kosmetik)** berdasarkan faktor harga dan tipe kulit. Tujuan utama dari proyek ini adalah untuk memahami preferensi konsumen terkait produk kosmetik, serta melihat hubungan antara harga produk dan tipe kulit yang paling umum.



## Business Understanding

Saat ini, sudah banyak sekali produk **cosmetic (kosmetik)** yang dijual di pasaran. Umumnya, faktor-faktor yang mempengaruhi konsumen dalam mempertimbangkan pemilihan produk **cosmetic (kosmetik)**, antara lain berdasarkan tipe kulit, harga, ingredients (bahan yang digunakan), brand atau perusahaan yang memproduksi, dan rank. Bahkan tidak sedikit orang juga memilih suatu produk hanya berdasarkan harga karena menyesuaikan budget dan tipe kulit. Oleh karena itu, calon konsumen harus memahami produk **cosmetic (kosmetik)** yang akan dibeli disesuaikan dengan kebutuhan masing-masing. Diperlukan sebuah model *machine learning* yang dapat menganalisis preferensi konsumen dalam memilih **cosmetic (kosmetik)** berdasarkan faktor harga dan tipe kulit dengan akurat, sehingga calon konsumen dapat menyiapkan budget yang digunakan untuk membeli **cosmetic (kosmetik)**  dengan spesifikasi yang diinginkan.



### Problem Statements

Berdasarkan permasalahan yang telah dijelaskan, problem statements dari proyek ini adalah sebagai berikut.

1. Ketersediaan produk untuk tipe kulit apa saja yang paling berpengaruh terhadap referensi konsumen dalam memilih suatu produk ***cosmetic (kosmetik)*** ?

2. Bagaimana hubungan antara preferensi konsumen terkait produk ***cosmetic (kosmetik)*** dengan harga produk dan ketersediaan produk untuk beberapa tipe kulit?

3. Bagaimana membuat atau memilih model machine learning yang memiliki akurasi terbaik dalam memprediksi harga dari ketersediaan produk terhadap beberapa tipe kulit pada pemilihan suatu produk ***cosmetic (kosmetik)*** ?

   

### Goals

Adapun tujuan yang hendak dicapai dari proyek ini adalah sebagai berikut .

1. Mengetahui faktor ketersediaan produk untuk tipe kulit apa saja yang paling berkorelasi dengan referensi konsumen dalam memilih suatu produk ***cosmetic (kosmetik)***.

2. Memahami preferensi konsumen terkait produk ***cosmetic (kosmetik)***, serta melihat hubungan antara harga produk terhadap beberapa tipe kulit yang paling umum.

3. Membuat model machine learning yang memiliki akurasi terbaik dalam memprediksi harga dari ketersediaan produk terhadap beberapa tipe kulit pada pemilihan suatu produk ***cosmetic (kosmetik)***.

   

### Solution Statements

Adapun solusi yang kami ajukan untuk menyelesaikan permasalahan yang telah diuraikan adalah sebagai berikut.

1. Melakukan analisis deskriptif untuk mengetahui pola dan informasi yang tersimpan di data mengenai faktor ketersediaan produk untuk tipe kulit apa saja yang paling berkorelasi dengan referensi konsumen dalam memilih suatu produk ***cosmetic (kosmetik)***.
2. Melakukan proses *Data Manipulation* untuk menggabungkan kolom-kolom yang berpengaruh terhadap akurasi prediksi price atau harga pada **cosmetic (kosmetik)**. 
3. Melakukan  Proses *Preprocessing* seperti :
   - Mengecek *missing value* dan duplikasi data. Kebetulan dataset yang digunakan tidak ada *missing value* dan duplikasi data.
   - Menghapus kolom yang tidak berpengaruh terhadap prediksi harga
   - Melakukan visualisasi data untuk melihat persebaran dan korelasi antar kolom
   - Membagi data menjadi *training* dan *test set*, dengan prosentase 85% banding 15%. Alasan menggunakan 15% karena jumlah data yang digunakan banyak, jadi hanya dengan 15% sudah didapatkan banyak data tes.
   - Melakukan *Encoding* terhadap kolom yang bertipe objek / kategorikal menggunakan fungsi `Map`.
4. Melakukan pemilihan model terbaik menggunakan LazyPredict
   - Memilih 4 algoritma yang menghasilkan model dengan performa terbaik
   - Perfoma model terbaik dilihat dari skor *Mean Square Error* (MSE), *Root Mean Square Error* (RMSE), dan *R Square* (R2).



## Data Understanding

Data yang digunakan pada proyek ini didapatkan melalui Kaggle dan dapat diakses melalui tautan berikut https://www.kaggle.com/datasets/kingabzpro/cosmetics-datasets.

Adapun variabel-variabel yang terdapat pada dataset adalah sebagai berikut :

1. **Label**: Label produk **cosmetic (kosmetik)**.
2. **Brand**: Nama brand produk **cosmetic (kosmetik).**
3. **Name**: Nama produk **cosmetic (kosmetik)**.
4. **Price**: Harga produk **cosmetic (kosmetik)**.
5. **Rank**: Ranking/peringkat produk **cosmetic (kosmetik)**.
6. **Ingredients**: Komposisi bahan yang digunakan untuk membuat produk **cosmetic (kosmetik)**.
7. **Combination**: Jenis tipe kulit Kombinasi.
8. **Dry**: Jenis tipe kulit kering.
9. **Normal**: Jenis tipe kulit normal.
10. **Oily**: Jenis tipe kulit oily.

Dataset yang digunakan terdiri dari 1472 baris dan 11 kolom. Pada dataset, terdapat 7 fitur numerikal dan 4 fitur kategorikal. Ringkasan statistik dari data-data numerikal dapat dilihat pada Tabel 1.

|           | **Price**   | **Rank**    | **Combination** | **Dry**     | **Normal**  | **Oily**    | **Sensitive** |
| --------- | ----------- | ----------- | --------------- | ----------- | ----------- | ----------- | ------------- |
| **count** | 1472.000000 | 1472.000000 | 1472.00000      | 1472.000000 | 1472.000000 | 1472.000000 | 1472.000000   |
| **mean**  | 55.584239   | 4.153261    | 0.65625         | 0.614130    | 0.652174    | 0.607337    | 0.513587      |
| **std**   | 45.014429   | 0.633918    | 0.47512         | 0.486965    | 0.476442    | 0.488509    | 0.499985      |
| **min**   | 3.000000    | 0.000000    | 0.00000         | 0.000000    | 0.000000    | 0.000000    | 0.000000      |
| **25%**   | 30.000000   | 4.000000    | 0.00000         | 0.000000    | 0.000000    | 0.000000    | 0.000000      |
| **50%**   | 42.500000   | 4.300000    | 1.00000         | 1.000000    | 1.000000    | 1.000000    | 1.000000      |
| **75%**   | 68.000000   | 4.500000    | 1.00000         | 1.000000    | 1.000000    | 1.000000    | 1.000000      |
| **max**   | 370.000000  | 5.000000    | 1.00000         | 1.000000    | 1.000000    | 1.000000    | 1.000000      |

Pada tahap Data Understanding, dilakukan analisis data eksploratif untuk mendapatkan pemahaman tentang karakteristik data, memahami struktur data, dan mengidentifikasi potensi masalah atau kesalahan yang mungkin terjadi pada dataset. Berikut adalah beberapa kegiatan yang dilakukan dalam tahap Data Understanding proyek ini:

1. Memberikan informasi dasar tentang data, seperti jumlah data, keberadaan missing value, duplikasi data, korelasi antar kolom, dan sebaran data.

2. Melakukan manipulasi data untuk mendapatkan variabel atau fitur baru yang mungkin relevan untuk analisis.

3. Melakukan visualisasi data untuk memahami korelasi dan sebaran data. Dalam visualisasi korelasi antar kolom, biasanya digunakan heatmap seperti yang ditunjukkan pada Gambar 1. 

![image-20230712220212680](C:\Users\syali\AppData\Roaming\Typora\typora-user-images\image-20230712220212680.png)

Berdasarkan heatmap tersebut, dapat dilihat bahwa beberapa kolom seperti Rank, Combination, Dry, dan sebagainya memiliki korelasi dengan kolom 'Price (in IDR)'. Semakin dekat nilai korelasi dengan 1, maka korelasinya semakin tinggi. Namun, perlu diingat bahwa visualisasi heatmap hanya menampilkan korelasi pada kolom yang memiliki data numerikal, sehingga korelasi pada kolom yang memiliki data kategorikal tidak dapat ditampilkan dengan metode ini.

## Data Preparation

Adapun teknik data preparation yang dilakukan pada proyek ini adalah sebagai berikut.

1. Feature Selection : Melakukan seleksi fitur untuk menyeleksi kolom yang berperan sebagai data fitur dan kolom yang menjadi data label.
2. Data Splitting: Membagi dataset menjadi data latih dan data uji. Pada proyek ini perbandingan data latih dan data uji adalah 85 : 15.
3. Menampilkan informasi jumlah data latih dan data uji. Jumlah data latih adalah 1251, sedangkan data uji terdapat 221 data. jumlah data fitur yang dipakai untuk pelatihan adalah 7.

## Modelling

Pada tahap ini dilakukan proses pelatihan untuk mendapatkan model dengan performa terbaik. Tahapan yang dilakukan pada proses Modelling adalah sebagai berikut.

1. Memprediksi algoritma dengan performa terbaik menggunakan Lazy Predict

   Lazy Predict adalah library Python yang membantu dalam membuat model *machine learning* dengan cepat dan mudah. Library ini dikembangkan untuk mempercepat proses eksplorasi data dan pemodelan awal. Hasil dari proses pelatihan yang dilakukan Lazy Predict ditunjukan pada Tabel 2.
   
   ![tabel 2](S:\KULIAH\SMT 4\AI\Tugas Besar\tabel 2.jpeg)

Algoritma dengan performa terbaik dilihat dari nilai R-Square dan RMSE. Semakin besar nilai R-Square   (mendekati 1) maka model semakin akurat. Sedangkan pada RMSE, apabila nilai semain kecil (mendekati 0), maka akurasi model akan semakin tinggi. Berdasarkan hasil R-Square dan RMSE menggunakan Lazy Predict pada Tabel 2, dapat dilihat algoritma-algoritma yang dapat digunakan untuk mempredikasi harga. Disini, kami akan menggunakan algoritma **GradientBoostingRegressor****, **RandomForestRegressor**, dan **BaggingRegressor** karena lebih mudah kami pahami.

- Menggunakan `ColumnTransformer` untuk mengubah data kategorik menjadi numerik

   Pada proyek ini masih mempertahankan kolom kategorikal yaitu Brand dan OS. Sebab pada saat ingin mempredikasi harga smartphone, calon pembeli tentunya akan memilih Brand dan OS dalam bentuk kategori bukan numerik. Oleh karena itu kita ubah data kategorik menjadi numberik menggunkan teknik OneHotEncoding. Tapi sebelum dilakukan teknik `OneHotEncoding` dilakukan harus menampilkan indeks dari masing-masing kolom menggunakan fungsi `enumerate()`. Brand berada di indeks 0, dan OS berada di index 9. Selanjutkan dilakukan proses `ColumnTransformer`.

- Membuat pipeline untuk menggabungkan data numerik dan kategorik

   Hasil penggunakan teknik `ColumnTransformer` disimpan dalam objek feature. Selanjutnya dilakukan proses pipeline untuk menggabungkan dan meng-optimasi kolom numerikal dan kategorikan agar dapat di proses oleh algoritma machine learning. 

- Memilih 3 (tiga) algoritma dengan performa terbaik untuk di evaluasi

   Setelah dilakukan proses pelatihan oleh Lazy Predict, diperoleh 3 algoritma dengan performa terbaik yaitu :

   **GradientBoostingRegressor**

   ​	GradientBoostingRegressor adalah algoritma pemodelan yang digunakan dalam pembelajaran mesin untuk memprediksi variabel target berkelanjutan. Ini adalah metode ensambel yang menggabungkan beberapa pohon keputusan untuk membuat model yang lebih kuat. Algoritma GradientBoostingRegressor bekerja dengan menggabungkan banyak pohon keputusan sederhana. Setiap pohon yang ditambahkan ke model berusaha untuk memperbaiki kesalahan prediksi yang dihasilkan oleh pohon sebelumnya. Algoritma ini bekerja dengan cara mengoptimalkan gradien fungsi kerugian (misalnya, *Mean Squared Error*) menggunakan proses iteratif.

   **RandomForestRegressor**

   ​	RandomForestRegressor adalah algoritma pemodelan yang digunakan dalam pembelajaran mesin untuk memprediksi variabel target berkelanjutan. Ini adalah metode ensambel yang menggabungkan beberapa pohon keputusan acak (*random decision trees*) untuk membuat model yang lebih kuat. Pada dasarnya, algoritma RandomForestRegressor bekerja dengan menggabungkan hasil dari banyak pohon keputusan acak yang diberi bobot yang sama. Setiap pohon keputusan acak dibangun dengan menggunakan subset acak dari data pelatihan dan subset acak dari fitur (variabel independen). Proses ini dikenal sebagai bootstrap aggregating atau biasa disebut juga sebagai "bagging".

   **BaggingRegressor**

   ​	BaggingRegressor adalah algoritma pemodelan yang digunakan dalam pembelajaran mesin untuk memprediksi variabel target berkelanjutan. Ini adalah metode ensambel yang menggabungkan beberapa model regresi (misalnya, Regresi Linier, DecisionTreeRegressor) untuk membuat model yang lebih kuat. Pada dasarnya, algoritma BaggingRegressor bekerja dengan membuat beberapa model regresi yang berbeda menggunakan subset acak dari data pelatihan. Setiap model regresi dibangun secara independen dan tidak saling bergantung satu sama lain. Ketika melakukan prediksi, hasil dari semua model regresi digabungkan untuk menghasilkan prediksi akhir dengan menggunakan rata-rata atau mayoritas suara (tergantung pada jenis variabel target).  Namun, BaggingRegressor tidak memberikan interpretasi model yang langsung seperti Regresi Linier. Selain itu, dalam beberapa kasus, jika terdapat korelasi yang kuat antara fitur, BaggingRegressor mungkin tidak memberikan peningkatan yang signifikan dalam kinerja prediksi dibandingkan dengan model regresi tunggal.

5. Menambahkan parameter tunning untuk mengingkatkan performa model

   Penambahan parameter menggunakan **Teknik Grid Search** sehingga akan diperoleh hyperparameter dari masing-masing algoritma GradienBoostingRegressor, RandomForestRegressor, dan BaggingRegressor.



## Evaluation

1. Metrik evaluasi yang digunakan adalah Mean Square Error (MSE), Root Mean Square Error (RMSE), dan R2 Score.

   

   **MSE** melakukan pengurangan nilai data aktual dengan data peramalan dan hasilnya dikuadratkan (*squared*) kemudian dijumlahkan secara keseluruhan dan membaginya dengan banyaknya data yang ada. Rumus dari MSE adalah sebagai berikut 
   $$
     MSE = \frac{1}{n} \Sigma_{i=1}^n({y}-\hat{y})^2
   $$
     Diketahui:

     - n = Jumlah Data
     - yi = *Actual Value* / Nilai Sebenarnya
     - ŷi = *Predicted Value* / Nilai Prediksi

   

   **RMSE** adalah jumlah dari kesalahan kuadrat atau selisih antara nilai sebenarnya dengan nilai prediksi yang telah ditentukan. Cara menghitungnya tinggal mengakar kan mse menggunakan fungsi *np.sqrt*. Rumus dari RMSE adalah sebagai berikut.
   $$
   RMSE = \sqrt{(\frac{1}{n})\sum_{i=1}^{n}(y_{i} - x_{i})^{2}}
   $$
   Diketahui:

   - n = Jumlah Data
   - yi = *Actual Value* / Nilai Sebenarnya
   - ŷi = *Predicted Value* / Nilai Prediksi

   

   **R2 Score** dijadikan sebagai pengukuran seberapa baik garis regresi mendekati nilai data asli yang dibuat melalui model. Rumus dari R2 Score adalah sebagai berikut.
   $$
   R^2 = 1 - {SS_R \over SS_T} =  1 - {\sum_{i} (y_i - ŷ_p) ^ 2 \over \sum_{i} (y_i - ȳ) ^ 2}
   $$

   - SSR : Kuadrat dari selisih nilai Y prediksi dengan nilai rata-rata Y = ∑ (Ypred – Yrata-rata)²

   - SST : Kuadrat dari selisih nilai Y aktual dengan nilai rata-rata Y = ∑ (Yaktual – Yrata-rata)²

     

2. MSE melakukan pengurangan nilai data aktual dengan data peramalan dan hasilnya dikuadratkan (squared) kemudian dijumlahkan secara keseluruhan dan membaginya dengan banyaknya data yang ada

3. RMSE adalah jumlah dari kesalahan kuadrat atau selisih antara nilai sebenarnya dengan nilai prediksi yang telah ditentukan. Cara menghitungnya tinggal mengakar kan mse menggunakan fungsi np.sqrt

4. R2 Score dijadikan sebagai pengukuran seberapa baik garis regresi mendekati nilai data asli yang dibuat melalui model.

5. Menampilkan hasil pengujian MSE, RMSE, dan R2 Score dari 3 algoritma teratas.



## Conclusion

1. Berdasarkan hasil pengukuran, terdapat faktor yang mempengaruhi *Price* yaitu kolom Rank, dan Tipe kulit (kolom Combination, Dry, Normal, Oily).
2. Proses preprocessing yang dilakukan adalah dengan melakukan manipulasi data seperti mengabungkan Resolution X dan Resolution Y untuk menghasilkan fitur baru yaitu PPI. Menghapus data yang tidak memiliki korelasi yang signifikan dengan *Price*, dan mengubah format tipe data pada setiap kolom yang memiliki korelasi.
3. Berdasarkan hasil pengujian model, diperoleh hasil bahwa algoritma GradienBoosting memiliki performa yang paling baik yaitu memiliki nilai RMSE paling kecil dan R2 Score paling besar.
4. Meningkatkan performa model dapat dilakukan dengan menambahkan hyperparameter. Pemilihan hyperparameter yang menghasilkan performa terbaik dapat dilakukan menggunakan teknik Grid Search.
5. Dataset yang digunakan memiliki rentang jangkauan yang berbeda (imbalace), oleh sebab itu agar performa model lebih baik maka perlu dilakukan teknik SMOTE untuk menangani imbalance dataset.



## Referensi

[1] ZAKARIA, SRI INDRAWATI. 2011. *HUBUNGAN KEPERCAYAAN DIRI DENGAN INTENSI MEMBELI KOSMETIK PADA MAHASISWA.* Other thesis, University of Muhammadiyah Malang. Diakses pada Senin, 10 Juli 2023. http://eprints.umm.ac.id/id/eprint/31862

[2] Erna Ferrinadewi. *ATRIBUT PRODUK YANG DIPERTIMBANGKAN DALAM PEMBELIAN KOSMETIK DAN PENGARUHNYA PADA KEPUASAN KONSUMEN DI SURABAYA*. JMK (Journal of Management and Entrepreneurship) [Vol. 7 No. 2 (2005): SEPTEMBER 2005](https://jurnalmanajemen.petra.ac.id/index.php/man/issue/view/2842). Diakses pada Senin, 10 Juli 2023. https://jurnalmanajemen.petra.ac.id/index.php/man/article/view/16360.

[3] Alyauma Hajjah, Yulvia Nora Marlim. *ANALISIS ERROR TERHADAP PERAMALAN DATA PENJUALAN*. Jurnal Teknologi Informasi [Vol 20, No 1 (2021)](http://publikasi.dinus.ac.id/index.php/technoc/issue/view/226). Diakses pada Rabu, 12 Juli 2023. https://doi.org/10.33633/tc.v20i1.4054

[4] Chat GPT.



**---Ini adalah bagian akhir laporan---**