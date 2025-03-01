[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/_CBw5qWL)
# Graded Challenge 3

_Graded Challenge ini dibuat guna mengevaluasi pembelajaran pada Hacktiv8 Comprehensive Data Analytics Program khususnya pada konsep Web Scraping dan Pandas._

---

## Assignment Instructions

*Graded Challenge 3* dikerjakan dalam format **Notebook (.ipynb)**  di bawah ini:

1. *Project* dinyatakan selesai dan diterima untuk dinilai jika notebook dapat dirun seluruhnya tanpa ada error (code block web scraping tidak perlu dirun ulang).

2. Pada tugas Graded Challenge 3, akan diminta untuk membuat:
   -  **Notebook (.ipynb)** yang berisikan pengambilan dan pengolahan. Kerjakan dengan Visual Studio Code!

3. Notebook **wajib** diberikan keterangan atau pengenalan dengan menggunakan `comment` atau `docstring` yang berisikan Judul tugas, Nama, Batch, dan penjelasan singkat tentang program yang dibuat, fitur-fitur. Contoh:
    ```py
    '''
    =================================================
    Graded Challenge 3

    Nama  : Fahmi Iman Alfarizki
    Batch : CODA-RMT-0011

    Program ini dibuat untuk melakukan automatisasi pengolahan (cleaning) data text yang berguna untuk pemodelan model analisa sentimen.
    =================================================
    '''
    ```
5. Tiap cell diberikan penjelasan mengenai apa yang dilakukan/dijalankan dengan markdown.

6. **WARNING**: Plagiarisme sekecil apapun dapat terdeteksi. Tugas ini akan diuji tingkat plagiarismenya dengan software khusus.

---

## Assignment Submission

- Simpan assignment pada Graded Challenge 3 ini dengan nama `P0G3_<nama-student>.ipynb` (notebook). Misal `P0G3_fahmi-iman.ipynb`(**Maksimal nama dua suku kata**).
- Push file Assigment yang telah dibuat ke repository Github Classroom masing-masing student.

---

## Assignment Objectives

*Graded Challenge 3* ini dibuat guna mengevaluasi konsep Web Scraping dan Pandas sebagai berikut:

- Mampu mengambil data dari sumber internet dengan Web Scraping.
- Mampu melakukan data preparation sebelum analisis selanjutnya dengan Pandas.

---

## Assignment Instructions and Cases

#### Case
Kamu ingin menambah pendapatanmu dengan berjualan. Namun, kamu tidak punya cukup modal untuk produksi barang dan hanya cukup untuk promosi, sehingga kamu memutuskan untuk menjalanan skema dropship di platform Tokopedia.

Kamu masih bingung akan berjualan apa dan teringat bahwa saat ini sedang viral seblak. Namun, kamu tidak yakin apakah benar bahwa masyarakat memiliki animo yang besar terhadap seblak.

Karena kamu lulusan bootcamp CODA Hacktiv8, dengan kemampuan dan pengetahuan kamu, kamu ingin menganalisis bagaimana penjualan produk seblak di Tokopedia. Apakah orang suka, apakah banyak yang beli, dsb.

Tantangannya, kamu tidak punya data sama sekali selain yang terpampang pada website e-commerce Tokopedia. Oleh karena itu, perjalanan kamu dimulai dari pengambilan data menggunakan Web Scraping!

