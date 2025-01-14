# DESKRIPSI

Files can always be changed in a secret way. Can you find the flag? cat.jpg

# SOLUSI 

Pertama download file dengan menjalankan perintah ```wget https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg```, dapat di lihak bahwa file ialah jpg (gambar).
Untuk memvalidasi bahwa file tersebut termasuk ke dalam file foto, maka dapat menggunakan perintah dari hexdump, binwalk, file.

Tentunya flag berada tersembunyi dalam gambar tersebut untuk mengetahuinya kita menjalankan perintah ```file cat.jpg``` untuk melihat petunjuk dari gambar tersebut.

Untuk menampilkan hexadesimal dari file atau data biner beserta versi textnya (jika ada) menggunakan perintah ```hexdump -C cat.jpg```

Lalu yang terakhir ialah ```binwalk cat.jpg``` untuk menganalisis dan mengekstrak data tersembunyi dari gambar

Setelah memvalidasi bahwa file tersebut termasuk ke dalam format gambar, kita menjalankan perintah ```gimp cat.jpg``` untuk mencari metadata dengan melihat toolbar dan tekan ```image``` >> ```metadata``` >> ```view metadata``` >> ```xmp``` dan kita dapat melihat bahwa ada code dengan base64 ```cGljb0NURnt0aGvfbTN0YWrhdGFfMXNfbW9kaWZpZWR9```

base64 ialah encoding dari representasi biner menjadi text ASCII, dan untuk decoding kita dapat menjalankan perintah ```echo cGljb0NURnt0aGvfbTN0YWrhdGFfMXNfbW9kaWZpZWR9 | base64 -d``` dan mendapatkan flag 
