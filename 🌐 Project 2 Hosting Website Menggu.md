🌐 Project 2: Hosting Website Menggunakan NGINX Di WSL

📌 Deskripsi :

Project ini berfokus pada implementasi web server NGINX, mulai dari instalasi, konfigurasi virtual host, hingga deployment website sederhana. 

Simulasi dilakukan menggunakan WSL untuk merepresentasikan environment server Linux secara lokal.



🖥️ Environment

OS: Windows 11

Virtual Environment: WSL (Windows Subsystem for Linux)

Linux Distro: Ubuntu

Web Server: NGINX



🎯 Tujuan

* Menginstall dan menjalankan NGINX
* Membuat website sederhana menggunakan HTML
* Mengkonfigurasi virtual host
* Mengakses website menggunakan domain local



⚙️ Langkah-Langkah

1. Update System
sudo apt update 
sudo apt upgrade -y

2. Install Nginx
sudo apt install nginx -y

3. Cek Status Nginx
sudo service nginx status

4. Membuat Folder Website
sudo mkdir -p /var/www/project2

5. Membuat File HTML
sudo nano /var/www/project2/index.html

Isi file :
<h1>Project Nginx - Vanda</h1>
<p>Website berhasil dijalankan 🚀</p>

6. Mengatur Permission
sudo chown -R $USER:$USER /var/www/project2
sudo chomd -R 755 /var/www/project2
Penjelasan :
- Parameter $USER:$USER -> berarti user yang sedang aktif dijadikan sebagai owner dan group dari folder tersebut
- Permission 755 ->
   7 (owner) - read, write, execute
   5 (group) - read, execute
   5 (others) - read, execute

7. Konfigurasi Nginx 
sudo nano /etc/nginx/sites-available/project2
Isi konfigurasi :
server {
	listen 80;
	server_name project2.local;
	
	root /var/www/project2;
	index index.html;

	location / {
		try_files $uri $uri/ =404;
	}
}

8. Mengaktifkan Config
sudo ln -s /etc/nginx/sites-available/project2 /etc/nginx/sites-enabled/

9. Test Konfigurasi
sudo nginx -t

10. Restart Nginx
sudo service nginx restart

11. Konfigurasi Hosts di Windows
Edit file :
C:\Windows\System32\drivers\etc\hosts
Tambahkan :
127.0.0.1 project2.local

12. Akses Website
Buka browser :
http://project2.local

📊 Hasil
NGINX berhasil diinstall dan dijalankan
Website berhasil dibuat dan diakses
Domain lokal (project1.local) berhasil digunakan
Konfigurasi virtual host berjalan dengan baik

🧠 Insight
Memahami cara kerja web server NGINX
Mengetahui konsep virtual host
Memahami hubungan antara domain dan server
Mampu melakukan deployment website sederhana di lingkungan Linux

📸 Dokumentasi
1-nginx-status.png → Status NGINX berjalan
2-localhost.png → Tampilan default NGINX di browser
3-folder-website.png → Struktur folder website
4-html-file.png → Isi file index.html
5-nginx-config.png → Konfigurasi virtual host
6-nginx-test.png → Hasil test konfigurasi (nginx -t)
7-project1-local.png → Website berjalan di project1.local

