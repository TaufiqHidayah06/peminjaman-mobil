# PWA Peminjaman Kendaraan

Paket ini adalah **PWA launcher** untuk aplikasi Google Apps Script yang sudah ada.
Backend, spreadsheet, login, QR/barcode, dan fungsi `google.script.run` tetap berada
di Google Apps Script. PWA ini membungkus halaman Web App dalam iframe agar shell
PWA dapat diinstal dari Android dan PC.

## 1. Persiapkan URL Apps Script

1. Buka project Google Apps Script.
2. Deploy > Manage deployments.
3. Edit deployment Web app atau buat deployment baru.
4. Pastikan URL Web App berakhiran `/exec`.
5. Pastikan pengaturan akses deployment sesuai kebijakan aplikasi Anda.
6. Salin URL tersebut.

`doGet()` pada script yang diberikan sudah memakai:
`.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)`
sehingga halaman dapat dimuat di dalam wrapper iframe.

## 2. Hosting PWA (wajib HTTPS)

Upload seluruh isi folder ini ke hosting statis HTTPS, misalnya:
- GitHub Pages
- Firebase Hosting
- Netlify

Jangan hanya membuka `index.html` dari file lokal. Service worker dan instalasi PWA
membutuhkan origin HTTPS (localhost hanya untuk pengujian).

Setelah hosting aktif, buka URL hosting PWA. Masukkan URL Apps Script `/exec`
satu kali. URL disimpan di browser perangkat tersebut.

## 3. Instal di Android

1. Buka URL hosting PWA melalui Chrome.
2. Masukkan URL Apps Script `/exec`.
3. Tekan **Buka Aplikasi**.
4. Buka menu Chrome (⋮), pilih **Instal aplikasi** atau **Tambahkan ke layar utama**.
5. Ikuti konfirmasi instalasi.

## 4. Instal di Windows / PC

1. Buka URL hosting PWA melalui Chrome atau Edge.
2. Masukkan URL Apps Script `/exec`.
3. Tekan **Buka Aplikasi**.
4. Klik ikon instal di address bar, atau menu browser > **Install page as app**.

## Catatan penting

- PWA ini meng-cache file shell (HTML, manifest, ikon) saja. Data peminjaman,
  autentikasi, pencarian, QR, dan update status tetap memerlukan internet.
- Jangan cache halaman atau respons Apps Script yang berisi data pribadi/token.
- Jika deployment Apps Script berubah, perbarui URL melalui tombol ⚙ pada PWA.
- Fitur kamera/scan QR harus diuji pada perangkat sebenarnya. Jika kamera dibuka
  di tab baru dari halaman Apps Script, izinkan akses kamera pada browser.
- PWA bukan APK Android atau EXE Windows native; aplikasi dipasang melalui browser.
- `ALLOWALL` mengizinkan halaman Apps Script ditampilkan di iframe. Gunakan hanya
  hosting PWA yang Anda kendalikan dan tetap pertahankan autentikasi backend.
