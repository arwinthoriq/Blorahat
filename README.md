# BloraHat Professional Security Audit Framework v2.0

![Python](https://img.shields.io/badge/Python-3.x-green.svg)
![License](https://img.shields.io/badge/License-Confidential-red.svg)

BloraHat adalah instrumen assessment keamanan tingkat lanjut yang dirancang untuk membantu auditor sistem informasi dalam memetakan permukaan serangan (*attack surface*) dan menguji ketahanan infrastruktur aplikasi web terhadap berbagai vektor ancaman siber modern.

## ⚠️ Disclaimer
Alat ini dikembangkan khusus untuk tujuan **Security Auditing**, **Penetration Testing**, dan **Edukasi**. Segala bentuk penggunaan terhadap target sistem tanpa izin tertulis dari pihak otoritas terkait adalah sepenuhnya tanggung jawab pengguna. Pengembang tidak bertanggung jawab atas kerugian atau dampak hukum yang timbul dari penyalahgunaan instrumen ini.

## Fitur Utama
- **Automated Authentication Probing**: Menguji integritas mekanisme validasi input pada gerbang otentikasi termasuk pengujian bypass otomatis.
- **Object Identifier Assessment (IDOR)**: Pemindaian kerentanan pada manipulasi identifier record secara sekuensial dan konkuren untuk mendeteksi potensi kebocoran informasi.
- **Deep Infrastructure Audit**: Pemindaian port jaringan, identifikasi versi layanan (*banner grabbing*), dan probing mendalam pada port layanan administratif (seperti Port 8080).
- **Vulnerability Injection Suite**: Modul audit otomatis untuk mendeteksi celah *Injection* (Error & Time-Based) serta *Cross-Scripting* pada berbagai endpoint secara simultan.
- **Advanced Evasion & Cache Audit**: Simulasi teknik manipulasi header untuk *IP Masking*, pengujian *Server-Side Request Forgery* (SSRF), dan analisis integritas *Web Cache*.
- **Self-Healing Environment**: Logika internal yang mampu mendeteksi dan memperbaiki kerusakan dependensi secara mandiri untuk menjamin stabilitas eksekusi.

## 🛠️ Instalasi dan Persiapan

Framework ini dirancang dengan pendekatan **Zero-Configuration** agar dapat langsung digunakan oleh auditor tanpa hambatan teknis instalasi.

### Metode 1: Windows (Auto-Launcher) - *Rekomendasi*
Cukup jalankan file `launcher.bat`. Sistem akan secara otomatis melakukan:
1. Validasi lingkungan Python di sistem operasi.
2. Instalasi otomatis jika komponen Python belum terdeteksi (via Winget).
3. Konfigurasi otomatis library pendukung melalui manajemen PIP internal.
4. Perbaikan mandiri (*Self-Healing*) jika ditemukan pustaka yang korup atau hilang.
5. Eksekusi modul utama secara instan.

### Metode 2: Manual Setup
Jika Anda ingin mengatur lingkungan secara manual:
1. Pastikan sistem Anda telah terpasang Python 3.10+.
2. Pasang seluruh dependensi yang diperlukan:
   ```bash
   python -m pip install -r requirements.txt
   ```
3. Jalankan framework:
   ```bash
   python main.py
   ```

## 🖥️ Alur Kerja Audit

Setelah aplikasi berjalan, pengguna dapat mengakses berbagai modul audit melalui menu interaktif:

1. **Auth Test**: Modul untuk memverifikasi ketahanan enkapsulasi token dan validasi input otentikasi.
2. **Object Identifier Scan**: Melakukan iterasi pada identifier sistem untuk mengidentifikasi celah otorisasi horizontal.
3. **Security Config Audit**: Menganalisis *Security Headers* dan melakukan penelusuran terhadap jalur direktori sensitif yang terekspos.
4. **Parameter Discovery**: Melakukan pemetaan URL internal secara cerdas dan mensimulasikan manipulasi variabel jalur (*path variables*).
5. **Vulnerability Scan**: Audit injeksi mendalam menggunakan berbagai payload standar industri untuk mendeteksi kelemahan sanitasi input.
6. **Infrastructure Audit**: Melakukan pemetaan layanan jaringan dan *service probing* untuk menemukan vektor serangan pada level layanan backend.
7. **Advanced Evasion**: Menguji kebijakan keamanan jaringan terhadap teknik *spoofing* dan eksploitasi dependensi eksternal.

## 🔐 Keamanan Source Code

Framework ini mendukung fitur **Obfuscation** tingkat tinggi untuk melindungi logika audit selama fase distribusi:
- Gunakan `obfuscate_code.bat` untuk memproteksi *source code* menggunakan PyArmor.
- File hasil proteksi akan berada di direktori `dist/` dalam format terenkripsi yang tetap dapat dieksekusi namun tidak dapat dibaca secara manual.

## 📋 Persyaratan Sistem
- Windows 10/11 atau Linux (Ubuntu/Debian recommended).
- Python 3.10 ke atas.
- Koneksi internet untuk penarikan dependensi otomatis saat inisialisasi pertama.

---
**BloraHat Security Team**  
*Dedicated to Infrastructure Resilience and Application Security.*
