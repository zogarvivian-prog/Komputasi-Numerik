# Algoritma Penyelesaian Sistem Persamaan Non Linear - Metode Bisection
Nama : Ariance zogar 
Nim : 202521420005
Mata Kuliah : Komputasi Numerik

## 1. Deskripsi Masalah
Metode Bisection digunakan untuk mencari akar dari persamaan non linear
yang bentuknya f(x) = 0, dimana persamaan tersebut sulit diselesaikan
dengan cara analitik biasa.

Contoh persamaan yang saya gunakan:
f(x) = x^3 - x - 2 = 0

Tujuan kita adalah menemukan nilai x yang membuat f(x) mendekati 0.

## 2. Konsep Dasar
Metode ini bekerja dengan cara mengurung akar di dalam sebuah interval [a, b].
Syaratnya, nilai f(a) dan f(b) harus berlawanan tanda, artinya:
f(a) * f(b) < 0

Kalau syarat itu terpenuhi, berarti di antara a dan b pasti ada akar.

Lalu interval itu dibagi dua terus-menerus sampai intervalnya sangat kecil,
sehingga titik tengahnya bisa dianggap sebagai akar.

## 3. Langkah-Langkah Algoritma
1. Tentukan fungsi f(x) yang akan dicari akarnya.
   Contoh: f(x) = x^3 - x - 2

2. Tentukan interval awal [a, b].
   Contoh: a = 1, b = 2, karena f(1) = -2 (negatif) dan f(2) = 4 (positif)

3. Tentukan toleransi error (epsilon) dan iterasi maksimum.
   Contoh: epsilon = 0.001, iterasi maksimum = 100

4. Cek syarat awal: Jika f(a) * f(b) > 0, maka interval salah.
   Ulangi dari langkah 2 dengan interval baru.

5. Mulai perulangan (looping):
   a. Hitung titik tengah: c = (a + b) / 2
   b. Hitung nilai f(c)
   c. Jika f(c) == 0 atau (b - a) / 2 < epsilon, maka c adalah akar.
      Berhenti dan tampilkan c sebagai hasil.
   d. Jika f(a) * f(c) < 0, artinya akar ada di kiri.
      Maka ubah b = c (geser batas kanan ke tengah)
   e. Jika tidak, artinya akar ada di kanan.
      Maka ubah a = c (geser batas kiri ke tengah)

6. Ulangi langkah 5 sampai syarat berhenti terpenuhi atau
   iterasi sudah mencapai maksimum.

7. Tampilkan hasil akhir: nilai akar (c), nilai f(c), jumlah iterasi,
   dan tabel riwayat iterasi.

## 4. Contoh Perhitungan Manual (2 Iterasi Awal)
Iterasi 1: a=1, b=2 -> c = 1.5 -> f(1.5) = -0.125
Karena f(1) * f(1.5) > 0, maka a baru = 1.5

Iterasi 2: a=1.5, b=2 -> c = 1.75 -> f(1.75) = 1.609
Karena f(1.5) * f(1.75) < 0, maka b baru = 1.75

Proses ini dilanjutkan sampai interval sangat kecil.

## 5. Kelebihan dan Kekurangan
Kelebihan:
- Pasti menemukan akar jika syarat awal terpenuhi
- Konsepnya sederhana dan mudah dipahami
- Tidak butuh turunan fungsi

Kekurangan:
- Prosesnya agak lambat karena harus banyak iterasi
- Tidak bisa digunakan jika tidak ada interval awal yang tepat
