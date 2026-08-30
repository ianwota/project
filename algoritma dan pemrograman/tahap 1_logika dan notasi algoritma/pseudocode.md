# Pseudocode — Program Hitung Total Biaya Jasa Layanan AC

## 1. Judul (Header)

```text
PROGRAM Hitung_Total_Biaya_Jasa_Layanan_AC
```

## 2. Deklarasi (Kamus)

```text
Kamus:
    Jenis_Layanan : String
    Jumlah_Unit   : Integer
    Harga         : Integer
    Total_Biaya   : Integer
```

### Daftar Harga

```text
    Cuci AC           = Rp75.000
    Isi Freon         = Rp275.000
    Pasang AC         = Rp250.000
    Bongkar Pasang AC = Rp300.000
```

## 3. Deskripsi (Algoritma)

```text
Deskripsi:

START

    Tampilkan daftar jenis layanan dan harga

    Masukkan Jenis_Layanan

    Masukkan Jumlah_Unit

    Tentukan Harga berdasarkan Jenis_Layanan

    Total_Biaya ← Harga × Jumlah_Unit

    Tampilkan Total_Biaya

END
```

## 4. Rumus

```text
Total_Biaya = Harga × Jumlah_Unit
```

## 5. Contoh

```text
Jenis_Layanan = Cuci AC
Jumlah_Unit   = 2
Harga         = Rp75.000

Total_Biaya = Rp75.000 × 2
            = Rp150.000
```

**Output:**

```text
Total Biaya = Rp150.000
```
