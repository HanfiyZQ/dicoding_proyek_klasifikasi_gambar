# 🧠 Intel Image Classification with CNN & TensorFlow

Proyek ini bertujuan untuk mengklasifikasikan gambar ke dalam 6 kategori lingkungan menggunakan model **Convolutional Neural Networks (CNN)** dengan **TensorFlow**. Dataset yang digunakan adalah [Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification) dari Kaggle, yang berisi lebih dari 25.000 gambar berukuran 150x150 piksel.

> ✅ Proyek ini merupakan bagian dari **Machine Learning Engineer Path by Dicoding Indonesia**, khususnya dalam course **Belajar Fundamental Deep Learning**.

---

## 📁 Dataset

Dataset terdiri dari 6 kelas:
- `buildings`
- `forest`
- `glacier`
- `mountain`
- `sea`
- `street`

📊 **Distribusi data:**
- **Training**: 11.228 gambar (80%)
- **Validation**: 2.806 gambar (20%)
- **Testing**: 3.000 gambar

Dataset digunakan dengan preprocessing otomatis dari `tf.keras.preprocessing.image_dataset_from_directory`.

---

## 🧠 Model Arsitektur

Model CNN yang dibangun memiliki struktur:

- Rescaling → Conv2D + BatchNorm + MaxPooling (x4)
- Global Average Pooling
- Dropout 50%
- Dense(128, ReLU) + Dropout 30%
- Output layer: Dense(6, Softmax)

> **Loss function**: sparse categorical crossentropy  
> **Optimizer**: Adam  
> **Callbacks**: EarlyStopping, ModelCheckpoint, ReduceLROnPlateau

---

## 📈 Hasil Evaluasi Test Akhir

```python
Test Accuracy: 85.6667%
Test Loss: 0.4432
