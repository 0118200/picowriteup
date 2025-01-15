# DESKRIPSI

Can you get the real meaning from this file.
Download the file here.

# SOLUSI 

pertama download file pada ```wget https://artifacts.picoctf.net/c_titan/2/enc_flag``` dan kita akan menginvestigasi file jenis apa yang berada pada file tersebut.
Untuk menginvestigasi kita menggunakan perintah ```file enc_flag``` dan menunjukkan bahwa file tersebut terdapat text ASCII di dalamnya, jadi kita coba membuka file tersebut dengan perintah ```cat enc_flag``` setelah file terbaca ```YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6YzRNalV3YUcxcWZRPT0nCg==``` 
dan memberikan kode ASCII namun terdapat ciri ciri bahwa kode tersebut termasuk dalam base64 encode

Untuk menyelesaikan encode kita perlu decode base64 tersebut untuk mendapatkan flag dengan perintah ```echo YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6YzRNalV3YUcxcWZRPT0nCg== | base64 -d``` dan memberikan kode yang telah di decode 
```b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ=='```
Namun masih saja menjadi base64, kita akan decode nya sekali lagi ```echo d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ== | base64 -d``` dan mendapatkan hasil
```wpjvJAM{jhlzhy_k3jy9wa3k_78250hmj}```

Untuk mengetahui kode tersebut termasuk kedalam jenis apa, kita bisa saja langsung decode menggunakan website multi solver input kode sebelumnya dan akan muncul hasil decode nya, dan kode telah di decode menjadi 
```picoCTF{caesar_d3cr9pt3d_...}```
Yang dimana kode tersebut terdapat pada ```caesar```
