# Magang Merdeka Data Scraper via API Request 

![Bahasa Indonesia](https://img.shields.io/badge/Bahasa-Indonesia-blue.svg)

Script Py buat scrape data lowongan magang dari API KaMek, pake lib requests buat manggil API-nya dan pandas buat ngerapihin data yang didapet.

Berhubung di postman mentok 100 per pull padahal param "limit" udah diatur >100, dicoba yang gampang aja skaligus bisa looping sampe semua data di ke pull 

## Prep
Pastiin udah punya library yang dibutuhin. Bisa diinstall pake command berikut:

```bash
pip install requests pandas
```

## To Use

1. Buka script di Colab or IDE apapun yg support Python.
2. Atur parameter sesuai kebutuhan:
   - `url`: Endpoint API untuk data lowongan magang.
   - `limit`: Jumlah data yang diambil setiap kali panggil API (gua atur 100 karna emg mentok 100).
   - `offset`: Titik awal pengambilan data.
   - Parameter lainnya seperti `location_key`, `mitra_key`, `keyword`, `sector_id`, `sort_by`, dan `order` atur sesuai kebutuhan.
3. Atur mau perusahaan mana aja yang mau di include ke file output excel di array `corp` untuk perusahaan korporat dan `bumn` untuk perusahaan BUMN. kalo mau tau apa aja perusahaan yang tersedia bisa run `print(set(all_data['mitra_name']))`
4. Run script.

Script bakal terus manggil API dengan inkrementasi offset sebanyak value limit sampe ga ada lagi data yang dipull. Data yang berhasil diambil digabungin dan di proses baik per perusahaan dan summary keseluruhan pilihan perusahaan, di akhir proses pas semua data udah ke pull script bakal nyimpen data ke file Excel `corp_sum.xlsx` dan `bumn_sum.xlsx`dan langsung di auto unduh.


