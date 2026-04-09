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
```bash
sudo useradd -m -s /bin/bash developer
sudo useradd -m -s /bin/bash tester
```


### 2. Membuat Password
```bash
sudo passwd developer
sudo passwd tester
```
### Cek User
```bash
cat /etc/passwd | grep developer
cat /etc/passwd | grep tester
```

### 3. Membuat Folder Project
```bash
sudo mkdir /project_app
sudo mkdir /backup
```
### Cek Hasil
```bash
ls -ld /project_app
ls -ld /backup
```

### 4. Mengatur Ownership 
```bash
sudo chown developer:developer /project_app
```
### Cek Hasil
```bash
ls -ld /project_app
```

### 5. Mengatur Permission 
```bash
sudo chmod 755 /project_app
```
### Cek Hasil
```bash
ls -ld /project_app
```
Penjelasan chmod 755 :
- Owner (developer) -> read, write, execute
- Group -> read, execute
- Others (tester) -> read, execute
