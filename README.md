# Pertemuan 13 - Debugging dan Testing

Nama: Ziana Alfia Zahra  
NIM: 2225250076  
Kelas: 3A

## Kasus

Pertemuan ini membahas debugging, tracing, testing, dan test case pada program Python. Terdapat tiga kasus, yaitu bug batas kelulusan, kesalahan perhitungan rata-rata, dan penanganan file nilai.

## Test Case

| ID | Input | Expected | Actual Awal | Status |
|---|---|---|---|---|
| T1 | [80, 60, 90, 70] | 75.0 | 60.0 | FAIL |
| T2 | [100, 80] | 90.0 | 36.0 | FAIL |
| T3 | Nilai 60 | Lulus | Tidak lulus | FAIL |
| T4 | Nilai 59 | Tidak lulus | Tidak lulus | PASS |
| T5 | [80, 60, 90, 70] | 90 | 0 | FAIL |

## Bug Report

### B01 - Kesalahan Rata-rata

- **Gejala:** Hasil rata-rata tidak sesuai dengan jumlah data.
- **Lokasi:** Fungsi `hitung_rata_rata()`.
- **Akar penyebab:** Pembagi selalu menggunakan angka 5.
- **Perbaikan:** Menggunakan `len(nilai)` sebagai pembagi dan menangani list kosong.
- **Retest:** PASS.

### B02 - Kesalahan Status Kelulusan

- **Gejala:** Nilai 60 dinyatakan tidak lulus.
- **Lokasi:** Fungsi `status()`.
- **Akar penyebab:** Operator pembanding menggunakan `>`.
- **Perbaikan:** Mengganti operator menjadi `>=`.
- **Retest:** PASS.

### B03 - Kesalahan Nilai Tertinggi

- **Gejala:** Nilai tertinggi menghasilkan 0.
- **Lokasi:** Fungsi `nilai_tertinggi()`.
- **Akar penyebab:** Kondisi perbandingan menggunakan `<`.
- **Perbaikan:** Menggunakan `>` dan nilai awal dari data pertama.
- **Retest:** PASS.

## Retest

Setelah perbaikan, seluruh test case dijalankan kembali.

| ID | Hasil Setelah Perbaikan | Status |
|---|---|---|
| T1 | 75.0 | PASS |
| T2 | 90.0 | PASS |
| T3 | Lulus | PASS |
| T4 | Tidak lulus | PASS |
| T5 | 90 | PASS |

## Cara Menjalankan

Jalankan program praktik menggunakan perintah:

```bash
python3 praktik/praktik_4_debugging.py
```

Jalankan file kasus dan latihan secara terpisah untuk menguji masing-masing program.

## Refleksi

Saya mempelajari bahwa debugging harus dilakukan secara sistematis dengan mengamati output, menelusuri nilai variabel, menemukan akar penyebab bug, dan melakukan pengujian ulang. Test case membantu memastikan program menghasilkan output sesuai harapan setelah diperbaiki.