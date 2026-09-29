# Kebijakan Privasi — Daily Face Check

Berlaku sejak: 29 September 2026

Daily Face Check ("aplikasi") adalah aplikasi Android untuk mencatat foto wajah harian. Kebijakan
ini menjelaskan data apa yang diproses aplikasi, ke mana data itu pergi, dan bagaimana Anda dapat
menghapusnya.

Pengelola aplikasi: **Rizki Ashari**
Kontak: **adioebipu@gmail.com**

---

## 1. Ringkasan singkat

- Aplikasi **tidak memiliki server sendiri**. Tidak ada backend, tidak ada basis data milik
  pengelola.
- Foto hanya disimpan di **perangkat Anda** dan di **Google Drive milik Anda sendiri**.
- Pengelola aplikasi **tidak dapat** melihat, membaca, atau mengunduh foto Anda.
- Tidak ada iklan, tidak ada pelacakan, dan tidak ada analitik pihak ketiga.
- Data tidak dijual atau dibagikan ke pihak lain.

---

## 2. Data yang diproses

### 2.1 Foto wajah

Aplikasi meminta Anda mengambil **satu foto wajah melalui kamera depan** setiap hari. Pengambilan
foto hanya bisa dilakukan dari kamera aplikasi; aplikasi tidak menyediakan pilihan dari galeri.

Pengambilan foto dilakukan **atas tindakan Anda sendiri**. Aplikasi tidak mengambil foto secara
diam-diam di latar belakang, dan tidak ada berkas yang diunggah sebelum Anda menyetujui unggahan.

### 2.2 Pemeriksaan wajah

Sebelum foto disimpan, aplikasi memeriksa foto menggunakan **Google ML Kit Face Detection** untuk
memastikan ada tepat satu wajah pada posisi yang wajar dan gambar tidak buram.

Pemeriksaan ini **berjalan sepenuhnya di perangkat Anda**. Foto tidak dikirim ke Google ML Kit
maupun ke layanan lain untuk keperluan pemeriksaan ini.

### 2.3 Data yang disimpan di perangkat

Setelah foto berhasil diunggah, foto ukuran penuh dihapus dari perangkat, kecuali Anda memilih
menyimpannya. Yang tetap tersimpan di perangkat adalah:

- Nama berkas, tanggal dan jam pengambilan
- ID berkas di Google Drive serta tautannya
- Status unggah (berhasil, menunggu, atau gagal)
- Ukuran berkas
- Thumbnail berukuran kecil, dipakai untuk menampilkan halaman riwayat

### 2.4 Data akun Google

Saat Anda menghubungkan Google Drive, aplikasi membaca **nama tampilan, alamat email, dan informasi
kuota penyimpanan** akun tersebut — hanya untuk menampilkan status koneksi dan sisa ruang di halaman
Pengaturan.

Aplikasi **tidak pernah** meminta atau menyimpan password Google Anda.

---

## 3. Google Drive

### 3.1 Izin yang diminta

Aplikasi meminta **satu** izin Google, yaitu yang paling sempit:

```
https://www.googleapis.com/auth/drive.file
```

Izin ini, yang ditampilkan Google sebagai *"Melihat, mengedit, membuat, dan menghapus hanya file
Google Drive tertentu yang Anda gunakan dengan aplikasi ini"*, berarti aplikasi **hanya** dapat
mengakses berkas dan folder yang **dibuatnya sendiri**. Aplikasi tidak dapat melihat berkas lain di
Drive Anda.

Aplikasi **tidak** meminta izin `drive` maupun `drive.readonly` (akses penuh ke seluruh Drive).

### 3.2 Lokasi penyimpanan

Foto diunggah ke Drive pada akun Google yang Anda hubungkan sendiri, dengan struktur:

```
Daily Face Check/
  TAHUN/
    BULAN/
      YYYY-MM-DD_HH-mm-ss.jpg
```

Karena foto berada di Drive milik Anda, Anda dapat mengakses, mengunduh, memindahkan, atau
menghapusnya langsung melalui <https://drive.google.com> tanpa melalui aplikasi.

### 3.3 Penggunaan data Google (Limited Use)

Penggunaan informasi yang diterima aplikasi dari Google API mematuhi
[Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy),
termasuk persyaratan **Limited Use**. Secara khusus:

- Data Google hanya dipakai untuk menyediakan fitur yang terlihat oleh Anda, yaitu menyimpan foto
  harian ke Drive Anda sendiri.
- Data Google **tidak** ditransfer ke pihak ketiga, kecuali sejauh diperlukan untuk menyediakan
  fitur tersebut, untuk mematuhi hukum yang berlaku, atau sebagai bagian dari merger atau akuisisi
  (yang akan diumumkan lebih dahulu).
