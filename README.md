
##### Library yang saya gunakan :
import cv2
import numpy as np
from matplotlib import pyplot as plt

>>Fungsi remove_background(image_path) dalam kode tersebut digunakan untuk menghapus latar belakang dari sebuah gambar menggunakan beberapa langkah pemrosesan gambar.

Berikut adalah penjelasan isi kode tersebut:

Memuat gambar yang ditentukan oleh image_path menggunakan cv2.imread.

Mengubah gambar ke dalam skala keabuan (grayscale) menggunakan cv2.cvtColor dengan flag konversi cv2.COLOR_BGR2GRAY.

Menerapkan Gaussian blur pada gambar skala keabuan menggunakan cv2.GaussianBlur untuk mengurangi noise. Ukuran kernel disetel ke (5, 5) dan deviasi standar (standard deviation) disetel ke 0.

Melakukan deteksi tepi pada gambar yang telah di-blur menggunakan algoritma Canny dengan nilai ambang (threshold) 50 dan 150, menghasilkan gambar hanya dengan tepi-tepi objek.

Mencari kontur (contours) dalam gambar tepi menggunakan cv2.findContours dengan mode pengambilan (retrieval mode) cv2.RETR_EXTERNAL dan metode aproksimasi kontur cv2.CHAIN_APPROX_SIMPLE.

Membuat masker dengan dimensi yang sama seperti gambar skala keabuan menggunakan np.zeros_like. Lalu, menggambar kontur pada masker menggunakan cv2.drawContours dengan ketebalan cv2.FILLED, mengisi kontur dengan warna putih.

Mengaplikasikan masker ke gambar asli menggunakan cv2.bitwise_and untuk mengambil bagian depan (gambar tanpa latar belakang).
Menampilkan gambar asli dan gambar hasil dengan latar belakang dihapus secara berdampingan menggunakan plt.subplots dan imshow.

Untuk menggunakan kode ini, Anda perlu menginstal OpenCV dan Matplotlib, serta memberikan jalur (path) ke file gambar yang ingin Anda proses. Pada contoh kode ini, file gambar ditentukan dengan 'uas.jpg'.



