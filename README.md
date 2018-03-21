
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

Konfigurasi yang dilakukan adalah saat kita akan menghubungkan database ke Superset: 

1. Setelah melakukan login, pilih: **Sources** pada Menu Tab, lalu pilih **Databases**
     
     ![Login Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/3.0.PNG)

2. Kita akan diarahkan ke List Databases Page. Pilih **tanda tambah hijau** di kanan atas. 
     
     ![Login Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/3.PNG)
     ![Login Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/3.1.PNG)

3. Isi semua form. Mulai dari **Database** (nama database), **SQLAlchemy URL** (link ke database), hingga **Impersonate the logged on user**. Setelah itu pilih **Save**.
     
     ![Login Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/4.png)
     
4. Konfigurasi untuk terhubung dan kontrol Databases:
```
#---------------------------------------------------------
# Superset specific config
#---------------------------------------------------------
ROW_LIMIT = 5000
SUPERSET_WORKERS = 4

SUPERSET_WEBSERVER_PORT = 8088
#---------------------------------------------------------

#---------------------------------------------------------
# Flask App Builder configuration
#---------------------------------------------------------
# Your App secret key
SECRET_KEY = '\2\1thisismyscretkey\1\2\e\y\y\h'

# The SQLAlchemy connection string to your database backend
# This connection defines the path to the database that stores your
# superset metadata (slices, connections, tables, dashboards, ...).
# Note that the connection information to connect to the datasources
# you want to explore are managed directly in the web UI
SQLALCHEMY_DATABASE_URI = 'sqlite:////path/to/superset.db'

# Flask-WTF flag for CSRF
WTF_CSRF_ENABLED = True
# Add endpoints that need to be exempt from CSRF protection
WTF_CSRF_EXEMPT_LIST = []

# Set this API key to enable Mapbox visualizations
MAPBOX_API_KEY = ''
```

# Otomatisasi
[`^ kembali ke atas ^`](#)

# Cara Pemakaian
[`^ kembali ke atas ^`](#)

Berikut akan dijelaskan salah satu cara pemakaian bagi user baru:

1. Mengunjungi halaman utama Superset, seperti tampilan di bawah ini. lalu login dengan username dan password yang telah dimasukkan saat instalasi
![Login Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/1.PNG)

2. Lalu akan muncul list database contoh
![Home Page Superset](https://github.com/hafidz1997/KOMDAT/blob/master/2.PNG)




# Pembahasan
[`^ kembali ke atas ^`](#)

**Apache Superset** adalah aplikasi web yang dapat mengeksplorasi dan visualisasi data. **Apache Superset** memiliki antarmuka yang baik untuk mengeksplorasi dan memvisualisasikan dataset, dan membuat sebuah *dashboard* yang interaktif. Apache Superset ini memiliki kelebihan diantaranya :
- Terdapat berbagai macam visualisasi data yang baik
- Mudah, bebas kode, dan juga pengguna dapat mengolah serta menelusuri data lebih dalam. 
- Alur kerja yang mudah untuk membuat visualisasi dari kumpulan hasil data apapun.
- Dapat membuat visualisasi data tanpa harus mengetahui SQL


Namun, dalam setiap aplikasi pasti memiliki kekurangan dari segi tertentu. Kekurangan dari **Apache Superset** tersebut adalah :
- Tidak bisa melakukan kustomisasi
- Aplikasi ini adalah aplikasi baru tetapi dapat berkembang dengan cepat sehingga dapat banyak ditemukan bug-bug 





# Referensi
[`^ kembali ke atas ^`](#)

1. [About Apache](https://medium.com/@InDataLabs/superset-benefits-and-limitations-of-the-open-source-data-visualization-tool-by-airbnb-8dc8ac81efa9) - About Apache (InData Labs on Medium.com)
2. [Instalation](https://github.com/apache/incubator-superset) - Apache Superset Instalation with CLI
3. [Configuration](https://superset.apache.org) - Apache Superset Configuration
