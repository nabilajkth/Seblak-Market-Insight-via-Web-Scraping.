# Analisis Produk Seblak di Tokopedia dengan Web Scraping dan Pandas

Program ini dibuat untuk melakukan pengambilan data produk seblak di Tokopedia menggunakan teknik Web Scraping.
Data yang dikumpulkan mencakup nama produk, harga, penjual, kota toko, jumlah terjual, dan rating produk.
Data kemudian diolah menggunakan Pandas untuk dilakukan eksplorasi sederhana dan pembersihan (data preparation).
Hasil ini bertujuan untuk memberikan gambaran awal tentang potensi penjualan produk seblak secara online.

---

## 👉 Deskripsi Proyek

Proyek ini bertujuan untuk melakukan scraping data produk *Seblak* dari situs Tokopedia, mengolah data yang diperoleh, serta menyajikan visualisasi sederhana untuk menganalisis harga, penjual, dan rating produk. Data yang diambil mencakup beberapa halaman hasil pencarian.

---

## ⚙️ Tools & Library

* Python 3.8+
* Jupyter Notebook
* requests
* beautifulsoup4
* pandas
* time
* matplotlib
* seaborn

---

## 📄 Cara Menjalankan Proyek

### 1. Clone Repository

```bash
git clone https://github.com/username/nama-repo.git
cd nama-repo
```

### 2. Buat Virtual Environment (opsional)

```bash
python -m venv env
source env/bin/activate  # Mac/Linux
env\Scripts\activate   # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Jika tidak tersedia `requirements.txt`, install manual:

```bash
pip install requests beautifulsoup4 pandas matplotlib seaborn
```

### 4. Jalankan Jupyter Notebook

```bash
jupyter notebook
```

Lalu buka file: `P0G3_nabila-sulistiowati.ipynb`

---

## 🔧 Troubleshooting

### ❌ Safari WebDriver Error

```
SessionNotCreatedException: The Safari instance is already paired with another WebDriver session.
```

**Solusi:** Tutup semua jendela Safari dan restart Jupyter kernel.

### ❌ ModuleNotFoundError

```
ModuleNotFoundError: No module named 'requests'
```

**Solusi:** Jalankan ini di dalam notebook:

```python
!pip install requests beautifulsoup4
```

---

## 📊 Output

* Data scraping produk seblak dari beberapa halaman Tokopedia
* DataFrame hasil pembersihan & pengolahan data
* Visualisasi penjualan, persebaran penjual, dan harga produk

---

## 📝 Notes
- Scraping dari situs besar seperti Tokopedia dapat mengalami perubahan sewaktu-waktu.
- Jika proses scraping gagal atau data tidak muncul sesuai yang diharapkan, kemungkinan besar disebabkan oleh:
   * Perubahan struktur HTML pada halaman Tokopedia.
   * Diperlukannya pendekatan alternatif seperti Selenium untuk memuat elemen-elemen JavaScript secara dinamis.
- Pastikan selalu mengecek dan menyesuaikan kembali selector (class/id) ketika terjadi error atau hasil scraping kosong.

---

## 🌟 Credits

**Nama:** Nabila Sulistiowati

---
