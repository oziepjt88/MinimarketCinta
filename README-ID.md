# Minimarket Cinta Android — proyek APK gratis

Proyek Android WebView yang mengemas versi HTML **Minimarket Cinta - Barcode dan QRIS** sebagai aplikasi Android. APK debug dibuat otomatis melalui GitHub Actions; proyek ini belum menyertakan APK yang sudah dikompilasi.

## Yang disertakan
- HTML kasir, stok, laporan, shift, akun/PIN, pengeluaran, backup/pulihkan, ekspor dan impor yang berasal dari file HTML.
- Penyimpanan browser WebView lokal (offline pada perangkat yang sama).
- Scan barcode melalui pemindai ZXing bawaan aplikasi Android, lalu hasil barcode dikirim ke fungsi HTML.
- Pemilihan gambar QRIS dan file backup melalui pemilih file Android.
- Perintah cetak struk melalui dialog cetak Android.

## Batasan penting
- **Sinkronisasi cloud otomatis belum diaktifkan.** Data tetap lokal; untuk memindahkan data antarperangkat gunakan backup/pulihkan manual. Sinkronisasi otomatis memerlukan backend seperti Firebase/Supabase dan konfigurasi akun; itu tidak bisa dibuat aman tanpa kredensial dan pilihan kebijakan konflik data.
- QRIS hanya menampilkan gambar QRIS dan kasir harus memeriksa pembayaran masuk di aplikasi merchant. Tidak ada konfirmasi pembayaran otomatis.
- APK belum diuji pada perangkat Android fisik. Uji dulu dengan data demo dan jangan gunakan untuk transaksi nyata sampai seluruh alur diuji.
- APK debug belum ditandatangani sebagai rilis produksi.

## Cara membuat APK hanya dengan HP Android
1. Buat akun GitHub gratis atau masuk ke akun GitHub.
2. Buat repository baru bernama `MinimarketCintaAndroid`.
3. Upload semua isi folder proyek ini ke repository (termasuk folder `.github/workflows`). Lebih mudah menggunakan tampilan browser GitHub dalam mode desktop atau aplikasi editor Git yang mendukung upload folder.
4. Buka tab **Actions** di repository, pilih **Build APK Minimarket Cinta**, lalu tekan **Run workflow**. Jika workflow otomatis berjalan setelah upload, tunggu prosesnya selesai.
5. Buka proses yang berstatus hijau, cari bagian **Artifacts**, lalu unduh `Minimarket-Cinta-APK`. Ekstrak ZIP artifact dan temukan `app-debug.apk`.
6. Buka APK di HP dan izinkan pemasangan aplikasi dari sumber tersebut bila Android memintanya. Jangan bagikan APK debug ke publik sebagai rilis resmi.

## Pengujian wajib sebelum dipakai
1. Login admin dan buka shift.
2. Tambah produk demo ke keranjang; uji tunai pas, lebih, dan kurang.
3. Scan barcode dengan kamera.
4. Simpan gambar QRIS resmi, uji pembayaran, dan pastikan transaksi hanya dicatat setelah kasir memverifikasi dana masuk.
5. Uji stok, laporan, kedaluwarsa, pembatalan transaksi, backup/pulihkan, impor/ekspor, dan cetak struk.
6. Tutup dan buka ulang aplikasi untuk memastikan data masih ada.

## Catatan
Jangan masukkan QRIS contoh atau data transaksi nyata saat pengujian. Simpan backup rutin di tempat yang aman.
