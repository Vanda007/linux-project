# 🔐 Project 3: Remote Server menggunakan SSH (WSL)

## 📌 Deskripsi
Projek ini berfokus pada implementasi dan konfigurasi SSH server untuk melakukan remote akses ke sistem Linux.
Melalui projek ini, dilakukan simulasi koneksi ke server, verifikasi akses user, serta penerapan konfigurasi keamanan dasar seperti menonaktifkan login root.

---

## 🖥️ Environment
- OS : Windows 11
- Virtual Environment : WSL (Windows Subsystem for Linux)
- Linux Distro : Ubuntu
- Service : SSH Server

---

## 🎯 Tujuan
- Menginstall dan menjalankan SSH server
- Melakukan remote login ke server
- Memahami konsep akses jarak jauh
- Meningkatkan keamanan dengan menonaktifkan login root

---

## ⚙️ Langkah-Langkah
### 1. Install SSH Server
### Command :
```bash
sudo apt update
sudo apt install openssh-server -y
```

### 2. Cek Status SSH
### Command :
```bash
sudo service ssh status
```
**Pastikan status : active (running)**

### 3. Test Remote (localhost)
```bash
ssh developer@localhost
```
Jika muncul ***Are you sure you want to continue connecting (yes/no)?***, pilih ***yes*** kemudian masukkan password user developer

### 4. Verifikasi Login
```bash
Setelah berhasil login, cek dengan whoami maka outputnya akan developer
```

