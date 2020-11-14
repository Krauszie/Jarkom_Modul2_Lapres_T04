# Jarkom_Modul2_Lapres_T04

## 1. Buat alamat http://semerut04.pw 

Pada UML Malang, Jalankan perintah `nano /etc/bind/jarkom/semerut04.pw`
![gambar](https://user-images.githubusercontent.com/55182321/99148818-7c891d80-26bc-11eb-9bb4-269653957860.png)

Masukan seperti gambar di atas hingga mengisi name server (NS) dan A dengan ip probolinggo

![gambar](https://user-images.githubusercontent.com/55182321/99148899-151f9d80-26bd-11eb-86bd-0cee16d3863f.png)

Masukan zona semerut04.pw seperti gambar di atas dan juga masukan file nya

## 2. Buat alias http://www.semerut04.pw

Tambahkan CNAME pada semerut04.pw

![gambar](https://user-images.githubusercontent.com/55182321/99148818-7c891d80-26bc-11eb-9bb4-269653957860.png)

Masukan www dengan CNAME yang menuju ke semerut04.pw

## 3. Buat subdomain penanjakan.semerut04.pw

Tambahkan subdomain pada file /etc/bind/jarkom/semerut04.pw

![gambar](https://user-images.githubusercontent.com/55182321/99148818-7c891d80-26bc-11eb-9bb4-269653957860.png)

tambahkan penanjakan yang mengarah ke IP probolinggo

## 4. Buat reverse domain utama

Tambahkan zona di /etc/bind/named.conf.local

![gambar](https://user-images.githubusercontent.com/55182321/99149125-b9eeaa80-26be-11eb-80b3-d36e7a471f0a.png)

Tambahkan 73.151.10.in-addr.arpa angka `73.151.10` didapat dari byte ke 3 2 dan 1 IP probolinggo. Lalu buat file 73.151.10.in-addr.arpa di /etc/bind/jarkom/

![gambar](https://user-images.githubusercontent.com/55182321/99149212-37b2b600-26bf-11eb-8909-c665ee351fb1.png)

## 5. 

Pada UML malang ubah  /etc/bind/named.conf.local

![gambar](https://user-images.githubusercontent.com/55182321/99149539-44380e00-26c1-11eb-81c5-cdfe90fabe26.png)

Ubah zona malang menjadi type master dan masukan seperti gambar di atas

![gambar](https://user-images.githubusercontent.com/55182321/99149649-fd96e380-26c1-11eb-92dc-ed2d046d1090.png)

masukan zona semerut04.pw dengan tipe slave pada /etc/bind/named.conf.local di UML Mojokerto

## 6.
