# AI Employment Risk Index – Pedal Revo (IFEST 2024)

## 📌 Deskripsi Proyek

Proyek ini dikembangkan oleh tim **Pedal Revo** untuk ajang **Data Analytics Competition IFEST 2024**. Fokus utama proyek adalah menganalisis dan memprediksi pengaruh kecerdasan buatan (AI) terhadap risiko pekerjaan di Asia Tenggara, khususnya melalui indeks dampak AI terhadap berbagai sektor pekerjaan.

Di era Revolusi Industri 4.0, otomatisasi berbasis AI menjadi faktor penting yang memengaruhi dinamika ketenagakerjaan. Dengan memanfaatkan data dan teknik analisis modern, proyek ini bertujuan untuk memberikan wawasan yang dapat digunakan oleh para pembuat kebijakan dan pemangku kepentingan.

## 🎯 Tujuan

* Melakukan Exploratory Data Analysis (EDA) untuk mengidentifikasi pola dalam data.
* Memprediksi **gaji (Salary)** berdasarkan:

  * Dampak AI (**AI Impact**)
  * Jumlah tugas manual (**Tasks**)
  * Jumlah model AI yang digunakan (**AI Models**)
  * Rasio beban kerja AI (**AI\_Workload\_Ratio**)
* Mengidentifikasi sektor pekerjaan yang paling terdampak oleh otomatisasi berbasis AI.

## 🧪 Metodologi

### 📊 Exploratory Data Analysis

* **Pandas & NumPy:** Manipulasi data tabular dan komputasi numerik.
* **Matplotlib & Seaborn:** Visualisasi data dan korelasi fitur.

### ⚙️ Preprocessing

* **Label Encoding:** Konversi data kategorikal ke numerik.
* **Train-Test Split (80:20):** Untuk menghindari overfitting dan menguji generalisasi model.

### 🤖 Modeling

Model regresi yang digunakan:

* **XGBoost Regression** (model terbaik berdasarkan evaluasi)
* **Random Forest Regression**
* **Gradient Boosting Regression**
* **Decision Tree Regression**

### 📈 Evaluasi Model

* **RMSE (Root Mean Square Error):** Metrik untuk mengukur kesalahan prediksi.
* **R² Score:** Menilai seberapa baik model menjelaskan variasi data.

## 📂 Dataset

* Data mencakup satu negara di Asia Tenggara.
* Fitur-fitur utama: *AI Impact*, *Tasks*, *AI Models*, *AI\_Workload\_Ratio*, dan *Salary*.
* Kategori AI Impact:

  * **High Impact**: ≥ 60%
  * **Medium Impact**: 30% – <60%
  * **Less Impact**: <30%

## 📊 Visualisasi

* Heatmap korelasi antar fitur.
* Grafik hubungan antara kategori AI Impact dan Salary.

## ✅ Hasil & Evaluasi

Model terbaik: **XGBoost Regression**
Hasil evaluasi (R² Score): \~**0.9999**, menunjukkan performa prediksi yang sangat tinggi.

Temuan utama:

* Sektor dengan **AI Impact** yang tinggi cenderung memiliki rata-rata gaji yang lebih rendah.
* Pekerjaan dengan keterampilan rendah lebih rentan tergantikan oleh AI.
* Sebaliknya, pekerjaan dengan keterampilan tinggi tetap bernilai tinggi dan lebih aman dari risiko otomatisasi.

## 🧠 Kesimpulan

Kecerdasan buatan berpengaruh besar terhadap transformasi sektor pekerjaan, meskipun dampaknya berbeda-beda antar negara di Asia Tenggara. Proyek ini menunjukkan pentingnya pemetaan risiko pekerjaan akibat AI untuk merancang strategi kebijakan dan pelatihan kerja yang adaptif.

## 👥 Tim Pengembang

* I Putu Paramaananda Tanaya
* Muhammad Aldy Naufal Fadhilah 
* Jonathan Young
* Nada Firdaus
