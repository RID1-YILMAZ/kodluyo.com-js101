- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "➕ Operatörler : Aritmetik"
- run = "node main.js"

- parts/0:
- text
# ➕ Aritmetik Operatörler : Toplama

Aritmetik operatörler sayılarla işlem yapmamızı sağlar. En temel olanı ``+`` işaretidir
ve iki sayıyı toplar. Değişkenleri de toplayabilir, sonucu metinle birlikte
yazdırabiliriz.

<code-view name="main.js" language="javascript">
let armut = 8;
let elma = 5;
console.log("Meyve sayısı:", armut + elma);
</code-view>

<code-view name="Terminal" language="bash">
Meyve sayısı: 13
</code-view>

# 🎯 1. Görev

``armut`` ve ``elma`` sayılarını toplayıp ``Meyve sayısı: 13`` yazdıran programı yazar
mısın?

- files/main.js/.block
// iki meyve sayısını toplar mısın?
let armut = 8;
let elma = 5;
console.log("Meyve sayısı:", armut <<< ❓ >>> elma);
---------------------
- tests/0/output
Meyve sayısı: 13

---------------------
- tests/1/files/main.js/.block
// iki meyve sayısını toplar mısın?
let armut = 12;
let elma = 3;
console.log("Meyve sayısı:", armut <<< ❓ >>> elma);
- tests/1/output
Meyve sayısı: 15

---------------------
- parts/1:
- text
# ➖ Çıkarma ve Negatif Sayılar

``-`` işareti iki sayıyı çıkarır. Sonuç sıfırdan küçükse **negatif** bir sayı elde ederiz
ve başında eksi işareti görünür. Bakiye hesapları bu operatörün klasik örneğidir.

<code-view name="main.js" language="javascript">
let bakiye = 45;
bakiye = bakiye - 80;
console.log("Bakiye:", bakiye);
</code-view>

<code-view name="Terminal" language="bash">
Bakiye: &minus;35
</code-view>

# 🎯 2. Görev

45 lira bakiyeden 80 lira harcayınca terminale ``Bakiye: -35`` yazdıran programı yazar
mısın?

- files/main.js/.block
// harcamayı bakiyeden düşer misin?
let bakiye = 45;
bakiye = bakiye <<< ❓ >>> 80;
console.log("Bakiye:", bakiye);
---------------------
- tests/0/output
Bakiye: &minus;35

---------------------
- tests/1/files/main.js/.block
// harcamayı bakiyeden düşer misin?
let bakiye = 100;
bakiye = bakiye <<< ❓ >>> 80;
console.log("Bakiye:", bakiye);
- tests/1/output
Bakiye: 20

---------------------
- parts/2:
- text
# ✖️ Çarpma

Sayıları çarpmak için ``*`` işaretini kullanırız. Matematikteki ``×`` işareti klavyede
yoktur; JavaScript'te yerini yıldız alır. Bir kutudaki kalem sayısı ile kutu sayısını
çarparak toplam kalemi buluruz.

<code-view name="main.js" language="javascript">
let kutu = 6;
let kalem = 12;
console.log(kutu * kalem, "kalem");
</code-view>

<code-view name="Terminal" language="bash">
72 kalem
</code-view>

# 🎯 3. Görev

6 kutunun her birinde 12 kalem varsa ``72 kalem`` yazdıran programı yazar mısın?

- files/main.js/.block
// kutu sayısı ile kalem sayısını çarpar mısın?
let kutu = 6;
let kalem = 12;
console.log(kutu <<< ❓ >>> kalem, "kalem");
---------------------
- tests/0/output
72 kalem

---------------------
- tests/1/files/main.js/.block
// kutu sayısı ile kalem sayısını çarpar mısın?
let kutu = 4;
let kalem = 9;
console.log(kutu <<< ❓ >>> kalem, "kalem");
- tests/1/output
36 kalem

---------------------
- parts/3:
- text
# ➗ Bölme

``/`` işareti bölme yapar. Sonuç tam sayı olmak zorunda değildir; 7 pastayı 2 kişiye
bölersek kişi başına ``3.5`` pasta düşer. JavaScript ondalık kısmı da yazar.

<code-view name="main.js" language="javascript">
let pasta = 7;
let kişi = 2;
console.log("Kişi başına", pasta / kişi, "pasta");
</code-view>

