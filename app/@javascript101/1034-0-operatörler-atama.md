- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "🔁 Operatörler : Atama"
- run = "node main.js"

- parts/0:
- text
# 🔁 **Atama** Operatörleri

Bir değişkene değer vermek için ``=`` kullanırız. Aynı değişkeni kendisiyle işleme sokup
sonucu yine ona yazmak çok sık olur; bunun için kısa yollar vardır. ``puan += 5`` demek
``puan = puan + 5`` demektir.

<code-view name="main.js" language="javascript">
let puan = 10;
puan += 5;
console.log(puan);

let mesaj = "Merhaba";
mesaj += " Dünya";
console.log(mesaj);
</code-view>

<code-view name="Terminal" language="bash">
15
Merhaba Dünya
</code-view>

# 🎯 1. Görev

``15`` ve ``Merhaba Dünya`` yazdıran programı yazar mısın?

- files/main.js/.block
// puanı 5 artır, metnin sonuna devamını ekle
let puan = 10;
puan <<< ❓ >>> 5;
console.log(puan);

let mesaj = "Merhaba";
mesaj <<< ❓ >>> " Dünya";
console.log(mesaj);
---------------------
- tests/0/output
15
Merhaba Dünya

---------------------
- tests/1/files/main.js/.block
// puanı 5 artır, metnin sonuna devamını ekle
let puan = 20;
puan <<< ❓ >>> 5;
console.log(puan);

let mesaj = "Merhaba";
mesaj <<< ❓ >>> " Dünya";
console.log(mesaj);
- tests/1/output
25
Merhaba Dünya

---------------------
- parts/1:
- text
# ✅ Tebrikler : ``-=`` (Çıkararak Atama)

``bakiye -= 30`` demek ``bakiye = bakiye - 30`` demektir. Hesaptan para çekmek, stoktan
ürün düşmek gibi işlemlerde bu kısa yolu kullanırız.

<code-view name="main.js" language="javascript">
let bakiye = 100;
bakiye -= 30;
console.log(bakiye);
</code-view>

<code-view name="Terminal" language="bash">
70
</code-view>

# 🎯 2. Görev

100 liradan 30 lira harcanınca terminale ``70`` yazdıran programı yazar mısın?

- files/main.js/.block
// bakiyeden 30 lira düşer misin?
let bakiye = 100;
bakiye <<< ❓ >>> 30;
console.log(bakiye);
---------------------
- tests/0/output
70

---------------------
- tests/1/files/main.js/.block
// bakiyeden 30 lira düşer misin?
let bakiye = 50;
bakiye <<< ❓ >>> 30;
console.log(bakiye);
- tests/1/output
20

---------------------
- parts/2:
- text
# ✅ Tebrikler : ``*=`` (Çarparak Atama)

``fiyat *= 3`` demek ``fiyat = fiyat * 3`` demektir. Zam yapmak ya da aynı üründen birkaç
tane almak gibi işlemlerde kullanılır.

<code-view name="main.js" language="javascript">
let fiyat = 20;
fiyat *= 3;
console.log(fiyat);
</code-view>

<code-view name="Terminal" language="bash">
60
</code-view>

# 🎯 3. Görev

Tanesi 20 lira olan üründen 3 tane alınınca terminale ``60`` yazdıran programı yazar
mısın?

- files/main.js/.block
// fiyatı 3 ile çarpar mısın?
let fiyat = 20;
fiyat <<< ❓ >>> 3;
console.log(fiyat);
---------------------
- tests/0/output
60

---------------------
- tests/1/files/main.js/.block
// fiyatı 3 ile çarpar mısın?
let fiyat = 15;
fiyat <<< ❓ >>> 3;
console.log(fiyat);
- tests/1/output
45

---------------------
- parts/3:
- text
# ✅ Tebrikler : ``/=`` (Bölerek Atama)

``para /= 4`` demek ``para = para / 4`` demektir. Tam bölünmeyen sayılarda sonuç ondalıklı
çıkabilir; JavaScript bu durumda virgül değil nokta kullanır.

<code-view name="main.js" language="javascript">
let para = 100;
para /= 4;
console.log(para);
</code-view>

<code-view name="Terminal" language="bash">
25
</code-view>

# 🎯 4. Görev

100 lirayı 4 kişiye paylaştırınca terminale ``25`` yazdıran programı yazar mısın?

