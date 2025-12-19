# 📘 Judul Proyek
*PREDIKSI KOMENTAR SPAM PADA YOUTUBE MENGGUNAKAN MACHINE LEARNING DAN DEEP LEARNING*

## 👤 Informasi
- **Nama:** Abyan Raga Kusuma  
- **Repo:** https://github.com/abyan441/234311001_UAS_DataScience
- **Video:** https://youtu.be/qc0GdaXAhw0

---

# 1. 🎯 Ringkasan Proyek
- Memprediksi komentar spam dan non-spam berdasarkan fitur CONTENT 
- Melakukan data preparation (cleaning, scaling, splitting).  
- Membangun 3 pendekatan model:
(1) Baseline – Naive Bayes
(2) Advanced ML – Random Forest
(3) Deep Learning – Long Short-Term Memory (LSTM)
- Melakukan evaluasi menggunakan Accuracy, Precision, Recall, F1-Score.
- Menentukan model terbaik dan memberikan insight dari hasil pemodelan.  

---

# 2. 📄 Problem & Goals
**Problem Statements:**  
- Sistem perlu mampu mengklasifikasikan komentar YouTube menjadi spam atau non-spam dengan tingkat akurasi yang cukup tinggi, meskipun komentar sering pendek, tidak baku, dan mengandung variasi bahasa informal.
- Dataset komentar mengandung banyak noise seperti emoticon, tautan, huruf kapital berlebih, serta teks tidak terstruktur, sehingga membutuhkan proses preprocessing yang tepat sebelum dilakukan pemodelan.
- Model machine learning tradisional memiliki keterbatasan dalam memahami konteks teks, sehingga diperlukan model deep learning seperti LSTM yang mampu mempelajari pola urutan kata secara lebih efektif.
- Sistem deteksi spam harus dapat bekerja secara otomatis dan stabil untuk membantu moderasi komentar dalam skala besar, sehingga solusi yang dikembangkan harus tepat, efisien, dan mudah diimplementasikan.

**Goals:**  
- Mengembangkan tiga model prediksi (baseline, advanced machine learning, dan deep learning) untuk mengklasifikasikan komentar YouTube menjadi spam atau non-spam, serta membandingkan performanya secara sistematis.
- Mencapai performa akurasi dan F1-score yang tinggi pada model akhir, sehingga mampu mendeteksi komentar spam secara efektif meskipun teks pendek, informal, dan bervariasi.
- Menerapkan preprocessing teks yang tepat untuk mengatasi noise pada data, seperti pembersihan karakter khusus, normalisasi teks, penghapusan tautan, dan tokenisasi, sehingga meningkatkan kualitas input data.
- Mengidentifikasi model terbaik berdasarkan metrik evaluasi (Accuracy, Precision, Recall, dan F1-Score) yang paling sesuai dalam memfilter komentar spam secara otomatis.

---
## 📁 Struktur Folder
```
234311026_UAS_DataScience/
│
├── data/
│   ├── communities.data
│   └── communities.names                   
│
├── notebooks/       
│   └──234311026_uasdata01.ipynb
│
├── src/                   
│   
├── models/                 
│   ├── gradient_boosting_model.joblib
│   ├── linear_regression_model.joblib
│   ├── mlp_model.h5
│   └── mlp_savedmodel/
│       ├── fingerprint.pb
│       ├── saved_model.pb
│       └── variables/
│           ├── variables.data-00000-of-00001
│           └── variables.index
│
├── images/                 
│   ├── feature important plot.png
│   ├── heatmap hubungan antar ftr.png
│   ├── histogram distribusi ftr.png
│   ├── perbandingan data asli vs predict.png
│   ├── perbandingan performa antar model.png
│   ├── scatter plot hubungan antar ftr.png
│   ├── train vs val loss per epoch.png
│   └── train vs val mae.png
│
├── requirements.txt
├── Checklist Submit.md
├── LICENSE        
├── .gitignore
└── README.md
```
---

# 3. 📊 Dataset
- **Sumber:** UCI Machine Learning Repository  
- **Jumlah Data:**  350 baris, 3 fitur dan 1 target 
- **Tipe:** text

### Fitur Utama
Dataset asli memiliki **3 fitur**, namun proyek ini hanya menggunakan **1 fitur utama** yang relevan dengan komentar spam dan non-spam  
Berikut tabel fitur yang digunakan:

| **Nama Fitur**        | **Deskripsi** |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------|
| **AUTHOR**            | Nama Pengguna yang memberikan komentar.                                                                                       |
| **DATE**              | Tanggal komentar diposting.                                                                                                   |
| **CONTENT**           | Isi komentar YouTube.                                                                                                         |

