# DESKRIPSI

I wrote you a song. Put it in the picoCTF{} flag format

# SOLUSI

Pertama unduh file lagu tersebut pada perintah ```wget https://jupiter.challenges.picoctf.org/static/c0863a3b0170d6dd176be3a595b4b75e/lyrics.txt```
baca file text tersebut dengan ```cat lyrics.txt``` 

berikut ialah lirik lagu terdapat ctf yang tersembunyi

```
Pico's a CTFFFFFFF
my mind is waitin
It's waitin

Put my mind of Pico into This
my flag is not found
put This into my flag
put my flag into Pico


shout Pico
shout Pico
shout Pico

My song's something
put Pico into This

Knock This down, down, down
put This into CTF

shout CTF
my lyric is nothing
Put This without my song into my lyric
Knock my lyric down, down, down

shout my lyric

Put my lyric into This
Put my song with This into my lyric
Knock my lyric down

shout my lyric

Build my lyric up, up ,up

shout my lyric
shout Pico
shout It

Pico CTF is fun
security is important
Fun is fun
Put security with fun into Pico CTF
Build Fun up
shout fun times Pico CTF
put fun times Pico CTF into my song

build it up

shout it
shout it

build it up, up
shout it
shout Pico
```
Pada hint terdapat clue ```Do you think you can master rockstar?``` apakah kita bisa master rockstar
Sebelum itu kita akan cari terlebih dahulu ```master rockstar``` itu apa 

Untuk informasi lebih lanjut tentang Rockstar, kunjungi [Rockstar Programming Language](https://codewithrockstar.com).

Ternyata master rockstar ialah suatu bahasa pemrograman yang dibuat agar menyerupai sebuah lagu ataupun puisi, pada website ```master rockstar``` kita dapat menyalin lagu picoctf ke dalam programnya dan run/rock untuk mengeluarkan outputnya

Outputnya berupa kode ASCII : 
```
114
114
114
111
99
107
110
114
110
48
49
49
51
114
```
Untuk mengubah kode ASCII menjadi semula dapat menjalankan perintah seperti ini :

```python3 -c "ascii = [ 114, 114, 114, 111, 99, 107, 110, 114, 110, 48, 49, 49, 51, 114]; print(''.join(chr(i)for i in ascii))"```
(kode untuk mengubah ASCII angka)

dan telah diubah menjadi : 

```rrrocknrn0113r```

flag : ```picoCTF{rrrocknrn0113r}```
