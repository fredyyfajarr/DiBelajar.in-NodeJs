# Backend Proyek LMS "DiBelajar.in"

Ini adalah bagian backend dari aplikasi Learning Management System (LMS) "DiBelajar.in". Dibangun dengan stack Node.js, Express, dan MongoDB, backend ini berfungsi sebagai REST API yang menangani semua logika bisnis, manajemen data, dan otentikasi pengguna untuk platform.

---

### ✨ Fitur Utama

* 🔐 **Otentikasi & Otorisasi**: Sistem login, register, dan lupa password berbasis JWT dengan role-based access control (Admin, Instruktur, Student).
* 📚 **Manajemen Konten Dinamis**:
    * CRUD penuh untuk Kursus, Materi pembelajaran (termasuk konten tes), dan Kategori.
    * Sistem Kategori yang bisa dikelola oleh Admin/Instruktur.
* 👥 **Manajemen Pengguna & Pendaftaran**:
    * Admin dapat mengelola semua pengguna di dalam sistem.
    * Siswa dapat mendaftar ke kursus, dan progresnya dilacak.
* 📂 **Upload File ke Cloud**: Menangani upload file untuk *thumbnail* kursus dan pengumpulan tugas siswa menggunakan Multer dan Cloudinary.
* 📝 **Fitur Interaktif & Lanjutan**:
    * Penyimpanan hasil tes siswa.
    * Sistem forum diskusi berantai (*threaded*) untuk setiap materi.
    * Sistem Ulasan & Rating bintang untuk setiap kursus.
    * Notifikasi otomatis untuk pendaftaran kursus dan penyelesaian materi.
* 📊 **Analitik & Laporan**:
    * Endpoint statistik untuk dasbor admin (total pengguna, kursus, dll).
    * Endpoint analitik per kursus untuk Instruktur dan Admin.
* 🔍 **Query Lanjutan**: Middleware kustom untuk menangani pencarian, paginasi, dan filter data (termasuk filter per kategori) di berbagai *endpoint*.
* 🛡️ **Keamanan & Validasi**: Validasi input yang kuat menggunakan Joi dan penanganan error yang terpusat.

---

### 💻 Teknologi yang Digunakan

* **Runtime**: Node.js
* **Framework**: Express.js
* **Database**: MongoDB dengan Mongoose ODM
* **Otentikasi**: JSON Web Token (JWT), Bcrypt
* **Validasi**: Joi
* **Upload File**: Multer, Cloudinary
* **Lainnya**: `dotenv`, `winston` (untuk logging), `nodemailer` (untuk email), `cors`, `helmet`

---

### 🚀 Instalasi dan Setup

1.  **Clone repository ini:**
    ```bash
    git clone [URL_REPOSITORY_ANDA]
    cd dibelajar.in-nodejs-backend
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Buat file `.env`** di dalam folder root `backend`. Salin konten di bawah ini dan sesuaikan nilainya.

    ```env
    # Port Server
    PORT=3000

    # Koneksi MongoDB (contoh: MongoDB Atlas atau lokal)
    MONGODB_URI=mongodb+srv://<user>:<password>@<cluster-url>/lms_db?retryWrites=true&w=majority

    # JSON Web Token
    JWT_SECRET=rahasia-jwt-anda-yang-sangat-panjang-dan-aman

    # Konfigurasi Cloudinary (untuk upload gambar)
    CLOUDINARY_CLOUD_NAME=nama-cloud-anda
    CLOUDINARY_API_KEY=api-key-anda
    CLOUDINARY_API_SECRET=api-secret-anda

    # Konfigurasi Nodemailer (contoh menggunakan Mailtrap atau Gmail)
    EMAIL_HOST=smtp.mailtrap.io
    EMAIL_PORT=2525
    EMAIL_USERNAME=username_mailtrap
    EMAIL_PASSWORD=password_mailtrap
    EMAIL_FROM=noreply@dibelajar.in
    ```

4.  **Jalankan server development:**
    ```bash
    npm run dev
    ```
    Server akan berjalan di `http://localhost:3000`.

---

### 🌐 API Endpoints Utama

* `/api/auth`: Rute untuk registrasi, login, logout, dan lupa password.
* `/api/users`: Rute untuk manajemen pengguna (CRUD oleh Admin) dan profil.
* `/api/courses`: Rute untuk manajemen kursus dan materi.
* `/api/categories`: Rute untuk manajemen kategori.
* `/api/enrollments`: Rute untuk manajemen pendaftaran kursus.
* `/api/reviews`: Rute untuk mengelola ulasan kursus.
* `/api/stats`: Rute untuk statistik dasbor admin.
* `/api/notifications`: Rute untuk notifikasi pengguna.

---

### ©️ Lisensi & Copyright

Copyright (c) 2025 Fredy Fajar Adi Putra. Seluruh hak cipta dilindungi.