<code-view name="Terminal" language="bash">
Kişi başına 3.5 pasta
</code-view>

# 🎯 4. Görev

7 pastayı 2 kişiye eşit paylaştırıp ``Kişi başına 3.5 pasta`` yazdıran programı yazar
mısın?

- files/main.js/.block
// pastayı kişi sayısına böler misin?
let pasta = 7;
let kişi = 2;
console.log("Kişi başına", pasta <<< ❓ >>> kişi, "pasta");
---------------------
- tests/0/output
Kişi başına 3.5 pasta

---------------------
- tests/1/files/main.js/.block
// pastayı kişi sayısına böler misin?
let pasta = 9;
let kişi = 4;
console.log("Kişi başına", pasta <<< ❓ >>> kişi, "pasta");
- tests/1/output
Kişi başına 2.25 pasta

---------------------
- parts/4:
- text
# 🍬 Kalan (mod) Operatörü

``%`` işareti bölme işleminden kalanı verir. 23 şekeri 5 çocuğa paylaştırırsak her çocuğa
4 şeker düşer ve 3 şeker artar. Kalan operatörü, bir sayının başka bir sayıya tam bölünüp
bölünmediğini anlamak için de kullanılır.

<code-view name="main.js" language="javascript">
let şeker = 23;
let çocuk = 5;
console.log(şeker % çocuk, "şeker artar");
</code-view>

<code-view name="Terminal" language="bash">
3 şeker artar
</code-view>

# 🎯 5. Görev

23 şekeri 5 çocuğa eşit paylaştırınca ``3 şeker artar`` yazdıran programı yazar mısın?

- files/main.js/.block
// bölümden kalanı bulur musun?
let şeker = 23;
let çocuk = 5;
console.log(şeker <<< ❓ >>> çocuk, "şeker artar");
---------------------
- tests/0/output
3 şeker artar

---------------------
- tests/1/files/main.js/.block
// bölümden kalanı bulur musun?
let şeker = 17;
let çocuk = 4;
console.log(şeker <<< ❓ >>> çocuk, "şeker artar");
- tests/1/output
1 şeker artar

---------------------
- parts/5:
- text
# ⏫ Üs Alma

``**`` işareti bir sayının kuvvetini alır. ``2 ** 10`` demek "2'nin 10. kuvveti" yani
10 tane 2'nin çarpımı demektir. Üs operatörü çarpma işaretinin iki kez yazılmasıyla
oluşur, onu çarpmayla karıştırmamalıyız.

<code-view name="main.js" language="javascript">
let taban = 2;
let kuvvet = 10;
console.log("Sonuç:", taban ** kuvvet);
</code-view>

<code-view name="Terminal" language="bash">
Sonuç: 1024
</code-view>

# 🎯 6. Görev

2'nin 10. kuvvetini hesaplayıp ``Sonuç: 1024`` yazdıran programı yazar mısın?

- files/main.js/.block
// taban sayısının kuvvetini alır mısın?
let taban = 2;
let kuvvet = 10;
console.log("Sonuç:", taban <<< ❓ >>> kuvvet);
---------------------
- tests/0/output
Sonuç: 1024

---------------------
- tests/1/files/main.js/.block
// taban sayısının kuvvetini alır mısın?
let taban = 3;
let kuvvet = 4;
console.log("Sonuç:", taban <<< ❓ >>> kuvvet);
- tests/1/output
Sonuç: 81

---------------------
- parts/6:
- text
# 🔁 Artırma ve Azaltma : ++ ve --

Bir sayıyı bir artırmak için ``++``, bir azaltmak için ``--`` kullanırız. ``sayaç++``
yazımı ``sayaç = sayaç + 1`` ile aynı işi yapar ama daha kısadır. Bu kısayol özellikle
döngülerde çok işimize yarayacak.

<code-view name="main.js" language="javascript">
let sayaç = 5;
sayaç++;
sayaç++;
console.log("Sayaç:", sayaç);
sayaç--;
console.log("Sayaç:", sayaç);
</code-view>

<code-view name="Terminal" language="bash">
Sayaç: 7
Sayaç: 6
</code-view>

# 🎯 7. Görev

5'ten başlayıp sayacı iki kez artırıp bir kez azaltan programı yazar mısın? Terminale
önce ``Sayaç: 7`` sonra ``Sayaç: 6`` yazmalı.

