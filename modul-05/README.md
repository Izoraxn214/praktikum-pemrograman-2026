
# 💡 Hint — Modul Praktikum 6: Mengurutkan (Sorting)

> File ini isinya **petunjuk**, bukan jawaban jadi. Coba kerjain dulu sendiri, buka hint satu per satu kalau mentok.
> Bagian yang ada tanda ▶ bisa diklik buat dibuka.

---

## 📌 Ringkasan Tugas

Buat program yang:
1. Menampilkan judul, **Nama**, dan **NRM**.
2. Menampilkan **data nilai awal** (100 data).
3. Mengurutkan data dari **terkecil → terbesar**.
4. Menampilkan **data terurut** dalam **10 baris × 10 kolom**, dipisah koma.
5. Diakhiri tulisan `*selesai*`.

**Materi yang dipakai:** `print` + format, `while` loop, `list`.

> ⚠️ Kalau dosen minta pakai **while loop**, jangan langsung pakai `sorted()` atau `.sort()` — itu biasanya dianggap "curang". Bikin algoritma sorting-nya sendiri.

---

## 📝 Laporan Pendahuluan — 4 Langkah Pembuatan Program

Isi keempat langkah ini **sebelum** ngoding:

| Langkah | Yang ditulis |
|---|---|
| 1. Analisis masalah | Apa input-nya, apa output-nya, apa yang harus diproses |
| 2. Algoritma | Langkah-langkah dalam bahasa manusia (urut, bernomor) |
| 3. Flowchart / Pseudocode | Gambaran alur program, terutama bagian loop |
| 4. Implementasi (coding) | Terjemahan algoritma ke Python |

<details>
<summary>▶ Hint: Analisis masalah</summary>

- **Input:** list `Nilai` berisi 100 bilangan bulat (sudah ditentukan di modul, tidak perlu `input()`).
- **Proses:** membandingkan dan menukar posisi elemen sampai urut naik (ascending).
- **Output:** teks identitas, data awal, data terurut 10 per baris.

</details>

---

## 🧠 Hint 1 — Pilih Algoritma

Untuk tugas level ini, yang paling gampang dijelasin di laporan:

| Algoritma | Ide singkat |
|---|---|
| **Bubble Sort** | Bandingkan 2 elemen bersebelahan, tukar kalau yang kiri lebih besar. Ulangi sampai tidak ada yang ditukar. |
| **Selection Sort** | Cari nilai terkecil dari sisa data, taruh di depan. Ulangi. |

Saran: **Bubble Sort**, karena paling cocok sama `while` loop.

<details>
<summary>▶ Hint: Cara kerja Bubble Sort (contoh kecil)</summary>

Data: `[5, 2, 4, 1]`

```
Putaran 1: [2, 5, 4, 1] → [2, 4, 5, 1] → [2, 4, 1, 5]   ← angka terbesar "mengapung" ke kanan
Putaran 2: [2, 4, 1, 5] → [2, 1, 4, 5]
Putaran 3: [1, 2, 4, 5]
Putaran 4: tidak ada yang ditukar → SELESAI
```

Kuncinya: setiap putaran, elemen terbesar yang tersisa pindah ke posisi paling kanan.

</details>

---

## 🔁 Hint 2 — Menukar Dua Elemen List

Di Python, menukar isi dua posisi bisa satu baris:

```python
a[i], a[i+1] = a[i+1], a[i]
```

<details>
<summary>▶ Hint: Cara lain (pakai variabel bantu)</summary>

```python
temp = a[i]
a[i] = a[i+1]
a[i+1] = temp
```

Cara ini bagus buat dijelasin di flowchart karena lebih kelihatan langkahnya.

</details>

---

## 🔄 Hint 3 — Struktur `while` untuk Sorting

Butuh **dua loop bersarang**:
- **Loop luar** → mengulang putaran, berhenti kalau sudah tidak ada pertukaran.
- **Loop dalam** → jalan dari indeks `0` sampai sebelum elemen terakhir, membandingkan pasangan bersebelahan.

<details>
<summary>▶ Hint: Pseudocode</summary>

```
salin data ke list baru (biar data awal tetap utuh)
n ← panjang data
ditukar ← True

SELAMA ditukar:
    ditukar ← False
    i ← 0
    SELAMA i < n - 1:
        JIKA data[i] > data[i+1]:
            tukar data[i] dan data[i+1]
            ditukar ← True
        i ← i + 1
```

</details>

<details>
<summary>▶ Hint: Kenapa harus disalin dulu?</summary>

Kalau langsung ngurutin `Nilai`, isi aslinya ikut berubah. Padahal kamu masih perlu nampilin **data awal**.
Pakai `Nilai.copy()` atau `Nilai[:]`, atau tampilkan data awal **sebelum** proses sorting.

</details>

---

## 🖨️ Hint 4 — Menampilkan Data Awal (satu baris, dipisah koma)

<details>
<summary>▶ Hint</summary>

`join` cuma bisa menggabungkan string, jadi angka harus diubah dulu:

```python
", ".join(str(x) for x in Nilai)
```

</details>

---

## 🧱 Hint 5 — Menampilkan 10 Data per Baris

Data terurut harus muncul **10 baris, masing-masing 10 angka**.

Idenya: ambil potongan list per 10 elemen → `data[0:10]`, `data[10:20]`, dst.

<details>
<summary>▶ Hint: Pakai while + slicing</summary>

```
k ← 0
SELAMA k < panjang data:
    ambil potongan data[k : k+10]
    cetak potongan itu dipisah koma
    k ← k + 10
```

</details>

<details>
<summary>▶ Hint: Biar kolomnya rapi (opsional)</summary>

Pakai format lebar tetap supaya angka sejajar:

```python
f"{x:3d}"   # lebar 3 karakter, rata kanan
```

Contoh hasil:
```
 13,  14,  15,  15,  22,  24,  24,  25,  26,  27
```

</details>

---

## 🧩 Hint 6 — Kerangka Program

<details>
<summary>▶ Buka kalau udah bener-bener mentok</summary>

```python
Nilai = [85, 13, 99, ...]   # salin lengkap 100 data dari modul

print("Program Sorting")
print("Nama :", ...)
print("NRM  :", ...)
print()

print("Data nilai awal :")
# TODO: tampilkan Nilai dipisah koma

data = ...          # TODO: salinan Nilai
n = ...
ditukar = True

while ditukar:
    ditukar = False
    i = 0
    while i < n - 1:
        # TODO: bandingkan & tukar
        i += 1

print()
print("Data nilai terurut :")
k = 0
while k < n:
    # TODO: cetak 10 data per baris
    k += 10

print("*selesai*")
```

</details>

---
