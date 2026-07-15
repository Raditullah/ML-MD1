# 🧠 PADL Modul 1 — Dasar Deep Learning & Computer Vision

Panduan lengkap dari instalasi hingga deployment. Ikuti urutan step di bawah ini.

---

## 📁 Struktur Folder

```
PADL_M1/
│
├── README.md                  ← (file ini)
├── requirements.txt           ← semua library yang dibutuhkan
│
├── data/
│   └── caltech101/            ← taruh dataset Caltech-101 di sini
│       ├── accordion/
│       ├── airplanes/
│       └── ...
│
├── models/
│   ├── mlp.py                 ← definisi MLP sederhana
│   └── alexnet.py             ← definisi AlexNet untuk Caltech-101
│
├── utils/
│   ├── datasets.py            ← CustomImageDataset
│   └── training_loops.py      ← fungsi train & evaluate
│
├── scripts/
│   ├── train_mlp.py           ← latih MLP pada data simulasi
│   ├── train_alexnet_caltech.py ← latih AlexNet pada Caltech-101
│   └── mnist_app.py           ← studi kasus MNIST + GUI pygame
│
├── outputs/                   ← hasil training tersimpan di sini
│
└── lab3_fastapi/              ← Lab 3: deployment API
    ├── app.py                 ← FastAPI server
    ├── templates/
    │   └── index.html         ← halaman web sederhana
    └── test_api.py            ← script uji coba API
```

---

## ⚙️ STEP 1 — Persiapan Environment

### 1.1 Install Python (3.9 atau 3.10 direkomendasikan)
Download dari: https://www.python.org/downloads/

### 1.2 Buat virtual environment
```bash
# Di terminal VSCode (Ctrl+` untuk buka terminal)
cd PADL_M1

# Buat venv
python -m venv venv

# Aktifkan venv
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate
```

### 1.3 Install semua library
```bash
pip install -r requirements.txt
```

> ⚠️ Jika punya GPU NVIDIA, install PyTorch versi CUDA dari https://pytorch.org/get-started/locally/

---

## 📦 STEP 2 — Download Dataset Caltech-101

1. Buka: https://data.caltech.edu/records/mzrjq-6wc02
2. Download file `caltech-101.zip`
3. Extract dan pindahkan isi folder `101_ObjectCategories` ke dalam `data/caltech101/`

Struktur yang benar:
```
data/caltech101/
├── accordion/
│   ├── image_0001.jpg
│   └── ...
├── airplanes/
│   └── ...
└── ...
```

---

## 🔬 STEP 3 — Jalankan Studi Pendahuluan

Baca modul dan jawab pertanyaan P1–P4 dalam laporan minimal 4 halaman.

---

## 🚀 STEP 4 — Latih MLP (Training pada Data Simulasi)

```bash
python3 scripts/train_mlp.py
```

Yang terjadi:
- Membuat dataset 2D sintetis
- Melatih MLP 1 hidden layer selama 50 epoch
- Menampilkan loss dan akurasi per epoch

---

## 🖼️ STEP 5 — Studi Kasus MNIST (CNN + GUI)

```bash
python3 scripts/mnist_app.py
```

Yang terjadi:
- Download dataset MNIST otomatis
- Melatih CNN bergaya LeNet selama 15 epoch (~5-10 menit)
- Membuka GUI: gambar angka dengan mouse, klik "Klasifikasi"

---

## 🏆 STEP 6 — Latih AlexNet pada Caltech-101

```bash
python3 scripts/train_alexnet_caltech.py
```

Yang terjadi:
- Memuat dataset dari `data/caltech101/`
- Melatih AlexNet selama 10 epoch
- Menyimpan grafik loss & akurasi ke `outputs/`
- Menyimpan model ke `outputs/alexnet_caltech.pth`

---

## 🌐 STEP 7 — Lab 3: Deploy FastAPI

```bash
# Masuk ke folder lab3
cd lab3_fastapi

# Jalankan server
uvicorn app:app --reload
```

Buka browser: http://127.0.0.1:8000

Upload gambar → klik Prediksi → lihat hasil!

---

## ✅ Checklist Tugas

- [ ] Studi Pendahuluan P1–P4 (4+ halaman)
- [ ] Lab 1: Dataset kustom 3–5 kelas, min 50 gambar/kelas
- [ ] Lab 2: Implementasi ResNet/MobileNet sendiri, bandingkan dengan AlexNet
- [ ] Lab 3: FastAPI deployment berjalan di localhost
- [ ] Tugas Analisis A1–A4: grafik, confusion matrix, model alternatif
# ML-MD1
