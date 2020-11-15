# Jarkom_Modul2_Lapres_D14

### KELOMPOK        : D14
ANGGOTA         :

* Muhammad Haris W.     (05111840000029)
* Vieri Fath Ayuba      (05111840000153)

## Jawaban Soal Praktikum Jarkom Modul 2

### Soal No. 1
#### 1. Membuat domain semerud14.pw dengan membuat konfigurasi di MALANG seperti dibawah ini :

- Lakukan perintah pada Malang sebagai berikut


      nano /etc/bind/named.conf.local

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >

- Membuat folder jarkom di dalam /etc/bind


      mkdir /etc/bind/jarkom


- Copykan file db.local pada path /etc/bind ke dalam folder jarkom dan ubah namanya menjadi semerud14.pw


       cp /etc/bind/db.local /etc/bind/jarkom/semerud14.pw
- Buka file semerud14.pw dan edit seperti dibawah ini :


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1B.JPG" >

- Restart bind9 dengan perintah 

       service bind9 restart

- Untuk memeriksanya, lakukan ping domain semerud14.pw dengan melakukan perintah berikut  pada client GRESIK dan SIDOARJO

        ping semerud14.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1C.JPG" >



### Soal No. 2
#### 2. Membuat alias www.semerud14.pw

-  Buka file semerud14.pw pada server MALANG dan tambahkan konfigurasi seperti gambar di bawah ini :

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/2A.JPG" >

- Kemudian cek dengan melakukan ping www.semerud14.pw


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/2B.JPG" >


### Soal No. 3
#### 3. Membuat subdomain http://www.penanjakan.semerud14.pw

- Buka file semerud14.pw pada server MALANG dan tambahkan konfigurasi seperti gambar di bawah ini :

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/3A.JPG" >

- Kemudian cek dengan melakukan ping ke subdomain dengan perintah berikut dari client GRESIK

         ping penanjakan.semerud14.pw
         
         
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/3B.JPG" >


### Soal No. 4
#### 4. Reverse domain untuk domain utama

- Edit file /etc/bind/named.conf.local pada MALANG


       nano /etc/bind/named.conf.local
       

- Lalu tambahkan konfigurasi seperti gambar di bawah ini :


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/4A.JPG" >


- Copykan file db.local pada path /etc/bind ke dalam folder jarkom dan ubah menjadi 79.151.10.in-addr.arpa.

- Setelah itu tambahkan konfigurasi seperti gambah di bawah ini :


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/4B.JPG" >


- Kemudian restart bind9 dengan perintah


         service bind9 restart
 
- Untuk mengecek apakah konfigurasi sudah benar atau belum, lakukan perintah berikut pada client GRESIK


         host -t PTR 10.151.79.124


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/4C.JPG" >


### Soal No. 5
#### 5. DNS Server Slave 


- Konfigurasi Pada Server MALANG : Edit file /etc/bind/named.conf.local dan tambahkan konfigurasi seperti gambar di bawah ini :


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/5A.JPG" >

- Lakukan restart bind9

      service bind9 restart


- Konfigurasi Pada Server MOJOKERTO : buka file /etc/bind/named.conf.local pada MOJOKERTO dan tambahkan konfigurasi seperti gambar dibawah ini:

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/5B.JPG" >

- Lakukan restart bind9

      service bind9 restart

- Testing 

- Pada server MALANG silahkan matikan service bind9

      service bind9 stop
 
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/5C.JPG" >
 
- Lakukan ping ke semerud14.pw pada client GRESIK. Jika ping berhasil maka konfigurasi DNS slave telah berhasil


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/5D.JPG" >


### Soal No. 6
#### 6. Subdomain dengan alamat http://gunung.semerud14.pw yang didelegasikan pada server MOJOKERTO dan mengarah ke IP Server PROBOLINGGO 

- Pada MALANG, edit file /etc/bind/jarkom/semeruc04.pw dan ubah menjadi seperti di bawah ini:

      nano /etc/bind/jarkom/semeruc04.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/6A.JPG" >


- Kemudian edit file /etc/bind/named.conf.options pada MALANG.

      nano /etc/bind/named.conf.options
      
- Kemudian comment dnssec-validation auto; dan tambahkan baris berikut pada /etc/bind/named.conf.options

      allow-query{any;};
      
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/6B.JPG" >


- Pada MOJOKERTO edit file /etc/bind/named.conf.options

      nano /etc/bind/named.conf.options

- Kemudian comment dnssec-validation auto; dan tambahkan baris berikut pada /etc/bind/named.conf.options

      allow-query{any;};


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/6C.JPG" >



- Kemudian edit file gunung.semerud14.pw menjadi seperti dibawah ini

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/6D.JPG" >


- Restart bind9

      service bind9 restart
      
- Testing : Lakukan ping ke domain gunung.semerud14.pw dari client GRESIK


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/6E.JPG" >


### Soal No. 7
#### 7. Subdomain dengan nama http://naik.gunung.semerud14.pw, domain ini diarahkan ke IP Server PROBOLINGGO.



<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >







