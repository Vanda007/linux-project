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

1. **Membuat User** <br>
sudo useradd -m -s /bin/bash developer <br>
sudo useradd -m -s /bin/bash tester

3. **Memberikan Password** <br>
sudo passwd developer
sudo passwd tester

4. **Membuat Folder Project** <br>
sudo mkdir /project\_app
sudo mkdir /backup

5. **Mengatur Ownership** <br>
sudo chown developer:developer /project\_app

6. **Mengatur Permission** <br>
sudo chmod 755 /project\_app <br>

Penjelasan : <br>
Owner (developer) -> read, write, execute <br>
Others (tester) -> read, execute

7. **Testing Akses**
Login sebagai developer <br>
su - developer
cd /project\_app
touch test.txt <br>
Hasil : Berhasil membuat file

Login sebagai tester <br>
su - tester
cd /project\_app
touch gagal.txt <br>
Hasil : Gagal (Permission denied) karena tester tidak memiliki permission write pada folder /project_app


8. **Setup Folder Backup** <br>
sudo chown developer:developer /backup
sudo chmod 700 /backup
<br>
Penjelasan permission 700 : <br>
Hanya owner (developer) yang memiliki akses penuh <br>
User lain tidak dapat read, write, execute

9. **Testing Backup Akses** <br>
su - tester
cd /backup <br>
Hasil : Permission denied
<br>
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
