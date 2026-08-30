# 🧮 Sistem Perhitungan Estimasi Biaya Service AC

> **Project Algoritma & Pemrograman — Computational Thinking**

Sistem Perhitungan Estimasi Biaya Service AC adalah sebuah rancangan algoritma untuk membantu usaha jasa service AC independen dalam menghitung estimasi biaya layanan secara **cepat, terstruktur, dan akurat**.

Project ini dibuat sebagai penerapan konsep **Computational Thinking**, khususnya **Decomposition, Pattern Recognition, Abstraction, dan Algorithm Design**, sebelum dikembangkan menjadi sebuah aplikasi atau kalkulator otomatis.

---

## 📌 Latar Belakang

Dalam usaha jasa service AC, perhitungan biaya sering dilakukan secara manual. Ketika jumlah pesanan meningkat atau terjadi **high volume order**, proses tersebut dapat menjadi lambat dan meningkatkan risiko kesalahan perhitungan.

Contohnya, teknisi atau admin harus menghitung:

- Jenis layanan yang dipilih pelanggan
- Harga setiap layanan
- Jumlah unit AC
- Subtotal setiap layanan
- Total keseluruhan biaya

Oleh karena itu, diperlukan sebuah alur perhitungan yang terstruktur sehingga proses estimasi biaya dapat dilakukan dengan lebih cepat dan mengurangi **human error**.

---

## 🎯 Tujuan Project

Project ini bertujuan untuk merancang algoritma perhitungan estimasi biaya service AC yang:

- ⚡ Mempercepat proses perhitungan
- 🎯 Mengurangi kesalahan perhitungan manual
- 📋 Memiliki alur yang terstruktur
- 🔄 Dapat menangani lebih dari satu jenis layanan
- 💻 Siap dikembangkan menjadi aplikasi digital atau kalkulator otomatis

---

## 🧠 Penerapan Computational Thinking

### 1. Decomposition

Masalah utama yaitu **menghitung total biaya service AC** dipecah menjadi beberapa komponen sederhana:

| Komponen | Keterangan |
|---|---|
| Jenis Layanan | Kategori layanan yang dipilih pelanggan |
| Jumlah Unit | Banyaknya AC yang akan dikerjakan |
| Harga Satuan | Harga untuk satu unit layanan |
| Subtotal | Harga layanan × jumlah unit |
| Total Biaya | Jumlah seluruh subtotal |

Dengan decomposition, masalah yang kompleks menjadi beberapa bagian yang lebih mudah untuk diproses.

---

### 2. Pattern Recognition

Ditemukan pola yang sama pada setiap transaksi layanan:

**Pilih layanan → Tentukan harga → Masukkan jumlah unit → Hitung subtotal**

Rumus yang digunakan:

```text
Subtotal = Harga Satuan × Jumlah Unit
```

Jika pelanggan memilih beberapa jenis layanan, maka:

```text
Total Biaya = Subtotal 1 + Subtotal 2 + ... + Subtotal n
```

Pola tersebut dapat digunakan berulang kali untuk setiap jenis layanan.

---

### 3. Abstraction

Tidak semua informasi pelanggan diperlukan dalam proses perhitungan biaya.

Informasi yang **tidak digunakan dalam kalkulasi** antara lain:

- Merek AC
- Tipe AC
- Keluhan pelanggan
- Lokasi detail
- Kondisi ruangan

Informasi yang menjadi fokus utama sistem:

```text
Jenis Layanan
Jumlah Unit
Harga Satuan
```

Dengan abstraction, sistem hanya memproses informasi yang relevan dengan perhitungan biaya.

---

### 4. Algorithm Design

Algoritma dirancang untuk mengubah proses manual menjadi langkah-langkah yang sistematis.

#### Pseudocode

```text
START

DEKLARASI DAFTAR HARGA
    Cuci AC        = Rp75.000
    Overhaul       = Rp150.000
    Pasang AC      = Rp300.000
    Bongkar Pasang = Rp350.000
    Isi Freon      = Rp275.000

DEKLARASI Total_Biaya = 0

ULANGI:
    Pilih Jenis_Layanan
    Masukkan Jumlah_Unit

    Ambil Harga_Satuan berdasarkan Jenis_Layanan

    Subtotal = Harga_Satuan × Jumlah_Unit

    Total_Biaya = Total_Biaya + Subtotal

    Tanyakan:
        "Apakah ada layanan lain?"

    Jika YA:
        kembali ke proses input pesanan

    Jika TIDAK:
        lanjutkan

Tampilkan Total_Biaya

END
```

