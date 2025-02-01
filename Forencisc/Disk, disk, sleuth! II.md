# DESKRIPSI

All we know is the file with the flag is named `down-at-the-bottom.txt`... Disk image: dds2-alpine.flag.img.gz

# SOLUSI

Pertama kita donwload file terlebih dahulu, setelah itu kita mencari tau file tersebut dengan format apa ```file dds2-alpine.flag.img.gz``` dan file tersebut berupa gunzip jadi kita akan gunzip utk mendapatkan file tanpa ekstrak
```gunzip dds2-alpine.flag.img.gz```

Lalu kita cari tahu file tersebut format apa ```file dds2-alpine.flag.img```, Setelah kita mengetahui bahwa itu adalah disk
Kita akan menggunakan command memeriksa partisi pada disk ```mmls dds2-alpine.flag.img```. mmls untuk menampilkan layout partisi pada disk img
```
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000262143   0000260096   Linux (0x83)
```
Pada linux (0x83) kita mengetahui pada offset dimulai dari 2048, kita coba cek partisi tsb ```fls -o 2048 dds2-alpine.flag.img```
___fls___ untuk membaca list dari partisi ___-o 2048___ dan pada file ___dds2-alpine.flag.img___
```
d/d 26417:	home
d/d 11:	lost+found
r/r 12:	.dockerenv
d/d 20321:	bin
d/d 4065:	boot
d/d 6097:	dev
d/d 2033:	etc
d/d 8129:	lib
d/d 14225:	media
d/d 16257:	mnt
d/d 18289:	opt
d/d 16258:	proc
d/d 18290:	root
d/d 16259:	run
d/d 18292:	sbin
d/d 12222:	srv
d/d 16260:	sys
d/d 18369:	tmp
d/d 12223:	usr
d/d 14229:	var
V/V 32513:	$OrphanFiles
```
Terdapat list dari partisi tersebut menemukan dir root, kita coba menggunakan perintah ```fls -o 2048 dds2-alpine.flag.img 18290```
sama fungsi command seperti sebelumnya, namun menambahkan sedikit perbedaan yaitu ___18290___ untuk membuka dir root
```
r/r 18291:	down-at-the-bottom.txt
```
Kita menemukan file yang ber ekstensi .txt dan dapat dibaca, umumnya membaca ssebuah text menggunakan ___cat___ namun berbeda dengan sleuth kit kita menggunakan ___icat___.
```icat -o 2048 dds2-alpine.flag.img 18291``` 

___icat___ untuk membaca dari offset ___-o 2048___ oleh disk ___dds2-alpine.flag.img___ dan kode dari dir root ___18291___
```
   _     _     _     _     _     _     _     _     _     _     _     _     _  
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \ 
 ( p ) ( i ) ( c ) ( o ) ( C ) ( T ) ( F ) ( { ) ( f ) ( 0 ) ( r ) ( 3 ) ( n )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/ 
   _     _     _     _     _     _     _     _     _     _     _     _     _  
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \ 
 ( s ) ( 1 ) ( c ) ( 4 ) ( t ) ( 0 ) ( r ) ( _ ) ( n ) ( 0 ) ( v ) ( 1 ) ( c )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/ 
   _     _     _     _     _     _     _     _     _     _     _  
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \ 
 ( 3 ) ( _ ) ( f ) ( f ) ( 2 ) ( 7 ) ( f ) ( 1 ) ( 3 ) ( 9 ) ( } )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/ 
```
Output pada diatas kita bisa menyusun menjadi flag yang utuh, namun dengan cara lain kita juga dapat menggunakan autopsy
