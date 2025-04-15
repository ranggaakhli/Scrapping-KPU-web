📊 DP4 Voter Data Sampling – KPU Web Scraping & Stratified Sampling

🧠 Project Idea

Dalam rangka memahami distribusi data pemilih di Indonesia, proyek ini bertujuan untuk melakukan web scraping terhadap data Daftar Penduduk Potensial Pemilih Pemilu (DP4) dari situs resmi KPU: https://satupetadata.kpu.go.id/data_pemilih. Data ini mencakup jumlah pemilih berdasarkan provinsi dan jenis kelamin.

🎯 Tujuan

Mengambil data total pemilih per provinsi beserta proporsi gender-nya (Laki-laki dan Perempuan).
Menghitung jumlah sampel menggunakan rumus Slovin.
Menerapkan stratified random sampling berdasarkan provinsi dan gender.
Melakukan eksperimen oversampling pada 7 provinsi dengan jumlah sampel kecil (dikalikan faktor 2).
Menghitung pembobotan (weighting) pasca-oversampling agar hasil tetap representatif secara nasional.
🛠️ Langkah-langkah

Scraping
Mengambil data DP4 dari halaman web KPU dan mengolahnya menjadi DataFrame yang mencakup kolom:
Provinsi
Pemilih_Laki_Laki
Pemilih_Perempuan
Total_Pemilih
Perhitungan Sampel – Slovin's Formula
n
=
N
1
+
N
⋅
e
2
n= 
1+N⋅e 
2
 
N
​	
 
Dengan e = 0.05 (margin of error), dihitung jumlah sampel total nasional.
Stratified Sampling
Distribusi sampel dilakukan secara proporsional berdasarkan propinsi dan gender untuk memastikan representasi yang adil.
Oversampling (Eksperimen)
Untuk 7 provinsi dengan sampel terlalu kecil (< threshold tertentu), dilakukan penggandaan ukuran sampel (faktor 2).
Pembobotan (Weighting)
Karena oversampling mengubah proporsi populasi asli, bobot dihitung ulang:
Weight
=
Proporsi Populasi Asli
Proporsi Sampel
Weight= 
Proporsi Sampel
Proporsi Populasi Asli
​	
 
Bobot ini nantinya digunakan untuk analisis agar tetap merefleksikan populasi secara akurat.
