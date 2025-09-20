# 🌸 Klasifikasi Bunga Iris dengan ANN + PCA

Proyek ini merupakan implementasi **Artificial Neural Network (ANN)** untuk melakukan klasifikasi jenis bunga **Iris** berdasarkan 4 fitur:  
- Sepal length  
- Sepal width  
- Petal length  
- Petal width  

Untuk mengurangi dimensi fitur dan meningkatkan efisiensi model, digunakan metode **Principal Component Analysis (PCA)** sebelum data masuk ke ANN.  

---

## 📂 Struktur Proyek
- `iris_ann_pca.ipynb` → notebook utama berisi kode training, evaluasi, dan visualisasi  
- `iris.csv` → dataset Iris (opsional, jika tidak menggunakan bawaan sklearn)  
- `iris_ann_pca.h5` → model terlatih yang disimpan  
- `README.md` → dokumentasi proyek  

---

## ⚙️ Metodologi
1. **Data**  
   - Dataset Iris (150 sampel, 3 kelas: *Setosa*, *Versicolor*, *Virginica*).  
   - 4 fitur numerik.  

2. **Preprocessing**  
   - Normalisasi fitur dengan **StandardScaler**  
   - Reduksi dimensi dengan **PCA (2 komponen utama)**  
   - Label encoding & one-hot encoding  

3. **Implementasi Model (ANN)**  
   - Arsitektur jaringan:  
     - Input layer: 2 neuron (hasil PCA)  
     - Hidden layer 1: 8 neuron, aktivasi ReLU  
     - Hidden layer 2: 8 neuron, aktivasi ReLU  
     - Output layer: 3 neuron, aktivasi Softmax  
   - Optimizer: Adam  
   - Loss: Categorical Crossentropy  

4. **Evaluasi**  
   - Akurasi pada data uji  
   - Confusion Matrix  
   - Precision, Recall, F1-score  
   - Grafik Akurasi & Loss (training vs validation)  

---

## 📊 Hasil
- **Akurasi**: ± 93–96% pada data uji  
- **Confusion Matrix** menunjukkan bahwa *Iris-setosa* diklasifikasikan sempurna, kesalahan kecil hanya terjadi antara *Versicolor* dan *Virginica*.  
- **Precision, Recall, F1-score** rata-rata > 0.90  
- **Grafik Training/Validation** menunjukkan tidak ada overfitting signifikan.  

---

## 🚀 Implementasi Prediksi
Contoh penggunaan model untuk klasifikasi bunga baru:

```python
sample = [5.1, 3.5, 1.4, 0.2]  # sepal length, sepal width, petal length, petal width
label, prob = predict_iris(sample, scaler, pca, model, ["Iris-setosa","Iris-versicolor","Iris-virginica"])
print("Prediksi:", label)
print("Probabilitas:", prob)
