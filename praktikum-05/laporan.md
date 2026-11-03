# Laporan Praktikum Pertemuan 5 — Pemrograman Web 1 

Nama  : Seftiana Noormah Darani
NIM   : 2510010119
Kelas : 3B REG TI BJB

## Percobaan 1 — Box Model 
## Tabel Pengamatan 3.3

| No | Kondisi      | Lebar Kotak A (px) | Lebar Kotak B (px) |
|----|--------------|--------------------|--------------------|
| 1  | padding 20px |350                 |300                 |
| 2  | padding 40px |390                 |300                 |

| No | Kondisi                 | Jarak judul-paragraf (px) |
|----|-------------------------|---------------------------|
| 3  | Block biasa             |30                         |
| 4  | Di dalam flex column    |50                         |

| No | Kondisi .menu a     | Latar menimpa teks lain? (ya/tidak)|
|----|---------------------|------------------------------------|
| 5  | inline (bawaan)     |ya                                  |
| 6  | inline-block        |tidak                               | 

## Percobaan 2 — Flexbox Lab 
## Tabel Pengamatan 4.3

| No | Properti dan nilai                               | Pengamatan (tulis dengan kalimat Anda sendiri)                                                                |
|----|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| 1  | display: flex                                    | Item berpindah posisi dari vertikal menjadi horizontal.                                                       |
| 2  | justify-content: space-between                   | Item menempel di ujung kiri dan kanan, sisa ruang terbagi rata di antara item.                                |
| 2  | justify-content: space-evenly                    | Jarak kosong di tepi kiri, kanan, dan antar-item terbagi sama rata secara presisi.                            |
| 3  | align-items: stretch vs center                   | Stretch ditarik memenuhi wadah, sedangkan center membuat item berada di tengah vertikal.                      |
| 4  | flex-direction: column + justify-content: center | Item tersusun vertikal, dan justify-content memindahkan item ke posisi tengah secara vertikal.                |
| 5  | 8 item x 200 px, nowrap vs wrap                  | Pada nowrap item dipaksa mengecil, sedangkan pada wrap item yang tidak muat pindah ke baris baru di bawahnya. |
| 6  | .b { flex-grow: 1 }                              | Item B melebar mengisi seluruh sisa ruang kosong yang tersedia pada wadah.                                    |
| 7  | Lebar A / B / C (px)                             | Lebar A = 200px, Lebar B = 300px, Lebar C = 400px.                                                            |
| 8  | .c { order: -1 }                                 | Urutan tampilan item C berpindah menjadi paling depan/pertama di sebelah kiri.                                |
| 9  | .c { margin-left: auto }                         | Item C terdorong ke ujung paling kanan wadah, menyisakan ruang kosong di sebelah kirinya.                     |
| 10 | gap: 24px                                        | Terbentuk jarak pemisah sebesar 24px secara konsisten di antara item.                                         |

## Percobaan 3 — Positioning 
## Tabel Pengamatan 5.3

| No  | Eksperimen                                 | Pengamatan                                                                                                                                                                                           |
|-----|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | Header sticky saat digulir                 | Header mengikut alur dokumen saat di atas, lalu menempel terkunci di batas atas layar (`top: 0`) ketika halaman digulir ke bawah.                                                                    |
| 2a  | Header fixed tanpa padding-top body        | Header keluar dari alur dokumen normal sehingga menutupi bagian atas dari judul `h1` dan paragraf pertama halaman.                                                                                   |
| 2b  | Header fixed dengan padding-top 64px       | Konten halaman turun ke bawah sejauh 64px sehingga teks awal halaman kembali terlihat sepenuhnya dan tidak tertutup header.                                                                          |
| 3   | .notif tanpa position: relative            | Badge angka "3" melompat keluar dari tombol lonceng dan menempel ke pojok kanan atas elemen leluhur terdekat yang memiliki posisi (`.header`).                                                       |
| 4   | .lapis-1 z-index 3, lalu lapis-2 z-index 5 | Urutan tumpukan berubah; Lapis 1 menutupi Lapis 3, kemudian Lapis 2 yang memiliki `z-index` paling tinggi (5) berada di posisi paling depan menutupi semuanya.                                       |
| 5   | Header z-index 1                           | Header masih berada di atas elemen lapis yang tidak memiliki `z-index`, tetapi elemen lapis yang memiliki `z-index` lebih tinggi (seperti Lapis 1 dan Lapis 2) akan menutupi header saat bersentuhan.|
| 6   | Tombol Bantuan di layar 375 px             | Tombol bantuan dengan posisi `fixed` akan tetap konsisten menempel melayang di pojok kanan bawah jendela browser meskipun layar dipersempit atau digulir.                                            |

