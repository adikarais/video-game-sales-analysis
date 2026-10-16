# Ringkasan Analisis: Penjualan Video Game Global (1980–2016)

**Penulis:** Adika Rais Muhammad Abror
**Tanggal:** Jumat, 16 Oktober 2026
**Tools:** Microsoft Excel (PivotTable, Chart, Slicer)

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

1. Memisahkan sheet `Raw` (data asli), `Working` (data kerja), dan `Clean` (data siap analisis).
2. Memperbaiki format angka dari koma desimal (format Eropa) menjadi titik desimal.
3. Memperbaiki kolom `Year` yang terkonversi menjadi tanggal karena pengaturan regional Excel.
4. Menghapus baris duplikat.
5. Menangani nilai `N/A` dan `(Blanks)` pada kolom `Year` dan `Publisher`:
   - Baris dengan `Year = N/A` tetap digunakan untuk analisis Genre, Platform, dan Publisher.
   - Baris dengan `Year = N/A` dikecualikan dari analisis tren tahunan.
   - Baris dengan `Platform = Blank` dihapus karena tidak dapat dianalisis.

### 3.3 Pendekatan Analisis

- **PivotTable** digunakan untuk agregasi data per Genre, Platform, Publisher, dan Year.
- **Visualisasi** menggunakan Bar Chart (untuk perbandingan kategori) dan Line Chart (untuk tren waktu).
- **Dashboard interaktif** dilengkapi Slicer agar pengguna dapat memfilter data secara dinamis.

---

## 4. Temuan Utama

### 4.1 Genre vs Global Sales

| Peringkat | Genre | Kontribusi |
|---|---|---|
| 1 | Action | 19,63% |
| 2 | Sports | 14,92% |
| 3 | Shooter | 11,63% |
| 4 | Role-Playing | 10,40% |
| 5 | Platform | 9,32% |
| 6 | Misc | 9,08% |
| 7 | Racing | 8,21% |
| 8 | Fighting | 5,03% |
| 9 | Simulation | 4,40% |
| 10 | Puzzle | 2,75% |
| 11 | Adventure | 2,67% |
| 12 | Strategy | 1,96% |

**Insight:**

- **Action** adalah genre teratas dengan kontribusi **19,63%** dari total penjualan global.
- **Tiga genre teratas** (Action, Sports, Shooter) menyumbang **46,18%** dari total penjualan global — hampir setengah pasar.
- **Strategy** adalah genre terendah (1,96%), menunjukkan preferensi pasar yang sangat terpusat pada genre-genre aksi dan olahraga.

### 4.2 Platform vs Region (NA, EU, JP)

| Platform | NA (juta) | EU (juta) | JP (juta) | Other (juta) |
|---|---|---|---|---|
| X360 | 601,05 | 280,58 | 12,18 | 85,54 |
| PS2 | 583,84 | 339,29 | 139,19 | 193,44 |
| Wii | 507,71 | 268,38 | 69,33 | 80,61 |
| PS3 | 392,25 | 343,67 | 79,74 | 141,92 |
| DS | 390,71 | 194,65 | 175,57 | 60,53 |
| PS | 336,51 | 213,60 | 139,82 | 40,91 |
| GBA | 187,54 | 75,25 | 47,33 | 7,73 |
| XB | 186,69 | 60,95 | 1,38 | 8,72 |
| N64 | 139,02 | 41,06 | 34,22 | 4,38 |
| GC | 133,46 | 38,71 | 21,58 | 5,18 |

**Insight:**

- **X360** adalah platform teratas di NA (601 juta), namun hampir tidak ada di JP (12 juta).
- **Nintendo DS** adalah platform terkuat di JP (175,57 juta), mengalahkan PS2 dan PS.
- **PS2** adalah satu-satunya platform yang kuat di ketiga region sekaligus (NA 584, EU 339, JP 139).
- **Xbox (XB)** hampir tidak ada di JP (1,38 juta) — menunjukkan selera pasar Jepang sangat berbeda dengan NA/EU.

