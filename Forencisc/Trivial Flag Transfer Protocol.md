# DESKRIPSI

Figure out how they moved the flag.

# SOLUSI

Pertama kita download file terlebih dahulu dan kita mendapatkan file ___tftp.pcapng___
___Tftp___ adalah sebuah metode untuk mentransfer file dari klien ke server atau sebaliknya
___Pcapng___ adalah format file yang digunakan untuk merekam jaringan ( versi lebih baik dari pcap )

Kita akan mengetahui terlebih dahulu file seperti apa ```file tftp.pcapng```  dan kita mengetahui bahwa ialah file pcapng, yang dimana pcapng versi yang di ciptakan untuk mengatasi kekurangan dari pcap

Kita buka wireshark untuk mengetahui transfer yang telah berjalan. ```File >> Open >> tftp.pcapng``` dan kita bisa melihat bahwa terdapat beberapa paket.

TFTP adalah metode transfer file sederhana yang tanpa menggunakan autentikasi dan menggunakan UDP. Untuk memfilter tftp menggunakan perintah ```tftp.type``` yang mengeluarkan beberapa paket yang hanya bertipe tftp.

Terdapat beberapa source file seperti ___instructions.txt, plan, program.deb, picture1-3.bmp___ yang akan membantu kita menemukan file flag

Untuk menyimpan kita dapat mengikuti ```File >> Export Object >> TFTP >> Save All >> Ok/Open (lalu simpan pada folder yang diinginkan ``` memilih tftp karena sesuai dengan format/filenya

Kita membuka folder yang telah kita export object tftp, kita baca file instructions nya ```cat instructions.txt``` mendapatkan text yang telah di encode, kita akan decode menggunakan ___CacheSleuth https://www.cachesleuth.com/multidecoder/ ( website )___
Lalu tempel text yang telah di salin untuk di decode:
```
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA
```
dan mendapatkan hasil ( asal dari ROT13 ) :
```
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
```
Menunjukkan bahwa kita harus mencari file tersembunyi melalui yang lain ( plan )
Kita baca file plan dan mendapatkan 
```
VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF
```
decode kembali seperti cara di awal menggunakan website dan mendapatkan hasil ( asal dari ROT13) :
```
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
```
Menunjukkan bahwa kita harus mencari file tersembunyi melalui yang lain ( foto )
Foto yang mempunyai format ___.bmp___ menunjukkan ialah file bitmap seperti gambar dapat dibuka dengan perintah ```eog picture1.bmp```

Namun dari foto 1-3 tidak menunjukkan hasil apapun dan saya membaca ulang hasil decode dari plan ialah memberi clue/petunjuk tentang ___program.deb___ kita coba saja install dengan perintah ```sudo apt-get install ./program.deb```

Dan kita menemukan petunjuk ```Note, selecting 'steghide' instead of './program.deb'```

Kita akan mencoba menggunakan steghide, jika belum mengetahui tentang steghide kita akan membuka websitenya steghide. Steghide sendiri dapat menyelesaikan file bmp ( bitmap )

Dengan perintah : 
```
steghide extract -sf <filename> -p <password>
```
steghide : tools
extract : mengekstrak 
-sf : stegofile ( menentukan file sumber data yg tersembunyi )
<file name> : nama file
-p : untuk password
<password> : password file
```
steghide extract -sf ./picture1.bmp -p “DUEDILIGENCE”
```
Pada saat kita membaca hasil decode dari file plan terdapat clue ___DUEDILIGENCE___ kita coba saja pakai menjadi pw

Mendapatkan output 
```
steghide: could not extract any data with that passphrase!
```
kita coba picture 2 dan 3
```
steghide extract -sf ./picture2.bmp -p “DUEDILIGENCE”
```
dan tetap sama 
```
steghide extract -sf ./picture3.bmp -p “DUEDILIGENCE”
```
mendapatkan file flag.txt dan kita baca mendapatkan flag : ```picoCTF{h1dd3n_1n_pLa1n_51GHT_...}```
