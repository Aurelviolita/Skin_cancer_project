Baik, saya sudah menyesuaikan **README.md** ini **langsung berdasarkan isi file `CNN_skincancer_FIX.ipynb`**, bukan versi generik. Struktur, istilah, dan alur mengikuti *pipeline* yang benar-benar ada di notebook (Kaggle setup, HAM10000, CNN, focal loss, fine-tuning, dan evaluasi).

Silakan **copy–paste langsung** ke file `README.md` di repository GitHub kamu.

---

# **Skin Cancer Classification using CNN**

Proyek ini membangun model *Convolutional Neural Network (CNN)* untuk mengklasifikasikan jenis kanker kulit menggunakan dataset **HAM10000**. Implementasi dilakukan menggunakan **TensorFlow/Keras** dan dijalankan di lingkungan **Google Colab** dengan integrasi dataset dari **Kaggle**.

## **Deskripsi Proyek**

Tujuan utama proyek ini adalah mengembangkan model klasifikasi citra medis yang mampu membedakan berbagai jenis lesi kulit secara akurat. Model dilatih menggunakan citra dermatoskopik dan menerapkan teknik *data augmentation*, *class imbalance handling*, serta *fine-tuning* untuk meningkatkan performa klasifikasi.

Notebook utama:
`CNN_skincancer_FIX.ipynb`

## **Dataset**

Dataset yang digunakan adalah **HAM10000 – Human Against Machine with 10000 Training Images**, diunduh langsung dari Kaggle.

Link dataset:
[https://www.kaggle.com/datasets/surajghuwalewala/ham1000-segmentation-and-cl](https://www.kaggle.com/datasets/surajghuwalewala/ham1000-segmentation-and-cl)

### **Kelas Lesi Kulit**

Dataset terdiri dari 7 kelas diagnosis:

* **akiec** – Actinic keratoses & intraepithelial carcinoma
* **bcc** – Basal cell carcinoma
* **bkl** – Benign keratosis-like lesions
* **df** – Dermatofibroma
* **mel** – Melanoma
* **nv** – Melanocytic nevi
* **vasc** – Vascular lesions

## **Preprocessing Data**

Tahapan *preprocessing* yang diterapkan pada notebook meliputi:

* Ekstraksi dan penataan ulang struktur dataset
* *Stratified split* data menjadi:

  * **Train set**: 80%
  * **Validation set**: 10%
  * **Test set**: 10%
* Resize gambar ke ukuran input model
* Normalisasi nilai piksel
* *Data augmentation* (rotasi, flipping, zoom)
* Penanganan *class imbalance* melalui:

  * *Class weighting*
  * **Focal Loss** (opsional)

## **Arsitektur Model**

Model dibangun menggunakan arsitektur **CNN berbasis transfer learning** dengan opsi *fine-tuning*.

### **Karakteristik Utama**

* **Backbone pretrained** (ImageNet)
* *Custom classification head*
* Regularisasi untuk mencegah *overfitting*
* Opsi *fine-tuning* pada layer tertentu

### **Konfigurasi Pelatihan**

* **Optimizer**: Adam
* **Loss Function**:

  * Categorical Crossentropy
  * *Focal Loss* (untuk data tidak seimbang)
* **Metrics**: Accuracy
* **Epochs**: Disesuaikan (default pada notebook)
* **Batch Size**: 32
* **Early Stopping**: Digunakan

## **Pelatihan Model**

Proses pelatihan mencakup:

1. Inisialisasi model CNN
2. Training pada data train dengan augmentasi
3. Validasi performa setiap epoch
4. Penyimpanan model terbaik ke direktori output

Model dilatih menggunakan fungsi modular sehingga mendukung:

* *Fine-tuning layer*
* Eksperimen loss function
* Penyimpanan hasil pelatihan

## **Evaluasi**

Evaluasi dilakukan pada **test set** yang terpisah, dengan metrik utama:

* Accuracy
* Loss

Hasil evaluasi (isi setelah training selesai):

```
Test Loss     : [isi nilai]
Test Accuracy : [isi nilai]
```

Notebook juga mendukung analisis tambahan seperti:

* Perbandingan performa antar konfigurasi
* Analisis *overfitting* melalui kurva loss & accuracy

## **Penggunaan**

Untuk menjalankan proyek ini:

1. Upload `kaggle.json` ke Google Colab
2. Jalankan seluruh sel pada notebook `CNN_skincancer_FIX.ipynb`
3. Model akan:

   * Mengunduh dataset
   * Melatih CNN
   * Mengevaluasi hasil
   * Menyimpan model terbaik

Contoh prediksi:

```python
predictions = model.predict(test_generator)
predicted_class = np.argmax(predictions, axis=1)
```

## **Struktur File**

```
├── CNN_skincancer_FIX.ipynb
├── kaggle.json
├── models_out/
│   └── best_model.h5
└── README.md
```

## **Kesimpulan**

Proyek ini menunjukkan bahwa CNN dengan *transfer learning* dan teknik penanganan data tidak seimbang dapat memberikan performa yang baik dalam klasifikasi kanker kulit. Pendekatan ini relevan untuk pengembangan sistem pendukung diagnosis berbasis AI di bidang medis.

