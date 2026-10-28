# Kamus data dan ukuran

| Kolom | Arti dan pemakaian |
| --- | --- |
| Store | ID toko; tidak memuat nama atau lokasi |
| Date | Tanggal rekap mingguan; sumber dd-mm-yyyy |
| Weekly_Sales | Nilai penjualan mingguan, diperlakukan sebagai USD |
| Holiday_Flag | Label libur sumber, 0 atau 1; tidak mencakup semua minggu ramai |
| Temperature | Nilai suhu sesuai sumber; dipakai untuk korelasi tanpa konversi unit |
| Fuel_Price | Harga bahan bakar sesuai sumber; tanpa konversi unit |
| CPI | Indeks harga konsumen; dipakai untuk pemeriksaan hubungan statistik |
| Unemployment | Ukuran pengangguran sesuai sumber |
| Year dan Month | Tahun dan nomor bulan dari Date |
| Year_Month | Kunci bulan dalam bentuk YYYY-MM |
| Holiday_Label | Nama Nonlibur atau Libur dari Holiday_Flag |
| ISO_Week | Nomor minggu ISO untuk pasangan antar tahun |

Total penjualan = SUM(Weekly_Sales). Rata-rata jaringan per minggu = total / jumlah tanggal minggu unik. Rata-rata toko per minggu = total / jumlah baris toko-minggu. Pangsa = penjualan toko / total. YoY persen = (penjualan 2012 pada minggu sebanding / penjualan 2011 pada minggu sebanding − 1) × 100. CV persen = simpangan baku mingguan / rata-rata mingguan × 100; ini ukuran variasi relatif, bukan skor efisiensi.

Tabel data lengkap teramati untuk 45 toko pada 143 minggu. Asumsi kelengkapan diperiksa oleh notebook. Penjualan tidak disamakan dengan laba. Korelasi tidak disamakan dengan sebab.
