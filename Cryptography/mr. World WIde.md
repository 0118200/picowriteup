# DESKRIPSI

A musician left us a message. What's it mean?

# SOLUSI

Kita di suruh membaca message tersebut, ```cat message.txt``` dan mendapatkan sebuah flag yang masih menjadi code 
```
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}
```
Dapat di lihat bahwa flag tsb tidak dapat dibaca melainkan seperti koordinat, coba kita buka 1 per 1 dari koordinat tsb , 
```
(35.028309, 135.753082) - Kyoto, Jepang
(46.469391, 30.740883) - Odessa, Ukraina
(39.758949, -84.191605) - Dayton, Ohio, AS
(41.015137, 28.979530) - Istanbul, Turki
(24.466667, 54.366669) - Abu Dhabi, UEA
(3.140853, 101.693207) - Kuala Lumpur, Malaysia
_
(9.005401, 38.763611) - Addis Ababa, Ethiopia
(-3.989038, -79.203560) - Loja, Ekuador
(52.377956, 4.897070) - Amsterdam, Belanda
(41.085651, -73.858467) - Sleepy Hollow, New York, AS
(57.790001, -152.407227) - Kodiak, Alaska, AS
(31.205753, 29.924526) - Alexandria, Mesir
```
Bagaimana jika kita melihat huruf awal di setiap nama tempat tsb : KODIAK_ALASKA , dan ternyata benar flag : picoCTF{KODIAK_ALASKA}
