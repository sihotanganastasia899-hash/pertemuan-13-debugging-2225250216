# Pertemuan 13 - Debugging dan Testing

Nama: Cindhy Sherenita Sihotang
NIM: 2225250216
Kelas: 3F

## Kasus
Praktik ini menguji dan memperbaiki program Python yang memproses data nilai mahasiswa (menghitung rata-rata, status kelulusan, dan nilai tertinggi) yang sebelumnya mengandung beberapa *logical error*.

## Test Case
| ID | Input | Expected | Actual Awal | Status |
|---|---|---|---|---|
| T1 | [80, 60, 90, 70] (rata-rata) | 75.0 | 60.0 | FAIL |
| T2 | [100, 80] (rata-rata) | 90.0 | 40.0 | FAIL |
| T3 | 60 (status) | Lulus | Tidak lulus | FAIL |
| T4 | 59 (status) | Tidak lulus | Tidak lulus | PASS |
| T5 | [80, 60, 90, 70] (tertinggi) | 90 | 0 | FAIL |

## Bug Report
- **B01 (Rata-rata):** Pembagi pada fungsi ditulis secara hardcode angka 5, diperbaiki menggunakan `len(nilai)`.
- **B02 (Status Kelulusan):** Operator pembanding menggunakan `>` sehingga nilai 60 dianggap tidak lulus, diperbaiki menjadi `>=`.
- **B03 (Nilai Tertinggi):** Inisialisasi variabel tertinggi diawali angka 0 dan menggunakan operator `<` yang salah, diperbaiki dengan menginisialisasi elemen pertama list dan operator `>`.

## Retest
Seluruh test case (T1 sampai T5) telah dijalankan ulang dan menghasilkan status **PASS** tanpa ada regresi.

## Cara Menjalankan
```bash
py praktik/praktik_4_debugging.py