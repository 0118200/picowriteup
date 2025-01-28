# DESKRIPSI 

This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...
Download the image here

# SOLUSI

Pada msb ini kita di suruh menginvestigasi gambar untuk mendapatkan flag

Pertama kita download tools menggunakan ___stegsolve___ dengan command :
```
wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
chmod +x stegsolve.jar
```
Lalu kita dapat membuka tools tersebut atau kita bisa menggunakan perintah ```java -jar stegsolve```
Open file pada tools tersebut dan kita mencoba untuk mengekstrak

Sebelum mengekstrak kita mengganti ___Bit Order___ menjadi ___First MSB___, Menggunakan ___Row___ untuk metode ___Extract By___,Lalu kita coba analisis berbagai warna rgb (red green blue)

Dan kita mendapatkan petunjuk pada ___Red 7, Green 7, Blue 7___ bahwa ada flag pada text tersebut diatass

Lalu kita save text dengan nama file ___Text___

Untuk membacanya kita dapat dengan perintah ```cat Text | grep pico```

Mendapatkan output : ```220a7069636f4354 467b31355f793075  ".picoCT F{15_y0u```
Untuk mendapatkan isi full dari flag kita menggunakan perintah ```strings Text | less```

Dan mendapatkan output berbagai macam text dan menemukan flag : ```picoCTF{15_y0ur_que57...d55bee}```
