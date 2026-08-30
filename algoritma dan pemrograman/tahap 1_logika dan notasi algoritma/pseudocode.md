# Pseudocode: Sistem Perhitungan Estimasi Biaya Jasa Service AC

Dokumen ini berisi rancangan pseudocode formal dan terstruktur berbasis prinsip *Computational Thinking* untuk mengotomatisasi perhitungan total biaya estimasi pada layanan service AC independen.

---

## 1. Definisi Masalah & Spesifikasi Data

### A. Masalah Usaha
* **Keluhan:** Keterlambatan dan kesalahan manual dalam menghitung total estimasi biaya service AC saat lonjakan order (*high volume*).
* **Solusi:** Algoritma otomatisasi perhitungan estimasi biaya berbasis multi-layanan dan biaya tambahan.

### B. Kamus Data / Konstanta (Daftar Tarif Service)

| Kode Layanan | Nama Layanan | Tarif Satuan (IDR) |
| :--- | :--- | :--- |
| `CUCI` | Cuci AC | Rp 75.000 |
| `OVERHAUL` | Overhaul / Cuci Besar | Rp 150.000 |
| `PASANG` | Pasang AC Baru / Bekas | Rp 300.000 |
| `BONGKAR_PASANG` | Bongkar Pasang AC | Rp 350.000 |
| `FREON` | Isi / Tambah Freon | Rp 275.000 |

---

## 2. Pseudocode Formal (Standardized Style)

```text
PROGRAM HitungEstimasiBiayaServiceAC

// ==========================================
// DEKLARASI KONSTANTA & VARIABLES
// ==========================================
CONST
    HARGA_CUCI           : INTEGER = 75000
    HARGA_OVERHAUL       : INTEGER = 150000
    HARGA_PASANG         : INTEGER = 300000
    HARGA_BONGKAR_PASANG : INTEGER = 350000
    HARGA_FREON          : INTEGER = 275000

VARIABLES
    kode_layanan    : STRING
    harga_satuan    : INTEGER
    jumlah_unit     : INTEGER
    subtotal        : INTEGER
    biaya_transport : INTEGER
    total_biaya     : INTEGER
    tambah_layanan  : BOOLEAN

// ==========================================
// ALGORITMA UTAMA
// ==========================================
BEGIN
    // Inisialisasi awal
    total_biaya <- 0
    biaya_transport <- 0
    tambah_layanan <- TRUE

    OUTPUT "=========================================="
    OUTPUT "   SYSTEM ESTIMASI BIAYA SERVICE AC       "
    OUTPUT "=========================================="

    // 1. Input Biaya Transport / Kedatangan (Opsional/Opsional Dasar)
    INPUT biaya_transport
    IF biaya_transport > 0 THEN
        total_biaya <- total_biaya + biaya_transport
    ENDIF

    // 2. Perulangan Input Multi-Layanan
    WHILE (tambah_layanan == TRUE) DO
        OUTPUT "Pilih Layanan: [CUCI, OVERHAUL, PASANG, BONGKAR_PASANG, FREON]"
        INPUT kode_layanan

        // Determinasi Harga Satuan Berdasarkan Abstraksi Pola
        SWITCH (kode_layanan) DO
            CASE "CUCI":
                harga_satuan <- HARGA_CUCI
            CASE "OVERHAUL":
                harga_satuan <- HARGA_OVERHAUL
            CASE "PASANG":
                harga_satuan <- HARGA_PASANG
            CASE "BONGKAR_PASANG":
                harga_satuan <- HARGA_BONGKAR_PASANG
            CASE "FREON":
                harga_satuan <- HARGA_FREON
            DEFAULT:
                harga_satuan <- 0
                OUTPUT "Peringatan: Jenis layanan tidak valid!"
        ENDSWITCH

        // Jika kode layanan valid
        IF harga_satuan > 0 THEN
            OUTPUT "Masukkan Jumlah Unit/Paket:"
            INPUT jumlah_unit

            WHILE (jumlah_unit <= 0) DO
                OUTPUT "Jumlah unit harus lebih dari 0. Masukkan kembali:"
                INPUT jumlah_unit
            ENDWHILE

            // Kalkulasi Subtotal
            subtotal <- harga_satuan * jumlah_unit
            total_biaya <- total_biaya + subtotal

            OUTPUT "Subtotal Layanan: Rp ", subtotal
        ENDIF

        // Konfirmasi Apakah Ada Tambahan Layanan Lain
        OUTPUT "Tambah layanan lain? (TRUE / FALSE):"
        INPUT tambah_layanan

    ENDWHILE

    // 3. Tampilkan Ringkasan & Total Akhir
    OUTPUT "------------------------------------------"
    OUTPUT "TOTAL ESTIMASI BIAYA : Rp ", total_biaya
    OUTPUT "=========================================="

END
```

---

## 3. Pemetaan Computational Thinking

1. **Dekomposisi:**
   * Memecah kalkulasi keseluruhan menjadi: *Biaya Transport*, *Perhitungan Subtotal Per Layanan*, dan *Akumulasi Total Biaya*.
2. **Pattern Recognition (Pola):**
   * Menggunakan pola perulangan (`WHILE loop`) karena 1 transaksi bisa berisi $N$ jenis layanan.
   * Menghitung subtotal dengan formula konsisten: $	ext{Subtotal} = 	ext{Harga Satuan} 	imes 	ext{Jumlah Unit}$.
3. **Abstraction (Abstraksi):**
   * Penggunaan struktur `SWITCH-CASE` untuk mengisolasi logika pemetaan kode layanan ke harga spesifik tanpa mengganggu alur akumulasi biaya.
4. **Algorithm Design:**
   * Alur logis sekuensial yang dilengkapi dengan validasi input (pengecekan `jumlah_unit > 0` dan layanan valid).
