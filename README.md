# ACP Inventory Android

Proyek Android Studio untuk membungkus Google Apps Script Web App Anda menjadi APK Android menggunakan WebView.

## 1. Yang perlu disiapkan
- Android Studio terbaru yang mendukung Android Gradle Plugin 8.x.
- URL **Web App** Google Apps Script Anda yang berakhiran `/exec`.
- Pastikan deployment Apps Script dapat diakses dari perangkat Android sesuai kebutuhan login/permission Anda.

## 2. Pasang URL Apps Script
Buka:

`app/src/main/java/com/acpgroup/inventory/MainActivity.kt`

Cari:

`private val appsScriptUrl = "https://script.google.com/macros/s/URL Apps Script sudah diisi di MainActivity.kt/exec"`

Ganti dengan URL Web App Anda.

## 3. Buka di Android Studio
1. Extract ZIP.
2. Android Studio → **Open** → pilih folder `ACPInventoryAndroid`.
3. Tunggu Gradle Sync selesai.
4. Jalankan pada emulator/HP Android.
5. Untuk APK: **Build → Generate App Bundles or APKs → Generate APKs**.

## 4. Catatan penting untuk Apps Script
HTML Anda saat ini menggunakan `google.script.run` di beberapa bagian. Karena itu APK ini **tidak menjalankan HTML sebagai file lokal**; APK membuka URL Web App Apps Script agar environment Google Apps Script tetap tersedia.

File HTML yang digunakan sebagai basis juga disertakan di root proyek:
`Page_Modern_Inventory_Login.html`

## 5. Fitur WebView
- JavaScript aktif
- DOM Storage aktif
- Cookie aktif
- Tombol Back Android mengikuti navigasi WebView
- Download laporan ditangani oleh DownloadManager Android
- Portrait orientation
- HTTPS only

## Build tanpa Android Studio

Lihat `README_CLOUD_BUILD.md`. Folder `.github/workflows/build-apk.yml` akan membangun `app-debug.apk` melalui GitHub Actions.
