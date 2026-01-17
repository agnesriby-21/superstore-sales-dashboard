# Superstore Sales Dashboard (Power BI)

Sebuah project **data analysis dan data visualization** yang dibangun menggunakan **Power BI** untuk menganalisis performa penjualan berdasarkan dataset *Sample Superstore*.  
Dataset ini berisi data **sales, profit, product, category, segment, dan region** pada periode **2014–2017**.

Project ini bertujuan untuk memahami **tren kinerja bisnis** serta menghasilkan **insight berbasis data** yang dapat mendukung pengambilan keputusan.

---

## Project Objectives
- Menganalisis performa penjualan dan profit secara historis
- Melakukan perbandingan performa **Year-over-Year (YoY)**
- Mengidentifikasi produk, segment, dan region dengan kontribusi tertinggi
- Membangun dashboard ringkas dan informatif dalam satu halaman
- Mengimplementasikan **DAX Measures** untuk perhitungan KPI dan analisis lanjutan

---

## Dashboard Overview

Dashboard dibuat dalam bentuk **one-page dashboard** dengan fokus pada ringkasan performa bisnis.

### KPI Cards
- **Total Sales**
- **Total Profit**
- **Total Orders**
- **Prior Year (PY)** untuk setiap KPI
- **vs PY (%)** sebagai indikator pertumbuhan YoY

---

### Visualizations
- **Sales Trend by Year**  
  Menampilkan tren penjualan dari tahun 2014 hingga 2017
- **Profit by Product**  
  Bar chart dengan visual pembeda antara **profit dan loss**
- **Sales by Segment**  
  Donut chart untuk melihat distribusi penjualan per segment
- **Profit by State**  
  Horizontal bar chart untuk kontribusi profit per state
- **Slicers (Dynamic Filters)**:
  - Date
  - Category
  - Segment

---

## Dashboard Screenshot
![Dashboard Preview](Dashboard.png)

---

## Key Insights
- Penjualan menunjukkan **tren meningkat dari 2014–2016**, sedangkan penurunan di 2017 disebabkan oleh data yang hanya mencakup sebagian tahun.
- **Technology dan Office Supplies** menjadi kategori dengan kontribusi profit terbesar, sementara beberapa subkategori **Furniture mengalami kerugian**.
- **Consumer segment** merupakan kontributor penjualan terbesar.
- **New York dan California** menghasilkan profit tertinggi dibandingkan state lainnya.
- Seluruh **KPI mengalami peningkatan YoY**, menunjukkan pertumbuhan bisnis yang positif.

---

## Key Technical Highlights
- Data modeling menggunakan struktur yang efisien untuk analisis Power BI
- Penggunaan **DAX Measures** untuk KPI, Prior Year, dan YoY calculation
- Dynamic filtering menggunakan **Slicers**
- Visual encoding untuk membedakan nilai profit dan loss
- Dashboard layout dirancang dengan fokus pada **business readability**

---

## Tech Stack

| Layer | Teknologi |
|------|----------|
| Data Visualization | Power BI |
| Data Modeling | Power BI Data Model |
| Calculation | DAX |
| Dataset | Sample Superstore |
| Visualization | KPI Cards, Bar Chart, Donut Chart, Line Chart |

---

## Project Structure


---

## DAX Measures (Key Examples)

```DAX
Total Sales = SUM(Orders[Sales])

Total Profit = SUM(Orders[Profit])

Total Orders = DISTINCTCOUNT(Orders[Order ID])

-- Prior Year Metrics
Sales PY =
CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Calendar'[Date]))

Profit PY =
CALCULATE([Total Profit], SAMEPERIODLASTYEAR('Calendar'[Date]))

Orders PY =
CALCULATE([Total Orders], SAMEPERIODLASTYEAR('Calendar'[Date]))

-- Year-over-Year %
Sales vs PY % =
DIVIDE([Total Sales] - [Sales PY], [Sales PY])

Profit vs PY % =
DIVIDE([Total Profit] - [Profit PY], [Profit PY])

Orders vs PY % =
DIVIDE([Total Orders] - [Orders PY], [Orders PY])

