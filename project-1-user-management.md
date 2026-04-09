**Project 1 :**

**User & Permission Management (WSL - Linux Sysadmin Simulation)**

📌 **Deskripsi :**

Project ini bertujuan untuk mensimulasikan tugas seorang system administrator dalam mengelola user, folder, serta permission pada system Linux. 

Environment yang digunakan adalah Windows Subsystem for Linux (WSL), sehingga dapat meniru server Linux secara lokal.


**🖥️ Environment :**

OS : Windows 11
Virtual Environment : WSL (Windows Subsystem for Linux)
Linux Distro : Ubuntu


**🎯 Tujuan :**

* Membuat dan mengelola user
* Mengatur hak akses (permission)
* Mensimulasikan skenario kerja di server Linux


**⚙️ Langkah-Langkah :**

1. **Membuat User**
   
sudo useradd -m -s /bin/bash developer
sudo useradd -m -s /bin/bash tester

3. **Memberikan Password**
   
sudo passwd developer
sudo passwd tester

5. **Membuat Folder Project**
   
sudo mkdir /project\_app
sudo mkdir /backup

7. **Mengatur Ownership**
   
sudo chown developer:developer /project\_app

9. **Mengatur Permission**
    
sudo chmod 755 /project\_app

Penjelasan :

Owner (developer) -> read, write, execute
Others (tester) -> read, execute

11. **Testing Akses
    
Login sebagai developer**

su - developer
cd /project\_app
touch test.txt

Hasil : Berhasil membuat file

**Login sebagai tester**

su - tester
cd /project\_app
touch gagal.txt

Hasil : Gagal (Permission denied) karena tester tidak memiliki permission write pada folder /project_app


7. **Setup Folder Backup**
   
sudo chown developer:developer /backup
sudo chmod 700 /backup

Penjelasan permission 700 :

Hanya owner (developer) yang memiliki akses penuh

User lain tidak dapat read, write, execute

8. Testing Backup Akses

su - tester
cd /backup

Hasil : Permission denied

su - developer
cd /backup
Hasil : Berhasil mengakses folder



📊 **Hasil :**

* User berhasil dibuat
* Permission berjalan sesuai kebutuhan
* User developer memiliki akses penuh
* User tester hanya memiliki akses terbatas



**🧠 Insight :**

Melalui project ini saya memahami bahwa pengaturan permission sangat penting dalam menjaga keamanan sistem.

Kesalahan dalam pemberian hak akses dapat menyebabkan user yang tidak berwenang mengakses atau memodifikasi data penting.



**📸 Dokumentasi :**
Screenshot hasil pengujian dapat dilihat pada folder screenshots/
