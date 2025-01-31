# DESKRIPSI

Can you find the flag? shark1.pcapng.

# SOLUSI

Kita download filenya, lalu kita buka file pcapng menggunakan wireshark.
pcapng dapat menggunakan tcp jadi kita coba untuk memilih paket yang dengan tcp ```klik kanan >> follow >> tcp``` dan pada pojok kanan bawah terdapat stream pada follow tcp

Kita ubah hingga menemukan flagnya, dan pada stream 5 kita menemukan sesuatu seperti flag namun telah di encode, tugas kita sekarang adalah mendecode text tersebut menggunakan chiper decode dan menemukan hasil bahwa decode tersebut berasal dari ROT13
```
cvpbPGS{c33xno00_1_f33_h_qrnqorrs}
```
sebelum decode
```
picoCTF{p33kab00_1_s33_u_...}
```
setelah decode
