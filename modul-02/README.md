# Modul Praktikum 2: Mencari Faktor Bilangan

Modul praktikum ini bertujuan untuk membuat program pencari faktor dari suatu bilangan bulat positif kurang dari 100. Program akan berjalan secara berulang untuk menerima input angka dan menampilkan daftar faktornya hingga pengguna memasukkan angka `0`.

---

## 1. Deskripsi Tugas

Membuat program interaktif untuk mencari seluruh faktor dari suatu bilangan.
* **Contoh:**
  * Bilangan 15 $\rightarrow$ faktornya adalah: 1, 3, 5, 15.
  * Bilangan 24 $\rightarrow$ faktornya adalah: 1, 2, 3, 4, 6, 8, 12, 24.
* **Ketentuan Khusus:** Wajib menggunakan tipe data `list` untuk menyimpan daftar faktor bilangan yang ditemukan.

---

## 2. Hint Sintaks & Komponen Coding yang Digunakan

Berikut adalah komponen dan konsep pemrograman Python yang perlu diterapkan dalam kode program:

1. **Format Pencetakan (`print` format)**
   * Digunakan untuk menampilkan *header* identitas (Nama dan NRM) serta pesan luaran.
   * *Hint:* Gunakan f-string (misalnya `f"Bilangan {bil} Faktornya = {faktor}"`) agar penggabungan teks dan variabel lebih rapi.

2. **Perulangan Utama (`while` / `do-while` loop)**
   * Digunakan agar program dapat terus meminta input bilangan dari pengguna secara berulang.
   * *Hint:* Gunakan perulangan `while True:` dan tambahkan kondisi penghentian (`break`) saat pengguna memasukkan angka `0`.

3. **Tipe Data & Manipulasi List (`list`)**
   * Digunakan untuk menampung seluruh faktor dari bilangan yang diinput.
   * *Hint:* 
     * Inisialisasi *list* kosong (misal: `faktor = []`) di dalam *loop* input agar *list* direset setiap kali ada input angka baru.
     * Gunakan metode `.append()` untuk menambahkan faktor yang ditemukan ke dalam *list*.

4. **Operasi Sisa Bagi / Modulo (`%`)**
   * Digunakan untuk mengecek apakah suatu angka pembagi merupakan faktor dari bilangan yang diuji.
   * *Hint:* Suatu angka `i` adalah faktor dari `bilangan` jika `bilangan % i == 0`.

5. **Perulangan Iterasi Faktor (`for` loop)**
   * Digunakan untuk menguji seluruh kandidat pembagi dari `1` sampai sebesar `bilangan`.
   * *Hint:* Gunakan fungsi `range(1, bilangan + 1)` untuk menguji setiap angka pembagi.

6. **Input Handling (`input()` & `int()`)**
   * Digunakan untuk menerima masukan dari pengguna dan mengonversinya menjadi tipe data bilangan bulat (integer).

---

## 3. Hint Alur Logika Pemrograman (Pseudocode)

1. Tampilkan identitas Nama dan NRM di bagian awal program.
2. Jalankan perulangan `while`:
   - Minta masukan angka dari pengguna (`Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = `).
   - Periksa apakah angka masukan bernilai `0`:
     - Jika bernilai `0`, cetak `*SELESAI*` dan hentikan perulangan (`break`).
   - Buat variabel *list* kosong untuk menampung faktor.
   - Jalankan perulangan `for` dari `1` hingga angka yang dimasukkan pengguna:
     - Jika angka masukan habis dibagi angka iterasi (sisa bagi == 0):
       - Masukkan angka iterasi tersebut ke dalam *list* faktor menggunakan `.append()`.
   - Tampilkan hasil bilangan beserta *list* faktor yang didapatkan.

---

## 4. Contoh Luaran (Output) Program

```text
Program Faktor Bilangan
Nama : [Nama Praktikan]
NRM  : [NRM Praktikan]
XXXXXXXXXXXXXXXXXX
9999999999999999
Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = 15
Bilangan 15 Faktornya = [1, 3, 5, 15]
Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = 24
Bilangan 24 Faktornya = [1, 2, 3, 4, 6, 8, 12, 24]
Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = 0
*SELESAI*
