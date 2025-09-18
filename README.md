# 🤖 AI Employment Risk Index: Menganalisis Dampak Otomatisasi Terhadap Pekerjaan di Asia Tenggara

**Sebuah Proyek Analisis Data oleh Tim Pedal Revo untuk IFEST 2024**

---



## 📌 1. Domain Proyek: Analisis Ketenagakerjaan & Dampak Teknologi

Kita berada di tengah **Revolusi Industri 4.0**, sebuah era yang ditandai oleh konvergensi teknologi digital, fisik, dan biologis. Salah satu pilar utamanya adalah **Kecerdasan Buatan (AI)** dan otomatisasi, yang secara fundamental mengubah cara kita bekerja, hidup, dan berinteraksi. AI tidak hanya menghadirkan peluang efisiensi dan inovasi yang luar biasa, tetapi juga memicu disrupsi signifikan di pasar tenaga kerja global, termasuk di kawasan Asia Tenggara yang dinamis.

Seiring dengan semakin masifnya adopsi AI, muncul pertanyaan krusial: Pekerjaan mana yang paling berisiko tergantikan? Sektor mana yang akan bertransformasi? Dan bagaimana dampaknya terhadap tingkat pendapatan (gaji)? Menjawab pertanyaan-pertanyaan ini bukan lagi sekadar latihan akademis, melainkan sebuah kebutuhan mendesak bagi pemerintah, institusi pendidikan, dan para pekerja untuk dapat beradaptasi.

Proyek **"AI Employment Risk Index"** ini dikembangkan untuk menjawab tantangan tersebut. Dengan pendekatan berbasis data, kami bertujuan untuk membedah hubungan kompleks antara adopsi AI dan dinamika ketenagakerjaan. Proyek ini tidak hanya mengukur, tetapi juga memprediksi risiko pekerjaan, memberikan sebuah "peta jalan" berbasis bukti yang dapat digunakan oleh para pemangku kepentingan untuk menavigasi masa depan dunia kerja yang terus berevolusi.

---

## 🎯 2. Business Understanding

### 🔍 Problem Statements

1.  Bagaimana tingkat adopsi dan dampak AI (**AI Impact**) dalam suatu pekerjaan berkorelasi dengan tingkat pendapatan (**Salary**) di berbagai sektor industri di Asia Tenggara?
2.  Dapatkah kita membangun sebuah model prediktif yang sangat akurat untuk mengestimasi gaji seorang pekerja berdasarkan metrik-metrik terkait AI seperti jumlah tugas manual, jumlah model AI yang digunakan, dan rasio beban kerja AI?
3.  Sektor pekerjaan mana yang menunjukkan kerentanan tertinggi terhadap otomatisasi AI, dan sebaliknya, sektor mana yang menunjukkan ketahanan atau bahkan mengalami peningkatan nilai?

### 🎯 Objectives

1.  Mengembangkan model regresi *machine learning* yang andal untuk memprediksi **gaji** berdasarkan variabel-variabel yang merefleksikan integrasi AI dalam suatu pekerjaan.
2.  Mengevaluasi dan membandingkan beberapa algoritma regresi (*XGBoost, Random Forest, Gradient Boosting, Decision Tree*) untuk menentukan model dengan akurasi prediksi tertinggi.
3.  Mengidentifikasi dan menganalisis pola-pola kunci dari data untuk menghasilkan **"AI Employment Risk Index"**, yang mengklasifikasikan pekerjaan berdasarkan tingkat dampaknya oleh AI.
4.  Menyajikan temuan yang dapat ditindaklanjuti (*actionable insights*) bagi para pembuat kebijakan untuk merancang program *upskilling* dan *reskilling* yang relevan.

### 💡 Solusi yang Diusulkan

Sebuah pendekatan analitik kuantitatif yang memanfaatkan *ensemble learning* untuk pemodelan prediktif. Model **XGBoost Regression** dipilih sebagai solusi utama karena kemampuannya yang terbukti dalam menangani hubungan data yang kompleks dan memberikan akurasi superior. Model ini dilatih menggunakan fitur-fitur seperti `AI Impact`, `Tasks`, `AI Models`, dan `AI_Workload_Ratio` untuk memprediksi `Salary`, yang kemudian hasilnya diinterpretasikan untuk memetakan lanskap risiko pekerjaan.

