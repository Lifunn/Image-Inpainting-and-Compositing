# 🖼️ AI Image Inpainting & Compositing Pipeline

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green)
![AI Model](https://img.shields.io/badge/Model-LaMa%20Inpainting-orange)
![AI Model](https://img.shields.io/badge/Model-Rembg%20(U2Net)-purple)

Proyek ini adalah implementasi pipeline **Computer Vision** untuk memanipulasi posisi objek dalam foto secara realistis. Menggunakan kombinasi teknik **Image Matting** (untuk ekstraksi objek) dan **Generative Inpainting** (untuk memperbaiki background), sistem ini memungkinkan pemindahan objek tanpa meninggalkan "lubang" (hole) pada latar belakang.

---

## 📸 Demo Hasil

Berikut adalah hasil dari pipeline pemrosesan gambar langkah demi langkah:

### 1. Masalah & Solusi
Memindahkan objek "Bapak" dari pinggir ke tengah, sekaligus memasukkan objek "Teman". Background yang ditinggalkan objek dibersihkan menggunakan AI.

| Background Asli (Input) | Hasil Inpainting (Clean BG) | Hasil Akhir (Final Result) |
| :---: | :---: | :---: |
| ![background](https://github.com/user-attachments/assets/8e97e63f-d82c-4350-88b3-f08b71a56f65) | <img width="640" height="640" alt="1_Inpainting_Background_Bersih" src="https://github.com/user-attachments/assets/5a871723-906b-44e5-ab1b-cc3d2b2c4bed" /> |  <img width="640" height="640" alt="5_Final_Result" src="https://github.com/user-attachments/assets/4dd8de8a-a1fa-4938-a83d-9ec3c1c0fd65" />|

### 2. Proses Step-by-Step
Pipeline memecah proses menjadi beberapa tahapan logis:

| Tahap 1: Matting (Ekstraksi) | Tahap 2: Compositing (Layering) |
| :---: | :---: |
| <img width="1200" height="1600" alt="2_Cutout_Teman" src="https://github.com/user-attachments/assets/c8827109-4ff5-4faf-8495-0282403b8b54" /> | <img width="640" height="640" alt="3_Compositing_Step_1" src="https://github.com/user-attachments/assets/57cbd3ca-5698-40b0-9f56-5982550bdf32" /> |

---

## 🛠️ Fitur Utama

*   **Object Matting:** Menggunakan `rembg` (U-2-Net) untuk memisahkan manusia dari background dengan presisi tinggi (Alpha Channel).
*   **Deep Learning Inpainting:** Menggunakan model **LaMa (Large Mask Inpainting)** via `simple-lama-inpainting` untuk mengisi background yang hilang dengan tekstur yang realistis (bukan sekadar blur).
*   **Automatic Masking:** Pembuatan mask otomatis dari objek yang dideteksi dengan teknik Dilasi (`cv2.dilate`) untuk hasil inpainting yang bersih.
*   **Smart Compositing:** Algoritma penempatan otomatis untuk mengatur posisi objek agar berada di tengah frame (`center alignment`).

---

## ⚙️ Teknologi yang Digunakan

*   **Python 3.x**
*   **[Rembg](https://github.com/danielgatis/rembg):** Untuk menghapus background (Background Removal).
*   **[Simple LaMa](https://github.com/advimman/lama):** State-of-the-art AI untuk Image Inpainting.
*   **OpenCV & NumPy:** Untuk pemrosesan citra digital (masking, dilasi).
*   **Pillow (PIL):** Untuk manipulasi dan komposisi gambar.

---

## 🚀 Cara Menjalankan

### 1. Clone Repository
```bash
git clone https://github.com/username-kamu/nama-repo.git
cd nama-repo
