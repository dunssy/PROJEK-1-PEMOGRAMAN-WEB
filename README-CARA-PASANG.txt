# PATCH RAPI FINAL - MEY SALON

Salin file sesuai struktur folder berikut ke project kamu.
Jangan simpan di folder lain karena path include/script sudah disesuaikan dengan project yang kamu kirim.

## File utama yang wajib diganti
1. config/controller.php
   - tambah_layanan dan edit_layanan sudah menyimpan harga_min, harga_max, keterangan_harga, gambar_layanan.
   - upload gambar layanan masuk ke uploads/layanan.

2. user/booking-controller.php
   - total_dp diambil dari input customer, bukan dari SUM(harga_min).
   - minimal DP divalidasi Rp 50.000.
   - jadwal booking dikirim ke JS sebagai object: jam_mulai, jam_selesai, layanan, status.

3. user/views/section-layanan.php
   - data-price-max dobel sudah dibuang.
   - gambar layanan bisa membaca dari uploads/layanan atau layout/images.

4. layout/js/booking-script.js
   - fungsi disable jam dobel sudah dirapikan.
   - booking bentrok dicek memakai jam_mulai dan jam_selesai.
   - hari Rabu otomatis nonaktif.
   - range harga tetap memakai harga_min dan harga_max.

5. admin/detail-booking.php
   - proses Done Booking menyimpan total final admin ke transaksi.total_bayar.
   - status booking menjadi Done.
   - logika lama sisa_pembayaran/status_pembayaran/tanggal_pelunasan dihapus.

6. admin/pendapatan-walkin.php
   - insert walk-in tidak lagi memakai kolom tambahan_harga.

## File JS/CSS yang saya pisahkan
- layout/js/booking-script.js      => booking customer
- layout/js/booking-detail.js      => detail booking admin
- layout/js/detail-layanan.js      => detail layanan admin
- layout/js/main.js                => landing/user UI
- layout/js/main-admin.js          => admin UI
- layout/css/style.css             => user/landing
- layout/css/style-admin.css       => admin

## Catatan penting
- Pastikan folder uploads/layanan boleh ditulis oleh server.
- Jika halaman user masih memanggil ../layout/js/booking-script.js, simpan file booking-script.js ke layout/js/.
- Setelah mengganti file, refresh browser dengan Ctrl + F5.
