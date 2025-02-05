# DESKRIPSI

I found this cipher in an old book. Can you figure out what it says? Connect with nc jupiter.challenges.picoctf.org 32411.

# SOLUSI

Pertama kita buka terlebih dahulu netcatnya ``` nc jupiter.challenges.picoctf.org 32411```
```
Encrypted message:
Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo 

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3x7g996649}

Ehk ktryy herq-ooizxetypd jjdcxnatoty ol f aordllvmlbkytc inahkw socjgex, bls sfoe gwzuti 1467 my Rjzn Hfetoxea Gqmexyt.

Tnj Gimjyèrk Htpnjc iy ysexjqoxj dosjeisjd cgqwej yse Gqmexyt Doxn ox Fwbkwei Inahkw.

Tn 1508, Ptsatsps Zwttnjxiax tnbjytki ehk xz-cgqwej ylbaql rkhea (g rltxni ol xsilypd gqahggpty) ysaz bzuri wazjc bk f nroytcgq nosuznkse ol yse Bnretèwp Cousex.

Gplrfdo’y xpcuso butvlky lpvjlrki tn 1555 gx l cuseitzltoty ol yse lncsz. Yse rthex mllbjd ol yse gqahggpty fce tth snnqtki cemzwaxqj, bay ehk fwpnfmezx lnj yse osoed qptzjcs gwp mocpd hd xegsd ol f xnkrznoh vee usrgxp, wnnnh ify bk itfljcety hizm paim noxwpsvtydkse.
```
Mengeluarkan output seperti di atas, sebelumnya kita baca petunjuk pada soal nya ___I found this cipher in an old book___ apakah ini termmasuk dari jenis chiper buku? 

Coba kita lihat judulnya ___la cifra de___, la cifra de memiliki beberapa sejarah pada chipper seperti ___chaesar, viginere, dll___

Jika kode kali ini berasal dari chipper kita coba buka ```https://www.dcode.fr/cipher-identifier?__r=1.c727313ae9727d463292f4e489ae0eb2``` atau bisa di buka pada chrome, tullis saja chiper identify

Lalu salin text tsb pada kolom yang tersedia untuk text decode, Jika sudah akan mengeluarkan jenis chipper pada kolom di kiri dan terdapat identifikasi hasil dari text cippernya, membuktikan bahwa viginere chipper teridentifikasi

Kita tekan saja viginere nya lalu paste lagi text nya pada kolom text viginere dan akan mengeluarkan output flagnya : ```picoCTF{b311a50_0r_v1gn3r3_...}```
