# Klasifikasi Iris dengan ANN — Proyek Machine Learning

Proyek ini adalah implementasi **Artificial Neural Network (ANN)** untuk klasifikasi jenis bunga *Iris* menggunakan dataset Iris. Model dilatih dan dievaluasi di Google Colab.  

# Anggota Kelompok
- Aulia Dwi Rahmadani   (G1A023043)
- Habib Al Qodri        (G1A023047)
- Yohanes Adi Prasetya  (G1A023049) 
- Rayhan Muhammad Adha  (G1A023051) 
- Ghazi Al-Ghifari      (G1A023053)

---

## 🔍 Metodologi

1. **Data**
   - Dataset: Iris (150 contoh, 3 kelas: *setosa*, *versicolor*, *virginica*)  
   - Fitur: `sepal length`, `sepal width`, `petal length`, `petal width`

2. **Preprocessing**
   - Normalisasi fitur dengan `StandardScaler`  
   - (Opsional: reduksi dimensi dengan PCA, tergantung versi)  
   - One-hot encoding untuk label  
   - Split data menjadi training dan testing (misalnya 80% train / 20% test)

3. Model ANN
   - Input sesuai jumlah fitur (4)  
   - Beberapa hidden layer (jumlah neuron, layer bisa berbeda, misalnya satu atau dua hidden layer)  
   - Aktivasi hidden layer: ReLU  
   - Output layer dengan Softmax (untuk kelas 3)  
   - Kompilasi model: loss function `categorical_crossentropy`, optimizer `Adam`, metrik `accuracy`

5. **Training**
   - Epoch dan batch size sesuai yang diatur di notebook (misalnya 50 epoch, batch size 5 atau 10)  
   - Monitoring training vs validation (accuracy dan loss)

6. **Evaluasi**
   - Menghitung akurasi di set test  
   - Confusion Matrix  
   - Precision, Recall, F1-Score per kelas  
   - Visualisasi: grafik akurasi training & validasi, grafik loss training & validasi

---

## 📈 Visualisasi & Hasil

### Grafik Akurasi (Training vs Validasi)

<img width="505" height="470" alt="image" src="https://github.com/user-attachments/assets/9294de43-c6dd-4a7f-ad3a-336cebae130d" />

### Grafik Loss (Training vs Validasi)

<img width="536" height="393" alt="image" src="https://github.com/user-attachments/assets/086392c4-40f3-4c12-a260-eba70e756265" />

### Confusion Matrix

<img width="536" height="393" alt="image" src="https://github.com/user-attachments/assets/c0b39e7c-071d-4c07-8978-e5a7ec83b1e5" />

---

## 🖥️ Kode Utama Prediksi & Implementasi

Berikut contoh cuplikan kode untuk memuat model terlatih dan melakukan prediksi terhadap data baru (fitur input):

```python
import numpy as np
import tensorflow as tf
from sklearn.preprocessing import StandardScaler

# Load model yang sudah dilatih
model = tf.keras.models.load_model("model_iris_ann.h5")

# Load scaler yang digunakan di preprocessing (jika kamu menyimpan scaler)
# misalkan scaler disimpan dengan joblib
import joblib
scaler = joblib.load("scaler.pkl")

# Fungsi prediksi
def predict_iris(sample):
    """
    sample: array/list dengan 4 fitur [sepal_length, sepal_width, petal_length, petal_width]
    """
    sample_np = np.array(sample).reshape(1, -1)
    sample_scaled = scaler.transform(sample_np)
    preds = model.predict(sample_scaled)
    class_index = np.argmax(preds, axis=1)[0]
    class_names = ["Iris-setosa", "Iris-versicolor", "Iris-virginica"]
    return class_names[class_index], preds

# Contoh penggunaan
sample = [5.1, 3.5, 1.4, 0.2]
label, probabilities = predict_iris(sample)
print("Prediksi:", label)
print("Probabilitas:", probabilities)
