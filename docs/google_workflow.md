# Alur Colab Google Sheets dan Looker Studio

## Berkas yang sudah dibuat

- Colab: https://colab.research.google.com/drive/1MtU4msonzBqRCB_1MaiDwv3eJ9Vk0NpL
- Sheets: https://docs.google.com/spreadsheets/d/1bcIDtRnMCotxuGRRCP31Cyo-Fu1aX4mAwmlVx1b6W2M/edit
- Docs: https://docs.google.com/document/d/1k1ymVVeFtOVYi7j58q1Gu9uW4wmD4kSNu4aPtlOLc00/edit

Semua mengikuti izin akun pemilik. Tautan tidak otomatis memberi akses publik.

## Menggunakan Sheets langsung

Buka Dashboard. Pilih tahun B3, bulan E3, toko H3. Pilih Semua untuk jaringan. Ringkasan mengikuti ketiganya; grafik mengikuti tahun dan toko. Ini sudah dapat dipakai tanpa Colab.

## Menjalankan ulang Colab dan mengirim data

1. Buka notebook dan simpan salinan jika ingin bereksperimen.
2. Aktifkan baris instalasi `%pip` pada bagian 1 bila diperlukan. Jalankan analisis berurutan sampai bagian 9.
3. URL Sheets sudah diisi pada bagian 10. Ubah RUN_GOOGLE_SYNC menjadi True. Login dengan akun Google yang punya izin edit ke Sheets tersebut.
4. Sel mengganti isi Weekly_Data. Jumlah baris tidak ditumpuk. Dashboard tetap ada.
5. Cocokkan total dan jumlah minggu dengan angka uji di bawah.

Tanggal dikirim sebagai nomor tanggal spreadsheet, lalu diformat yyyy-mm-dd. Tidak ada password atau token di dalam notebook. Saat login belum dilakukan, koneksi Colab ke Sheets belum aktif. Data yang sekarang ada di Sheets dimuat saat pembuatan proyek, bukan melalui sesi login Colab pengguna.

Rentang dashboard saat ini berakhir di baris 6436 dan memakai 45 toko. Jika dataset berubah jumlah toko atau panjangnya, perluas semua rentang formula, pembagi minggu jaringan, serta pilihan toko. Jangan menganggap formula lama otomatis menampung cakupan baru. Sinkronisasi dijalankan manual dan tidak memperbarui teks laporan Google Docs.

## Menghubungkan Looker Studio

1. Buka https://lookerstudio.google.com/ dengan akun yang mempunyai akses ke Sheets. Buat laporan kosong.
2. Pilih tambah data → Google Sheets → Walmart Sales Analysis Dashboard → Weekly_Data. Gunakan header baris pertama. Pilih rentang A1:M6436 agar catatan sumber di kolom O tidak terbaca sebagai field.
3. Periksa Date bertipe Date; Store menjadi dimensi. Weekly_Sales menjadi angka mata uang USD dengan agregasi SUM. Year dan Month dapat dipakai sebagai dimensi numerik atau teks sesuai kontrol.
4. Tambahkan kartu `SUM(Weekly_Sales)`, kartu `COUNT_DISTINCT(Date)`, grafik waktu dengan dimensi Date dan metrik SUM(Weekly_Sales), serta grafik batang dengan dimensi Store.
5. Tambahkan metrik terhitung `SUM(Weekly_Sales) / COUNT_DISTINCT(Date)` untuk rata-rata penjualan per minggu pada toko terpilih. `AVG(Weekly_Sales)` mempunyai arti rata-rata per toko per minggu.
6. Tambahkan kontrol rentang tanggal dan dropdown Store. Atur rentang awal 1–30 September 2011. Dataset historis ini akan terlihat kosong jika default memakai 28 hari terakhir.
7. Aktifkan cross-filter grafik bila ingin klik toko untuk menyaring grafik lain. Setiap kontrol harus memakai sumber Weekly_Data yang sama.
8. Uji angka September di bawah. Pilih kembali rentang seluruh dataset jika ingin melihat pola historis.

Dashboard Looker Studio belum dibuat dalam pengerjaan ini. Langkah ini adalah panduan pemasangan, bukan tautan ke laporan yang sudah aktif. Sheets merupakan dashboard interaktif yang sudah dibuat dan diuji. Penyegaran Looker mengikuti mekanisme konektornya; menjalankan Colab tidak menjamin laporan Looker menyegarkan seketika.

## Angka uji

| Pilihan | Total USD | Minggu | Rata-rata per minggu USD |
| --- | ---: | ---: | ---: |
| 2011 bulan 9 semua toko | 220.847.738,42 | 5 | 44.169.547,68 |
| 2012 bulan 9 semua toko | 180.645.544,47 | 4 | 45.161.386,12 |
| 2012 bulan 9 toko 14 | 6.547.171,22 | 4 | 1.636.792,81 |

Tampilan dan pemisah angka mengikuti locale akun. Nilai harus tetap sama sampai toleransi satu sen. Tanggal minggu ditempatkan ke bulan tanggal sumber dan tidak dipisahkan secara harian.

## Referensi resmi

- https://colab.research.google.com/notebooks/io.ipynb
- https://docs.gspread.org/en/master/advanced.html
- https://docs.cloud.google.com/data-studio/connect-to-google-sheets
- https://docs.cloud.google.com/data-studio/tutorial-create-a-google-sheets-data-source
