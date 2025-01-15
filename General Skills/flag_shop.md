# DESKRIPSI

There's a flag shop selling stuff, can you buy a flag? Source. Connect with nc jupiter.challenges.picoctf.org 4906.

#  SOLUSI

Buka program dari source nya untuk melihat bagaimana cara kerja dari program tersebut
Pada program tersebut memiliki 3 opsi, opsi 1 untuk melihat uang kita, opsi 2 untuk membeli flag, dan opsi ke 3 untuk keluar dari program

Jika kita ingin membeli flag yang asli, diharuskan mempunyai uang senilai ```100000``` dolar, namun uang yabg kita punya hanya 1100

Jadi kita akan melihat dari flag palsu :
```
int number_flags = 0;
                fflush(stdin);
                scanf("%d", &number_flags);
                if(number_flags > 0){
                    int total_cost = 0;
                    total_cost = 900*number_flags;
                    printf("\nThe final cost is: %d\n", total_cost);
                    if(total_cost <= account_balance){
                        account_balance = account_balance - total_cost;
                        printf("\nYour current balance after transaction: %d\n\n", account_balance);
                    }
                    else{
                        printf("Not enough funds to complete purchase\n");
                    }
```

Kita dapat melihat bahwa harga dari fake flag senilai ```900``` dolar, uang kita cukup untuk membeli itu, Namun bagaimana cara kita cukup mempunyai uang untuk membeli flag asli?

Pertama kita memasukan opsi 1 untuk membeli flag palsu 
```
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
```
Kita di suruh memasukan jumlah yang diinginkan, kita coba memasukan jumlah melewati dari ```2147483647``` (max bit int) 
```
These knockoff Flags cost 900 each, enter desired quantity
2147483468

The final cost is: -162000

Your current balance after transaction: 163100
```
Kenapa bisa gitu? 
> Pada ```total_cost``` di deklarasi bahwa itu adalah integer, dan int memiliki nilai antara ```-2147483647 hingga 2147483647```
  Signed integer memiliki ciri jika biner di bit awal bernilai `0` maka bilangan tersebut positif (+) sedangkan jika bernilai ` maka bilangan tersebut termasuk (-)

> Jadi kita akan mencoba menggunakan negatif untuk input tersebut dengan cara :
  Menambahkan nilai 1 ataupun lebih dari ```2147483647``` untuk menjadikannya negatif

Kenapa positif bisa menjadi negatif?
> Karena tipe 32 bit, biner dari 2147483647 (max) ialah :
```
0111 1111 1111 1111 1111 1111 1111 1111
```
> bit awal bernilai 0 yang menandakan bahwa bilangan tersebut ialah positif

> Jika kita menambahkan 1 menjadi :
```
1000 0000 0000 0000 0000 0000 0000 0000
```
> Bit awal bernilai 1 yang menandakan bahwa bilangan tersebut ialah negatif dan bernilai -2147483647

Dan setelah itu kita memiliki uang melebihi dari yang sebelumnya, dan kita dapat membeli flag yang asli dan mendapatkan flag :
```
picoCTF{m0n3y_bag5_...}
```
