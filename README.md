# 📱 LandMeasure — Android APK

Aplikasi Android untuk mengukur luas lahan dari peta satelit dengan dukungan GPS mobile.

Ini adalah **WebView wrapper** yang menampilkan aplikasi web LandMeasure yang di-host di Zaro.

---

## 🚀 Cara Build APK

### Opsi A — Automatic via GitHub Actions (Rekomendasi, tanpa install apapun)

1. Push repo ini ke GitHub
2. Buka tab **Actions** di repo
3. Klik workflow **Build Android APK** → **Run workflow**
4. Tunggu ~5 menit
5. Download APK dari section **Artifacts** atau **Releases**

### Opsi B — Build Lokal di Laptop

Butuh: [Android Studio](https://developer.android.com/studio) atau JDK 17 + Android SDK

```bash
# Clone repo
git clone https://github.com/USERNAME/LandMeasure-APK.git
cd LandMeasure-APK

# Build APK
./gradlew assembleDebug

# APK ada di: app/build/outputs/apk/debug/app-debug.apk
```

---

## 📥 Install APK ke HP Android

1. Transfer file `app-debug.apk` ke HP (via USB / Bluetooth / Google Drive)
2. Buka file di HP → tap **Install**
3. Kalau muncul warning **"Install from unknown sources"**:
   - Buka **Settings → Apps → Special access → Install unknown apps**
   - Izinkan browser/file manager kamu
4. Buka aplikasi **LandMeasure** dari home screen
5. Izinkan **akses lokasi** saat diminta → GPS akan aktif

---

## ⚙️ Konfigurasi

### Ganti URL Aplikasi

Edit file `app/src/main/java/com/bangke/landmeasure/MainActivity.java`, baris:

```java
private static final String APP_URL = "https://app.zaro.ai/apps/land-measure-ap-pgi8u8";
```

Ganti dengan URL aplikasi kamu (Zaro / Vercel / domain sendiri), lalu build ulang.

### Ganti Nama & Package

- **Nama app**: edit `app/src/main/res/values/strings.xml`
- **Package ID**: edit `app/build.gradle` → `applicationId`
- **Version**: edit `app/build.gradle` → `versionCode` / `versionName`

### Ganti Icon

Ganti file di `app/src/main/res/drawable/ic_launcher_foreground.xml` dengan icon kamu (SVG vector), atau taruh PNG di folder `mipmap-*/`.

---

## 🔐 Permissions

- **Location (GPS)** — WAJIB untuk fitur ukur lahan via GPS
- **Internet** — untuk load peta satelit
- **Camera** — untuk fitur foto lapangan (roadmap)
- **Storage** — untuk export KML/GeoJSON (roadmap)

---

## 🛠️ Tech Stack

- **Android WebView** (Java, native)
- **Min SDK 21** (Android 5.0 Lollipop+)
- **Target SDK 34** (Android 14)
- **Backend web** : React app di Zaro platform

---

## 📄 License

MIT
