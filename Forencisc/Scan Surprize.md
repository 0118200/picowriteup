# DESKRIPSI 

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
challenge.zip
The same files are accessible via SSH here:
ssh -p 56398 ctf-player@atlas.picoctf.net
Using the password f3b61b38. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!

# SOLUSI 

Pertama masukkan ```ssh -p 56398 ctf-player@atlas.picoctf.net``` dan masukan password ```f3b61b38``` dan ketik ```yes``` untuk mengakses ssh dan dapat menampilkan qr code, di dalam qr code tersebut kita dapat melihat flag

Untuk membaca qrcode kita dapat menggunakan zbar-tools, kita menginstall dengan cara : ```sudo apt install zbar-tools```, lalu jangan lupa simpan qrcode tersebut.
gunakan perintah : ```zbarimg namaimg.png``` untuk menampilkan hasil dari qrcode tersebut dan mendapatkan flag ```picoCTF{p33k_@_..._...}```
