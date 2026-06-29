[README.md](https://github.com/user-attachments/files/29465597/README.md)
# ✅ To Do List App

Aplikasi web full-stack untuk manajemen tugas harian. Pengguna dapat membuat kategori tugas dan mengelola task di dalamnya, lengkap dengan fitur deadline dan status penyelesaian.

---

## 🛠️ Tech Stack

- **Frontend**: React.js
- **Backend**: Express.js (Node.js)
- **Database**: PostgreSQL

---

## 📁 Struktur Folder

```
todo-list-app/
├── frontend/        # React App
│   ├── src/
│   ├── public/
│   └── package.json
├── backend/         # Express API
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   └── package.json
└── README.md
```

---

## ⚙️ Cara Menjalankan di Lokal

### Prasyarat

Pastikan sudah terinstall:
- [Node.js](https://nodejs.org/) v18+
- [PostgreSQL](https://www.postgresql.org/) v14+
- npm atau yarn

---

### 1. Clone Repository

```bash
git clone https://github.com/username-kamu/todo-list-app.git
cd todo-list-app
```

---

### 2. Setup Database

Buka PostgreSQL dan jalankan perintah berikut:

```sql
CREATE DATABASE todo_app;
```

Lalu buat tabel dengan menjalankan query ini:

```sql
-- Tabel Categories
CREATE TABLE categories (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  description TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tabel Tasks
CREATE TABLE tasks (
  id SERIAL PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  description TEXT,
  deadline DATE,
  status VARCHAR(20) DEFAULT 'pending',
  category_id INTEGER REFERENCES categories(id) ON DELETE CASCADE,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

### 3. Jalankan Backend

```bash
cd backend
npm install
```

Buat file `.env` di folder `backend/`:

```env
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=password_kamu
DB_NAME=todo_app
PORT=5000
```

Jalankan server:

```bash
npm run dev
```

Backend akan berjalan di: `http://localhost:5000`

---

### 4. Jalankan Frontend

Buka terminal baru:

```bash
cd frontend
npm install
npm start
```

Frontend akan berjalan di: `http://localhost:3000`

---

## 📌 Fitur Utama

### CRUD Categories
- Tambah kategori tugas (Kuliah, Pribadi, Kerja, dll.)
- Edit nama dan deskripsi kategori
- Hapus kategori beserta seluruh task di dalamnya
- Lihat daftar semua kategori

### CRUD Tasks
- Tambah task baru ke dalam kategori
- Edit judul, deskripsi, dan deadline task
- Update status task (pending / selesai)
- Hapus task
- Filter task berdasarkan kategori atau status

---

## 👤 Developer

**Nama**: [Nama Kamu]  
**NIM**: [NIM Kamu]  
**Kelas**: [Kelas Kamu]  
**Mata Kuliah**: Pemrograman Web 2  
**Universitas**: Universitas Teknologi Bandung
