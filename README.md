# Minpro-2-DDP-SistemManajemenProyekDesain

**Nama:** [Lithalia Geminifer Addawiyah]  
**NIM:** [2609116088]  
**Kelas:** [C]  

---

## 1. Deskripsi Singkat Program
Program ini merupakan sistem manajemen data proyek desain berbasis Command Line Interface (CLI) menggunakan bahasa Python. Program menerapkan *Role-Based Access Control* (RBAC) dengan dua peran pengguna:
* **Admin:** Memiliki akses penuh terhadap fitur CRUD (Create, Read, Update, Delete) data proyek.
* **User:** Memiliki hak akses terbatas untuk menampilkan seluruh data proyek dan mencari proyek berdasarkan nama klien.

Program memanfaatkan struktur data **Dictionary** untuk menyimpan data proyek serta **Function** untuk memisahkan setiap modul logika program.

---

## 2. Gambar Flowchart & Penjelasan Alur

![Flowchart Program](flowchart_minpro2)

### Penjelasan Alur Flowchart:
* **Menu Utama & Login:** Pengguna memilih menu Login. Sistem melakukan verifikasi username dan password. Jika salah 3 kali, batas kesempatan habis dan pengguna dikembalikan ke Menu Utama.
* **Menu Admin:**
  * **Tampilkan Data Proyek:** Menampilkan tabel daftar seluruh proyek desain.
  * **Tambah Data Proyek:** Menerima input nama klien, jenis desain, dan deadline, lalu menyimpannya ke dalam dictionary data proyek.
  * **Ubah Data Proyek:** Memvalidasi input nomor proyek (harus berupa angka dan ada di daftar). Jika valid, sistem memperbarui detail data proyek tersebut.
  * **Hapus Data Proyek:** Memvalidasi nomor proyek lalu menghapus data terkait dari dictionary.
  * **Logout:** Mengakhiri sesi Admin dan mengarahkan kembali ke Menu Utama.
* **Menu User:**
  * **Tampilkan Data Proyek:** Menampilkan daftar seluruh proyek desain yang ada.
  * **Cari Proyek:** Menerima input nama klien dan mencocokkan data pada sistem. Jika ditemukan, detail proyek ditampilkan.
  * **Logout:** Mengakhiri sesi User dan mengarahkan kembali ke Menu Utama.

---

## 3. Dokumentasi Program & Output

### A. Tampilan Login & Validasi Kesempatan
![Dokumentasi Login](screenshot_login.png)
*Penjelasan:* Tampilan saat pengguna melakukan login dan sistem memproses validasi masukan kredensial (serta alur jika gagal 3 kali).

### B. Fitur Admin (CRUD)
![Dokumentasi Admin](screenshot_admin.png)
*Penjelasan:* Tampilan saat Admin menjalankan menu Tampilkan, Tambah, Ubah, Hapus Data Proyek, serta penanganan error saat input tidak sesuai.

### C. Fitur User
![Dokumentasi User](screenshot_user.png)
*Penjelasan:* Tampilan saat User melihat data dan menjalankan fitur pencarian nama klien.

---

## 4. Penjelasan Penerapan Nilai Tambah
* **Error Handling (`try-except`):** Mencegah program *crash* saat pengguna memasukkan tipe data huruf pada pilihan nomor (seperti pada menu Ubah/Hapus Data).
* **Penggunaan Library Python:** Menggunakan library `os` untuk membersihkan layar terminal, `sys` untuk menghentikan program, dan `prettytable` untuk menyajikan data dalam bentuk tabel yang rapi.
