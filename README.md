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

Pada soal ini, untuk mengetahui aktivitas yang dilakukan oleh user dapat kita lihat pada clue yang diberikan yaitu “mengunggah suatu file”. Mengunggah suatu file identik dengan perilaku STORE pada komputer sehingga kita dapat mencari paket dengan info STOR dan didapatkan request dan response yang relevan dengan informasi tersebut yaitu pada paket no 147 dan 149.

> A. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 

Pada pertanyaan ini kita diminta untuk mencari sequence number (raw) dari request STOR. Kita bisa dapatkan nilai ini dengan membuka “Transmission Control Protocol” pada paket tersebut dan bisa kita temukan nilainya disana.

![1A1](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/4a63dfff-7d49-4df5-9a8b-2ee0ebb04050)

![1A2](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/5f9ab2b7-1bc0-4620-97dc-ba254ac14b78)

> B. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?

Selanjutnya pada pertanyaan ini, di section yang sama dapat kita temukan nilai 
“Acknowledgment number (raw)” dibawah nilai pada pertanyaan sebelumnya.

![1B](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/66485acb-ec4b-4666-a846-ed3332695b2d)

> C. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Pada pertanyaan ini, kita perlu membuka response dari aktivitas STOR yang berhasil dilakukan yaitu pada paket ke 149. Sama seperti sebelumnya, kita perlu membuka section “Transmission Control Protocol” dan dapat kita temukan nilainya disana

![1C](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/3e9d6839-1690-4644-9e3f-2610d59f4a4a)

> D. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Terakhir untuk mencari nilai “Acknowledgment number (raw)” dapat kita temukan 
dibawah nilai pada soal sebelumnya untuk response dari aktivitas STOR.

![1D](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/a739f33a-eadb-4b90-8c05-dc2b12337ae4)

### Soal 2
> Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

Untuk melihat server yang digunakan pada portal praktikum Jaringan Komputer dapat kita lihat pada salah satu protokol paket yang terekam didalam soal2.pcapng. Disini kami menggunakan salah satu paket dengan protokol TCP. Setelah itu kita perlu klik kanan pada paket tersebut, lalu pilih follow, dan memilih “TCP Stream”. Selanjutny akan muncul salah satu request yang telah berjalan dengan contoh dibawah ini dan dapat kita lihat pada detail server. Detailnya dapat dilihat dibawah ini

![2A1](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/b476b68e-3ba2-4933-9e96-8e48fcd3f0fa)

![2A2](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/2224edc9-f110-4d3a-9045-b53419e88a6f)

### Soal 3
> Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

A. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

Untuk menghitung banyak paket yang tercapture pada IP source maupun destination address 239.22.22.250 dengan port 3702 dapat menggunakan kueri filter ‘ip.dst’ untuk address dan ‘udp.port’ untuk port yang diinginkan. Pada kasus ini kita perlu memasukkan kueri “ip.dst == 239.255.255.250 && udp.port == 3702”, maka akan keluar semua paket dengan kueri tersebut dan apabila dihitung total akan ada 21 paket

![3A](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/15216841-1520-461d-8638-f6ce7127c6ed)

B. Protokol layer transport apa yang digunakan?

Pada pertanyaan ini, protokol yang digunakan ialah UDP karena didapatkan dari hasil sebelumnya.

![3B](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/68a1b350-e179-4534-b048-cbec16bcf39f)

### Soal 4
> Berapa nilai checksum yang didapat dari header pada paket nomor 130?

Pada soal ini, kita perlu mencari paket yang didapatkan ke-130, lalu pada bagian “User Datagram Protocol” (kiri bawah) kita expand dan bisa kita dapatkan nilai checksum 0x18e5

![4.1](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/28e98de4-ebac-41c1-84cb-0cb5491f664f)

![4.2](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92737767/ad579f01-935b-4f9a-959f-98d72ee04db2)

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

![image](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/ae9fece6-f243-4aba-912d-2cf47c2e4fbc)

### Soal 7
> Berapa jumlah packet yang menuju IP 184.87.193.88?

Untuk mencari packet kita tinggal melakukan pengecekan pada nomor yang ada di sebelah kiri

Tetapi jika kita ingin mencari jumlah packet yang menuju suatu IP, kita harus melakukan filter terhadap ``source`` dari suatu IP. Disini kita bisa menggunakan bantuan capture filter ``ip.src = 184.87.193.88`` dan nanti akan didapatkan packet yang menuju IP 184.87.193.88

![image](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/0106c219-8dc1-4f32-9d80-861e315becec)

Didapatkan bahwa Jumlah Packet yang ada adalah ``6``

Selanjutnya kita tinggal memasukkan ke dalam ``Netcat``

![image](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/2947185b-b7ff-4966-a28c-afe35185260a)

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

![image](https://github.com/Caknoooo/Jarkom-Modul-1-A09-2023/assets/92671053/f8fff2a4-8fb6-43f1-b31f-0d7657db82b5)

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
