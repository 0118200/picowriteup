# DESKRIPSI

Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: dds1-alpine.flag.img.gz

# SOLUSI

pertama kita download filenya dan kita cari tau menggunakan ekstesi/format apa yang ada di file nya ```file dds1-alpine.flag.img.gz```

Setelah kita tau bahwa filenya di gunzip, kita menggunakan ```gunzip dds1-alpine.flag.img.gz``` untuk mengatasi file tsb, lalu muncul file ___dds1-alpine.flag.img___

Lalu kita coba mencari filenya dengan 2 command saja, hanya dengan strings dan grep dan perpaduan antara keduanya menggunakan pipe 
```strings dds1-alpine.flag.img | grep picoCTF```

Dan mendapatkan output berupa flag 
```picoCTF{f0r3ns1c4t0r_n30phyt3_...}```
