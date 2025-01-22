# DESKRIPSI

If you can find the flag on this disk image, we can close the case for good!
Download the disk image here.

# SOLUSI

PCAP (Packet Capture) adalah format file yang digunakan untuk menyimpan data jaringan yang ditangkap dari aktivitas lalu lintas jaringan
Jadi saya menggunakan whiresark untuk menganalisis jaringan

Pertama buka file pcap pada whiresark, pilih ```Packet Bytes``` untuk melihat data mentah dari pcap tsb,
dan saya memilih ```narrow & wide```, dapat memilih salah satunya jika ```narrow``` untuk fokus pada data tertentu (mempersempit), namun untuk ```wwide``` menunjukkan data dalam cangkupan luas,
dan memilih mode ```string``` untuk mencari flag dalam beberapa paket seperti frame data, packet bytes, protokol tertentu

lalu untuk yang terakhir menjalankan perintah 
```
strings trace.pcap | grep "pico"
```
mendapatkan flag 
```
picoCTF{P64P_4N4L7S1S_SU55355FUL_...}
```

# PENJELASAN

```strings``` untuk mengekstrak semua data menjadi text yang bisa dibaca

```trace.pcap``` file flag

```|``` (pipe) untuk memindahkan output strings kepada grep 

```grep "pico"``` untuk mencari teks pada output strings
