# Rock Paper Scissors Detection with YOLOv8

## 📌 Overview

Proyek ini adalah model deteksi objek untuk permainan Rock, Paper, Scissors menggunakan YOLOv8. Dataset yang digunakan berasal dari [Roboflow](https://universe.roboflow.com/roboflow-58fyf/rock-paper-scissors-sxsw). Model ini memungkinkan pendeteksian gerakan tangan yang mewakili batu, kertas, dan gunting.

## 📂 Dataset

Dataset yang digunakan dalam proyek ini berasal dari [Roboflow Rock-Paper-Scissors](https://universe.roboflow.com/roboflow-58fyf/rock-paper-scissors-sxsw), yang berisi:

- **3129 gambar**
- **3 kelas**: `Rock`, `Paper`, `Scissors`

## 🚀 Installation

Sebelum memulai, pastikan Anda memiliki Python dan pip terinstall.

```bash
pip install roboflow ultralytics
```

## 📥 Download Dataset

Unduh dataset dari Roboflow menggunakan script berikut:

```python
from roboflow import Roboflow
rf = Roboflow(api_key="PpyxJvnkU6JM6oWUppg8")
project = rf.workspace("face-woman").project("rock-paper-scissors-sxsw-rzrbf")
version = project.version(1)
dataset = version.download("yolov8")
```

## 🎯 Training Model

Untuk melatih model menggunakan YOLOv8, gunakan perintah berikut:

```bash
yolo train model=yolov8s.pt data=/absolute/path/to/data.yaml epochs=25
```

## 📊 Visualisasi Hasil

Untuk melihat hasil pelatihan, jalankan kode berikut:

```python
from IPython.display import display
from PIL import Image

img = Image.open("/content/rock-paper-scissors-1/runs/detect/train/confusion_matrix.png")
display(img)
```

## 💾 Download Model

Setelah pelatihan selesai, kompres folder hasil training dan unduh modelnya:

```python
import shutil
from google.colab import files

folder_path = "/content/rock-paper-scissors-1/runs/detect/train"
zip_path = "/content/train.zip"

shutil.make_archive(zip_path.replace(".zip", ""), 'zip', folder_path)
files.download(zip_path)
```

## 📡 Mencegah Disconnect di Google Colab

Gunakan skrip JavaScript berikut untuk mencegah Google Colab terputus:

```javascript
function keepColabAlive() {
    setInterval(() => {
        console.log("Menghindari disconnect Colab...");
        document.querySelector("colab-toolbar-button").click();
    }, 60000); // Setiap 60 detik
}
keepColabAlive();
```

Untuk menghentikan fungsi ini, gunakan:

```javascript
clearInterval();
```

## 🖼️ Contoh Hasil Deteksi

Berikut adalah beberapa contoh hasil deteksi model yang telah dilatih:





## 🔗 Sumber Daya

- Dataset: [Roboflow Rock-Paper-Scissors](https://universe.roboflow.com/roboflow-58fyf/rock-paper-scissors-sxsw)
- Dokumentasi YOLOv8: [Ultralytics](https://docs.ultralytics.com)
- Google Colab: [Colab Notebook](https://colab.research.google.com)

## ✍️ Kontributor

- **Hanif Maulana Arrasyid**



