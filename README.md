# ✈️ Aviation Customer Experience & Service Recovery Analysis (British Airways)

<img src="Dashboard Image.png" alt="British Airways Review Dashboard" width="1000">

*[Akses dashboard interaktif di Tableau Public](https://public.tableau.com/app/profile/muhammad.raihan.gibran/viz/airways_dashboard_analysis/Dashboard1#1)*

## 📌 Business Context

Dalam industri penerbangan, kepuasan pelanggan adalah faktor penentu loyalitas dan reputasi merek. British Airways menghadapi tantangan berupa fluktuasi kepuasan pelanggan yang sangat tidak stabil, yang berpotensi merusak posisi kompetitif maskapai di tengah ketatnya persaingan rute internasional.

Project ini mensimulasikan peran Data Analyst yang bertugas menganalisis lebih dari 1.300 ulasan pelanggan dari tahun 2016 hingga 2023 — menemukan akar masalah dari sentimen negatif, mengevaluasi konsistensi layanan antar armada pesawat, dan memberikan panduan strategis bagi manajemen operasional untuk menstabilkan kualitas layanan secara berkelanjutan.

## 🎯 Pertanyaan Analisis

1. Fasilitas atau layanan mana yang paling banyak memicu keluhan pelanggan?
2. Apakah kualitas pengalaman terbang konsisten di seluruh tipe pesawat yang dioperasikan?
3. Bagaimana stabilitas performa layanan dari waktu ke waktu, terutama di masa transisi operasional?

## 💡 Key Findings (Executive Summary)

| Temuan | Detail |
|---|---|
| **Layanan dengan skor terendah** | In-Flight Entertainment (rata-rata 1.4/10) |
| **Layanan dengan skor tertinggi** | Cabin Staff Service — satu-satunya layanan yang relatif memuaskan |
| **Pesawat dengan rating terbaik** | Boeing 747-400 dengan skor 4.7 |
| **Pesawat dengan rating terburuk** | Airbus A321 dengan skor 3.6 |
| **Pesawat dengan volume ulasan terbanyak** | Airbus A320 (263 ulasan) dengan skor moderat 4.3 |
| **Pola tren bulanan** | Sangat volatil — skor sering anjlok mendekati angka 1 tanpa pola yang konsisten |

> 🔑 **Insight utama:** Pelanggan British Airways tidak keberatan dengan kru kabin — masalah utamanya ada pada fasilitas. Skor hiburan 1.4 dan makanan 2.4 menunjukkan pelanggan merasa harga tiket yang mereka bayar tidak sebanding dengan pengalaman yang mereka dapatkan. Ini adalah masalah value perception, bukan masalah SDM.

## 📊 Rekomendasi Strategis

**Perombakan In-Flight Entertainment:** Skor 1.4 dari 10 adalah angka kritis yang tidak bisa diabaikan. Manajemen perlu mengalokasikan capital expenditure untuk memperbarui sistem hiburan dalam penerbangan, terutama pada rute jarak jauh di mana penumpang menghabiskan berjam-jam tanpa hiburan yang layak.

**Audit Vendor Katering:** Tinjauan ulang kontrak dengan vendor makanan perlu dilakukan segera. Food & Beverages di skor 2.4 mengonfirmasi bahwa masalah ini bukan sekadar selera, melainkan standar kualitas yang tidak terpenuhi secara konsisten.

**Fokus Retrofit pada Armada A320:** Armada A320 memiliki volume penumpang tertinggi berdasarkan jumlah ulasan yang masuk. Peningkatan kecil pada Seat Comfort — yang saat ini berada di skor 2.9 — pada armada ini akan berdampak langsung pada peningkatan Overall Rating perusahaan secara keseluruhan.

**Replikasi Standar Boeing 747-400:** Lakukan investigasi internal untuk memahami praktik terbaik yang membuat armada 747-400 mendapat rating 4.7. Identifikasi apakah faktor utamanya adalah konfigurasi kursi, kru yang bertugas, atau rute yang dilayani, lalu terapkan standar tersebut ke armada lain untuk meredam volatilitas grafik bulanan.

## 🛠️ Tech Stack & Metodologi

| Tahap | Tools | Yang Dilakukan |
|---|---|---|
| **Data Preparation** | Tableau | Grouping pesawat dengan ulasan kurang dari 50 ke kategori "Others" untuk mengurangi noise dan memfokuskan analisis pada armada utama |
| **Analisis & Visualisasi** | Tableau | Membangun dashboard interaktif dengan Custom Parameters dan Calculated Fields untuk analisis metrik yang bisa dipilih secara dinamis |
| **Pemetaan Geografis** | Tableau | Menggabungkan dataset ulasan dengan data Countries.csv untuk visualisasi distribusi penumpang berdasarkan negara asal |

**Dataset:** 1.351 ulasan pelanggan British Airways (2016-2023) dengan 19 kolom, mencakup rating keseluruhan, seat comfort, cabin staff service, food & beverages, ground service, value for money, entertainment, tipe pesawat, tipe penumpang, kelas kursi, dan rute penerbangan.

## ⚙️ Proses Analisis

### 1. Data Preparation (Tableau)

Dataset ulasan pelanggan digabungkan dengan tabel Countries.csv menggunakan relationship di Tableau untuk mengaktifkan visualisasi peta geografis berdasarkan negara asal penumpang.

Tipe pesawat yang memiliki kurang dari 50 ulasan dikelompokkan ke dalam satu kategori "Others" menggunakan fitur Grouping di Tableau. Langkah ini penting agar analisis armada tidak terdistorsi oleh data yang terlalu sedikit untuk menghasilkan kesimpulan yang valid.

### 2. Analisis & Visualisasi (Tableau)

Dashboard dibangun menggunakan dua fitur Tableau tingkat lanjut:

**Custom Parameters:** Memungkinkan pengguna memilih metrik mana yang ingin ditampilkan secara dinamis — misalnya beralih antara melihat skor rata-rata Entertainment, Food & Beverages, atau Seat Comfort dalam satu tampilan yang sama tanpa perlu membuat chart terpisah untuk setiap metrik.

**Calculated Fields:** Digunakan untuk menghitung nilai rata-rata per metrik layanan berdasarkan filter yang aktif, termasuk filter berdasarkan tipe pesawat, kelas kursi, tipe penumpang, dan rentang waktu.

Hasil analisis divisualisasikan dalam empat bentuk utama: tren rata-rata rating per bulan, perbandingan skor per tipe pesawat, peta distribusi geografis penumpang, dan perbandingan skor per metrik layanan.

## 📁 Struktur Repositori

| File / Folder | Keterangan |
|---|---|
| Airways Review Dashboard.twbx | File Tableau Packaged Workbook berisi dashboard dan data yang sudah terintegrasi |
| Dashboard Image.png | Screenshot tampilan dashboard |
| data/ba_reviews.csv | Dataset utama berisi 1.351 ulasan pelanggan British Airways |
| data/Countries.csv | Dataset pendukung untuk pemetaan geografis berdasarkan negara asal penumpang |

## 📚 Apa yang Saya Pelajari

- Cara menggunakan Custom Parameters di Tableau untuk membangun dashboard yang lebih fleksibel — satu chart bisa menampilkan berbagai metrik berbeda tanpa perlu duplikasi visualisasi
- Pentingnya keputusan analitis dalam pengelompokan data — memutuskan untuk menggabungkan pesawat dengan ulasan sedikit ke kategori "Others" adalah langkah yang mencegah kesimpulan yang menyesatkan dari data yang tidak representatif
- Membaca data kepuasan pelanggan memerlukan konteks — skor staf kabin yang relatif baik justru membuat skor fasilitas yang rendah semakin mencolok karena kesenjangannya terlihat jelas
- Volatilitas tren bulanan bisa menjadi indikator masalah sistemik seperti ketiadaan SOP, bukan sekadar variasi normal

*Disclaimer: Project ini menggunakan dataset publik ulasan pelanggan British Airways sebagai simulasi Data Analysis dan Business Intelligence.*
