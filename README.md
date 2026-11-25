# MediRemind

Aplikasi Android untuk membantu pasien mencatat konsumsi obat dan membantu dokter memantau kepatuhan pasien dari jarak jauh. Admin mengelola pengguna dan memverifikasi akun dokter.

> Status: tahap awal pengembangan. Roadmap ini adalah rencana kerja, bukan daftar fitur yang sudah selesai.

## Tujuan proyek

- Pasien melihat jadwal obat harian, mengonfirmasi obat yang diminum, dan meninjau riwayat.
- Dokter mengelola pasien, resep, jadwal, dan memantau kepatuhan.
- Admin mengelola akun dan memverifikasi dokter.
- Dokter mengekspor laporan kepatuhan ke CSV dan membacanya kembali dari penyimpanan lokal.

## Teknologi dan batasan

- Aplikasi native Android: Kotlin, Jetpack Compose, MVVM, Navigation Compose.
- Backend REST API: Node.js dan Express; database MySQL.
- Komunikasi HTTPS dengan JSON; autentikasi JWT dan refresh token.
- Di luar versi 1.0: pengingat notifikasi, stok obat, WebSocket, pembayaran, dan integrasi rumah sakit.

## Rencana target per minggu

### Minggu 1 — Fondasi sistem
- [ ] Tetapkan struktur aplikasi Android, backend, dan lapisan MVVM.
- [ ] Rancang relasi User, Resep, Jadwal, dan Log Konsumsi.
- [ ] Siapkan proyek backend, MySQL, konfigurasi lingkungan, dan panduan menjalankan.
- **Hasil:** kerangka aplikasi/backend berjalan dan rancangan data terdokumentasi.

### Minggu 2 — Registrasi, autentikasi, dan sesi
- [ ] Buat registrasi pasien/dokter dengan email unik dan password ter-hash.
- [ ] Implementasikan login, access token, refresh token, dan logout.
- [ ] Terapkan pembatasan akses berdasarkan role; dokter baru menunggu verifikasi.
- **Hasil:** alur autentikasi serta navigasi sesuai role berfungsi.

### Minggu 3 — Pengelolaan pengguna oleh Admin
- [ ] Tampilkan daftar pengguna, pencarian nama/email, dan filter role/status.
- [ ] Buat tambah/ubah data, verifikasi dokter, penonaktifan, dan penghapusan dengan konfirmasi.
- **Hasil:** Admin dapat mengelola akun melalui aplikasi dan API.

### Minggu 4 — Pengelolaan pasien oleh Dokter
- [ ] Hubungkan pasien melalui email atau kode pasien.
- [ ] Buat daftar, detail, pencarian, catatan dokter, dan pemutusan hubungan.
- [ ] Batasi dokter pada data pasien yang terhubung dengannya.
- **Hasil:** hubungan dokter-pasien dan aturan akses berjalan.

### Minggu 5 — Resep
- [ ] Buat resep dengan nama obat, dosis, tanggal mulai, durasi, dan catatan.
- [ ] Validasi kolom wajib dan durasi positif.
- [ ] Sediakan lihat untuk pasien serta ubah/hapus untuk dokter.
- [ ] Tangani penghapusan jadwal dan log terkait.
- **Hasil:** resep dapat dikelola sesuai role.

### Minggu 6 — Jadwal minum
- [ ] Tambah, lihat, ubah, dan hapus jam minum pada resep.
- [ ] Cegah jam ganda dan tampilkan jadwal hari ini untuk resep aktif.
- **Hasil:** jadwal harian dapat digunakan pasien.

### Minggu 7 — Konfirmasi dan riwayat konsumsi
- [ ] Tampilkan status menunggu, diminum, atau terlewat.
- [ ] Simpan konfirmasi beserta waktu dan catatan pasien.
- [ ] Cegah konfirmasi ganda; izinkan koreksi/pembatalan pada hari yang sama.
- [ ] Tambahkan riwayat dengan filter tanggal atau obat.
- **Hasil:** pasien dapat mencatat konsumsi dan menelusuri riwayatnya.

### Minggu 8 — Dashboard kepatuhan Dokter
- [ ] Hitung persentase dari jadwal yang sudah jatuh tempo.
- [ ] Tampilkan ringkasan dan indikator kepatuhan per pasien.
- [ ] Sediakan riwayat dan catatan dengan filter rentang tanggal.
- [ ] Muat ulang data melalui tarik-untuk-menyegarkan.
- **Hasil:** dokter dapat memantau pasien yang ditanganinya.

### Minggu 9 — Ekspor dan laporan tersimpan
- [ ] Ekspor riwayat dan persentase kepatuhan ke CSV lokal.
- [ ] Tampilkan laporan tersimpan dan buka file untuk dibaca kembali.
- [ ] Tampilkan pesan bila penyimpanan gagal.
- **Hasil:** laporan lokal dapat diekspor, dibuka, dan dibaca ulang.

### Minggu 10 — Integrasi dan persiapan demo
- [ ] Uji alur utama Pasien, Dokter, dan Admin.
- [ ] Periksa validasi server, kepemilikan data, HTTPS, dan penanganan token.
- [ ] Periksa performa, pesan loading/error, dokumentasi endpoint, dan panduan penggunaan.
- **Hasil:** kandidat demo versi 1.0 dengan alur inti dan dokumentasi tervalidasi.

## Kriteria keberhasilan

- Pasien dapat mengonfirmasi konsumsi dari beranda dalam paling banyak dua ketukan.
- Data hanya dapat diakses oleh pasien dan dokter yang berwenang.
- Persentase kepatuhan konsisten dengan jadwal yang sudah jatuh tempo.
- CSV dapat disimpan dan dibaca kembali di aplikasi.

> Durasi tiap minggu adalah target perencanaan dan dapat disesuaikan dengan progres.
