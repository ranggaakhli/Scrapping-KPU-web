# 📊 Sampling Data Pemilih DP4 – Web Scraping & Stratified Random Sampling

## 🧠 Ringkasan Proyek

Proyek ini melakukan scraping data **Daftar Penduduk Potensial Pemilih Pemilu (DP4)** dari situs resmi **KPU**, mencakup jumlah pemilih per **provinsi dan jenis kelamin**. Tujuannya adalah menyimulasikan proses sampling survei nasional menggunakan pendekatan **stratified random sampling**.

## 🎯 Tujuan

- Scraping data pemilih berdasarkan provinsi dan gender  
- Menghitung **ukuran sampel** dengan **rumus Slovin** (Margin of Error: 3%)  
- Menerapkan **stratified sampling** berdasarkan provinsi & gender  
- Melakukan **oversampling** (×2) pada 7 provinsi dengan sampel kecil  
- Menghitung **pembobotan** agar hasil tetap representatif  

## 🛠️ Langkah-langkah

1. **Web Scraping**  
   Mengambil data dari [website KPU](https://satupetadata.kpu.go.id/data_pemilih) menggunakan `BeautifulSoup`. Data terdiri dari:  
   - Nama Provinsi  
   - Jumlah Laki-laki  
   - Jumlah Perempuan  
   - Jumlah Total  

2. **Perhitungan Ukuran Sampel**  
   Menggunakan rumus Slovin:  
   ```math
   n = \frac{N}{1 + N \cdot e^2}
   ```
   Di mana `N` adalah total populasi dan `e = 0.03`.

3. **Stratified Sampling**  
   Sampel dibagi secara proporsional berdasarkan provinsi dan gender. Pemilihan dilakukan secara acak dengan `numpy`.

4. **Oversampling (Eksperimen)**  
   Provinsi dengan sampel terkecil dikalikan dua (×2) untuk mengurangi under-representation.

5. **Pembobotan**  
   Menghitung bobot untuk mengembalikan proporsi populasi asli:  
   ```math
   \text{Bobot} = \frac{\text{Proporsi Populasi Nyata}}{\text{Proporsi Sampel}}
   ```
