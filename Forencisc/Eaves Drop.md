# DESKRIPSI

Download this packet capture and find the flag.
Download packet capture

# SOLUSI

Pertama kita download file terlebih dahulu, jika sudah kita dapat mengecek file tersebut dengan format apa ```file capture.flag.pcap``` dan ternyata termasuk dalamm file pcap, pcap identik menggunakan tools wireshark

Sebelum itu file pcap di ekstrak dan diubah agar bisa di baca oleh manusia menggunakan command ```strings capture.flag.pcap```
```
openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
```
mungkin ini sebuah petunjuk, kita coba nanti
```
Could you transfer the file to me again?
```
Seperti kita harus mentransfer nya?
```
Oh great. Ok, over 9002?
```
Ada apa dengan port 9002? mari kita coba cek pada wireshark, ```File >> Open >> capture.flag.pcap```

Pada paket, kita cari dengan port ___9002___, dan kita menemukannya lalu ```klik kanan >> follow >> tcp stream```
```
Salted__...<.P...O.r..E~cbk.......p&.}.......
.F
```
Kita mempunyai petunjuk bahwa ___openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123___ dan ___Could you transfer the file to me again?___ 

Bagaimana jika kita coba save filenya dengan nama ___file.des3___ dan menggunakan command tsb ```openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123```
```
Can't open "file.des3" for reading, No such file or directory
40F75952397F0000:error:80000002:system library:BIO_new_file:No such file or directory:../crypto/bio/bss_file.c:67:calling fopen(file.des3, rb)
40F75952397F0000:error:10000080:BIO routines:BIO_new_file:no such file:../crypto/bio/bss_file.c:75:
```
Sepertinya file tidak terbaca, bagaimana jika command tidak bisa membaca ASCII , melainkan biner, karena enkripsi data bisa melihat biner data
```openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123```
```
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
```
Kita coba cek folder yang kita tempat i saat ini ```ls``` dan menemukan file ```file.txt``` langsung saja kita baca ```cat file.txt``` dan mendapatkan flag ```picoCTF{nc_73115_411_5786acc3}```
