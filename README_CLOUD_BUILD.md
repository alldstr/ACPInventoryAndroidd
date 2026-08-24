# ACP Inventory - Cloud Build (No Android Studio)

Project Android WebView untuk Google Apps Script.

## URL Apps Script

URL Web App sudah tertanam di:

`app/src/main/java/com/acpgroup/inventory/MainActivity.kt`

## Cara build tanpa Android Studio

1. Buat/login akun GitHub.
2. Buat repository baru, misalnya `ACPInventoryAndroid`.
3. Upload seluruh isi folder project ini ke repository (bukan ZIP-nya sebagai satu file).
4. Pastikan branch utama bernama `main`.
5. Buka tab **Actions**.
6. Pilih workflow **Build ACP Inventory APK**.
7. Klik **Run workflow**.
8. Tunggu sampai status selesai.
9. Buka hasil workflow tersebut dan cari bagian **Artifacts**.
10. Download `ACP-Inventory-APK`.
11. Extract ZIP artifact, lalu install `app-debug.apk` di HP Android.

Workflow menggunakan GitHub Actions untuk menyediakan Java dan Android SDK, kemudian mengunduh Gradle dan menjalankan `assembleDebug`.

## Catatan

- APK ini adalah debug APK untuk penggunaan internal/testing.
- Untuk publikasi ke Google Play, diperlukan release signing dan konfigurasi Play App Signing.
- Aplikasi membutuhkan koneksi internet karena halaman utama berasal dari Google Apps Script Web App.
- Jika URL Apps Script berubah, edit `appsScriptUrl` di `MainActivity.kt`.