---

## 📁 3. Dataset Overview

* **Sumber**: Disediakan oleh panitia **Data Analytics Competition IFEST 2024**.
* **Cakupan Geografis**: Data mewakili satu negara di kawasan Asia Tenggara.
* **Konteks**: Dataset ini dirancang untuk mensimulasikan data ketenagakerjaan di era adopsi AI, menghubungkan metrik teknologi dengan indikator ekonomi (gaji).

---

## 📋 4. Fitur & Target Dataset

### 📥 Fitur Input (Prediktor)

| Fitur | Deskripsi |
| :--- | :--- |
| `AI Impact` | Tingkat dampak AI terhadap suatu pekerjaan, dikategorikan menjadi **High, Medium, Less Impact**. |
| `Tasks` | Jumlah tugas manual dalam suatu pekerjaan yang berpotensi untuk diotomatisasi. |
| `AI Models` | Jumlah model atau sistem AI yang diimplementasikan dalam alur kerja. |
| `AI_Workload_Ratio`| Rasio beban kerja yang ditangani oleh AI dibandingkan dengan manusia. |

### 🎯 Target Output (yang Diprediksi)

| Target | Deskripsi |
| :--- | :--- |
| `Salary` | Gaji atau pendapatan yang diterima untuk pekerjaan tersebut. |

---

## 🔍 5. Data Understanding & EDA

Analisis data eksplorasi dilakukan untuk mengungkap pola awal dan hubungan antar variabel.

* **Analisis Korelasi (Heatmap)**:
    * Sebuah *heatmap* korelasi dibangun untuk memvisualisasikan hubungan linear antar semua fitur numerik. Ditemukan adanya korelasi negatif yang cukup signifikan antara fitur-fitur yang merepresentasikan dampak AI dengan `Salary`.

* **Hubungan AI Impact vs. Gaji**:
    * Visualisasi data menunjukkan tren yang jelas: semakin tinggi kategori **`AI Impact`** suatu pekerjaan, semakin rendah rata-rata **`Salary`** yang diterima. Sektor dengan *Less Impact* memiliki rata-rata gaji tertinggi, diikuti oleh *Medium Impact*, dan yang terendah adalah sektor *High Impact*.



* **Insight Kunci**: EDA awal secara kuat mengindikasikan bahwa **otomatisasi AI cenderung menekan tingkat upah**, terutama pada pekerjaan-pekerjaan yang sebagian besar tugasnya dapat digantikan oleh teknologi. Ini memvalidasi hipotesis awal dan menjadi dasar yang kuat untuk pemodelan prediktif.

---

## ⚙️ 6. Data Preparation (Preprocessing)

Untuk mempersiapkan data sebelum masuk ke tahap pemodelan, dua langkah utama dilakukan:

| Langkah | Penjelasan |
| :--- | :--- |
| **Label Encoding** | Fitur kategorikal `AI Impact` (High, Medium, Less) dikonversi menjadi representasi numerik (misalnya, 2, 1, 0) agar dapat diproses oleh model regresi. |
| **Train-Test Split** | Dataset dibagi menjadi **80% data latih** dan **20% data uji**. Langkah ini krusial untuk melatih model pada mayoritas data dan mengevaluasinya pada data yang belum pernah dilihat, sehingga dapat mengukur kemampuan generalisasi model dan menghindari *overfitting*. |

---

## 🤖 7. Model Development

Sebuah pendekatan komparatif diadopsi dengan menguji empat model regresi yang berbeda untuk menemukan yang paling akurat.

