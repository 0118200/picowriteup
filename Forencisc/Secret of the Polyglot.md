# DESKRIPSI

The Network Operations Center (NOC) of your local institution picked up a
suspicious file, they're getting conflicting information on what type of file it is.
They've brought you in as an external expert to examine the file. Can you
extract all the information from this strange file?
Download the suspicious file here.

# SOLUSI 

Pertama install ```poppler-utils``` adalah kumpulan alat perintah untuk bekerja dengan dokumen PDF dengan perintah : ```sudo apt install poppler-utils```. Setelah terinstall kita menjalankan perintah ```pdftotext flag2of2-final.pdf
``` untuk mengubah pdf menjadi text agar bisa dibaca menggunakan perintah ```cat```.

Setelah itu kita menjalankan perintah : ```cat flag2of2-final.txt``` dan mendapatkan output : ```1n_pn9_&_..._...}```, namun sepertinya flag tersebut ialah terpisah dan kita harus mendapatkan flag 1 nya untuk menggabungkan menjadi flag yang utuh.
Jika kita menjalankan perintah ```cat flag2of2-final.pdf``` ialah berisi dari file png (gambar), atau kita dapat menjalankan dengan perintah ```file flag2of2-final.pdf``` dan terdapat file png (gambar) didalam pdf tersebut.

Lalu untuk membaca file png tersebut kita harus mengubah file pdf menjadi file png dengan perintah : ```mv flag2of2-final.pdf flag2of2-final.png``` dan file berubah menjadi png (gambar) namun kita membutuhkan png tersebut menjadi text dengan cara install gocr : ```sudo apt install gocr```

nb : GOCR adalah sebuah program perangkat lunak untuk optical character recognition (OCR), yang berfungsi untuk mengubah teks yang ada dalam gambar (misalnya gambar hasil scan atau foto teks) menjadi teks yang dapat diedit.

Setelah itu kita menjalankan perintah : ```gocr flag2of2-final.png | tr -d "\n"``` untuk membaca png tersebut menjadi text. Perintah ```tr -d "\n"``` digunakan untuk menghapus karakter newline

Dan kita telah berhasil mendapatkan flag : ```piconF{f1u3n7_``` namun kita harus menggabungkan kedua part menjadi satu untuk menjadikan flag yang utuh ```piconF{f1u3n7_1n_pn9_&_..._...}```
