# 🛒 Shopee Scraper V2

Proyek ini terdiri dari 2 bagian utama: login otomatis Shopee (dengan CAPTCHA trigger) dan scraping produk berdasarkan kata kunci pencarian. Otentikasi menggunakan cookie yang disimpan setelah login berhasil.

---

## 📂 Struktur Folder

```
scrapingV2/
├── login_and_cookie_gui.py     # Proses login Shopee + CAPTCHA handler + save cookie
├── scraper_gui.py              # Scraper produk Shopee berbasis kata kunci dan jumlah halaman
├── shopee_cookies.json         # Cookie login tersimpan (otomatis dibuat setelah login)
└── README.md                   # Dokumentasi ini
```

---

## 🔐 1. Login Shopee & Simpan Cookie

**File**: `login_and_cookie_gui.py`

### 🚀 Cara pakai:
1. Jalankan script:
    ```bash
    python login_and_cookie_gui.py
    ```
2. Masukkan kata kunci pencarian apa saja di GUI yang muncul.
   - Tujuannya adalah untuk memicu CAPTCHA Shopee.
3. Login manual via browser otomatis yang terbuka.
4. Jika CAPTCHA muncul dan login gagal → program akan auto-refresh sampai berhasil.
5. Setelah berhasil login, cookie disimpan otomatis ke `shopee_cookies.json`.

> ⚠️ Cookie akan digunakan oleh script scraping. Tanpa login, scraping tidak bisa berjalan.

---

## 📦 2. Scraping Produk Shopee

**File**: `scraper_gui.py`

### 🚀 Cara pakai:
1. Jalankan script:
    ```bash
    python scraper_gui.py
    ```
2. Masukkan di GUI:
    - Kata kunci pencarian
    - Jumlah halaman yang ingin di-scrape
    - Nama file output (contoh: `produk.csv`)
3. Klik **"Mulai Scraping"**
4. Hasil akan disimpan ke file `.csv`

> ✅ Cookie otomatis dimuat dari `shopee_cookies.json`

---

## 📌 Fitur Utama

- 🚪 Login Shopee via GUI & browser
- 🔐 Simpan cookie agar tidak perlu login ulang
- 🤖 Auto-handle CAPTCHA: refresh otomatis hingga berhasil
- 🔍 Scrape produk dengan:
  - Nama produk
  - Harga
  - Terjual
  - Lokasi
  - Rating
- 💾 Simpan ke `.csv`

---

## 💡 Catatan Tambahan

- Pastikan cookie sudah dibuat terlebih dahulu sebelum scraping.
- Jika login gagal karena CAPTCHA, cukup jalankan ulang login script.
- Diuji pada situs Shopee Indonesia (`shopee.co.id`).

---

## 📥 Dependensi

Install semua dependensi dengan pip:

```bash
pip install undetected-chromedriver selenium beautifulsoup4 pandas
```

---

## 👨‍💻 Developer

Dibuat oleh: **[Mochamad Marvin Rimbawan]**  
Untuk kebutuhan edukasi, scraping terbatas, dan eksperimen teknis.

---

## 📄 Lisensi

Proyek ini menggunakan lisensi **MIT License** – Bebas digunakan, dimodifikasi, dan disebarluaskan.
