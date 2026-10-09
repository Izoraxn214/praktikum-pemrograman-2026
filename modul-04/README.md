# Modul Praktikum 4 — Program Grading 🎓

> **Isi repo ini cuma HINT, bukan jawaban jadi.** Pakai buat ngarahin logika, terus tulis kode lo sendiri ya.

## 📌 Ringkasan Tugas

Bikin program yang:
1. Baca data nilai mahasiswa dari file **`DataNilai.xlsx`**
2. Hitung **Nilai Akhir (NA)** tiap mahasiswa
3. Tentuin **Grade** berdasarkan tabel
4. Cetak **tabel laporan** yang rapi + **rekapitulasi** jumlah tiap grade

**Konsep yang wajib dipakai:** `print` format, `while` / do-loop, `list`, konsep *counting*.

---

## 🧮 Rumus & Aturan

```
NA = 30% × Nilai Lain2 + 35% × UTS + 35% × UAS
```

| Rentang NA | Grade |
|-----------|-------|
| 86 – 100  | A     |
| 81 – 85   | A-    |
| 76 – 80   | B+    |
| 71 – 75   | B     |
| 66 – 70   | B-    |
| 61 – 65   | C+    |
| 56 – 60   | C     |
| < 56      | TL (Tidak Lulus) |

---

## 🪜 4 Langkah Pembuatan Program (buat Laporan Pendahuluan)

<details>
<summary><b>1. Definisi / Analisis Masalah</b></summary>

- **Input:** Nama, Nilai Lain2, UTS, UAS (dari Excel)
- **Proses:** hitung NA → tentukan grade → hitung jumlah tiap grade
- **Output:** tabel laporan + rekapitulasi
</details>

<details>
<summary><b>2. Algoritma (langkah-langkah)</b></summary>

1. Mulai
2. Baca file Excel, simpan tiap kolom ke `list`
3. Siapkan counter tiap grade = 0
4. Set `i = 0`
5. Selama `i < jumlah data`:
   - Hitung NA[i]
   - Tentukan grade[i] pakai if-elif
   - Tambah counter grade yang sesuai
   - Cetak 1 baris tabel
   - `i = i + 1`
6. Cetak rekapitulasi
7. Selesai
</details>

<details>
<summary><b>3. Flowchart</b></summary>

Gambar sesuai algoritma di atas. Bagian pentingnya:
- **Decision (belah ketupat)** buat kondisi loop `i < n`
- **Decision berantai** buat penentuan grade (A? → A-? → B+? → ...)
- Panah balik dari akhir loop ke kondisi `i < n`
</details>

<details>
<summary><b>4. Pseudocode / Coding</b></summary>

Lihat bagian hint kode di bawah ⬇️
</details>

---

## 💡 Hint Kode (Python)

### Hint 1 — Baca file Excel

Bisa pakai `pandas` (paling gampang) atau `openpyxl`.

```python
import pandas as pd

df = pd.read_excel("DataNilai.xlsx")
print(df.columns)   # CEK DULU nama kolomnya apa aja!
```

Terus ubah kolomnya jadi `list` (karena modul minta pakai list):

```python
nama = df["Nama"].tolist()        # sesuaikan nama kolom dengan file lo
# lakukan hal yang sama untuk kolom nilai lain2, UTS, UAS
```

> ⚠️ Kalau error `ModuleNotFoundError`, install dulu: `pip install pandas openpyxl`

### Hint 2 — Rumus NA

Ingat persen = dibagi 100. `30%` → `0.30`.

```python
na = 0.30 * ... + 0.35 * ... + 0.35 * ...
```

### Hint 3 — Penentuan grade (jebakan!)

Jangan pakai `81 <= na <= 85`, karena NA bisa **desimal** (misal `85.5`) dan bakal "jatuh di celah" antar rentang. Pakai batas bawah aja dari atas ke bawah:

```python
if na >= 86:
    grade = "A"
elif na >= 81:
    grade = "A-"
elif ...:
    ...
else:
    grade = "TL"
```

### Hint 4 — Konsep counting

Siapin variabel penghitung di **luar** loop, tambahin di **dalam** loop:

```python
jumlah_A = 0
# ... dst untuk grade lain

# di dalam loop:
if grade == "A":
    jumlah_A += 1
```

> 💭 Bonus: bisa juga pakai `dict` biar lebih ringkas, tapi pastiin dulu boleh sama asisten/dosen.

### Hint 5 — While loop

```python
i = 0
while i < len(nama):
    # hitung NA, grade, counting, print baris
    i += 1      # JANGAN LUPA, kalau nggak infinite loop 💀
```

### Hint 6 — Print format biar tabelnya lurus

Pakai f-string dengan lebar kolom:

```python
print(f"{no:<4}| {nama[i]:<14}| {na:>6.2f} | {grade:^6} |")
```

| Format | Arti |
|--------|------|
| `:<14` | rata kiri, lebar 14 karakter |
| `:>6`  | rata kanan, lebar 6 |
| `:^6`  | rata tengah, lebar 6 |
| `.2f`  | 2 angka di belakang koma |

Garis pemisah: `print("-" * 39)`

---

## 🖥️ Contoh Struktur Output

```
Program Grading
Nama : <nama lo>
NRM  : <NIM lo>

LAPORAN GRADING MAHASISWA
---------------------------------------
No  | Nama          | Nilai  | Grade  |
    | Mahasiswa     | Akhir  |        |
----|---------------|--------|--------|
1   | MAHASISWA 1   |  xx.xx |   xx   |
2   | MAHASISWA 2   |  xx.xx |   xx   |
...
---------------------------------------
Rekapitulasi :
Grade A     = ...
Grade A-    = ...
Grade B+    = ...
Grade B     = ...
Grade B-    = ...
Grade C+    = ...
Grade C     = ...
Tidak Lulus = ...
Total Mahasiswa = ...
*selesai*
```

> 📝 Di contoh output modul, **Grade B** nggak ada di rekapitulasi (kayaknya typo). Tetep masukin aja biar totalnya cocok.

---

Good luck! 🚀
