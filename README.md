
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

10. Jalankan server web pada port 8088
```
$ superset runserver
```
11. Buka **Superset** dengan mengakses localhost:8088 pada browser

# Konfigurasi

[`^ kembali ke atas ^`](#)

- Untuk menentukan konfigurasi umum, batasan upload file, batas memori yang diperlukan, dan ekstensi/format file yang dapat diupload , dapat dilakukan dengan membuka submenu **Content settings** yang terdapat pada menu **Settings** dan mengisi field sesuai kebutuhan.
     
     ini gambar

- Kita dapat membatasi batas upload size untuk avatar pada user di submenu **User settings**. 
     
     ini gambar

- Untuk melengkapi dan melakukan improve pada aplikasi, kita dapat menambahkan fitur tertentu di submenu **Available Plugins** pada menu **Plugins**.
     
     ini gambar

- Untuk mengupload dan menambahkan plugin secara manual, dapat dilakukan pada menu **Add New**.
     
     ini gambar

- Kita dapat mempercantik tampilan aplikasi dengan menambahkan atau mengganti tema aplikasi pada submenu **Themes** di **Appearance**.
     
     ini gambar


# Maintenance

[`^ kembali ke atas ^`](#)

Maintenance dibutuhkan untuk melakukan improvisasi dan kualitas pada aplikasi. Salah satu dari aktivitas maintenance adalah melakukan modifikasi, memperbaiki fitur yang ada, maupun meningkatkan performa aplikasi kita. Oleh karena itu, kita perlu mengaktifkan fitur Maintenance mode saat akan melakukan maintenance, agar tidak ada client yang mengakses aplikasi selama proses maintenance berjalan. Berikut ini adalah langkah-langkah yang harus dilakukan :

1. Login ke dalam admin aplikasi kita.
2. Klik submenu **Special pages** pada menu **Pages**.

     ini gambar

3. Checked / Unchecked box untuk masuk ke dalam mode maintenance.

     ini gambar

4. Untuk menyampaikan pesan yang ingin disampaikan kepada orang yang akan mengakses aplikasi web saat mode maintenance, kita dapat menambahkan pesan pada field **Maintenance message**.
5. Klik tombol **Save** untuk menyimpan perubahan.



# Otomatisasi
[`^ kembali ke atas ^`](#)

Salah satu cara yang bisa digunakan untuk menginstall oxwall dengan cepat yaitu dengan menggunakan layanan web-hosting provider, salah satunya yaitu **Installatron**,berikut cara menginstall oxwall menggunakan installatron:

1. Mengunjungi **Installatron**
2. Search oxwall pada installatron, seperti gambar berikut ini

    ini gambar

3. klik tombol **Install this application** lalu mengisi informasi yang tersedia pada form

    ini gambar

4. Tunggu hingga proses instalasi selesai.

Otomatisasi lain yang dapat digunakan pada oxwall yaitu otomatisasi task system menggunakan cron job. Cron job merupakan aplikasi "task scheduler" yang berfungsi untuk memanajemen task apa saja yang diperlukan dalam aplikasi seperti oxwall dan menjalankan task tersebut secara otomatis. Cron job diperlukan oleh oxwall agar admin tidak perlu mengatur aplikasi secara rutin.


# Cara Pemakaian
[`^ kembali ke atas ^`](#)

Berikut akan dijelaskan salah satu cara pemakaian oxwall bagi user baru:

1. Mengunjungi halaman utama oxwall, seperti tampilan di bawah ini.
![Login Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/1.PNG)

2. Klik Sign up lalu mengisi data registrasi yang tersedia setelah masuk ke halaman registrasi
![Home Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/2.PNG)

3. Setelah melakukan registrasi, user akan otomatis login ke oxwall dan diarahkan ke halaman beranda akun user tersebut.


4. User dapat masuk ke halaman profilnya sendiri dan juga dapat mengedit segala informasi yang sudah diisi pada form registrasi sebelumnya jika ada kesalahan isi.


5. Karena list user pada oxwall bersifat global, maka user dapat menambah pertemanan dengan user lain yang memiliki akun di oxwall dengan cara mengunjungi halaman browse user


6. Untuk dapat menambah pertemanan, user perlu untuk mengunjungi user lain yang ingin diajaka berteman lalu menekan button add friend


7. User juga dapat mengirim pesan kepada user lain untuk menerima pertemanannya


# Pembahasan
[`^ kembali ke atas ^`](#)

**Apache Superset** adalah aplikasi web yang dapat mengeksplorasi dan visualisasi data. **Apache Superset** memiliki antarmuka yang baik untuk mengeksplorasi dan memvisualisasikan dataset, dan membuat sebuah *dashboard* yang interaktif. Apache Superset ini memiliki kelebihan diantaranya :
- Terdapat berbagai macam visualisasi data yang baik
- Mudah, bebas kode, dan juga pengguna dapat mengolah serta menelusuri data lebih dalam. 
- Alur kerja yang mudah untuk membuat visualisasi dari kumpulan hasil data apapun.


Namun, setiap aplikasi pasti memiliki kekurangan dari segi tertentu, Kekurangan dari **Oxwall** ini adalah :
- Dari segi developer, aplikasi ini belum up-to-date, banyak fitur yang belum di*improve* seiring dengan teknologi aplikasi saat ini sehingga Oxwall tidak lebih baik dari aplikasi yang sudah berkembang saat ini.
- Tidak ada pengaturan yang baik pada pengelolaan privasi pengguna. Siapapun dapat melihat aktivitas maupun profil siapa saja.
- Dalam segi UX, pada saat melakukan sesi register terlalu banyak melakukan input data yang tidak dibutuhkan.



Apabila kira membandingkan **Oxwall** dengan jejaring sosial media seperti Facebook, CMS ini memiliki beberapa keunggulan dan kelemahan. Berikut adalah beberapa perbandingan antara Oxwall dengan Facebook ini :

- **Oxwall** menggunakan memori yang lebih ringan daripada **Facebook** karena modulnya lebih sedikit.
- **Facebook** memiliki plugin yang lengkap dan mendukung semua kustomisasi pada setiap fitur dibandingkan **Oxwall**.
- **Oxwall** memiliki fitur search yang detail berdasarkan kriteria tertentu, berbeda dengan **Facebook**
- **Facebook** memiliki pengguna yang jauh lebih banyak daripada **Oxwall** yang aktif pada forum-forum diskusi atau jejaring sosial yang bersifat enterprise. 


# Referensi
[`^ kembali ke atas ^`](#)

1. [About Apache](https://medium.com/@InDataLabs/superset-benefits-and-limitations-of-the-open-source-data-visualization-tool-by-airbnb-8dc8ac81efa9) - About Apache (InData Labs on Medium.com)
2. [Instalation](https://github.com/apache/incubator-superset) - Apache Superset Instalation with CLI
3. [Configuration](superset.apache.org) - Apache Superset Configuration
