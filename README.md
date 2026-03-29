# BloraHat Security Audit Tool v2.0

![Python](https://img.shields.io/badge/Python-3.x-green.svg)
![License](https://img.shields.io/badge/License-Open%20Source-blue.svg)

BloraHat adalah instrumen audit keamanan yang dirancang untuk menguji ketahanan sistem informasi terhadap kerentanan **Broken Authentication** dan **Insecure Direct Object Reference (IDOR)**.

## ⚠️ Disclaimer
Alat ini dibuat murni untuk tujuan **Security Testing** dan **Edukasi**. Segala bentuk penyalahgunaan terhadap sistem tanpa izin pemilik otoritas adalah tanggung jawab pengguna sepenuhnya. Penulis tidak bertanggung jawab atas kerugian yang ditimbulkan.

## Fitur Utama
- **Captcha Bypass Testing**: Menguji validasi sisi server terhadap parameter verifikasi captcha.
- **Session Token Hijacking**: Automasi perolehan token sesi setelah bypass autentikasi.
- **IDOR Scanner**: Mendeteksi kebocoran data pasien melalui manipulasi parameter objek pada URL secara konkuren.

## Instalasi

1. Clone repositori ini:
   ```bash
   git clone https://github.com/arwinthoriq/blorahat.git
   cd blorahat
   ```
2. Instal dependensi:
   ```bash
   pip install -r requirements.txt
   ```

## Penggunaan

Jalankan menu utama untuk memilih mode audit:
```bash
python main.py
```

### Konfigurasi Target
Anda dapat mengubah range target ID Rekam Medis pada file `1.py` di bagian:
```python
AWAL = int(_decode("NTAwMDAw"))
AKHIR = int(_decode("NTEwNTAw"))
```
