# Jarkom-Modul-1-A09-2023
**Praktikum Jaringan Komputer Modul 1 Tahun 2023**

## Author
| Nama | NRP |Github |
|---------------------------|------------|--------|
|Andika Laksana Putra | 5025211001 | https://github.com/DikaPutra07 |
|M. Naufal Badruttamam | 5025211240 | https://github.com/Caknoooo |

### List Soal
- [Soal 1](#Soal-1)
- [Soal 2](#Soal-2)
- [Soal 3](#Soal-3)
- [Soal 4](#Soal-4)
- [Soal 5](#Soal-5)
- [Soal 6](#Soal-6)
- [Soal 7](#Soal-7)
- [Soal 8](#Soal-8)
- [Soal 9](#Soal-9)
- [Soal 10](#Soal-10)

### Soal 1
> User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

A. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 

B. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

C. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

D. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

### Soal 2
> Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

### Soal 3
> Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

A. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

B. Protokol layer transport apa yang digunakan?

### Soal 4
> Berapa nilai checksum yang didapat dari header pada paket nomor 130?

### Soal 5
> Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

A. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

B. Port berapakah pada server yang digunakan untuk service SMTP?

C. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

### Soal 6
> Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan **"server SOURCE ADDRESS 7812 is invalid"**. ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

Untuk mengerjakan soal ini kita harus fokus terhadap pola decrypt yang diberikan yaitu ``a1 e5 u21`` karena ini meruapakan kunci di soal ini. Setelah kita paham terkait pola yang diberikan. Sekarang kita berfokus pada yang di bold pada soal yaitu ``SOURCE ADDRESS 7812``. Lalu kita mencari apa yang berhubungan dari kata-kata tersebut.

Setelah kita menemukan pola bahwa kita disuruh untuk mengecek PACKET bernomor 7812. Sekarang kita berfokus pada kata yang lain yaitu kita disuruh untuk melihat ``SOURCE ADDRESS`` dimana kita dapat melihat ``ip source`` yang ada disitu. Selanjutnya dari ``ip source`` tersebut. Kita dapat membentuk suatu barisan angka yang dapat dipecah menjadi beberapa angka karena huruf hanya ada 26

Berikut merupakan ``IP Source`` yang ditemukan 
```
104.18.14.101
```

Selanjutnya kita dapat menggabungkan IP Source tersebut menjadi deretan angka 
```
1041814101
```

Lalu kita dapat memecah menjadi angka yang ``<= 26``
```
10 4 18 14 10 1
```

Dari situ kita dapat membentuk suatu kata dari pola yang telah ditemukan yaitu 
```
JDRNJA
```

[SS masukkan ke NC]

### Soal 7
> Berapa jumlah packet yang menuju IP 184.87.193.88?

Untuk mencari packet kita tinggal melakukan pengecekan pada nomor yang ada di sebelah kiri

Tetapi jika kita ingin mencari jumlah packet yang menuju suatu IP, kita harus melakukan filter terhadap ``source`` dari suatu IP. Disini kita bisa menggunakan bantuan capture filter ``ip.src = 184.87.193.88`` dan nanti akan didapatkan packet yang menuju IP 184.87.193.88

![image](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/0106c219-8dc1-4f32-9d80-861e315becec)

Didapatkan bahwa Jumlah Packet yang ada adalah ``7``

Selanjutnya kita tinggal memasukkan ke dalam ``Netcat``

[SS NC]

### Soal 8
> Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

Untuk soal no 8, kita hanya melakukan kueri filter terhadap paket yang menuju port 80. Tetapi untuk kueri filter tidak dimasukkan ke dalam capture filter, melainkan dimasukkan ke dalam ``Netcat`` yang telah ada

Untuk mendapatkan kueri filter tersebut kita membutuhkan bantuan dari ``tcp`` dan ``udp`` untuk melakukan filter terhadap masing-masing port. ``tcp/udp`` dapat melakukan filter terhadap tujuan port yang diinginkan dengan menggunakan ``.dstport`` Dengan bantuan ``tcp.dstport == 80`` + ``udp.dstport == 80`` kita dapat mendapatkan seluruh port yang menuju port 80 tersebut. Karena kita menggunakan operasi ``+`` kita dapat mengimplementasikannya menggunakan operasi ``or``. Jadi untuk kueri Filter hasilnya adalah sebagai berikut:

![image](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/56213af9-61d3-4aca-b64d-1263a1651d6d)

### Soal 9
> Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

Untuk membuat kueri filter terhadap alamat asal dan tidak ingin menuju suatu alamat, kita dapat menggunakan beberapa logical operator yang ada pada capture filter. Operator yang digunakan adalah ``equal``, ``not equal``, ``AND``. Operator AND (&&) digunakan sebagai penyambung bahwa kita ingin melakukan dua kali operasi dengan syarat sama-sama terpenuhi. 

Karena kita ingin menuju alamat IP. Disini kita membutuhkan bantuan ``ip`` pada capture filter untuk melakukan filtering. Karena kita ingin melakukan pengecekan alamat ``asal / source`` dan alamat ``tujuan / destination``. Kita dapat menggunakan ``ip.src dan ip.dst`` untuk melakukan filtering tersebut.

Sehingga kueri yang dihasilkan adalah 
```
ip.src == 10.51.40.1 && ip.dst != 10.39.55.34
```

[SS]

### Soal 10
> Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

Untuk mencari kredensial suatu akun kita dapat menggunakan bantuan ``TELNET`` pada capture filter nya. Disini kami menggunakan algoritma ``BRUTE FORCE`` dimana kami melakukan pengecekan tiap packet dimulai dari yang terbesar. Karena packet yang kecil atau nomor yang kecil kebanyakan ``nihil`` dan untuk packet yang besar ada kredensial nya. Lalu kami menemukan bahwa kredensial password ada di packet 236. Berikut meruapakan ``password`` yang kami temukan 

![Screenshot (699)](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/f58d19ac-efa3-4401-8842-d455ee63823a)

Lalu dari password tersebut kita tinggal memasukkannya ke dalam ``Netcat`` dimana formatnya adalah ``[USERNAME]:[PASSWORD]``

Berikut merupakan kredensial yang telah kami dapatkan
```
dhafin:kesayangannyak0k0
```

![Screenshot 2023-09-18 214428](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/4b02dde3-6a94-4092-890f-7a2d74154900)
