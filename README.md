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






<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul2_Lapres_D14/blob/main/images/1A.JPG" >







