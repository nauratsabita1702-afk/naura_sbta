# TUGAS: Studi Kasus Sistem Transaksi & Validasi Toko Buku Modern
## A. Analisis Komponen

### 1. Variabel dan tipe data yang digunakan

No  Variabel   Tipe Data  Keterangan
1.  is_member  Boolean    status member pelanggan (input)
2.  jumlah_buku Integer   banyak buku yang dibeli (input) 
3.  total_awal  Real      total belanjan sebelum diptong diskon (input) 
4.  persen_diskon Real    besar presentase diskon (proses) 
5.  nominal_diskon Real   besar diskon dalam rupiah (output) 
6.  total_bayar  Real  total akhir uang yang harus dibayar (output) 

### 2. Struktur kontrol yang digunakan

1. ### Sequence:
   mulai dari urutan input (is_member, jumlah_buku, total_awal),perhitungan nominal_diskon, perhitungan total_bayar, dan menampilkan output
2. ### Selection (percabangan):
   - Mengecek is_member
   - is_member = true : mengecek total_awal >= 200000 AND jumlah_buku >= 3 jika terpenuhi mendapat diskon 15% dari total_awal diskon 10%
   - is_member = false : mengecek total_awal >= 300000 jika terpenuhi mendapat diskon 5%
3. ### Iteration (perulangan):
   pada WHILE akan mengecek total_awal < 0 ATAU jumlah_buku < 1 jika salah satu benar akan mengulang terus sampai total_awal >=0 DAN jumlah_buku >=1

## B. Pseudocode

```
PROGRAM PerhitunganTotalPembayaranTokoBukuModern

DEKLARASI:
   is_member      : boolean
   jumlah_buku    : integer
   total_awal     : real
   persen_diskon  : real 
   nominal_diskon : real
   total_bayar    : real

ALGORITMA:
   input (is_member)
   input (jumlah_buku)
   input (total_awal)

   WHILE (total_awal < 0) OR  (jumlah_buku < 1)
       OUTPUT("total_awal tidak boleh kurang dari 0 dan jumlah_buku minimal 1, silahkan input ulang")
       INPUT(jumlah_buku)
       INPUT(total_awal)
   ENDWHILE

   IF (is_member = true ) THEN
      persen_diskon <- 0.10
      IF (total_awal >= 200000 AND (jumlah_buku >= 3) THEN
         persen_diskon <- persen_diskon + 0.05
      ENDIF
   ELSE
      IF (total_awal >= 300000) THEN
         persen_diskon <- 0.05
      ELSE
         persen_diskon <- 0.0
      ENDIF
   ENDIF

   nominal_diskon <- total_awal × persen_diskon
   total_bayar <- total_awal - nominal_diskon

   OUTPUT (nominal_diskon)
   OUTPUT (total_bayar)

```

## C. Uji logika / trace table

Kasus A: is_member = true, total_awal = 250000, jumlah_buku = 4

| No | keterangan proses | is_member | jumlah_buku | total_awal | hasil validasi | persen_diskon | nominal_diskon | total_bayar | 
| -- | ---------- | --------- | ----------- | ---------- | ----------------- | ------------- | -------------- | ----------- |
| 1. | input status member pelanggan | true | - | - | - | - | - | - |
| 2. | input jumlah buku | true | 4 | - | - | - | - | - |
| 3. | input total belanja awal | true | 4 | 250000 | - | - | - | - |
| 4. | mengecek WHILE: 250000 < 0 false, 4 < 1 false -> loop tidak dijalankan | true | 4 | 250000 | false | - | - | - |
| 5. | is_member = true -> diskon dasar | true | 4 | 250000 | - | 0.10| - | - |
| 6. | mengecek IF: 250000 >= 200000 true AND 4 >= 3 true -> mendapat tambahan diskon 0.05 dari 0.10 | true | 4 | 250000 | - | 0.15 | - | - |
| 7. | perhitungan nominal_diskon | true | 4 | 250000 | - | 0.15 | 37500 | - |
| 8. | perhitungan total_bayar | true | 4 | 250000 | - | 0.15 | 37500 | 212500 |
| 9. | output nominal_diskon 37500, total_bayar 212500 | true | 4 | 250000 | - | 0.15 | 37500 | 212500 |

Kasus B: is_member = False, total_awal = 350000, jumlah_buku = 2

| No | keterangan proses | is_member | jumlah_buku | total_awal | hasil validasi | persen_diskon | nominal_diskon | total_bayar | 
| -- | ---------- | --------- | ----------- | ---------- | ----------------- | ------------- | -------------- | ----------- |
| 1. | input status member pelanggan | false | - | - | -| - | - | - |
| 2. | input jumlah buku | false | 2 | - | - | - | - | - |
| 3. | input total belanja awal | false | 2 | 350000 | - | - | - | - |
| 4. | mengecek WHILE: 350000 < 0 false, 2 < 1 false -> loop tidak dijalankan | false | 2 | 350000 | false | - | - | - |
| 5. | is_member = false -> tidak dapat diskon dasar | false | 2 | 350000 | - | - | - | - |
| 6. | mengecek IF: 350000 >= 300000 true -> mendapat diskon 0.05 | false | 2 | 350000 | - | 0.05 | - | - |
| 7. | perhitungan nominal_diskon | false | 2 | 350000 | - | 0.05 | 17500 | - |
| 8. | perhitungan total_bayar | false | 2 | 350000 | - | 0.05 | 17500 | 332500 |
| 9. | output nominal_diskon 17500, total_bayar 332500 | false | 2 | 350000 | - | 0.05 | 17500 | 332500 |

Kasus C: Input awal total_awal = -50000 (salah), lalu dikoreksi menjadi 100000, is_member = False, jumlah_buku = 1

| No | keterangan proses | is_member | jumlah_buku | total_awal | hasil validasi | persen_diskon | nominal_diskon | total_bayar | 
| -- | ---------- | --------- | ----------- | ---------- | ----------------- | ------------- | -------------- | ----------- |
| 1. | input stataus member pelanggan | false | - | - | - | - | - | - |
| 2. | input jumlah buku | false | 1 | - | - | - | - | - |
| 3. | input total belanja awal | false | 1 | -50000 | - | - | - | - |
| 4. | 




  
