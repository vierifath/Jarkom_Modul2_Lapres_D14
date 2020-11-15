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

- Konfigurasi pada MOJOKERTO 

- Edit file /etc/bind/delegasi/gunung.semerud14.pw menjadi seperti dibawah ini

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/7A.JPG" >

- Restart bind9

      service bind9 restart
      
- Testing : Lakukan ping ke domain naik.gunung.semerud14.pw dari client GRESIK


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/7B.JPG" >

### Soal No. 8
#### 8. Mengatur webserver untuk domain semerud14.pw

- Pindah ke directory /etc/apache2/sites-available
- Copy file default menjadi file semerud14.pw.conf

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/8A.JPG" >

- Restart apache

      service apache2 restart


- Akses dengan browser semerud14.pw


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/8B.JPG" >


### Soal No. 9
#### 9. Mengaktifkan mod rewrite agar urlnya menjadi http://semerud14.pw/home.

- Jalankan perintah 

      a2enmod rewrite

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/9A.JPG" >

- Lalu untuk semerud14.pw, AllowOverride diganti All

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/9B.JPG" >

- Lalu edit file .htaccess dan isikan seperti berikut

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/9C.JPG" >

- Testing : Akses dengan browser semerud14.pw/home

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/9D.JPG" >


### Soal No. 10
#### 10. Web http://penanjakan.semeruc04.pw akan digunakan untuk menyimpan assets file yang memiliki DocumentRoot pada /var/www/penanjakan.semerud14.pw dan memiliki struktur folder sebagai berikut



*  /var/www/penanjakan.semeruyyy.pw
 * /public/javascripts
 * /public/css
 * /public/images
 * /errors

- Ekstrak file asset ke folder penanjakan.semerud14.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/10A.JPG" >

- Lalu tambahkan ServerName dan DocumentRoot dengan penanjakan.semerud14.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/10B.JPG" >

- Aktifkan a2ensite penanjakan.semerud14.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/10C.JPG" >

- Testing : Akses dengan browser penanjakan.semerud14.pw/

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/10D.JPG" >


### Soal No. 11
#### 11. Pada folder /public dibolehkan directory listing namun untuk folder yang berada di dalamnya tidak dibolehkan.

- Pindah ke directory /etc/apache2/sites-available
- Nano penanjakan.semerud14.pw
- Atur indexes, + untuk dibolehkan dan - untuk tidak dibolehkan

- Pengaturan konfigurasi seperti gambar di bawah ini :

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/11A.JPG" >


- Testing 1 : Akses dengan browser penanjakan.semerud14.pw/public

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/11B.JPG" >


- Testing 2 : Akses dengan browser penanjakan.semerud14.pw/public/css/


<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/11C.JPG" >


### Soal No. 12
#### 12. Untuk mengatasi HTTP Error code 404, disediakan file 404.html pada folder /errors untuk mengganti error default 404 dari Apache.

- Pindah ke directory /etc/apache2/sites-available
- Nano penanjakan.semerud14.pw.conf
- Tambahkan : ErrorDocument 404 /errors/404.html

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/12A.JPG" >

- Restart apache

      service apache2 restart

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/12B.JPG" >


- Testing : Akses dengan browser penanjakan.semerud14.pw/(link yang tidak ada)

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/12C.JPG" >


### Soal No. 13
#### 13. Membuat konfigurasi virtual host agar dapat mengakses http://penanjakan.semerud14.pw/public/javascripts dengan http://penanjakan.semerud14.pw/js


- Pindah ke directory /etc/apache2/sites-available
- Nano penanjakan.semerud14.pw.conf
- Tambahkan : Alias “/js” “/var/www/penanjakan.semerud14.pw/public/javascripts”

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/13A.JPG" >

- Restart apache

      service apache2 restart

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/13B.JPG" >

- Testing : Akses dengan browser penanjakan.semerud14.pw/js

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/13C.JPG" >

### Soal No. 14
#### 14. Membuat naik.gunung.semerud14.pw di port 8888

- Pindah ke directory /etc/apache2/sites-available
- Nano naik.gunung.semerud14.pw
- Konfigurasi seperti gambar di bawah ini :

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/14A.JPG" >

Lalu pada ports.conf Listen untuk port 8888

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/14B.JPG" >


- Restart apache

      service apache2 restart

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/14C.JPG" >


- Testing : Akses dengan browser  naik.gunung.semerud14.pw:8888

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/14D.JPG" >


### Soal No. 15
#### 15. Memberikan Auth pada naik.gunung.semerud14.pw

- Untuk menambahkan user dan password menggunakan command berikut:

      htpasswd -c .htpasswd semeru
      
- Periksa username dan password apakah udah tersedia atau belum

      cat /etc/apache2/.htpasswd
      
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/15A.JPG" >

- Lalu tambahkan Auth untuk directory naik.gunung.semerud14.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/15B.JPG" >


- Restart apache

      service apache2 restart
      
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/15C.JPG" >


- Testing : Akses dengan browser  naik.gunung.semerud14.pw:8888

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/15D.JPG" >


- Setelah memasukkan username dan password

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/15E.JPG" >


### Soal No. 16
#### 16. Mengunjungi IP PROBOLINGGO akan dialihkan secara otomatis ke http://semerud14.pw.

- Rubah .htaccess default pada PROBOLINGGO untuk meredirect ip PROBOLINGGO ke semerud14.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/16A.JPG" >

- Ganti allowoverride none jadi all untuk directory /var/www/

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/16B.JPG" >


- Restart apache

      service apache2 restart
      
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/16C.JPG" >

- Testing : Akses dengan browser 10.151.79.124

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/16D.JPG" >


### Soal No. 17
#### 17. request gambar yang memiliki substring “semeru” akan diarahkan menuju semeru.jpg.

- Mengubah file .htaccess sesuai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/17A.JPG" >

- Tambahkan AllowOverride All untuk directory penanjakan.semerud14.pw

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/17B.JPG" >

- Restart apache

      service apache2 restart
      
- Testing : Akses dengan browser --> http://penanjakan.semerud14.pw/public/images/(...)semeru(...).jpg

<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/17C.JPG" >































