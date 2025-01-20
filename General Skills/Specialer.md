# DESKRIPSI

Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.
ssh -p 57485 ctf-player@saturn.picoctf.net. The password is d137d16e

# SOLUSI

Pertama kita masuk ke dalam ssh ```ssh -p 57485 ctf-player@saturn.picoctf.net``` dengan password ```d137d16e```

Lalu kita berada pada mode specialer$ , yang dimana mode ini berbeda dengan mode $special
Disini kita mencoba  menggunakan command ```echo "$(<filename)"``` untuk melihat dir/file

Langsung saja : 
```
Specialer$ pwd
/home/ctf-player
Specialer$ echo *
abra ala sim
Specialer$ echo */* 
abra/cadabra.txt abra/cadaniel.txt ala/kazam.txt ala/mode.txt sim/city.txt sim/salabim.txt
Specialer$ echo "$(</home/ctf-player/abra/cadabra.txt)"
Nothing up my sleeve!
Specialer$ echo "$(</home/ctf-player/abra/cadaniel.txt)"
Yes, I did it! I really did it! I'm a true wizard!
Specialer$ echo "$(</home/ctf-player/ala/kazam.txt)"
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_...}
```

# PENJELASAN 

```pwd``` untuk melihat dir kita saat ini

```echo *``` seperti ls, namun mencari semua file dan direktori yang ada di direktori kerja saat ini

```echo */*``` untuk mencetak semua file maupun dir

```echo "$(</home/ctf-player/ala/kazam.txt)"``` ```<``` (redirection file untuk mengarahkan isi input ke file dari perintah)

```/home/ctf-player/ala/kazam.txt``` (path file yang akan di baca)

```$()``` (command subtitution, shell menjalankan perintah pada dalam kurung)

```$(<filename)``` untuk membuka dan membaca, berbeda dengan ```cat``` yang hanya bisa membaca sebuah file

