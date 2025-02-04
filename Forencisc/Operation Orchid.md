# DESKRIPSI

Download this disk image and find the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download compressed disk image

# SOLUSI

Jadi kita akan mencari flag pada disk img, pertama install filenya,lalu cek termasuk file apakah tsb ```file disk.flag.img.gz``` dan merupakan file gz

Jadi akan kita gunzip terlebih dahulu agar dapat di cek ```gunzip disk.flag.img.gz``` 

Lalu kita coba buka disk nya ```mmls disk.flag.img```
```
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
```
Terdapat 3 partisi yang dapat kita cek ```fls -o 2048 disk.flag.img    ```
```
d/d 11:	lost+found
r/r 12:	ldlinux.sys
r/r 13:	ldlinux.c32
r/r 15:	config-virt
r/r 16:	vmlinuz-virt
r/r 17:	initramfs-virt
l/l 18:	boot
r/r 20:	libutil.c32
r/r 19:	extlinux.conf
r/r 21:	libcom32.c32
r/r 22:	mboot.c32
r/r 23:	menu.c32
r/r 14:	System.map-virt
r/r 24:	vesamenu.c32
V/V 25585:	$OrphanFiles
```
Tidak terdapat petunjuk sama sekali, kita coba partisi kedua juga sama dan waktu partisi ke 3
```fls -o 411648 disk.flag.img```
```d/d 460:	home
d/d 11:	lost+found
d/d 12:	boot
d/d 13:	etc
d/d 81:	proc
d/d 82:	dev
d/d 83:	tmp
d/d 84:	lib
d/d 87:	var
d/d 96:	usr
d/d 106:	bin
d/d 120:	sbin
d/d 466:	media
d/d 470:	mnt
d/d 471:	opt
d/d 472:	root
d/d 473:	run
d/d 475:	srv
d/d 476:	sys
d/d 2041:	swap
V/V 51001:	$OrphanFiles
```
Terdapat file root, kita coba buka ``` fls -o 411648 disk.flag.img 472```
```
r/r 1875:	.ash_history
r/r * 1876(realloc):	flag.txt
r/r 1782:	flag.txt.enc
```
Terdapat 3 file , terutama flag terdapat pada file ___flag.txt___
Kita coba cari flag.txt pada ```strings -t d disk.flag.img | grep flag.txt```
```
218985524 flag.txt
218985540 flag.txt.enc
219964416 touch flag.txt
219964431 nano flag.txt 
219964483 nano flag.txt 
219964506 openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
219964588 shred -u flag.txt
303193140 flag.txt
303317044 flag.txt
303317060 flag.txt.enc
303328308 flag.txt
303328324 flag.txt.enc
```
Terlihat seperti ada perintah untuk membuka flag enkripsi menggunakan password mari kita coba, namun kita kan ingin mencari password pada file ___flag.txt___, sedangkan pada perintahnya itu ingin menggunakan ___flag.txt.enc___ sebagai outputnya, bagaimana jika kita balik ___flag.txt___ sebagai outputnya

```openssl aes256 -d  -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567```
```
openssl aes256 -d  -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
408703AD787F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
```
coba kita baca file ___flag.txt___ ```cat flag.txt``` dan mendapatkan flag : ```picoCTF{h4un71ng_p457_}```
