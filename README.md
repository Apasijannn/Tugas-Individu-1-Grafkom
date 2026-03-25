# Tugas-Individu-1 Grafkom
Drawing Using HTML Canvas Graphics

Sebuah proyek rendering 2D interaktif yang menggambar dan menganimasikan bentuk "Origami Hummingbird" (Burung Kolibri Origami) menggunakan murni **HTML5 Canvas** dan **JavaScript**. Proyek ini dibuat untuk memenuhi Tugas Individu 1 pada mata kuliah Grafika Komputer.

## 📌 Deskripsi Proyek
Proyek ini mendemonstrasikan pemahaman dasar hingga menengah mengenai grafika komputer 2D di web. Tanpa menggunakan aset gambar eksternal (SVG/PNG), seluruh bentuk burung dibangun menggunakan koordinat matematika (metode *Pathing*) dan dimanipulasi secara langsung (metode *Transformasi*) di atas kanvas.

## 🚀 Fitur & Konsep Grafika Komputer
Kode pada repositori ini mengimplementasikan beberapa konsep utama dalam *rendering pipeline* grafika 2D:

### 1. Transformasi Matriks (Matrix Transformations)
* **Refleksi (Flip):** Memanfaatkan kombinasi `ctx.translate()` dan `ctx.scale(-1, 1)` untuk membalik sistem koordinat sumbu X. Ini memungkinkan gambar dicerminkan secara dinamis tanpa mengubah susunan koordinat *vertex* aslinya.
* **Translasi Dinamis (Hovering):** Menggunakan fungsi trigonometri `Math.sin(time)` di dalam *rendering loop* untuk menciptakan gelombang periodik, menghasilkan efek objek melayang (naik-turun) secara konstan dan mulus.
* **Koreksi Posisi (Centering):** Penyesuaian *offset* menggunakan translasi statis agar pusat massa (titik berat) dari gabungan poligon berada persis di tengah *viewport*.

### 2. Rendering Pipeline & Manajemen State
* **Loop Animasi:** Berjalan pada 60 FPS menggunakan `requestAnimationFrame`.
* **State Isolation:** Menggunakan metode `ctx.save()` dan `ctx.restore()` untuk memisahkan *state* kanvas. Hal ini memastikan transformasi yang diterapkan pada burung tidak memengaruhi rendering teks statis di bawahnya, dan mencegah terjadinya akumulasi pergeseran koordinat antar *frame*.
* **Frame Clearing:** Pembersihan piksel menggunakan `ctx.clearRect()` pada setiap awal *frame* untuk mencegah efek visual *trailing* atau penumpukan gambar.

### 3. Konstruksi & Shading (Pathing & Fill)
* Objek terdiri dari 6 komponen poligon (sayap atas, sayap, badan, ekor, leher, kepala) yang digambar titik per titik menggunakan `ctx.moveTo()` dan `ctx.lineTo()`.
* **Pencahayaan 3D Semu:** Menggunakan `ctx.createLinearGradient()` untuk memberikan efek *shading* lipatan kertas, ditambah properti bayangan (`shadowColor`, `shadowBlur`) untuk menghasilkan ilusi kedalaman spasial.

## 💻 Cara Menjalankan
Proyek ini tidak memerlukan instalasi *library* atau *framework* tambahan.
1. *Clone* repositori ini ke komputer lokal kamu.
2. Buka file `Tugas Individu 1 - 5054241036.html` menggunakan *web browser* modern apa saja (Chrome, Firefox, Safari, Edge).

## 👨‍💻 Identitas Penulis
* **Nama:** Anjay
* **Program Studi:** Artificial Intelligence Engineering
* **Institusi:** Institut Teknologi Sepuluh Nopember (ITS)

---
