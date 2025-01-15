# DESKRIPSI

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with nc jupiter.challenges.picoctf.org 29221.

# SOLUSI

Pertama buka terminal dan masukan perintah ```nc jupiter.challenges.picoctf.org 29221``` untuk mengakses netcat

Dan mendapatkan soal seperti :
```
Let us see how data is stored
computer
Please give the 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010 as a word.
```
Untuk mengubah biner >> text anda bisa menggunakan website : ```https://www.rapidtables.com/convert/number/binary-to-ascii.html```

Dan mendapatkan soal seperti :
```
Please give me the  160 151 145 as a word.
Input:
```
Untuk mengubah desimal >> text dapat menggunakan website : ```https://www.ascii-code.com/``` (cari pada tabel ASCII printable char)

Dan mendapatkan soal terakhir seperti :
```
Please give me the 6e75727365 as a word.
Input:
```
Untuk mengubah hex >> text anda bisa menggunakan website : ```https://www.duplichecker.com/hex-to-text.php```

Dan flag telah muncul : ```picoCTF{learning_about_converting_values_...}```
