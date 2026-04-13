# 🐧 Project 2: Hosting Website Menggunakan NGINX Di WSL

## 📌 Deskripsi 
Project ini berfokus pada implementasi web server NGINX, mulai dari instalasi, konfigurasi virtual host, hingga deployment website sederhana. 

Simulasi dilakukan menggunakan WSL untuk merepresentasikan environment server Linux secara lokal.

---

## 🖥️ Environment
- OS : Windows 11
- Virtual Environmnet : WSL (Windows Subsystem for Linux)
- Linux Distro : Ubuntu
- Web Server : NGINX

---
## 🎯 Tujuan
- Menginstall dan menjalankan nginx
- Membuat website sederhana menggunakan HTML
- Mengkonfigurasi virtual host
- Mengakses website menggunakan domail lokal

---

## ⚙️ Langkah-Langkah

### 1. Update System
### Command :
```bash
sudo apt update
sudo apt upgrade -y
```

### Eksekusi Command di Terminal :

### 2. Install Nginx
### Command :
```bash
sudo apt install nginx -y
```

### Eksekusi Command di Terminal :

### 3. Cek Status Nginx
### Command :
```bash
sudo service nginx status
```

### 4. Membuat Folder Website
### Command :
```bash
sudo mkdir -p /var/www/project2
```

### 5. Membuat File HTML
### Command :
```bash
sudo nano /var/www/project2/index.html
```
### Isi File
```bash
<h1>Project Nginx - Vanda</h1>
<p>Website berhasil dijalankan....</p>
```

### 6. Mengatur Permission
```bash
sudo chown -R $USER:$USER /var/www/project2
sudo chmod -R 755 /var/www/project2
```
Penjelasan :
- Parameter $USER:$USER /var/www/project2 <br>
  -> berarti user yang sedang aktif dijadikan sebagai owner dan group dari folder tersebut
- Permission 755 <br>
  7 (owner) - read, write, execute <br>
  5 (group) - read, execute <br>
  5 (others) - read, execute
