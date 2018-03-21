
<h5 align="center"><img src="https://cloud.githubusercontent.com/assets/130878/20946612/49a8a25c-bbc0-11e6-8314-10bef902af51.png"></h5>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Otomatisasi](#otomatisasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:

# Sekilas Tentang
[`^ kembali ke atas ^`](#)

**Superset** adalah perangkat lunak visualisasi data yang *open source*. Superset di desain oleh Airbnb. Superset adalah platform eksplorasi data yang dirancang dengan visual, intuitif dan interaktif. Tujuan utama Superset adalah mempermudah untuk mengolah dan memvisualisasikan data. Pengembangnya mengklaim bahwa Superset dapat melakukan analisis dengan cepat. 

# Instalasi
[`^ kembali ke atas ^`](#)

#### Kebutuhan Sistem :
- Virtualbox 2.6
- Ubuntu server 16.04
- Ubuntu bash di windows
- `cryptography` Python library
- Python virtualenv
- Python’s setup tools and pip

#### Proses Instalasi :
1. Lakukan update server
```
$ sudo apt update
```

2. Install ssh pada Ubuntu server
```
$ sudo apt install ssh
```

3. Login ke dalam server menggunakan SSH menggunakan ubuntu bash (Windows)
```
$ ssh student@localhost –p 2222
```

4. Install seluruh kebutuhan sistem yang diperlukan seperti `cryptography` Python library, Python virtualenv, dan Python’s setup tools and pip . 
```
#instalasi cryptography python library
$ sudo apt-get install build-essential libssl-dev libffi-dev python-dev python-pip libsasl2-dev libldap2-dev
#instalasi virtualenv
$ pip install virtualenv
# aktivasi virtualenv
$ virtualenv venv
$. ./venv/bin/activate
#install python setup dan pip
$ pip install --upgrade setuptools pip
```

5. Install Superset
```
$ pip install superset
```

6. Membuat user Admin
```
$ fabmanager create-admin --app superset
```

7. Inisialisasi database Superset
```
$ superset db upgrade
```

8. Memasukkan contoh data untuk visualisasi
```
$ superset load_examples
```

9. Membuat pengaturan awal
```
$ superset init
```

10. Jalankan server web pada port 8088, gunakan -p untuk mengikat port lain
```
$ superset runserver
```
11. Cek kembali localhost:8888/superset , maka superset sudah bisa digunakan

# Konfigurasi

[`^ kembali ke atas ^`](#)

- Untuk menentukan konfigurasi umum, batasan upload file, batas memori yang diperlukan, dan ekstensi/format file yang dapat diupload , dapat dilakukan dengan membuka submenu **Content settings** yang terdapat pada menu **Settings** dan mengisi field sesuai kebutuhan.
     
     ![content_setting](https://github.com/airjyp/Komdat---Oxwall/blob/master/konfigurasi/content_setting.png)

- Kita dapat membatasi batas upload size untuk avatar pada user di submenu **User settings**. 
     
     ![content_setting](https://github.com/airjyp/Komdat---Oxwall/blob/master/konfigurasi/user_setting.png)

- Untuk melengkapi dan melakukan improve pada aplikasi, kita dapat menambahkan fitur tertentu di submenu **Available Plugins** pada menu **Plugins**.
     
     ![konfigurasi](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/Screenshot%20(14).png)

- Untuk mengupload dan menambahkan plugin secara manual, dapat dilakukan pada menu **Add New**.
     
     ![konfigurasi](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/Screenshot%20(15).png)

- Kita dapat mempercantik tampilan aplikasi dengan menambahkan atau mengganti tema aplikasi pada submenu **Themes** di **Appearance**.
     
     ![konfigurasi](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/Screenshot%20(18).png)


# Maintenance

[`^ kembali ke atas ^`](#)

Maintenance dibutuhkan untuk melakukan improvisasi dan kualitas pada aplikasi. Salah satu dari aktivitas maintenance adalah melakukan modifikasi, memperbaiki fitur yang ada, maupun meningkatkan performa aplikasi kita. Oleh karena itu, kita perlu mengaktifkan fitur Maintenance mode saat akan melakukan maintenance, agar tidak ada client yang mengakses aplikasi selama proses maintenance berjalan. Berikut ini adalah langkah-langkah yang harus dilakukan :

1. Login ke dalam admin aplikasi kita.
2. Klik submenu **Special pages** pada menu **Pages**.

     ![pages](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/pages.png)

3. Checked / Unchecked box untuk masuk ke dalam mode maintenance.

     ![maintenance](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/maintenance.png)

4. Untuk menyampaikan pesan yang ingin disampaikan kepada orang yang akan mengakses aplikasi web saat mode maintenance, kita dapat menambahkan pesan pada field **Maintenance message**.
5. Klik tombol **Save** untuk menyimpan perubahan.



# Otomatisasi
[`^ kembali ke atas ^`](#)

Salah satu cara yang bisa digunakan untuk menginstall oxwall dengan cepat yaitu dengan menggunakan layanan web-hosting provider, salah satunya yaitu **Installatron**,berikut cara menginstall oxwall menggunakan installatron:

1. Mengunjungi **Installatron**
2. Search oxwall pada installatron, seperti gambar berikut ini

    ![Installatron](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/otomatisasi%20review.png)

3. klik tombol **Install this application** lalu mengisi informasi yang tersedia pada form

    ![form](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/otomatisasi%20install.png)

4. Tunggu hingga proses instalasi selesai.

Otomatisasi lain yang dapat digunakan pada oxwall yaitu otomatisasi task system menggunakan cron job. Cron job merupakan aplikasi "task scheduler" yang berfungsi untuk memanajemen task apa saja yang diperlukan dalam aplikasi seperti oxwall dan menjalankan task tersebut secara otomatis. Cron job diperlukan oleh oxwall agar admin tidak perlu mengatur aplikasi secara rutin.


# Cara Pemakaian
[`^ kembali ke atas ^`](#)

Berikut akan dijelaskan salah satu cara pemakaian oxwall bagi user baru:

1. Mengunjungi halaman utama oxwall, seperti tampilan di bawah ini.
![Halaman sebelum sign up](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/halaman%20sebelum%20login.png)

2. Klik Sign up lalu mengisi data registrasi yang tersedia setelah masuk ke halaman registrasi
![Form registrasi](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/form%20registrasi%20setelah%20diisi.png)

3. Setelah melakukan registrasi, user akan otomatis login ke oxwall dan diarahkan ke halaman beranda akun user tersebut.
![Halaman beranda](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/beranda.png)

4. User dapat masuk ke halaman profilnya sendiri dan juga dapat mengedit segala informasi yang sudah diisi pada form registrasi sebelumnya jika ada kesalahan isi.
![Lihat Profile](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/lihat%20profile.png)

5. Karena list user pada oxwall bersifat global, maka user dapat menambah pertemanan dengan user lain yang memiliki akun di oxwall dengan cara mengunjungi halaman browse user
![Halaman browse user](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/browse%20user.png)

6. Untuk dapat menambah pertemanan, user perlu untuk mengunjungi user lain yang ingin diajaka berteman lalu menekan button add friend
![Lihat profile user lain](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/lihat%20air.png)

7. User juga dapat mengirim pesan kepada user lain untuk menerima pertemanannya
![Send pm](https://github.com/airjyp/Komdat---Oxwall/blob/master/Screenshots/send%20pm%20air.png)


# Pembahasan
[`^ kembali ke atas ^`](#)

**Apache Superset** adalah aplikasi web yang dapat mengeksplorasi dan visualisasi data. **Apache Superset** memiliki antarmuka yang baik untuk mengeksplorasi dan memvisualisasikan dataset, dan membuat sebuah *dashboard* yang interaktif. Apache Superset ini memiliki kelebihan diantaranya :
- Terdapat berbagai macam visualisasi data yang baik
- Mudah, bebas kode, dan juga pengguna dapat mengolah serta menelusuri data lebih dalam. 
- Alur kerja yang mudah untuk membuat visualisasi dari kumpulan hasil data apapun.
- Dapat membuat visuaslisasi data tanpa menggunakan SQL



Namun, dalam setiap aplikasi pasti memiliki kekurangan dari segi-segi tertentu. Kekurangan dari **Apache Suprset** ini adalah :
- Masih terdapat masalah dalam kustomisasi 
- Aplikasi ini dapat berkembang dengan cepat sehingga pasti banyak ditemukan bug,tetapi bisa melaporkannya ke GitHub issues




Apabila dibandingkan **Apache Superset** dengan aplikasi bussiness intelligence lainnya seperti aplkasi bisrt terdapat keunggulan dan kelemahannya masing-masing. Berikut adalah beberapa perbandingan antara Apache Superset dengan birst :

- **Apache Superset** memiliki visualisasi yang beragam sedangkan **birst** masih terbatas untuk jenis visualisasinya.
- **Facebook** memiliki plugin yang lengkap dan mendukung semua kustomisasi pada setiap fitur dibandingkan **Oxwall**.
- **Oxwall** memiliki fitur search yang detail berdasarkan kriteria tertentu, berbeda dengan **Facebook**
- **Facebook** memiliki pengguna yang jauh lebih banyak daripada **Oxwall** yang aktif pada forum-forum diskusi atau jejaring sosial yang bersifat enterprise. 


# Referensi
[`^ kembali ke atas ^`](#)

1. [About Oxwall](https://www.oxwall.com/about) - Oxwall
2. [Apache Override](https://www.digitalocean.com/community/tutorials/how-to-rewrite-urls-with-mod_rewrite-for-apache-on-ubuntu-16-04) - DigitalOcean
3. [Mysql PHP Problem](https://developers.oxwall.com/forum/topic/55994?page=1) - Oxwall Forum
4. [Cron Jobs Config](https://wiki.oxwall.com/install:cron) - Oxwall Wiki
5. [Oxwall Review](https://alternativeto.net/software/oxwall/reviews/) - Alternativeto