- files/main.js/.block
// parayı 4 kişiye böler misin?
let para = 100;
para <<< ❓ >>> 4;
console.log(para);
---------------------
- tests/0/output
25

---------------------
- tests/1/files/main.js/.block
// parayı 4 kişiye böler misin?
let para = 90;
para <<< ❓ >>> 4;
console.log(para);
- tests/1/output
22.5

---------------------
- parts/4:
- text
# ✅ Tebrikler : ``%=`` (Kalanı Atama)

``şeker %= 5`` demek ``şeker = şeker % 5`` demektir ve değişkende bölümden kalanı
bırakır. Bir sayının başka bir sayıya tam bölünüp bölünmediğini anlamak için idealdir.

<code-view name="main.js" language="javascript">
let şeker = 17;
şeker %= 5;
console.log(şeker);
</code-view>

<code-view name="Terminal" language="bash">
2
</code-view>

# 🎯 5. Görev

17 şekeri 5'erli paylaştırınca kalan ``2`` şekeri terminale yazdıran programı yazar
mısın?

- files/main.js/.block
// bölümden kalanı değişkende bırakır mısın?
let şeker = 17;
şeker <<< ❓ >>> 5;
console.log(şeker);
---------------------
- tests/0/output
2

---------------------
- tests/1/files/main.js/.block
// bölümden kalanı değişkende bırakır mısın?
let şeker = 23;
şeker <<< ❓ >>> 5;
console.log(şeker);
- tests/1/output
3

---------------------
- parts/5:
- text
# ✅ Tebrikler : ``**=`` (Kuvvetini Atama)

``sayı **= 3`` demek ``sayı = sayı ** 3`` demektir. Yani değişkenin kendisini 3. kuvvete
yükseltir. ``2 ** 3`` sonucu ``8`` olduğu için ``sayı`` değişkeni ``8`` olur.

<code-view name="main.js" language="javascript">
let sayı = 2;
sayı **= 3;
console.log(sayı);
</code-view>

<code-view name="Terminal" language="bash">
8
</code-view>

# 🎯 6. Görev

``2`` sayısını 3. kuvvete yükseltip terminale ``8`` yazdıran programı yazar mısın?

- files/main.js/.block
// sayıyı 3. kuvvete yükseltir misin?
let sayı = 2;
sayı <<< ❓ >>> 3;
console.log(sayı);
---------------------
- tests/0/output
8

---------------------
- tests/1/files/main.js/.block
// sayıyı 3. kuvvete yükseltir misin?
let sayı = 3;
sayı <<< ❓ >>> 3;
console.log(sayı);
- tests/1/output
27

---------------------
- parts/6:
- text
# ✅ Tebrikler : ``++`` ve ``--``

Bir sayıyı yalnızca 1 artırmak ya da 1 azaltmak için ``++`` ve ``--`` kullanılır.
Operatör **sonra** yazılırsa (``sayaç++``) önce eski değer kullanılır, sonra artırılır.
Operatör **önce** yazılırsa (``--sayaç``) önce azaltılır, sonra yeni değer kullanılır.

<code-view name="main.js" language="javascript">
let sayaç = 5;
console.log(sayaç++);
console.log(sayaç);
console.log(--sayaç);
console.log(sayaç);
</code-view>

<code-view name="Terminal" language="bash">
5
6
5
5
</code-view>

# 🎯 7. Görev

``5``, ``6``, ``5`` ve ``5`` yazdıran programı yazar mısın?

- files/main.js/.block
// ++ ile artır, -- ile azalt
let sayaç = 5;
console.log(sayaç<<< ❓ >>>);
console.log(sayaç);
console.log(<<< ❓ >>>sayaç);
console.log(sayaç);
---------------------
- tests/0/output
5
6
5
5

---------------------
- tests/1/files/main.js/.block
// ++ ile artır, -- ile azalt
let sayaç = 9;
console.log(sayaç<<< ❓ >>>);
console.log(sayaç);
console.log(<<< ❓ >>>sayaç);
console.log(sayaç);
- tests/1/output
9
10
9
9

---------------------
- parts/7:
- text
# ✅ Tebrikler : ``||=`` ve ``??=``

``ad ||= "Misafir"`` demek "``ad`` yanlışsa ``Misafir`` yaz" demektir. ``??=`` ise yalnızca
değişken null ya da undefined ise devreye girer. Bu yüzden ``0 ??= 99`` sonucu ``0``
kalır, çünkü ``0`` geçerli bir değerdir.

