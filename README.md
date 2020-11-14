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

## 5. Membuat DNS slave

Pada UML malang ubah  /etc/bind/named.conf.local

![gambar](https://user-images.githubusercontent.com/55182321/99149539-44380e00-26c1-11eb-81c5-cdfe90fabe26.png)

Ubah zona malang menjadi type master dan masukan seperti gambar di atas

![gambar](https://user-images.githubusercontent.com/55182321/99149649-fd96e380-26c1-11eb-92dc-ed2d046d1090.png)

masukan zona semerut04.pw dengan tipe slave pada /etc/bind/named.conf.local di UML Mojokerto

## 6. Membuat domain gunung.semerut04.pw

Membuat delegasi ns1 dan menuju ke ip mojokerto

![gambar](https://user-images.githubusercontent.com/55182321/99148818-7c891d80-26bc-11eb-9bb4-269653957860.png)

Merubah allow-query pada named.conf.options

![gambar](https://user-images.githubusercontent.com/55182321/99152786-891a6f80-26d6-11eb-8fbd-509f319319fd.png)

Menambahkan allow transfer di zona semeru pada UML malang

![gambar](https://user-images.githubusercontent.com/55182321/99149539-44380e00-26c1-11eb-81c5-cdfe90fabe26.png)

Lalu, setting allow query any dpada UML Mojokerto

![gambar](https://user-images.githubusercontent.com/55182321/99152907-6c326c00-26d7-11eb-95c7-17278113153c.png)

Setelah itu setting allow transfer all pada zona gunung.semerut04.pw di named.conf.local

![gambar](https://user-images.githubusercontent.com/55182321/99152937-abf95380-26d7-11eb-9456-f474cb36cf9d.png)


## 7. Menambahkan subdomain naik.gunung.semerut04.pw

Menambahkan subdomain di UML Mojokerto

![gambar](https://user-images.githubusercontent.com/55182321/99152976-ef53c200-26d7-11eb-8aef-45051efc999c.png)

## 8. Mengatur web server 

Mengatur web server di probolinggo pada /etc/apache2/sites-available/semerut04.pw

![gambar](https://user-images.githubusercontent.com/55182321/99153624-12807080-26dc-11eb-9a55-425a9fb3fe2c.png)

menambahkan /var/www pada documentRoot dengan mendownload menggunakan wget dan mengganti nama semerut04.pw

![gambar](https://user-images.githubusercontent.com/55182321/99153680-976b8a00-26dc-11eb-9fda-34099d4c8f69.png)

Jika di cek di website akan terbuka 

![gambar](https://user-images.githubusercontent.com/55182321/99153721-f0d3b900-26dc-11eb-8374-2d135783e388.png)


## 9. Aktifkan mod rewrite

Mengaktifkan mod rewrite dan mengedit htaccess di /var/www/semerut04.pw

![gambar](https://user-images.githubusercontent.com/55182321/99153995-f9c58a00-26de-11eb-8e93-60b00a834c16.png)

maka juka di akses semerut04.pw/home akan keluar tanpa memerlukan index.php di urlnya

## 10. membuat web penanjakan .semerut04.pw

Membuat penanjakan pada sites-available 

![gambar](https://user-images.githubusercontent.com/55182321/99154220-b10ed080-26e0-11eb-9a42-3a1e7d675487.png)

mendownload file dari wget 10.151.36.202/penanjakan.semerut04.pw dan mengganti namanya

![gambar](https://user-images.githubusercontent.com/55182321/99154367-cf290080-26e1-11eb-9c9a-fdbc9033e7e1.png)

## 11. Pada /public diperbolehkan directory listing namun yang di dalam publc tidak

edit file penanjakan.semerut04.pw menjadi 

![gambar](https://user-images.githubusercontent.com/55182321/99154427-4bbbdf00-26e2-11eb-8aa5-75536ac72b7e.png)

Jika dilihat pada web untuk public, css, images, dan javascript maka,

![gambar](https://user-images.githubusercontent.com/55182321/99155657-74e16d00-26ec-11eb-932a-678bb9d01bd9.png)
![gambar](https://user-images.githubusercontent.com/55182321/99155662-84f94c80-26ec-11eb-98fd-c17d8ec9f35e.png)
![gambar](https://user-images.githubusercontent.com/55182321/99155665-90e50e80-26ec-11eb-9819-aec8fd03e135.png)
![gambar](https://user-images.githubusercontent.com/55182321/99155672-9b070d00-26ec-11eb-9b76-6b9fbbeb483d.png)


## 12. Merubah error page 404 

Untuk merubah, pindah ke /var/www/penanjakan.semerut04.pw lalu membuat .htaccess 

![gambar](https://user-images.githubusercontent.com/55182321/99154508-e1f00500-26e2-11eb-8382-05daa50ff7f5.png)

## 13. membuat mod alias dari /javascript menjadi /js

![gambar](https://user-images.githubusercontent.com/55182321/99154427-4bbbdf00-26e2-11eb-8aa5-75536ac72b7e.png)

menambahkan alias di bawah direktory listing

## 14. Membuat web naik.gunung.semerut04.pw

Membuat naik.gunung.semerut04.pw di site available

![gambar](https://user-images.githubusercontent.com/55182321/99154828-63489700-26e5-11eb-83b7-b116ba30b4ab.png)

menambahkan listen 8888 di port.cof pada apache2

![gambar](https://user-images.githubusercontent.com/55182321/99154939-3fd21c00-26e6-11eb-9cdf-78665b9c8e20.png)

## 15. membuat password 

Mengguakan command `htpasswd -c /etc/apache2/.htpasswd semeru` dan mengisi passwordnya dengan kuynaikgunung. 

![gambar](https://user-images.githubusercontent.com/55182321/99155201-5f6a4400-26e8-11eb-8bee-6b71c166daf7.png)

Merubah di site-available seperti pada gambar di atas

![gambar](https://user-images.githubusercontent.com/55182321/99155327-7493a280-26e9-11eb-8cde-715c4b47762c.png)

![gambar](https://user-images.githubusercontent.com/55182321/99155342-9bea6f80-26e9-11eb-9a9b-ec9a7e050a16.png)


Akan keluar seperti di atas

jika ingin melihat user apa saja serta menampilkan hasil hash nya yang sudah terdaftar menggunakan command `cat /etc/apache2/.htpasswd`

![gambar](https://user-images.githubusercontent.com/55182321/99155380-026f8d80-26ea-11eb-8b1c-c1317317b9e8.png)

## 16. Membuat jika kita mengetikan IP probolinggo akan ke redirect semerut04.pw

Menambahkan `Redirect / http://semerut04.pw`  file default pada site available 

![gambar](https://user-images.githubusercontent.com/55182321/99155479-d1dc2380-26ea-11eb-8e26-d2c0088e0586.png)


## 17. pada /var/www/penanjakan.semeruto4.pw/public/images yang memiliki substring “semeru” akan diarahkan menuju semeru.jpg.

Membuat file .htaccess pada /var/www/penanjakan.semerut04.pw dengan isi

![gambar](https://user-images.githubusercontent.com/55182321/99155559-91c97080-26eb-11eb-9f58-360b6079185f.png)

Jika di cek di web dengan mengakses 123semeru123.jpg, bukansemeruaja.jpg dan mahameru.jpg akan keluar seperti gambar dibawah 

![gambar](https://user-images.githubusercontent.com/55182321/99155591-e53bbe80-26eb-11eb-810b-7299c1efae8f.png)
![gambar](https://user-images.githubusercontent.com/55182321/99155601-f5ec3480-26eb-11eb-8cf1-6b6df8db1865.png)
![gambar](https://user-images.githubusercontent.com/55182321/99155615-0c928b80-26ec-11eb-8cf0-5e884173d088.png)
