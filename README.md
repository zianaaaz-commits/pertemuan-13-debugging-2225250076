# Pertemuan 13 - Debugging dan Testing

Nama: Ziana Alfia Zahra  
NIM: 2225250076  
Kelas: 3A

## Kasus

Pertemuan ini membahas debugging, tracing, testing, dan test case pada program Python. Terdapat tiga kasus, yaitu bug batas kelulusan, kesalahan perhitungan rata-rata, dan penanganan file nilai.

## Test Case

| ID | Target | Input | Expected | Actual Awal | Status |
|---|---|---|---|---|---|
| T1 | Rata-rata | [80, 60, 90, 70] | 75.0 | 60.0 | FAIL |
| T2 | Rata-rata | [100, 80] | 90.0 | 36.0 | FAIL |
| T3 | Status kelulusan | 60 | Lulus | Tidak lulus | FAIL |
| T4 | Status kelulusan | 59 | Tidak lulus | Tidak lulus | PASS |
| T5 | Nilai tertinggi | [80, 60, 90, 70] | 90 | 0 | FAIL |

## Bug Report

### B01 - Kesalahan Perhitungan Rata-rata
- **Gejala:** Hasil rata-rata tidak sesuai dengan jumlah data.
- **Test case:** T1 dan T2.
- **Lokasi:** Fungsi `hitung_rata_rata()`.
- **Akar penyebab:** Pembagi selalu menggunakan angka 5.
- **Perbaikan:** Menggunakan `len(nilai)` sebagai pembagi dan menangani list kosong.
- **Retest:** PASS.

### B02 - Kesalahan Status Kelulusan
- **Gejala:** Nilai 60 dinyatakan tidak lulus.
- **Test case:** T3.
- **Lokasi:** Fungsi `status()`.
- **Akar penyebab:** Operator pembanding menggunakan `>`.
- **Perbaikan:** Mengganti operator menjadi `>=`.
- **Retest:** PASS.

### B03 - Kesalahan Nilai Tertinggi
- **Gejala:** Nilai tertinggi menghasilkan 0.
- **Test case:** T5.
- **Lokasi:** Fungsi `nilai_tertinggi()`.
- **Akar penyebab:** Kondisi perbandingan menggunakan `<` dan nilai awal ditetapkan 0.
- **Perbaikan:** Menggunakan `>` dan menginisialisasi nilai tertinggi dari data pertama.
- **Retest:** PASS.

## Retest

Setelah perbaikan kode, seluruh test case dijalankan kembali dengan hasil berikut.

| ID | Target | Expected | Actual Setelah Perbaikan | Status |
|---|---|---|---|---|
| T1 | Rata-rata | 75.0 | 75.0 | PASS |
| T2 | Rata-rata | 90.0 | 90.0 | PASS |
| T3 | Status kelulusan | Lulus | Lulus | PASS |
| T4 | Status kelulusan | Tidak lulus | Tidak lulus | PASS |
| T5 | Nilai tertinggi | 90 | 90 | PASS |

## Cara Menjalankan

Jalankan program praktik menggunakan perintah:

```bash
python3 praktik/praktik_4_debugging.py
```

Jalankan file kasus dan latihan secara terpisah untuk menguji masing-masing program.

## Refleksi

Saya mempelajari bahwa debugging harus dilakukan secara sistematis dengan mengamati output, menelusuri nilai variabel, menemukan akar penyebab bug, dan melakukan pengujian ulang. Test case membantu memastikan program menghasilkan output sesuai harapan setelah diperbaik