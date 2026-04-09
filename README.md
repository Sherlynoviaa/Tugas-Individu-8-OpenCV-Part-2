# Tugas Individu 8 — OpenCV Part 2

**Mata Kuliah:** Praktikum Machine Learning (Computer Vision)  

**Dosen Pengampu:** Herfandi, Ph.D. — Informatika — Universitas Teknologi Sumbawa (UTS)



---



## Profil Mahasiswa

* **Nama:** Sherly Novia Indriani

* **NIM:** 231001057

* **Kelas:** Informatika — [C]



---



## Deskripsi Proyek

Repositori ini merupakan dokumentasi teknis hasil praktik mandiri mengenai pengolahan gambar lanjutan menggunakan library **OpenCV** pada Python. Praktikum ini merupakan kelanjutan dari OpenCV Part 1, berfokus pada teknik manipulasi gambar yang lebih kompleks dan interaktif, sebagai fondasi penting dalam pipeline *Computer Vision* dan *Deep Learning*.

Materi praktik mencakup empat topik utama: **Image Crop, Image Resize, Image Blending, dan Image Color Conversion**, termasuk penggunaan interaksi berbasis *mouse event* dan *trackbar slider*.



---



## Lingkungan Pengembangan (Environment)

Seluruh skrip dalam repositori ini disusun dan diuji menggunakan spesifikasi berikut:

* **Kode Editor:** Jupyter Notebook

* **Interpreter:** Python 3.x (conda environment: `opencv_env`)

* **Library Utama:** OpenCV (`cv2`), NumPy (`numpy`)



---



## Cakupan Praktikum

Tahapan koding yang dilakukan mencakup:

1. **Image Crop:** Melakukan pemotongan gambar menggunakan teknik *numpy slicing* dengan notasi `image[y_min:y_max, x_min:x_max]`, termasuk input manual dari user dan crop interaktif menggunakan *mouse event click* (drag & drop).

2. **Mouse Event OpenCV:** Mengimplementasikan `cv2.setMouseCallback()` dan `cv2.namedWindow()` untuk mendeteksi event `LBUTTONDOWN`, `MOUSEMOVE`, `LBUTTONUP`, dan `RBUTTONDOWN` guna membangun interaksi langsung pada jendela gambar.

3. **Image Resize:** Mengubah ukuran gambar menggunakan `cv2.resize()` dengan tiga pendekatan: ukuran tetap, rasio manual, dan parameter `fx`/`fy`. Dilengkapi perbandingan metode interpolasi (`INTER_LINEAR`, `INTER_NEAREST`, `INTER_AREA`, `INTER_CUBIC`) untuk kasus *shrinking* dan *enlarging*.

4. **Resize Interaktif:** Membangun aplikasi resize gambar secara real-time menggunakan mouse drag di atas canvas NumPy.

5. **Image Blending:** Menggabungkan dua gambar menggunakan formula *Linear Blending* `g(x) = (1−α)f0(x) + αf1(x)` melalui `cv2.addWeighted()`, mencakup gambar berukuran sama, berbeda ukuran (stretch & fit proporsional), penempatan di tengah (*center*), serta overlay transparan.

6. **Trackbar Slider:** Mengintegrasikan `cv2.createTrackbar()` untuk mengontrol parameter alpha secara interaktif pada proses blending.

7. **Image Color Conversion:** Mengkonversi ruang warna gambar menggunakan `cv2.cvtColor()` meliputi BGR → Grayscale, BGR → RGB, BGR → BGRA, serta memanipulasi channel Alpha untuk efek transparansi yang disimpan dalam format PNG.



---



## 🔍 Analisis & Kesimpulan Teknis

Setelah melakukan praktik mandiri, berikut adalah beberapa catatan analisis:

1. **Numpy Slicing sebagai Dasar Crop:** Operasi crop di OpenCV pada dasarnya adalah *array slicing* dari NumPy. Pemahaman mendalam tentang sistem koordinat gambar (sumbu Y ke bawah, sumbu X ke kanan) sangat krusial agar area crop sesuai dengan yang diinginkan, terutama saat membangun sistem deteksi objek yang memerlukan ekstraksi ROI (*Region of Interest*).

2. **Global Variable dalam Callback Function:** Penggunaan keyword `global` di dalam fungsi callback mouse menjadi kunci agar koordinat yang direkam saat event berlangsung dapat diakses di luar scope fungsi (di dalam `while loop`). Tanpa deklarasi `global`, nilai koordinat tidak akan diperbarui dan program tidak akan berfungsi dengan benar.

3. **Interpolasi dan Kualitas Gambar:** Pemilihan metode interpolasi berdampak signifikan pada kualitas visual. `INTER_CUBIC` menghasilkan gambar paling halus saat memperbesar, namun lebih lambat secara komputasi. Dalam konteks Computer Vision real-time, terdapat *trade-off* antara kecepatan dan kualitas yang harus disesuaikan dengan kebutuhan.

4. **Blending dan Alpha Channel:** Konsep blending dengan `addWeighted` adalah dasar dari banyak teknik lanjutan seperti *image augmentation* pada data training. Sementara channel Alpha pada format BGRA membuka jalan untuk komposisi gambar (*compositing*) yang lebih profesional — teknik yang lazim digunakan dalam Augmented Reality (AR).

5. **Kesimpulan:** Praktikum ini membuktikan bahwa OpenCV bukan sekadar library pengolah gambar statis, melainkan mampu membangun aplikasi visual yang interaktif. Kemampuan menggabungkan *mouse event*, *trackbar*, dan *real-time rendering* dalam satu loop merupakan pola desain fundamental yang akan terus digunakan dalam proyek Computer Vision yang lebih kompleks ke depannya.



---



## 📽️ Presentasi Video

Demonstrasi lengkap mengenai langkah-langkah praktikum, bedah kodingan baris demi baris, serta penjelasan konsep dapat diakses melalui tautan berikut:



👉 [https://youtu.be/_fS0R0MJfNo]



---