- files/main.js/.block
// önce iki kez artır, sonra bir kez azalt
let sayaç = 5;
sayaç<<< ❓ >>>;
sayaç<<< ❓ >>>;
console.log("Sayaç:", sayaç);
sayaç<<< ❓ >>>;
console.log("Sayaç:", sayaç);
---------------------
- tests/0/output
Sayaç: 7
Sayaç: 6

---------------------
- tests/1/files/main.js/.block
// önce iki kez artır, sonra bir kez azalt
let sayaç = 10;
sayaç<<< ❓ >>>;
sayaç<<< ❓ >>>;
console.log("Sayaç:", sayaç);
sayaç<<< ❓ >>>;
console.log("Sayaç:", sayaç);
- tests/1/output
Sayaç: 12
Sayaç: 11

---------------------
- parts/7:
- text
# 🧮 İşlem Önceliği

Bir satırda birden fazla işlem varsa JavaScript önce çarpmayı ve bölmeyi, sonra toplamayı
ve çıkarmayı yapar. Yani ``2 + 3 * 4`` işleminin sonucu ``20`` değil ``14`` olur.
Aynı öncelikteki işlemler soldan sağa doğru yapılır.

<code-view name="main.js" language="javascript">
console.log(2 + 3 * 4);
console.log(10 - 6 / 2);
</code-view>

<code-view name="Terminal" language="bash">
14
7
</code-view>

# 🎯 8. Görev

İşlem önceliğine uyarak iki satırda ``14`` ve ``7`` yazdıran programı yazar mısın?

- files/main.js/.block
// önce çarpma ve bölme yapılır
console.log(2 <<< ❓ >>> 3 <<< ❓ >>> 4);
console.log(10 <<< ❓ >>> 6 <<< ❓ >>> 2);
---------------------
- tests/0/output
14
7

---------------------
- tests/1/files/main.js/.block
// önce çarpma ve bölme yapılır
console.log(5 <<< ❓ >>> 2 <<< ❓ >>> 3);
console.log(20 <<< ❓ >>> 8 <<< ❓ >>> 4);
- tests/1/output
11
18

---------------------
- parts/8:
- text
# 🧷 Parantezle Önceliği Değiştirme

Parantez ``( )`` içindeki işlem her zaman önce yapılır. ``(2 + 3) * 4`` ifadesinde önce
toplama yapılır ve sonuç ``20`` olur. Parantezsiz hâlde ise sonuç ``14`` olurdu.

<code-view name="main.js" language="javascript">
console.log((2 + 3) * 4);
console.log(2 + 3 * 4);
</code-view>

<code-view name="Terminal" language="bash">
20
14
</code-view>

# 🎯 9. Görev

Parantez kullanarak ``20`` sonucunu, parantezsiz yazarak da ``14`` sonucunu veren
programı yazar mısın?

- files/main.js/.block
// parantezle önce toplama yaptırır mısın?
console.log(<<< ❓ >>> * 4);
console.log(2 + 3 * 4);
---------------------
- tests/0/output
20
14

---------------------
- tests/1/files/main.js/.block
// parantezle önce toplama yaptırır mısın?
console.log(<<< ❓ >>> * 6);
console.log(1 + 2 * 3);
- tests/1/output
30
7

---------------------
- parts/9:
- text
# 🔤 "5" + 1 ile "5" - 1 Farkı

``+`` işareti metin gördüğünde sayıyı da metne çevirip yan yana ekler; buna birleştirme
(concatenation) denir. Bu yüzden ``"5" + 1`` sonucu ``"51"`` olur. ``-`` işareti ise
metni sayıya çevirmek zorundadır, bu yüzden ``"5" - 1`` sonucu ``4`` olur.

<code-view name="main.js" language="javascript">
console.log("5" + 1);
console.log("5" - 1);
</code-view>

<code-view name="Terminal" language="bash">
51
4
</code-view>

# 🎯 10. Görev

``"5"`` metnine ``+`` uygulayınca ``51``, ``-`` uygulayınca ``4`` yazdıran programı
yazar mısın?

- files/main.js/.block
// metinle toplama ve çıkarma farkını göster
console.log("5" <<< ❓ >>> 1);
console.log("5" <<< ❓ >>> 1);
---------------------
- tests/0/output
51
4