<code-view name="main.js" language="javascript">
let ad = "";
ad ||= "Misafir";
console.log(ad);

let yaş = null;
yaş ??= 18;
console.log(yaş);

let sıfır = 0;
sıfır ??= 99;
console.log(sıfır);
</code-view>

<code-view name="Terminal" language="bash">
Misafir
18
0
</code-view>

# 🎯 8. Görev

``Misafir``, ``18`` ve ``0`` yazdıran programı yazar mısın?

- files/main.js/.block
// ad boşsa varsayılan ver, sıfırı ise koru
let ad = "";
ad <<< ❓ >>> "Misafir";
console.log(ad);

let yaş = null;
yaş <<< ❓ >>> 18;
console.log(yaş);

let sıfır = 0;
sıfır <<< ❓ >>> 99;
console.log(sıfır);
---------------------
- tests/0/output
Misafir
18
0

---------------------
- tests/1/files/main.js/.block
// ad boşsa varsayılan ver, sıfırı ise koru
let ad = "Ali";
ad <<< ❓ >>> "Misafir";
console.log(ad);

let yaş = null;
yaş <<< ❓ >>> 18;
console.log(yaş);

let sıfır = 0;
sıfır <<< ❓ >>> 99;
console.log(sıfır);
- tests/1/output
Ali
18
0

---------------------
- parts/8:
- text
# ✅ Tebrikler : ``&&=``

``stok &&= stok * 2`` demek "``stok`` doğruysa iki katına çıkar" demektir. Değişken
yanlışsa (``0`` gibi) hiçbir şey yapılmaz ve eski değeri kalır. Böylece atamayı bir koşula
bağlamış oluruz.

<code-view name="main.js" language="javascript">
let stok = 5;
stok &&= stok * 2;
console.log(stok);

let tükenmiş = 0;
tükenmiş &&= 42;
console.log(tükenmiş);
</code-view>

<code-view name="Terminal" language="bash">
10
0
</code-view>

# 🎯 9. Görev

``10`` ve ``0`` yazdıran programı yazar mısın?

- files/main.js/.block
// stok varsa iki katına çıkar
let stok = 5;
stok <<< ❓ >>> stok * 2;
console.log(stok);

let tükenmiş = 0;
tükenmiş <<< ❓ >>> 42;
console.log(tükenmiş);
---------------------
- tests/0/output
10
0

---------------------
- tests/1/files/main.js/.block
// stok varsa iki katına çıkar
let stok = 3;
stok <<< ❓ >>> stok * 2;
console.log(stok);

let tükenmiş = 0;
tükenmiş <<< ❓ >>> 42;
console.log(tükenmiş);
- tests/1/output
6
0

---------------------
- parts/9:
- text
# 🏆 Mini Tekrar

Öğrendiklerini birleştirelim: bir sayaçla adım adım hesap yapalım. ``+=`` ile 10 ekle,
``-=`` ile 4 çıkar, ``*=`` ile 2 ile çarp, ``/=`` ile 3'e böl. Sıfırdan başlayınca sonuç
``4`` olur.

<code-view name="main.js" language="javascript">
let sayaç = 0;
sayaç += 10;
sayaç -= 4;
sayaç *= 2;
sayaç /= 3;
console.log(sayaç);
</code-view>

<code-view name="Terminal" language="bash">
4
</code-view>

# 🎯 10. Görev

``4`` yazdıran programı yazar mısın? Cevabı verecek operatörleri sırayla tamamla.

- files/main.js/.block
// 10 ekle, 4 çıkar, 2 ile çarp, 3'e böl
let sayaç = 0;
sayaç <<< ❓ >>> 10;
sayaç <<< ❓ >>> 4;
sayaç <<< ❓ >>> 2;
sayaç <<< ❓ >>> 3;
console.log(sayaç);
---------------------
- tests/0/output
4

---------------------
- tests/1/files/main.js/.block
// 10 ekle, 4 çıkar, 2 ile çarp, 3'e böl
let sayaç = 6;
sayaç <<< ❓ >>> 10;
sayaç <<< ❓ >>> 4;
sayaç <<< ❓ >>> 2;
sayaç <<< ❓ >>> 3;
console.log(sayaç);
- tests/1/output
8

---------------------
