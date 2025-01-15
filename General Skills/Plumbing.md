# DESKRIPSI

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to jupiter.challenges.picoctf.org 4427.

# SOLUSI 

Awal kita memasukan ```nc jupiter.challenges.picoctf.org 4427``` dan menghasilkan text yang sangat banyak, tak mungkin jika kita melihat satu persatu untuk mencari flag

Jika output terlalu susah untuk di dapatkan atau di sembunyikan, maka kita hanya tinggal memindahkan outputnya kedalam file lain
dan file tersebut kita juga akan membuat baru untuk menyimpan outputnnya

```nc jupiter.challenges.picoctf.org 4427 > output.txt```

Setelah output tersimpan pada file, kita hanya tinggal mencari menggunakan perintah 

```grep -E "picoCTF" output.txt```

dan mendapatkan flag ```picoCTF{digital_plumb3r_...}```
