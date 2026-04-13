# 🐧 User & Permission Management (Linux Sysadmin Simulation)

## 📌 Deskripsi
Project ini mensimulasikan tugas seorang System Administrator dalam mengelola user, folder, serta permission pada sistem Linux.

Environment menggunakan WSL (Windows Subsystem for Linux) sehingga dapat meniru server Linux secara lokal.

---

## 🖥️ Environment
- OS: Windows 11
- Virtual Environment: WSL (Windows Subsystem for Linux)
- Linux Distro: Ubuntu

---

## 🎯 Tujuan
- Membuat dan mengelola user
- Mengatur hak akses (permission)
- Mensimulasikan skenario kerja di server Linux

---

## ⚙️ Langkah-Langkah

### 1. Membuat User
### Command :
```bash
sudo useradd -m -s /bin/bash developer
sudo useradd -m -s /bin/bash tester
```
### Eksekusi Command di Terminal :
![img](screenshots/1-create-user.png)


### 2. Membuat Password
### Command :
```bash
sudo passwd developer
sudo passwd tester
```
### Cek User
```bash
cat /etc/passwd | grep developer
cat /etc/passwd | grep tester
```
### Eksekusi Command di Terminal :
![img](screenshots/2-check-user.png)

### 3. Membuat Folder Project
### Command :
```bash
sudo mkdir /project_app
sudo mkdir /backup
```
### Cek Hasil :
```bash
ls -ld /project_app
ls -ld /backup
```
### Eksekusi Command di Terminal :
![img](screenshots/3-create-folder.png)

### 4. Mengatur Ownership 
### Command :
```bash
sudo chown developer:developer /project_app
```
### Cek Hasil :
```bash
ls -ld /project_app
```
### Eksekusi Command di Terminal :
![img](screenshots/4-chown.png)

### 5. Mengatur Permission 
### Command :
```bash
sudo chmod 755 /project_app
```
### Cek Hasil :
```bash
ls -ld /project_app
```
Penjelasan permission 755 :
- Owner (developer) → read, write, execute
- Group → read, execute
- Others (tester) → read, execute
### Eksekusi Command di Terminal :
![img](screenshots/5-chmod.png)

### 6. Testing Akses
- Login sebagai developer
```bash
su - developer
cd /project_app
touch test.txt
```
Hasil : Berhasil membuat file

- Login sebagai tester
```bash
su - tester
cd /project_app
touch text1.txt
```
Hasil : Gagal (Permission denied), karena tester tidak memiliki permission write pada folder /project_app

### Eksekusi Command di Terminal :
![img](screenshots/6-developer-test.png)
![img](screenshots/6-tester-test.png)

### 7. Setup Folder Backup
### Command :
```bash
sudo chown developer:developer /backup
sudo chmod 700 /backup
```
Penjelasan permission 700 : <br>
Hanya owner (developer) yang memiliki akses penuh, user lain tidak dapat read, write, execute

### Eksekusi Command di Terminal :
![img](screenshots/7-setup-folder-backup.png)

### 8. Testing Backup Akses
- Login sebagai tester
```bash
su - tester
cd /backup
```
Hasil : Permission denied

- Login sebagai developer
```bash
su - developer
cd /backup
```
Hasil : Berhasil mengkases folder

### Eksekusi Command di Terminal :
![img](screenshots/8-testing-backup-access.png)

---

## 📊 Hasil 
- User berhasil dibuat
- Permission berjalan sesuai kebutuhan
- User developer memiliki akses penuh
- User tester hanya memiliki akses terbatas

---

## 🧠 Insight 
Melalui project ini saya memahami bahwa pengaturan permission sangat penting dalam menjaga keamanan sistem.
Kesalahan dalam pemberian hak akses dapat menyebabkan user yang tidak berwenang mengakses atau memodifikasi data penting.

---