#### A. Web Scraping
1. Lakukan pengambilan data dari halaman pencarian kata kunci produk "seblak". Kamu bisa langsung akses link ini:
   https://www.tokopedia.com/search?navsource=&page=1&q=seblak&srp_component_id=02.01.00.00&srp_page_id=&srp_page_title=&st=
  
   Berikut tampilan halaman link di atas:
   ![img](https://github.com/FTDS-learning-materials/phase-0/blob/main/img/p0gc3_1.png?raw=true)

2. Ambil data `Nama Produk`, `Harga Produk`, `Penjual`, `Kota Toko`, `Banyaknya Terjual`, dan `Rating Produk`.

3. Tokopedia memiliki skema promosi sehingga pada panel teratas merupakan info produk suatu merchant yang membayar iklan. Kita akan ambil produk di dalam box yang reguler dengan elemen `<div class="css-974ipl">`.

   **Tambahan:** untuk produk baru, belum ada informasi berapa produk yang terjual dan rating sehingga hasil akhir akan berbeda jumlah data yang diperoleh untuk kolom `Banyaknya Terjual` dan `Rating Produk` seperti contoh gambar di bawah:

   ![img](https://github.com/FTDS-learning-materials/phase-0/blob/main/img/p0gc3_2.png?raw=true)

   Sehingga kamu perlu mengatasi hal ini dengan cara, jika menemukan bahwa tidak ada informasi `Banyaknya Terjual` dan `Rating Produk`, kamu hanya perlu mengisi data dengan `None` (tanpa string) dan pandas akan langsung mendeteksi sebagai missing value.

4. Untuk memudahkan kamu, sudah disediakan list elemen salah satu produk:
   ```html
   <div class="prd_link-product-name css-3um8ox" data-testid="spnSRPProdName">SEBLAK JUARA INSTAN MASAK BASAH ASLI BANDUNG ENAK MANTAP</div>
   <div class="prd_link-product-price css-1ksb19c" data-testid="spnSRPProdPrice">Rp22.000</div>
   <div class="css-1rn0irl"><span class="prd_link-shop-loc css-1kdc32b flip" data-testid="spnSRPProdTabShopLoc">Bandung</span><span class="prd_link-shop-name css-1kdc32b flip" data-testid="">Rasa Juara Indonesia</span></div>
   <span class="prd_label-integrity css-1duhs3e" data-testid="">Terjual 750+</span>
   <span class="prd_rating-average-text css-t70v7i" data-testid="">4.9</span>
   ```
  
   **WARNING:** Kamu harus mengecek lagi kebenaran dari elemen tersebut karena Tokopedia merupakan website dinamis yang bisa saja berubah lagi attribute dan attribute value nya. Perlu diingat juga, Tokopedia senantiasa ingin melakukan improvisasi khususnya UI website sehingga bisa jadi sedang dilakukan A/B Testing dan kamu mendapatkan tampilan web yang berbeda. Tampilan web berbeda, maka elemennya juga berbeda.

   Pastikan seluruh attribute dan values digunakan dalam positioning di Beautifulsoup-nya.

5. Ambil informasi produk minimal dari 10 halaman pencarian (perhatikan format url linknya dan eksplorasi terlebih dahulu halaman web nya).

6. Perlu diingat bahwa setiap orang dan setiap waktu akan menghasilkan hasil data yang berbeda, hal ini tidak masalah, yang paling penting jumlah data yang diperoleh minimal 50 data dari minimal 10 halaman yang diakses.

7. Simpan hasil scrape ke pandas data frame dan kemudian diolah. Kamu dibebaskan memberikan nama kolom yang memudahkan kamu.

#### B. Data Preparation

1. Lakukan eksplorasi data sederhana:
   - Tampilkan beberapa baris data
   - Tampilkan informasi rangkuman data - tuliskan kondisi struktur data berdasarkan ini
2. Lakukan pengubahan data di kolom  yang berisikan harga produk:
   Ambil angkanya saja, misal `Rp29.000` menjadi `29000`. Pastikan tipe data kolom ini setelah diubah formatnya menjadi integer atau float
3. Lakukan pengubahan data di kolom yang berisikan jumlah produk yang telah dijual:
   Jumlah produk yang terjual dituliskan sebagai `Terjual 750+`, `Terjual 1 rb`. Ambil angkanya saja. Misal `Terjual 750+` -> `750` dan `Terjual 1 rb` -> `1000`. Pastikan setelah diubah format datanya, kolom ini bertipe data integer atau float.

Notes: Untuk pengerjaan nomor 2 dan 3, kamu bisa menggunakan method `.str.replace` dan setelah itu ganti tipe data kolom dengan method `.astype()`.

## Assignment Rubrics

|**Key Component**|**Description**|**Points**|
|---|---|---|
|Web Scraping|Siswa mampu menerapkan function berdasarkan kasus yang ingin diselesaikan|10 pts|
|Data Preparation|Siswa mampu menerapkan looping sesuai dengan instruksi pada soal|10 pts|
|Runs Perfectly|Kode berjalan tapa ada error. Seluruh kode berfungsi dan dibuat dengan benar.|2 pts|
|Readability|Penulisan notebook rapih dengan disertai penjelasan menggunakan markdown atau comment.|3 pts|

Total: 25 pts
---
## Score Reduction

Jika Student terlambat mengumpulkan dengan waktu yang ditentukan, maka Graded Challenge akan diberi poin nol.

---