## Percobaan 4 — Dashboard 
![Desktop 1366 px](p4-dashboard/desktop.png) (gambarnya ada di bagian p4-dashboard/img)
![Mobile 375 px](p4-dashboard/mobile.png)    (gambarnya ada di bagian p4-dashboard/img)
 
## Jawaban Pertanyaan Analisis 
1. Mengapa box-sizing: border-box hampir selalu ditulis di baris pertama stylesheet proyek?

Karena border-box membuat ukuran elemen sudah termasuk padding dan border. Jadi, lebar elemen tidak bertambah meskipun kita menambahkan padding atau border. Hal ini membuat ukuran dan tata letak halaman lebih mudah diatur.

2. Mengapa pada eksperimen 4 item terkumpul di tengah secara vertikal?

Karena saat menggunakan flex-direction: column, arah utama (main axis) berubah menjadi vertikal. Properti justify-content: center mengatur posisi item pada arah utama tersebut. Akibatnya, semua item berkumpul di bagian tengah secara vertikal.

3. Perhitungan lebar B dan C pada eksperimen 7. Apa yang berubah jika .b diberi flex: 1 1 auto?

Lebar A adalah 200 px, sedangkan sisa ruang 800 px dibagi dengan perbandingan 1:2. Jadi, lebar B sekitar 266,7 px dan C sekitar 533,3 px. Jika B menggunakan flex: 1 1 auto, pembagian ruang akan memperhitungkan ukuran awal atau isi masing-masing item sehingga hasil lebarnya bisa berbeda.

4. Mengapa badge menempel ke header, bukan ke pojok halaman?

Karena ketika position: relative pada .notif dihapus, badge mencari elemen induk terdekat yang memiliki positioning. Dalam percobaan ini, elemen tersebut adalah header yang menggunakan position: sticky. Oleh karena itu, badge berpindah ke pojok kanan atas header.

5. Bandingkan sticky dan fixed untuk navbar dashboard. Mana yang dipilih dan alasannya?

Sticky membuat navbar tetap mengikuti aliran halaman dan menempel di bagian atas ketika halaman digulir. Sedangkan fixed membuat navbar selalu berada di posisi yang sama dan keluar dari aliran halaman. Saya memilih sticky karena lebih mudah digunakan dan tidak membuat konten tertutup navbar.

6. Apa fungsi flex: 1 pada .wrapper? Apa yang terjadi jika dihapus?

flex: 1 berfungsi membuat wrapper mengisi ruang kosong yang tersedia sehingga footer berada di bagian bawah halaman. Jika dihapus, wrapper tidak lagi mengisi seluruh ruang yang tersisa dan footer bisa naik ke tengah atau mengikuti tinggi konten saja.

## Kesimpulan 
Selama melakukan praktikum, saya mengalami beberapa kendala, seperti tampilan website yang tidak sesuai dengan yang diharapkan, CSS yang terkadang tidak berfungsi karena salah penulisan kode, dan posisi elemen yang sulit diatur. Selain itu, saya juga sempat bingung menentukan penggunaan Flexbox, mengatur jarak antar elemen, serta membuat tampilan tetap rapi saat ukuran layar diperkecil. Terkadang perubahan kode tidak langsung terlihat sehingga harus memeriksa kembali dan menyimpan file. Dari praktikum ini, saya belajar bahwa ketelitian dalam menulis kode sangat penting agar tampilan website dapat berjalan dengan baik.