### 🧪 **Model Kandidat**
1.  **Decision Tree Regression**: Model dasar yang mempartisi data berdasarkan aturan keputusan sederhana.
2.  **Random Forest Regression**: Model *ensemble* yang membangun banyak *decision tree* untuk meningkatkan stabilitas dan akurasi.
3.  **Gradient Boosting Regression**: Model *ensemble* yang membangun *tree* secara berurutan, di mana setiap *tree* baru memperbaiki kesalahan dari yang sebelumnya.
4.  **XGBoost Regression**: Implementasi *gradient boosting* yang dioptimalkan, dikenal karena kecepatan dan performanya yang sangat tinggi.

### 🏆 **Model Unggulan: XGBoost Regression**
**XGBoost (Extreme Gradient Boosting)** dipilih sebagai model final karena secara konsisten menunjukkan performa terbaik selama eksperimen. Keunggulannya terletak pada regularisasi bawaan yang mencegah *overfitting* dan kemampuannya menangani hubungan non-linear yang kompleks secara efisien.

---

## 📈 8. Evaluation, Hasil & Analisis

### 📐 **Metrik Evaluasi**
* **RMSE (Root Mean Square Error)**: Mengukur rata-rata magnitudo kesalahan prediksi dalam satuan yang sama dengan target (gaji).
* **R² Score (Koefisien Determinasi)**: Mengukur proporsi varians dalam variabel target yang dapat dijelaskan oleh model. Skor mendekati 1 menunjukkan model yang sangat baik.

### 📊 **Hasil Kuantitatif**
Model **XGBoost Regression** mencapai hasil yang luar biasa pada data uji:

> **R² Score: ~0.9999**

Skor R² yang mendekati sempurna (1.0) menunjukkan bahwa model mampu menjelaskan **hampir 99.99%** variasi dalam data gaji hanya dengan menggunakan empat fitur terkait AI. Ini menandakan hubungan yang sangat kuat dan dapat diprediksi antara adopsi AI dan struktur upah dalam dataset ini.

### 🧠 **Analisis Temuan Utama**
1.  **Tekanan Upah oleh Otomatisasi**: Terkonfirmasi secara kuantitatif bahwa sektor dengan **`AI Impact` tinggi** memiliki korelasi kuat dengan **gaji yang lebih rendah**. AI mengambil alih tugas-tugas rutin, mengurangi permintaan tenaga kerja manusia untuk peran tersebut.
2.  **Kerentanan Berbasis Keterampilan**: Pekerjaan dengan **keterampilan rendah** dan banyak tugas manual adalah yang paling rentan terhadap disrupsi dan penurunan upah.
3.  **Nilai Keterampilan Tinggi**: Sebaliknya, pekerjaan yang memerlukan **keterampilan tinggi**, kreativitas, pemikiran kritis, dan kecerdasan emosional tetap memiliki nilai tinggi dan cenderung lebih aman dari risiko otomatisasi, bahkan mungkin gajinya meningkat karena berkolaborasi dengan AI.

---

## ✅ 9. Kesimpulan

Proyek "AI Employment Risk Index" berhasil membuktikan bahwa dampak Kecerdasan Buatan terhadap pasar kerja dapat diukur dan diprediksi dengan tingkat akurasi yang sangat tinggi. Model **XGBoost Regression** kami, dengan **R² Score ~0.9999**, secara definitif menunjukkan bahwa variabel seperti dampak AI dan rasio beban kerja adalah prediktor kuat untuk tingkat gaji.

Temuan utama menegaskan adanya **transformasi struktural** di pasar kerja: peran berbasis keterampilan rendah menghadapi risiko signifikan, sementara peran berbasis keterampilan tinggi tetap vital. Wawasan ini sangat krusial dan dapat menjadi landasan bagi pemerintah dan lembaga terkait di Asia Tenggara untuk merancang **kebijakan yang proaktif**, seperti program pelatihan ulang (*reskilling*), penyesuaian kurikulum pendidikan, dan jaring pengaman sosial untuk membantu angkatan kerja beradaptasi dengan masa depan dunia kerja yang didukung oleh AI.

---

## 👥 10. Tim Pengembang (Pedal Revo)

Proyek ini merupakan hasil kolaborasi dari:

* I Putu Paramaananda Tanaya
* Muhammad Aldy Naufal Fadhilah
* Jonathan Young
* Nada Firdaus
