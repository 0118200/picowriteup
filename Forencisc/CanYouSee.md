# DESKRIPSI

How about some hide and seek?
Download this file here.

# SOLUSI 
Kita diberi file dengan zip, untuk membuka kita harus unzip terlebih dahulu dengan perintah ```unzip unknown.zip``` dan kita mendapatkan file ```ukn_reality_jpg``` untuk membuka gambar tersebut kita dapat menggunakan perintah ```gimp```

Jika kita belum memiliki alat tersebut dapat mengnstall dengan cara ```sudo apt install gimp``` dan untuk membuka gambar tersebut dengan ```gimp ukn_reality.jpg```

Untuk melihat yang tersembunyi pada gambar kita dapat menggunakan ```gimp```. Dan pada kasus ini kita akan melihat ```metadata``` dari gambar tersebut dengan melihat toolbar dan tekan ```image``` lalu tekan ```metadata``` >> ```view metadata``` >> ```xmp``` dan kita dapat melihat bahwa ada code dengan base64 ```cGljb0NURntNRTcORDQ3QV9ISUREM05fNGRhYmRkY2J9Cg==``` 

Tugas terakhir kita me decode base64 tersebut dengan cara menggunakan website ```https://www.base64decode.org/``` dan memasukan base64 sebagai input dan mendapatkan flag 
```picoCTF{ME74D47A_..._...}```

Atau juga dapat menjalankan perintah ```echo cGljb0NURntNRTcORDQ3QV9ISUREM05fNGRhYmRkY2J9Cg== | base64 -d```

nb: base64 merupakan metode encoding yang digunakan untuk merepresentasikan data biner kedalam ASCII 