### 4.3 Publisher

| Peringkat | Publisher | Total Sales (juta) | % dari Total |
|---|---|---|---|
| 1 | Nintendo | 1.786,54 | 20,0% |
| 2 | Electronic Arts | 1.110,32 | 12,4% |
| 3 | Activision | 727,46 | 8,2% |
| 4 | Sony Computer Entertainment | 607,50 | 6,8% |
| 5 | Ubisoft | 474,72 | 5,3% |
| 6 | Take-Two Interactive | 399,54 | 4,5% |
| 7 | THQ | 340,77 | 3,8% |
| 8 | Sega | 272,99 | 3,1% |
| 9 | Microsoft Game Studios | 245,79 | 2,8% |
| 10 | Atari | 157,22 | 1,8% |

**Insight:**

- **Nintendo menguasai 20% pasar global** dengan total 1.786,54 juta unit — jauh di atas kompetitor.
- **Tiga publisher teratas** (Nintendo, Electronic Arts, Activision) menyumbang **40,6%** dari total penjualan global.
- **Nintendo juga dominan di JP** (455 juta), sementara EA hampir tidak ada di JP (14 juta).
- **Sony Computer Entertainment** adalah satu-satunya publisher non-Nintendo yang kuat di ketiga region.

### 4.4 Tren Penjualan Global per Tahun

**Insight:**

- **Puncak industri** terjadi pada periode **2008–2009**, dengan penjualan global sekitar **678 juta unit**.
- Setelah 2009, penjualan **turun tajam** — pada 2016 di bawah 100 juta unit.
- **Pertumbuhan pesat** terjadi antara 1996–2008, seiring dengan munculnya konsol generasi ke-5 (PS1), ke-6 (PS2), dan ke-7 (PS3, X360, Wii).
- **Penurunan setelah 2009** kemungkinan dipengaruhi oleh pergeseran industri ke **mobile gaming** dan **digital download**, yang tidak tercakup dalam dataset ini.

---

## 5. Rekomendasi

### 5.1 Untuk Publisher dan Pengembang Game

1. **Fokus pada genre Action, Sports, dan Shooter** — ketiganya menyumbang hampir 50% pasar global.
2. **Sesuaikan strategi per region:**
   - **NA dan EU:** prioritaskan platform Xbox dan PlayStation.
   - **JP:** prioritaskan Nintendo dan PlayStation.
3. **Hindari merilis game Xbox-only untuk pasar Jepang** — platform ini hampir tidak diterima di sana.
4. **Pelajari strategi Nintendo** — mereka menguasai 20% pasar global dengan pendekatan first-party yang kuat.

### 5.2 Untuk Investor dan Analis Industri

1. **Perlu studi lanjutan** dengan data setelah 2016 untuk memahami tren pasca-konsol generasi ke-7.
2. **Pertimbangkan faktor eksternal** seperti pergeseran ke mobile gaming dan digital download yang tidak tercakup dalam dataset.

---

## 6. Keterbatasan Data

1. Dataset **tidak mencakup data penjualan setelah 2016 secara lengkap**, sehingga analisis tren dibatasi hingga 2016.
2. Sekitar **300+ baris** memiliki `Year = N/A` dan dikecualikan dari analisis tren tahunan. Baris ini tetap digunakan untuk analisis Genre, Platform, dan Publisher.
3. Beberapa baris memiliki `Publisher = Unknown` dan dipertahankan karena Publisher bukan variabel utama analisis.
4. Data penjualan bersifat **agregat global** dan tidak memuat informasi digital download atau mobile gaming.

---

## 7. Lampiran

- **Dashboard:** `VideoGameSales_Dashboard.xlsx`
- **Screenshot Dashboard:** `dashboard.png`
- **Dataset asli:** `data/vgsales.csv`

---

*Laporan ini dibuat sebagai bagian dari portofolio Data Analyst.*