- Data Google **tidak** dipakai atau ditransfer untuk keperluan periklanan.
- Data Google **tidak** dipakai untuk menentukan kelayakan kredit atau untuk pemberian pinjaman.
- Manusia **tidak** membaca isi Drive Anda. Pengelola aplikasi tidak memiliki akses teknis ke akun
  Google pengguna.

---

## 4. Yang tidak dilakukan aplikasi

- Tidak ada pengenalan wajah untuk mengidentifikasi siapa pemilik akun.
- Tidak ada pencocokan identitas, dan tidak ada verifikasi bahwa orang pada foto adalah pemilik akun.
- Tidak ada pelatihan model AI menggunakan foto Anda.
- Tidak ada pengiriman foto ke server pengelola atau ke layanan pihak ketiga mana pun.
- Tidak ada iklan, pelacak perilaku, maupun SDK analitik.
- Tidak ada penjualan atau penyewaan data.

**Penting:** deteksi wajah pada aplikasi ini hanya memeriksa **jumlah dan posisi** wajah. Aplikasi
ini bukan alat verifikasi identitas dan tidak dapat menjamin mampu mendeteksi semua foto palsu atau
penyamaran.

---

## 5. Izin Android yang diminta

| Izin | Alasan |
| --- | --- |
| `CAMERA` | Mengambil foto wajah harian dari kamera depan |
| `INTERNET`, `ACCESS_NETWORK_STATE` | Mengunggah foto ke Google Drive milik Anda |
| `POST_NOTIFICATIONS` | Menampilkan pengingat harian |
| `SCHEDULE_EXACT_ALARM` | Menjadwalkan pengingat tiap jam dengan tepat waktu |
| `RECEIVE_BOOT_COMPLETED` | Menyusun ulang jadwal pengingat setelah perangkat dinyalakan ulang |
| `VIBRATE`, `WAKE_LOCK` | Getaran dan membangunkan perangkat singkat saat notifikasi muncul |

Aplikasi **tidak** meminta izin mikrofon maupun akses penyimpanan bersama (`READ_EXTERNAL_STORAGE`,
`WRITE_EXTERNAL_STORAGE`). Foto hanya ditulis ke penyimpanan privat aplikasi sebelum diunggah.

Cadangan otomatis Android dinonaktifkan (`allowBackup="false"`) agar foto tidak ikut tercadangkan
ke layanan cadangan cloud.

---

## 6. Penyimpanan dan penghapusan data

### 6.1 Berapa lama data disimpan

Data disimpan sampai Anda menghapusnya sendiri. Aplikasi tidak menghapus data Anda secara otomatis
berdasarkan waktu.

### 6.2 Cara menghapus

- **Menghapus satu tanggal:** buka halaman Riwayat, pilih tanggal tersebut, lalu gunakan opsi hapus.
- **Menghapus seluruh data:** buka halaman **Pengaturan** → **Hapus foto & riwayat**. Anda dapat
  memilih untuk **menghapus berkas di Google Drive sekaligus**.
- **Memutuskan akun:** **Pengaturan** → **Putuskan**. Setelah diputuskan, aplikasi berhenti
  mengunggah sampai Anda menghubungkan akun kembali. Foto yang sudah tersimpan di Drive **tidak**
  dihapus dan tetap menjadi milik Anda.
- **Menghapus langsung dari Drive:** foto selalu dapat Anda hapus sendiri melalui
  <https://drive.google.com>.

Untuk menghentikan akses aplikasi ke akun Google Anda sepenuhnya, kunjungi
<https://myaccount.google.com/permissions> dan hapus aplikasi ini dari daftar.

---

## 7. Keamanan

- Password Google tidak pernah diminta dan tidak pernah disimpan.
- Access token dan refresh token tidak pernah ditulis ke kode sumber, berkas konfigurasi, maupun log
  aplikasi.
- Aplikasi tidak membuka koneksi HTTP tanpa enkripsi (`usesCleartextTraffic="false"`).
- Pemeriksaan wajah, penghitungan ketajaman gambar, dan pemrosesan thumbnail berjalan di perangkat.

---

## 8. Anak-anak

Aplikasi ini tidak ditujukan untuk anak di bawah usia 13 tahun, dan pengelola tidak dengan sengaja
mengumpulkan data dari anak-anak.

---

## 9. Perubahan kebijakan ini

Bila kebijakan ini berubah, tanggal *Berlaku sejak* di bagian atas akan diperbarui. Perubahan yang
bersifat material akan diumumkan melalui halaman ini sebelum mulai berlaku.

---

## 10. Kontak

Pertanyaan tentang kebijakan ini dapat disampaikan ke:

**adioebipu@gmail.com**
