# DESKRIPSI

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
ssh -p 59092 ctf-player@rhea.picoctf.net
Using the password 6dd28e9b. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
Checksum: 03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8
To decrypt the file once you've verified the hash, run ./decrypt.sh files/<file>.

# SOLUSI

Pertama ketik ssh berikut pada terminal anda **ssh -p 55959 ctf-player@rhea.picoctf.net**, lalu kita masukan password **6dd28e9b** dan ketik **yes** untuk setuju.
Untuk mengecek file yang saat kita berada ketik **ls** dan dapat melihat : **checksum.txt  decrypt.sh  files**. Jika kita membuka **cat checksum.txt** akan keluar **03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8** ialah hash

nb: hash adalah sebuah kriptografi yang mengubah input data (text) menjadi nilai tetap yang tidak bisa berubah kembali seperti semula.

Di direktori files terdapat 301 file, 8 kode acak yang terdiri dari 8 karakter dan masing masing berbeda. Lalu yang terakhir ada decrypt.sh ialah script untuk mendeskripsikan data yang telah di enkripsi tergantung dari bagaimana penggunaan algoritmanya.

**sha256sum** ialah untuk menghasilkan hash dari file maupun text, dan kita memiliki file yang harus di selesaikan dengan sha256sum. Dan kita menggunakan perintah __sha256sum files/*__ untuk mendapatkan checksum dari semua direktori. Namun kita akan memasangkan dengan **grep** untuk menemukan hasil yang lebih tepat dan akurat

perintah : __sha256sum files/* | grep 03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8__
output : __03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8  files/00011a60__

Lalu kita akan me decrypt file yang sudah di verifikasi oleh hash dengan menjalankan : **./decrypt.sh files/00011a60**
Dan kita akan mendapatkan flagnya **picoCTF{trust_but_..._...}**