---

# 4. 🔧 Data Preparation
- **Cleaning**: Pemeriksaan missing values, duplikasi, outliers, noise, dan range nilai. Dataset sudah bersih dan tidak memerlukan cleaning tambahan.
- **Feature Selection**: Memilih 1 fitur CONTENT yang paling relevan serta 1 target (`CLASS`).
- **Scaling**: Proses scaling tidak diterapkan pada dataset ini karena data berbentuk teks, bukan data numerik.
Representasi teks dilakukan menggunakan teknik TF-IDF untuk model machine learning dan tokenisasi serta padding untuk model deep learning (LSTM), sehingga scaling numerik tidak diperlukan.
- **Splitting**: Dataset dibagi menjadi dua bagian, yaitu data training dan data testing, menggunakan rasio 80% untuk training dan 20% untuk testing.
- **Balancing**: Dataset yang digunakan memiliki jumlah data Spam dan Non-Spam yang seimbang, sehingga tidak diperlukan teknik balancing tambahan seperti oversampling atau undersampling.

---

# 5. 🤖 Modeling
- **Model 1 – Baseline:** [Naive Bayes]  
- **Model 2 – Advanced ML:** [Random Forest]  
- **Model 3 – Deep Learning:** [Long Short-Term Memory (LSTM)]  

---

# 6. 🧪 Evaluation
**Metrik:** Accuracy, Precision, Recall, F1-Score
| Model                         | Accuracy | Precision| Recall   | F1-Score  | Training Time  |
|------------------------------|----------|----------|----------|-----------|-----------------|
| Baseline (Naive Bayes)       | 0.80     | 0.80     | 0.80     | 0.80      | ±2s-5 detik     |
| Advanced (Random Forest)     | 0.76     | 0.78     | 0.76     | 0.75      | >5 detik        |
| Deep Learning (SLTM)         | 0.84     | 0.85     | 0.84     | 0.84      | ±15–20 detik    |

---

# 7. 🏁 Kesimpulan

- **Model terbaik:** SLTM (Deep Learning)  
- **Alasan:**  
  Model LSTM menghasilkan performa tertinggi dengan accuracy sebesar 0.84 dan F1-score sebesar 0.84, serta menunjukkan keseimbangan yang baik antara precision dan recall. Keunggulan ini disebabkan oleh kemampuan LSTM dalam mempelajari urutan dan konteks kata pada teks, sehingga lebih efektif dalam menangkap pola bahasa yang kompleks dibandingkan model Naive Bayes dan Random Forest.

- **Insight penting:**  
  - Komentar YouTube didominasi oleh teks pendek, baik pada kelas spam maupun non-spam, sehingga pendekatan NLP untuk short text sangat relevan dalam proyek ini.
  - Komentar spam cenderung memiliki pola kata promosi dan ajakan, seperti penggunaan tautan, kata “subscribe”, “check”, atau frasa ajakan singkat lainnya, yang membedakannya dari komentar non-spam.
  - Model sederhana seperti Naive Bayes tetap memberikan performa yang kompetitif pada klasifikasi teks pendek, meskipun tanpa pemodelan konteks kata yang kompleks.
  - Model berbasis sekuens seperti LSTM mampu memberikan performa terbaik, karena dapat mempelajari urutan dan konteks kata dalam komentar, yang penting untuk membedakan spam yang ditulis menyerupai komentar normal. 


---

# 8. 🔮 Future Work

## 📌 Data Improvements
- [x] Mengumpulkan lebih banyak data  
- [x] Menambah variasi data  
- [x] Melakukan feature engineering lebih lanjut  

## 🤖 Model Enhancements
- [x] Mencoba arsitektur deep learning yang lebih kompleks  
- [x] Hyperparameter tuning lebih ekstensif  
- [x] Mencoba ensemble methods  
- [ ] Transfer learning dengan model yang lebih besar  

## 🚀 Deployment & System
- [x] Membuat API (Flask / FastAPI)  
- [x] Membuat web app (Streamlit / Gradio)  
- [ ] Containerization dengan Docker  
- [ ] Deploy ke cloud (Heroku / GCP / AWS)  

## ⚙️ Optimization
- [ ] Model compression (pruning / quantization)  
- [ ] Improving inference speed  
- [ ] Reducing model size  
t  

---

# 9. 🔁 Reproducibility
Gunakan environment:
Python Version:
- Python 3.9

Main Libraries & Versions:
- numpy==2.0.2
- pandas==2.2.2
- scikit-learn==1.6.1
- matplotlib==3.10.0
- seaborn==0.13.2

Deep Learning Framework:
- tensorflow==2.19.0
- keras 3.10.0

