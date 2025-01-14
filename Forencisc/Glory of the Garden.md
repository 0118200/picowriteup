# DESKRIPSI

This garden contains more than it seems.

# SOLUSI

Pada kasus ini kita diberikan fiie berupa foto yang terdapat flag tersembunyi di dalamnya. Kita akan memvalidasi terlebih dahulu apakah file tersebut memang foto dengan perintah ```file garden.jpg```
Setelah memvalidasi memang file tersebut ialah gambar

kita menjalankan perintah ```hexdump -C garden.jpg``` untuk menampilkan representasi hexadesimal dan text ASCII dari file gambar tersebut
atau dapat menggunakan perintah ```ghex garden.jpg``` dan flag ditemukan pada 

```70 69 63 6F 43 54 46 7B 6D 6F 72 65 5F 74 68 61 6E 5F 6D 33 33 74 73 5F 74 68 65 5F 33 79 33 33 64 64 32 65 45 46 35 7D```

ialah hexadesimal yang dapat diterjemahkan menjadi text ASCII ```picoCTF{more_than_m33ts_the_3y33dd2eEF5}```
