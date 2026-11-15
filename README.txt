# PWA Peminjaman Kendaraan

Paket ini adalah **PWA launcher** untuk aplikasi Google Apps Script yang sudah ada. PWA menyediakan halaman awal yang dapat diinstal; ketika tombol **Buka Aplikasi Peminjaman** ditekan, Web App Apps Script dibuka langsung di tab baru. Halaman Apps Script tidak dimuat di iframe karena pada pengujian dapat menghasilkan error 401.

Backend, spreadsheet, login, QR/barcode, dan fungsi `google.script.run` tetap berada di Google Apps Script.

## URL aplikasi

URL deployment `/exec` sudah diatur sebagai URL bawaan. Jika URL berubah, gunakan tombol ⚙ pada halaman PWA untuk memperbaruinya.

## Hosting PWA (wajib HTTPS)

Upload seluruh isi folder ini ke hosting statis HTTPS, misalnya GitHub Pages, Firebase Hosting, atau Netlify. Jangan hanya mengunggah file ZIP. Pastikan `index.html`, `manifest.webmanifest`, `sw.js`, dan folder `icons` berada di root repository/hosting.

## Instalasi

1. Buka URL GitHub Pages melalui Chrome (Android) atau Chrome/Edge (Windows).
2. Tekan **Instal** jika tombol tersedia, atau gunakan menu browser > **Install app / Tambahkan ke layar utama**.
3. Buka PWA yang telah terpasang.
4. Tekan **Buka Aplikasi Peminjaman**. Apps Script akan terbuka langsung di tab baru. Login dengan akun Google yang memiliki akses jika diminta.

## Catatan

- PWA ini adalah launcher, bukan aplikasi native APK/EXE dan bukan tampilan Apps Script yang terintegrasi di dalam shell.
- Data peminjaman, autentikasi, QR, dan update status tetap diproses oleh Apps Script dan memerlukan internet.
- Membuka Apps Script langsung membantu menghindari masalah cookie/login dan error 401 yang dapat muncul saat dipasang di iframe.
- Kamera/scan QR harus diuji pada perangkat sebenarnya dan izin kamera browser harus diaktifkan.
- Jangan mengubah atau menghapus pemeriksaan autentikasi backend hanya untuk mengatasi masalah tampilan.