---

## 💰 Daftar Harga Layanan

| No | Jenis Layanan | Harga / Unit |
|---:|---|---:|
| 1 | Cuci AC | Rp75.000 |
| 2 | Overhaul | Rp150.000 |
| 3 | Pasang AC | Rp300.000 |
| 4 | Bongkar Pasang | Rp350.000 |
| 5 | Isi Freon | Rp275.000 |

> Harga pada project ini merupakan **data simulasi untuk kebutuhan pembelajaran** dan dapat diubah sesuai kebutuhan usaha.

---

## 🔢 Contoh Perhitungan

Misalnya pelanggan memesan:

- Cuci AC: **2 unit**
- Isi Freon: **1 unit**

Maka:

```text
Cuci AC
= Rp75.000 × 2
= Rp150.000

Isi Freon
= Rp275.000 × 1
= Rp275.000
```

Total:

```text
Total Biaya
= Rp150.000 + Rp275.000
= Rp425.000
```

### Hasil Estimasi

**Rp425.000**

---

## 🔄 Flow Proses

```text
START
  │
  ▼
Pilih Jenis Layanan
  │
  ▼
Masukkan Jumlah Unit
  │
  ▼
Ambil Harga Satuan
  │
  ▼
Hitung Subtotal
  │
  ▼
Tambahkan ke Total Biaya
  │
  ▼
Ada layanan lain?
  │
  ├── YA ───────────────┐
  │                     │
  │                     ▼
  │              Pilih Jenis Layanan
  │
  └── TIDAK
          │
          ▼
    Tampilkan Total
          │
          ▼
         END
```

---

## 🛠️ Konsep yang Dipelajari

Project ini digunakan untuk memahami beberapa konsep dasar dalam **Algoritma dan Pemrograman**, yaitu:

- Computational Thinking
- Decomposition
- Pattern Recognition
- Abstraction
- Algorithm Design
- Input & Output
- Variabel
- Operasi aritmatika
- Percabangan
- Perulangan
- Perhitungan subtotal dan total
- Pseudocode
- Flowchart

---

## 🚀 Pengembangan Selanjutnya

Rancangan algoritma ini dapat dikembangkan menjadi aplikasi yang lebih lengkap, misalnya:

### Tahap 1 — Program Console
Membuat kalkulator biaya service AC menggunakan bahasa pemrograman seperti **C++ atau Python**.

### Tahap 2 — Kalkulator Digital
Menambahkan interface agar pengguna dapat memilih layanan dan jumlah unit dengan lebih mudah.

### Tahap 3 — Sistem Booking
Menambahkan fitur:

- Data pelanggan
- Nomor WhatsApp
- Alamat service
- Jadwal service
- Detail pesanan
- Estimasi biaya

### Tahap 4 — Sistem Manajemen Service AC
Mengembangkan sistem menjadi aplikasi yang memiliki:

- Customer management
- Order management
- Teknisi
- Riwayat service
- Invoice
- Laporan pendapatan
- Database
- Online booking

---

## 📂 Struktur Project

Struktur repository saat ini:

```text
ac-service-cost-calculator/
│
├── README.md
│
└── docs/
    ├── pseudocode.txt
    └── flowchart.png
```

> Struktur folder dapat disesuaikan ketika project mulai dikembangkan ke tahap coding.

---

## 🎓 Informasi Project

**Mata Kuliah:** Algoritma dan Pemrograman  
**Topik:** Computational Thinking & Algorithm Design  
**Project:** AC Service Cost Calculator  
**Status:** Algorithm Design / Pre-Coding

---

## 📄 Lisensi

Project ini dibuat untuk **keperluan pembelajaran dan portfolio**.

---

⭐ Jika project ini bermanfaat, jangan lupa **Star** repository ini!
