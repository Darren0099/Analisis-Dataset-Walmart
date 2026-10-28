# Catatan validasi

Tanggal 28 Oktober 2026.

## Sudah diperiksa

- Sel analisis Python pada notebook dieksekusi berurutan menggunakan Python standar. Keluaran teks dan gambar disimpan dalam ipynb. Ini bukan eksekusi kernel Jupyter atau Colab.
- Sumber 6.435 baris dan delapan kolom. Tidak ada nilai kosong, duplikasi, konflik kunci, atau minggu toko yang hilang. Setiap toko memiliki 143 minggu.
- Total detail, agregasi bulan, dan agregasi toko sama dengan USD 6.737.218.987,11.
- Pasangan 2011 dan 2012 memiliki 43 minggu untuk masing-masing 45 toko.
- Dashboard lokal dihitung ulang. Perubahan tahun, toko, dan bulan tanpa data diperiksa terhadap perhitungan detail independen. Tidak ditemukan kesalahan formula pada pemindaian.
- Setelah impor native Google Sheets, pilihan tahun 2012 menghasilkan September USD 180.645.544,47 dan empat minggu. Pilihan toko 14 menghasilkan USD 6.547.171,22. Semua dipulihkan ke September 2011 dan Semua, USD 220.847.738,42 dan lima minggu.
- Metadata Google Sheets mengonfirmasi dua tab, satu grafik, validasi tiga pilihan, dan tanggal numerik dengan format tanggal. Gambar pratinjau lokal diperiksa untuk kedua tab. Tampilan browser Google Sheets belum diperiksa langsung.
- Laporan Word dirender dan enam halaman diperiksa; tidak ada halaman kosong, tabel terpotong, atau gambar bertumpuk. Judul disanitasi sebelum impor native Google Docs.

## Belum diuji langsung

- Instalasi KaggleHub dan autentikasi akun pada sesi Colab pengguna.
- Sinkronisasi Colab ke Sheets melalui login pengguna. Tabel Sheets awal dimuat melalui impor hasil analisis lokal.
- Dashboard Looker Studio terpisah. Panduan, rumus, dan angka uji tersedia, tetapi laporannya belum dibuat.
- Repository dibuat oleh pemilik pada Darren0099/Analisis-Dataset-Walmart. Paket analisis dipublikasikan ke branch main melalui koneksi GitHub.

Dataset bersifat historis. Versi sumber dikenali dengan SHA256, bukan nomor versi Kaggle yang belum direkam. Rentang formula dashboard dibatasi ke snapshot 6.435 baris dan 45 toko. Perluas formula jika cakupan berubah.
