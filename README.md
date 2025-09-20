# Model ANN untuk Klasifikasi Iris

Repositori ini berisi proyek klasifikasi bunga *Iris* menggunakan **Artificial Neural Network (ANN)**. Dataset digunakan untuk membedakan tiga jenis iris: *Iris-setosa*, *Iris-versicolor*, dan *Iris-virginica*, berdasarkan empat fitur (sepal length, sepal width, petal length, petal width).

Notebook utama: **Metode_ANN.ipynb**.

---

## 📋 Isi Repositori

| File / Komponen             | Deskripsi                                                                 |
|-----------------------------|---------------------------------------------------------------------------|
| `Metode_ANN.ipynb`          | Notebook berisi kode implementasi, training, dan evaluasi model ANN       |
| `images/accuracy.png`       | Grafik akurasi training vs validasi                                       |
| `images/loss.png`           | Grafik loss training vs validasi                                          |
| `images/confusion_matrix.png` | Visualisasi confusion matrix                                             |
| README.md                   | Dokumentasi proyek ini                                                    |

---

## 🔍 Metodologi

1. **Data**
   - Dataset Iris (150 sampel, 3 kelas: *setosa*, *versicolor*, *virginica*)
   - Fitur:
     - Sepal length
     - Sepal width
     - Petal length
     - Petal width

2. **Preprocessing**
   - Normalisasi fitur dengan `StandardScaler`
   - Konversi label menjadi one-hot encoding
   - Split data menjadi train & test (misalnya 80:20)

3. **Model ANN**
   - Input layer: 4 neuron (untuk 4 fitur)
   - Hidden layer: Dense dengan ReLU activation
   - Output layer: 3 neuron dengan Softmax
   - Optimizer: Adam
   - Loss: Categorical Crossentropy

4. **Evaluasi**
   - Akurasi
   - Precision, Recall, F1-score
   - Confusion Matrix
   - Grafik akurasi & loss training vs validasi

---

## 📊 Hasil & Visualisasi

### Confusion Matrix
![Confusion Matrix](images/confusion_matrix.png)

### Grafik Akurasi Training vs Validasi
![Accuracy](images/accuracy.png)

### Grafik Loss Training vs Validasi
![Loss](images/loss.png)

---

## 🚀 Cara Menjalankan

1. **Clone repository**
   ```bash
   git clone https://github.com/KiaiAji/Model_ANN.git
   cd Model_ANN
