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
Terdapat list dari 
