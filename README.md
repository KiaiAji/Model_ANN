# Model ANN untuk Klasifikasi Iris

Repositori ini berisi proyek klasifikasi bunga *Iris* menggunakan **Artificial Neural Network (ANN)**. Dataset digunakan untuk membedakan tiga jenis iris: *Iris-setosa*, *Iris-versicolor*, dan *Iris-virginica*, berdasarkan empat fitur (sepal length, sepal width, petal length, petal width).

Notebook utama: **Metode_ANN.ipynb**.

---

## 📋 Isi Repositori

| File / Komponen            | Deskripsi                                                                 |
|----------------------------|---------------------------------------------------------------------------|
| `Metode_ANN.ipynb`         | Notebook yang berisi kode implementasi, training, evaluasi model ANN     |
| Dataset (jika ada)         | Data iris dalam bentuk CSV atau yang dipakai di notebook                 |
| `model_saved` / model file  | Model ANN setelah training (jika sudah disimpan)                         |
| README.md                  | Deskripsi proyek, cara menjalankan, hasil, dan panduan penggunaan model  |

---

## 🔍 Metodologi

1. **Data**
   - Dataset Iris dengan 150 sampel, 3 kelas (*setosa*, *versicolor*, *virginica*)
   - Fitur:
     - Sepal length
     - Sepal width
     - Petal length
     - Petal width

2. **Preprocessing**
   - Normalisasi fitur dengan `StandardScaler`
   - (Opsional jika ada) Reduksi dimensi dengan PCA
   - Konversi label menjadi bentuk numerik / one-hot encoding
   - Split data menjadi data latih dan data uji

3. **Model ANN**
   - Arsitektur jaringan (hidden layer / jumlah neuron bisa berbeda tergantung eksperimen)
   - Aktivasi: ReLU di hidden layer, Softmax di output layer
   - Optimizer: Adam
   - Loss function: Categorical Crossentropy

4. **Evaluasi**
   - Akurasi model pada data uji
   - Precision, Recall, F1-score per kelas
   - Confusion matrix
   - Visualisasi: grafik akurasi training vs validasi, grafik loss training vs validasi

---

## 🚀 Cara Menjalankan

1. **Clone repository**  
   ```bash
   git clone https://github.com/KiaiAji/Model_ANN.git
   cd Model_ANN
