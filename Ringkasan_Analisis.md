# Ringkasan Analisis: Penjualan Video Game Global (1980–2016)

**Penulis:** Adika Rais Muhammad Abror
**Tanggal:** Jumat, 16 Oktober 2026
**Tools:** Microsoft Excel (PivotTable, Chart, Slicer) & Python (pandas, matplotlib, seaborn)

---

## 1. Latar Belakang

Industri video game global telah mengalami pasang surut selama empat dekade terakhir. Memahami genre dan platform mana yang paling menguntungkan, serta bagaimana tren industri berubah dari waktu ke waktu, sangat penting bagi pengembang game, investor, dan analis pasar.

Analisis ini menggunakan dataset penjualan video game global yang mencakup **16.571 judul game** dari tahun **1980 hingga 2016**. Tujuan analisis adalah memberikan gambaran berbasis data tentang performa genre, distribusi platform per region, pengaruh publisher, dan tren penjualan sepanjang waktu.

---

## 2. Pertanyaan Bisnis

1. **Genre** mana yang penjualan globalnya tertinggi?
2. **Platform** mana yang paling dominan di setiap region (NA, EU, JP)?
3. **Publisher** mana yang paling berpengaruh di pasar global?
4. Bagaimana **tren penjualan global** dari tahun ke tahun?

---

## 3. Data dan Metodologi

### 3.1 Sumber Data

- **Dataset:** Video Game Sales
- **Sumber:** Kaggle
- **Jumlah baris (setelah cleaning):** 16.571
- **Periode:** 1980–2016
- **Kolom utama:** Name, Platform, Year, Genre, Publisher, NA_Sales, EU_Sales, JP_Sales, Other_Sales, Global_Sales

### 3.2 Proses Pembersihan Data

1. **Excel:** Memisahkan sheet `Raw`, `Working`, dan `Clean`. Memperbaiki format angka (koma menjadi titik) dan kolom `Year` yang terkonversi menjadi tanggal.
2. **Python:** Membersihkan nama kolom dari karakter tersembunyi (seperti titik koma) menggunakan `pandas`, menghapus baris yang kosong (`N/A`) pada kolom `Year` dan `Publisher`, serta menghapus data duplikat.
3. Menangani nilai `N/A` dan `(Blanks)`:
   - Baris dengan `Year = N/A` tetap digunakan untuk analisis Genre, Platform, dan Publisher.
   - Baris dengan `Year = N/A` dikecualikan dari analisis tren tahunan.
   - Baris dengan `Platform = Blank` dihapus karena tidak dapat dianalisis.

### 3.3 Pendekatan Analisis

- **Excel:** Menggunakan PivotTable untuk agregasi data dan visualisasi interaktif (Bar Chart, Line Chart, Slicer).
- **Python:** Menggunakan fungsi `groupby` untuk agregasi data dan library `matplotlib` & `seaborn` untuk membuat visualisasi programatik.
