Model_ANN/
├── data/                          # Folder dataset (jika menggunakan file eksternal)
│   └── README.md                  # Penjelasan tentang dataset
│
├── notebooks/                     # Folder notebook
│   └── Metode ANN.ipynb           # Notebook utama ANN
│
├── models/                        # Folder untuk menyimpan model terlatih
│   ├── iris_ann_model.h5          # File model hasil training (format Keras HDF5)
│   └── iris_ann_model.json        # (opsional) Arsitektur model dalam format JSON
│
├── scripts/                       # Folder untuk skrip Python modular
│   ├── preprocess.py              # Script preprocessing (scaling, PCA, encoding, splitting)
│   ├── train.py                   # Script training ANN
│   ├── evaluate.py                # Script evaluasi model (confusion matrix, report, dsb)
│   └── visualize.py               # Script untuk visualisasi hasil training
│
├── results/                       # Folder untuk output hasil eksperimen
│   ├── confusion_matrix.png       # Gambar confusion matrix
│   ├── training_history.png       # Grafik loss/accuracy per epoch
│   └── classification_report.txt  # Ringkasan metrik evaluasi
│
├── requirements.txt               # Daftar dependencies Python
├── README.md                      # Dokumentasi proyek
└── LICENSE                        # Lisensi proyek (misalnya MIT)

