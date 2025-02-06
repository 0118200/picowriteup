# DESKRIPSI

We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with nc jupiter.challenges.picoctf.org 43522

# SOLUSI

pertama kita masukan netcat terlebih dahulu, ```nc jupiter.challenges.picoctf.org 43522```

Lalu kita diberikan sebuah kode yang seperti kode chipper, kita coba decode menggunakan ```https://www.quipqiup.com/```

Kita masukan kode yang ingin di decode 
```
-------------------------------------------------------------------------------
slvbupew tyuy hw aliu dfpb - duykiyvsa_hw_s_loyu_fpmzjp_lbdmpivupd
-------------------------------------------------------------------------------
ny nyuy vle mist mluy etpv p kipueyu ld pv tliu lie ld liu wthg ehff ny wpn tyu whvx, pvj etyv h ivjyuwellj dlu ety dhuwe ehmy ntpe npw mypve za p wthg dlivjyuhvb hv ety wyp.  h miwe psxvlnfyjby h tpj tpujfa yayw el fllx ig ntyv ety wypmyv elfj my wty npw whvxhvb; dlu dulm ety mlmyve etpe etya upetyu gie my hvel ety zlpe etpv etpe h mhbte zy wphj el bl hv, ma typue npw, pw he nyuy, jypj nhethv my, gpuefa nhet duhbte, gpuefa nhet tluulu ld mhvj, pvj ety etlibtew ld ntpe npw aye zydluy my.

```
Dan mendapatkan flag : ```frequency_is_c_over_lambda_ogfmaunraf```

Jika kita memasukan flag dengan format flag seperti picoCTF{XXXX} maka flag akan ditolak, kenapa? karena pada clue/hint terdapat tulisan bahwa flagnya tidak akan memakai format flag melainkan text biasa/ flag biasa tanpa format
