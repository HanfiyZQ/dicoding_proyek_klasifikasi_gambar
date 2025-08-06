# 🧠 Intel Image Classification with CNN & TensorFlow

Proyek ini bertujuan untuk mengklasifikasikan gambar ke dalam 6 kategori lingkungan menggunakan **model CNN** dengan **TensorFlow**. Dataset yang digunakan adalah [Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification) dari Kaggle, yang berisi lebih dari 25.000 gambar 150x150 piksel.

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

## 🧠 Model Arsitektur

Model dibangun menggunakan **Convolutional Neural Networks (CNN)** dengan lapisan sebagai berikut:

- Rescaling → Conv2D → BatchNorm → MaxPooling (x4)
- Global Average Pooling
- Dropout 50% + Dense(128) + Dropout 30%
- Output layer: `softmax` (6 kelas)

> **Loss function**: sparse categorical crossentropy  
> **Optimizer**: Adam  
> **Callback**: EarlyStopping, ModelCheckpoint, ReduceLROnPlateau

## 📈 Hasil Evaluasi

```python
Test Accuracy: 85.6667%
Test Loss: 0.4432
