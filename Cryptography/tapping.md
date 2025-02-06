# DESKRIPSI

Theres tapping coming in from the wires. What's it saying nc jupiter.challenges.picoctf.org 9422

# SOLUSI

Pertama kita masukkan netcat pada soal tsb ```nc jupiter.challenges.picoctf.org 9422``` dan kita mendapatkan sebuah kode yang dimana kita harus decode untuk menjadikan flag yang dapat dibaca
```
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }
```
Pada kode diatas kita dapat melihatnya seperti sandi morse, kenapa? karena sandi morse memiliki sebuah titik 1 ketukan dan 2 ketukan, sama seperti flag kode diatas juga seperti itu, jadi kita coba decode sandi morse menggunakan website ```morse decode``` lalu kita buka web nya dan salin kode tsb pada kolom tabel dan enter untuk mengeluarkan outputnya sebagai text dan mendapatkan flag : ```PICOCTF{M0RS3C0D31SFUN268382...}```
