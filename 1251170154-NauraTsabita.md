# BAGIAN A: Rancangan Algoritma Dengan Karakteristik Lengkap 
## Studi Kasus Kelas C: Algoritma Pemesan Makanan Secara Online VIA Aplikasi
### Langkah-langkah Pemesanan Makanan Secara Online VIA Aplikasi Gofood
1. pengguna mulai dengan membuka aplikasi gojek lalu pilih menu **Gofood**
2. setelah itu, memilih restoran yang diinginkan melalui kolom pencarian
3. jika sudah memilih restoran selanjutnya memilih menu makanan atau minuman yang diinginkan dan menentukan jumlah pesanannya
4. selanjutnya, kalo sudah menentukan jumlah yang ingin dipesan lalu pencet tombol bacaan yang ada tulisan **"tambah"** agar menu yang sudah dipilih masuk ke keranjang 
5. lalu pencet gambar **"keranjang"** sehingga akan muncul **subtotal** dari seluruh menu yang udah dimasukkan
6. membuat alamat pengantaran yang akan dituju
7. memilih kecepatan pengiriman yang diinginkan
8. sesudah itu, akan muncul perhitungan **ongkos kirim** yang dijumlahkan dengan subtotal menjadi **total bayar** yang harus dibayarkan
9. memilih metode pembayaran yang diinginkan seperti **gopay**, **gopay later**, **kartu kredit atau debit**, **linkaja**, **kantong jago**, dan **cash**
10. jika sudah semuanya menekan tombol bacaan **"pesan dan antar sekarang"**
11. kalau pembayaran sudah berhasil otomatis pesanan akan masuk ke sistem restoran tapi kalau gagal pengguna harus memilih ulang metode pembayaran
12. restoran akan menerima pesanan tersebut 
13. jika sudah diterima otomatis akan mencarikan driver untuk mengambil pesanan
14. selanjutnya, restoran akan menyiapkan makanan sambil menunggu driver 
15. driver tiba akan mengambil pesanan yang sudah disiapkan
16. driver akan mengantarkan pesanan ke alamat tujuan
17. jika pesanan sudah sampai akan berubah menjadi **"pesanan selesai"**

### penjelasan 5 karakteristik yang digunakan:
- Input: pemilihan resto, pemilihan menu beserta jumlahnya, menentukan alamat pengantaran, pemilihan kecepatan pengiriman, pemilihan metode pembayaran
- Output: subtotal seluruh menu makanan dikeranjang, total bayar setelah digabungkan dengan ongkir, pesanan selesai
- Definiteness: kalau **"berhasil"** pesenan masuk kek sistem, kalau **"gagal"** memilih ulang metode pembayaran
- Finiteness: langkah selesai pada langkah ke 17 karena status udah berubah menjadi **"pesenan selesai"**
- Effectiveness: langkah langkah yang dapat dijalankan terdapat pada 5 dan 8

 # BAGIAN B: Analisis Pemilihan Struktur Data
 ## Pilihlah struktur data yang paling tepat (Array, Linked List, Stack, Queue, Binary Search Tree, Hash Table, atau Graph) untuk menyelesaikan 3 skenario di bawah ini. Berikan alasan logis mengapa struktur data tersebut dipilih!

 1. Skenario 1 (Fitur Fitur Undo / Redo):
Sebuah aplikasi pengolah kata (Text Editor) membutuhkan fitur untuk membatalkan ketikan terakhir pengguna (Undo) dan mengembalikannya lagi (Redo).
Struktur Data Terpilih: Stack
Alasan: cara kerja undo / redo seperti tumpukan piring di dapur jika mengetik hal baru akan membuat tumpukan baru dari ketikan sebelumnya. ketika user mengetik akan tersimpan ke dalam undo stack dan jika tombol undo ditekan ketikan paling akhir akan dikeluarkan dan akan dipindahkan ke redo stack  supaya dapat dikembalikan kembali

2. Skenario 2 (Peta Navigasi Rute Perjalanan):
Sebuah aplikasi GPS membutuhkan cara untuk memodelkan lokasi-lokasi kota beserta jalan penghubungnya guna mencari rute tercepat.
Struktur data terpilih: Graph
Alasan: setiap kota yang saling terhubung dengan kota lainnya biasanya ada beberapa pilihan jalan untuk sampai ke tujuan yang sama dengan waktu yang berbeda. maka dari itu struktur data yang tepat digunakan adalah GRAPH, di mana setiap kota dianggap sebagai node dan jalan yang menghubungkan antar kota dianggap edge dengan memberikan estimasi perjalanan

3. Skenario 3 (Sistem Login Pengguna Berbasis Username):
Sistem butuh mencari data akun dari jutaan user secara instan berdasarkan Username saat proses login.
Struktur data terpilih: Hash Table
Alasan: jumlah user yang login banyak dan jika ingin mencari username lain pasti akan muncul hasil yang berbeda, maka itu struktur data yang dipilih dengan tepat adalah HASH TABLE karena username akan memiliki alamat penyimpanan masing-masing jadi kalo ada pencarian terhadap username lain sistem akan menuju lokasi data yang dsibutkan oleh user pencari

# Bagian C: Eksplorasi Analogi Mandiri
## Pilih salah satu: Array, Linked List, Stack, Queue, Tree, Graph, atau Hash Table.
Jelaskan:
1. Nama analogi kehidupan sehari-hari yang Anda buat.
2. Bagaimana cara kerja analogi tersebut.
3. Mengapa analogi tersebut mencerminkan kelebihan atau kekurangan dari struktur data yang dipilih.
- pilihan struktur data saya: Queue
- Penjelasan:
  1. Nama analogi kehidupan sehari-hari yang di saya buat: antrean naik transportasi umum transjakarta, yaitu sistem antrean yang saya lakukan ketika menaiki transjakarta
  2. cara kerja analogi: ketika saya datang ke halte transjakarta halte tersebut sedang ramai dan saya tidak bisa langsung mengambil antrean di depan tetapi harus mengambil posisi yang paling belakang barisan. orang yang datang duluan sebelum saya sudah berada di barisan paling depan dan dia yang akan masuk pertama ke dalam ketika pintu bus terbuka. setelah orang pertama masuk, giliran orang berikutnya yang ada di barisan paling depan untuk masuk, dan seterusnya sampai giliran saya yang berada di barisan belakang masuk. ketika saya datang berbaris di paling belakang merepresentasikan proses enqueue. sebaliknya ketika saya sudah tiba untuk masuk ke dalam bus dan keluar dari barisan merepresentasikan proses dequeue. 
  3. mengapa analogi ini mencerminkan kelebihan atau kekurangan dari struktur data Queue?: kelebihan dari struktur data Queue menunjukkan sikap keadilan di mana urutan masuk bus berdasarkan siapa yang datang lebih dulu, bukan berdasarkan siapa yang datang belakangan, dan ini sesuai dengan prinsip FIFO (First In, First Out).

selain itu, analogi ini juga menunjukkan kekurangan struktur data Queue yaitu ketika saya sedang buru buru dan posisi saya itu berada di belakang barisan, membuat saya tetap menunggu sampai tiba giliran saya masuk tanpa mendahului orang yang berada di barisan depan. nah dengan itu struktur data Queue mempunyai kelemahan pada proses pengambilan data.

