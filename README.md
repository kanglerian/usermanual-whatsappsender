![](/images/logo.png ':size=230')

> WhatsApp Sender adalah aplikasi pengiriman pesan massal. Aplikasi ini memungkinkan Anda untuk mengirim pesan tanpa batas ke beberapa pengguna menggunakan satu akun. 

- Kirim gambar dengan satu klik
- Tidak perlu menyimpan kontak
- Keamanan Autentikasi lewat Smartphone

---

# Instalasi

Sebelum memakai Aplikasi Whatsapp Sender, maka kita harus menginstall terlebih dahulu di komputer / laptop atau server kita dengan 4 hal ini yang wajib ada di komputer:

1. **Server** Whatsapp Sender (terdapat di dalam paket) atau [Klik disini](/ ':target=_blank')
2. **Aplikasi** Whatsapp Sender (terdapat di dalam paket) atau [Klik disini](/ ':target=_blank')
3. **NodeJS** (tersedia di dalam paket) atau [Klik disini](https://drive.google.com/drive/folders/1er_PmXtLenmg2AnUm2-y_gI6pEnQf646?usp=share_link ':target=_blank')
4. **Git** (tersedia di dalam paket) atau [Klik disini](https://drive.google.com/drive/folders/1er_PmXtLenmg2AnUm2-y_gI6pEnQf646?usp=share_link ':target=_blank')

---

## Instalasi NodeJS

Install NodeJS versi ```v.18.13.0-x64.msi``` bisa [Download disini](https://nodejs.org/en/download/ ':target=_blank')

---

## Instalasi Git

Install Git dan sesuaikan dengan bit yang digunakan. Contohnya: Standalone Installer ```64-bit Git for Windows Setup```.

[Download Git disini](https://git-scm.com/download/win ':target=_blank')

Setelah selesai Instalasi NodeJS dan Git, maka kita Install PM2 untuk menjalankan server.

1. Buka git bash di Desktop / Halaman awal dengan cara klik kanan dan pilih ```git bash```
2. Ketik perintah ```npm install pm2 -g```
3. Ketik perintah ```npm install pm2-windows-startup -g```
4. Ketik perintah ```pm2-startup install```

---

## Instalasi Whatsapp Sender Desktop

Klik 2x aplikasi ```whatsapp-sender.exe``` yang sudah disediakan di dalam paket. Kemudian tunggu hingga selesai!

---

## Instalasi Server

### Windows

Ada dua macam aplikasi server yang kita sediakan. Dengan git repository atau dengan file compress ```.zip```.

#### Windows (.zip)

1. Pastikan kamu sudah memiliki Server Whatsapp Sender
2. Copy ke direktori ```C:/``` dan letakan di luar berdekatan dengan folder Windows
3. Buka folder `whatsapp-sender-server` kemudian klik kanan dan pilih ```Git bash```
4. Ketik perintah ```pm2 start index.js``` untuk menjalankan server
5. Ketik perintah ```pm2 save``` untuk menyiapkan server berjalan otomatis ketika menyalakan komputer (startup)
6. Ketik perintah ```pm2 list``` untuk melihat status server sedang ```online``` atau ```offline```
7. Jika sudah online, maka buka aplikasi Whatsapp Sender Desktopnya

---

#### Versi Git Repository

1. Pastikan kamu sudah memiliki Server Whatsapp Sender
2. Copy ke direktori ```C:/``` dan letakan di luar berdekatan dengan folder Windows
3. Buka folder `whatsapp-sender-server` kemudian klik kanan dan pilih ```Git bash```
4. Ketik ```npm install``` setelah itu tunggu sampai selesai
5. Buka file di ```node_modules/whatsapp-web.js/src/util``` kemudian edit file ```Injected.js```

```javascript
window.Store.Features = window.mR.findModule('FEATURE_CHANGE_EVENT')[0].LegacyPhoneFeatures;
```

Menjadi

```javascript
window.Store.Features = window.mR.findModule('LegacyPhoneFeatures')[0];
```

6. Buka folder `whatsapp-sender-server` kemudian klik kanan dan pilih ```Git bash```
7. Ketik perintah ```pm2 start index.js``` untuk menjalankan server
8. Ketik perintah ```pm2 save``` untuk menyiapkan server berjalan otomatis ketika menyalakan komputer (startup)
9. Ketik perintah ```pm2 list``` untuk melihat status server sedang ```online``` atau ```offline```
10. Jika sudah online, maka buka aplikasi Whatsapp Sender Desktopnya

---

# Panduan Penggunaan

Setelah Whatsapp Sender Server telah terinstall dan dijalankan. Maka kita buka aplikasi Whatsapp Sender Desktopnya.


## Autentikasi (login)
 
1. Siapkan Smartphone dengan Aplikasi Whatsapp
2. Klik ```titik tiga``` di sebelah kanan atas dan pilih ```Perangkat Tertaut```
3. Klik ```Tautkan perangkat``` kemudian akan muncul tampilan Scan QR Code
4. Kemudian Scan QR Code di aplikasi ```Whatsapp Sender Desktop```

![Tampilan QR Code](/images/Group-1.jpg ':size=450')

- ```1``` Tombol ```QR Code Generate``` digunakan untuk membuat ulang QR Code yang sudah kadaluwarsa. Catatan: Jika susah untuk login maka silahkan klik ```QR Code Generate``` sampai QR Code berubah ke bentuk yang lainnya. Untuk mendapatkan QR Code baru bisa mencapai 15 - 20 detik.
- ```2``` QR Code untuk autentikasi

---

## Halaman Utama

Jika sudah berhasil Scan QR Code maka kita akan dialihkan ke halaman utama Whatsapp Sender Desktop

![Halaman Utama](/images/Group-2.jpg ':size=450')


- ```1``` Ini adalah status dari Whatsapp Sender. Terdapat ```nama akun Whatsapp``` yang menandakan nomor yang sedang aktif. Dan status ```Ready``` yang menandakan bahwa aplikasi Whatsapp Sender sudah siap untuk mengirim pesan.
- ```2``` Tabel terkirim. Ini adalah informasi nomor mana saja yang terkirim dan yang tidak terkirim.
- ```3``` Ini adalah File Kontak. Dimana kita harus memasukan file dengan ekstensi ```.txt``` atau ```.csv``` untuk mengunggah nomor telpon target yang akan di kirim pesan.

![Halaman Upload Gambar](/images/Group-5.jpg ':size=450')

- ```4``` Ini adalah Gambar, untuk pengirim yang ingin mengirim pesan berbentuk gambar maka silahkan untuk upload gambar dalam bentuk ```.jpg/.png```. Namun ini adalah ```optional``` bisa kirim pesan dengan gambar ataupun tidak. Jika tidak akan mengirim gambar maka tidak perlu upload gambar.

![Halaman Utama 2](/images/Group-3.jpg ':size=450')

- ```5``` Ini adalah tempat text box untuk mengirim pesan. Kita bisa gunakan variabel yang ada di atas seperti ```nama```, ```nomor whatsapp```, ```tag 1``` s.d ```tag 3```. Terdapat panduan formating teks untuk bold, italic dan sebagainnya beserta Emoji.
<b>Gunakan format pesan teks</b> dengan contoh yang <b>tertera di halaman Pesan</b>.

---

## Unggah Kontak

Ada beberapa aturan yang digunakan untuk membuat file kontak.
1. Buatlah kontak dengan format ```.txt/.csv```
2. Pisahkan antara value dengan ```, (comma)```
3. Pastikan urutan nomor telpon target di bagian kedua.

```text
Nama,NomorTelpon,Variabel1,Variabel2,dst...
```

```text
Lerian,082313888318,Sistem Informasi,Universitas Terbuka
```

![Contoh File Kontak](/images/Group-6.jpg ':size=450')

Setelah selesai membuat daftar kontak, maka kita tinggal unggah ke kolom ```File Kontak``` ada di nomor 3.

![Halaman Utama](/images/Group-2.jpg ':size=450')
![Unggah Kontak](/images/Group-4.jpg ':size=450')

---

## Unggah Gambar

Untuk mengirim gambar ada aturan yang digunakan, namun sifatnya tetap (optional) tidak diwajibkan. Upload gambar di kolom nomor 4.

Format gambar harus dengan format ```.jpeg/.png/.jpg```

![Halaman Utama](/images/Group-2.jpg ':size=450')
![Halaman Upload Gambar](/images/Group-5.jpg ':size=450')

---

## Tulis Pesan

Ini adalah halaman untuk mengirim pesan, maka di dalamnya kita bisa menuliskan pesan apa saja berikut dengan variabel yang dinamis mengikuti yang kita cantumkan di file kontak.

![Halaman Tulis Pesan](/images/Group-6-1.jpg ':size=450')

Untuk mengirim pesan, maka silahkan untuk mengikuti contoh dibawah ini:

```text
Halo &var0, Selamat kamu mendapatkan kupon DISKON MARTABAK KUYA. Silahkan masukan kode &var2. Whatsapp Sender.
```
Keterangan:
1. &var0 adalah nama penerima target
2. &var2 adalah kode beasiswa


![Contoh File Kontak](/images/Group-6.jpg ':size=450')

Setelah menulis, jangan lupa kirim pesannya dengan menekan tombol kirim!

---

## Proses Mengirim Pesan

Ini adalah screenshot proses pengiriman pesan. Kita bisa melihat nomor mana yang terkirim dan mana yang tidak. Untuk yang <b>Tidak terkirim</b> maka sudah dipastikan nomor tersebut <b>Tidak terdaftar akun whatsapp</b>.

![Proses Mengirim Pesan](/images/Group-7.jpg ':size=450')

- ```1``` Ini adalah status pengiriman pesan. Ada ```bar loading``` yang menunjukan kita sudah mengirim pesan berapa persen.
- ```2``` Ini adalah table pengiriman pesan, kita bisa melihat secara realtime pesan sender terkirim atau tidak ke target. Untuk tabel ini, terkadang jumlahnya tidak akurat 1 - 2 nama. Tetapi pesan akan <b>tetap terkirim</b>.

Berikut ini adalah status terakhir, bagaimana menandakan pesan tersebut terkirim atau tidak.

![Hasil mengirim pesan](/images/Group-8.jpg ':size=450')

- ```1``` Ini adalah tanda pesan <b>Tidak terkirim</b> karena nomor whatsapp tidak terdaftar akun whatsapp.
- ```2``` Ini adalah tanda pesan <b>Terkirim</b>.

Ini adalah contoh pesan terkirim ke target nomor whatsapp berikut dengan mengirimkan gambar.

![Hasil mengirim pesan](/images/Group-9.jpg ':size=450')

---

## Autentikasi (Logout)

Demi keamanan, maka untuk ```Logout``` bisa dilakukan di Aplikasi Whatsapp Smartphone pengguna dengan cara membuka halaman ```Perangkat tertaut```

![Logout](/images/Group-11.jpg ':size=450')

---

# Lisensi

Jika mendaftar sebagai ```berlangganan``` maka jika muncul halaman seperti gambar dibawah ini segeralah hubungi Email: kanglerian@gmail.com untuk mendaftar atau bisa klik tombol <b>Daftar Sekarang!</b>

![Logout](/images/Group-10.jpg ':size=450')

# Tips & Trik

Untuk menghindari akun terkena ```banned``` maka disarankan untuk mengirim pesan per 100 nomor telpon. Jika terdapat target sebanyak 1000 kontak, maka kirim 100 kontak per 10 kali.

# Kontak

Email: kanglerian@gmail.com
