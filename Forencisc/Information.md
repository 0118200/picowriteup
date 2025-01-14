# DESKRIPSI

Files can always be changed in a secret way. Can you find the flag? cat.jpg

# SOLUSI 

Pertama download file dengan menjalankan perintah ```wget https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg```, dapat di lihak bahwa file ialah jpg (gambar).
Untuk memvalidasi bahwa file tersebut termasuk ke dalam file foto, maka dapat menggunakan perintah dari hexdump, binwalk, file.

Tentunya flag berada tersembunyi dalam gambar tersebut untuk mengetahuinya kita menjalankan perintah ```file cat.jpg``` untuk melihat petunjuk dari gambar tersebut.

Untuk menampilkan hexadesimal dari file atau data biner beserta versi textnya (jika ada) menggunakan perintah ```hexdump -C cat.jpg```

Lalu yang terakhir ialah ```binwalk cat.jpg``` untuk menganalisis dan mengekstrak data tersembunyi dari gambar

Setelah memvalidasi bahwa file tersebut termasuk ke dalam format gambar, kita menjalankan perintah ```gimp cat.jpg``` untuk mencari metadata 