---------------------
- tests/1/files/main.js/.block
console.log("8" <<< ❓ >>> 2);
console.log("8" <<< ❓ >>> 2);
- tests/1/output
82
6

---------------------
- parts/10:
- text
# 📊 Toplam ve Ortalama Hesabı

Üç notun toplamını bulmak için ``+`` operatörünü art arda kullanırız. Ortalama ise
toplamın not sayısına bölünmesiyle bulunur. Böylece aritmetik operatörleri gerçek bir
hesapta birlikte kullanmış oluruz.

<code-view name="main.js" language="javascript">
let not1 = 80;
let not2 = 90;
let not3 = 70;
let toplam = not1 + not2 + not3;
let ortalama = toplam / 3;
console.log("Toplam:", toplam);
console.log("Ortalama:", ortalama);
</code-view>

<code-view name="Terminal" language="bash">
Toplam: 240
Ortalama: 80
</code-view>

# 🎯 11. Görev

80, 90 ve 70 notlarının toplamını ve ortalamasını ``Toplam: 240``, ``Ortalama: 80``
biçiminde yazdıran programı yazar mısın?

- files/main.js/.block
// üç notun toplamını ve ortalamasını bulur musun?
let not1 = 80;
let not2 = 90;
let not3 = 70;
let toplam = not1 <<< ❓ >>> not2 <<< ❓ >>> not3;
let ortalama = toplam <<< ❓ >>> 3;
console.log("Toplam:", toplam);
console.log("Ortalama:", ortalama);
---------------------
- tests/0/output
Toplam: 240
Ortalama: 80

---------------------
- tests/1/files/main.js/.block
// üç notun toplamını ve ortalamasını bulur musun?
let not1 = 60;
let not2 = 70;
let not3 = 80;
let toplam = not1 <<< ❓ >>> not2 <<< ❓ >>> not3;
let ortalama = toplam <<< ❓ >>> 3;
console.log("Toplam:", toplam);
console.log("Ortalama:", ortalama);
- tests/1/output
Toplam: 210
Ortalama: 70

---------------------
- parts/11:
- text
# 🏆 Mini Tekrar : KDV Hesabı

Öğrendiklerimizi bir faturada birleştirelim. Önce fiyat ile adedi çarparak ara toplamı,
sonra yüzde 20 KDV'yi, en sonunda genel toplamı hesaplarız. İşlem önceliği burada da
devreye girer.

<code-view name="main.js" language="javascript">
let fiyat = 200;
let adet = 3;
let araToplam = fiyat * adet;
let kdv = araToplam * 20 / 100;
let toplam = araToplam + kdv;
console.log("Ara toplam:", araToplam);
console.log("KDV:", kdv);
console.log("Genel toplam:", toplam);
</code-view>

<code-view name="Terminal" language="bash">
Ara toplam: 600
KDV: 120
Genel toplam: 720
</code-view>

# 🎯 12. Görev

Tanesi 200 lira olan 3 ürünün ara toplamını, yüzde 20 KDV'sini ve genel toplamı
hesaplayan programı yazar mısın?

- files/main.js/.block
// ara toplamı, KDV'yi ve genel toplamı hesaplar mısın?
let fiyat = 200;
let adet = 3;
let araToplam = fiyat <<< ❓ >>> adet;
let kdv = araToplam <<< ❓ >>> 20 <<< ❓ >>> 100;
let toplam = araToplam <<< ❓ >>> kdv;
console.log("Ara toplam:", araToplam);
console.log("KDV:", kdv);
console.log("Genel toplam:", toplam);
---------------------
- tests/0/output
Ara toplam: 600
KDV: 120
Genel toplam: 720

---------------------
- tests/1/files/main.js/.block
// ara toplamı, KDV'yi ve genel toplamı hesaplar mısın?
let fiyat = 150;
let adet = 2;
let araToplam = fiyat <<< ❓ >>> adet;
let kdv = araToplam <<< ❓ >>> 20 <<< ❓ >>> 100;
let toplam = araToplam <<< ❓ >>> kdv;
console.log("Ara toplam:", araToplam);
console.log("KDV:", kdv);
console.log("Genel toplam:", toplam);
- tests/1/output
Ara toplam: 300
KDV: 60
Genel toplam: 360

---------------------
