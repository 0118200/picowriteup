# DESKRIPSI 

Cryptography can be easy, do you know what ROT13 is? cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}

# SOLUSI 

Pertama kita salin terlebih dahulu kode yang mirip seperti flag namun terasa acak, ```cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}``` kode tersebut memiliki pola seperti flag, namun terdapat karakter yang teracak, meskipun karakter teracak pola masih bisa di lihat bahwa itu ialah flag

Dengan itu, metode seperti ini sering kali encode menggunakan ```caesar chipper``` untuk decode kita akan menggunakan perintah 

```echo "cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}" | tr 'A-Za-z' 'N-ZA-Mn-za-m'```

Dan mendapatkan flag ```picoCTF{next_time_I'll_try_2_rounds_of_..._...}```

Atau bisa juga kita menggunakan ```website multiple decode``` untuk lebih mempermudah
