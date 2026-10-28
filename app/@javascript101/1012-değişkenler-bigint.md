- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "🔢 Değişkenler bigint : Çok Büyük Sayılar"
- run = "node main.js"

- parts/0:
- text
# 🎯 **bigint** : Çok Büyük Sayılar

Normal ``number`` türü çok büyük tam sayılarda hassasiyetini kaybeder. Bunun için
JavaScript'te **bigint** (büyük tam sayı) türü vardır. bigint yazmanın tek kuralı: sayının
sonuna küçük ``n`` harfi koymak (``123n``). Bu ``n`` ekranda görünmez, sadece değerin
türünü belirtir.

<code-view name="main.js" language="javascript">
let büyükSayı = 123n;
console.log(büyükSayı);
console.log(typeof büyükSayı);
</code-view>

<code-view name="Terminal" language="bash">
123
bigint
</code-view>

# 🎯 1. Görev

Terminale önce ``123`` sonra ``bigint`` yazdıran programı yazar mısın? Değerin sonuna
``n`` eklemeyi unutma, yoksa türü ``number`` olur.

- files/main.js/.block
// sonuna n ekleyerek bigint yapar mısın?
let büyükSayı = <<< ❓ >>>;
console.log(büyükSayı);
console.log(typeof büyükSayı);
---------------------
- tests/0/output
123
bigint

---------------------
- parts/1:
- text
# ✅ bigint mi, number mı?

Aynı rakamlar iki farklı türe ait olabilir: ``10`` bir ``number``, ``10n`` ise bir
``bigint``tir. Türü öğrenmek için ``typeof`` kullanırız. Bu ayrımı bilmek önemlidir; çünkü
iki türü doğrudan toplayamayız.

<code-view name="main.js" language="javascript">
console.log(typeof 10);
console.log(typeof 10n);
</code-view>

<code-view name="Terminal" language="bash">
number
bigint
</code-view>

# 🎯 2. Görev

``10`` için ``number``, ``10n`` için ``bigint`` yazdıran programı yazar mısın?

- files/main.js/.block
// 10 ve 10n değerlerinin türlerini yazar mısın?
console.log(typeof <<< ❓ >>>);
console.log(typeof <<< ❓ >>>);
---------------------
- tests/0/output
number
bigint

---------------------
- parts/2:
- text
# ➕ bigint ile Toplama

bigint değerler ``+`` ile tıpkı normal sayılar gibi toplanır. Sonuç yine ``bigint`` olur.
Ekranda ise ``n`` olmadan, sade bir sayı gibi görünür.

<code-view name="main.js" language="javascript">
let elma = 1n;
let armut = 2n;
console.log("Toplam:", elma + armut);
</code-view>

<code-view name="Terminal" language="bash">
Toplam: 3
</code-view>

# 🎯 3. Görev

``1n`` ile ``2n`` değerlerini toplayıp ``Toplam: 3`` yazdıran programı yazar mısın?

- files/main.js/.block
// iki bigint değeri toplar mısın?
let elma = 1n;
let armut = 2n;
console.log("Toplam:", elma <<< ❓ >>> armut);
---------------------
- tests/0/output
Toplam: 3

---------------------
- tests/1/files/main.js/.block
// iki bigint değeri toplar mısın?
let elma = 10n;
let armut = 5n;
console.log("Toplam:", elma <<< ❓ >>> armut);
- tests/1/output
Toplam: 15

---------------------
- parts/3:
- text
# ➖ bigint ile Çıkarma

``-`` işareti bigint değerlerden çıkarma yapar. Sonuç sıfırdan küçükse negatif bir bigint
elde ederiz; ekranda eksi işaretiyle görünür.

<code-view name="main.js" language="javascript">
let borç = 5n;
borç = borç - 8n;
console.log(borç);
</code-view>

<code-view name="Terminal" language="bash">
&minus;3
</code-view>

# 🎯 4. Görev

``5n`` değerinden ``8n`` çıkarıp terminale ``-3`` yazdıran programı yazar mısın?

- files/main.js/.block
// 8n çıkarır mısın?
let borç = 5n;
borç = borç <<< ❓ >>> 8n;
console.log(borç);
---------------------
- tests/0/output
&minus;3

---------------------
- tests/1/files/main.js/.block
// 8n çıkarır mısın?
let borç = 20n;
borç = borç <<< ❓ >>> 8n;
console.log(borç);
- tests/1/output
12

---------------------
- parts/4:
- text
# ✖️ bigint ile Çarpma

Çarpma için ``*`` işaretini kullanırız. bigint'in asıl gücü burada ortaya çıkar: çok büyük
sayılar bile bozulmadan çarpılır.

<code-view name="main.js" language="javascript">
let kalem = 12345n;
console.log("Kalem sayısı:", kalem * 2n);
</code-view>

<code-view name="Terminal" language="bash">
Kalem sayısı: 24690
</code-view>

# 🎯 5. Görev

``12345n`` değerini ``2n`` ile çarpıp ``Kalem sayısı: 24690`` yazdıran programı yazar
mısın?

- files/main.js/.block
// iki bigint değeri çarpar mısın?
let kalem = 12345n;
console.log("Kalem sayısı:", kalem <<< ❓ >>> 2n);
---------------------
- tests/0/output
Kalem sayısı: 24690

---------------------
- tests/1/files/main.js/.block
// iki bigint değeri çarpar mısın?
let kalem = 111n;
console.log("Kalem sayısı:", kalem <<< ❓ >>> 2n);
- tests/1/output
Kalem sayısı: 222

---------------------
- parts/5:
- text
# ⏫ bigint ile Üs Alma

``**`` işareti kuvvet alır. bigint'te **üs de bigint olmalıdır**, yani ``10`` değil ``10n``
yazılır. ``2n ** 10n`` demek "2'yi 10 kere kendisiyle çarp" demektir ve sonuç ``1024``
olur.

<code-view name="main.js" language="javascript">
let tane = 2n;
console.log("10 kat sonra:", tane ** 10n);
</code-view>

<code-view name="Terminal" language="bash">
10 kat sonra: 1024
</code-view>

# 🎯 6. Görev

Her adımda ikiye katlanan sayının 10 adım sonraki değerini ``10 kat sonra: 1024`` şeklinde
yazdıran programı yazar mısın?

- files/main.js/.block
// 2n sayısının 10. kuvvetini alır mısın?
let tane = 2n;
console.log("10 kat sonra:", tane <<< ❓ >>> 10n);
---------------------
- tests/0/output
10 kat sonra: 1024

---------------------
- tests/1/files/main.js/.block
// 3n sayısının 10. kuvvetini alır mısın?
let tane = 3n;
console.log("10 kat sonra:", tane <<< ❓ >>> 10n);
- tests/1/output
10 kat sonra: 59049

---------------------
- parts/6:
- text
# 🔍 bigint ile Karşılaştırma

Karşılaştırma operatörleri bigint değerlerde de çalışır: ``>``, ``<``, ``==``. Dikkat:
``10n == 10`` ifadesi ``true`` döner çünkü sadece değerler karşılaştırılır; ama
``10n === 10`` ifadesi ``false`` döner çünkü türler farklıdır.

<code-view name="main.js" language="javascript">
let a = 10n;
let b = 5n;
console.log("Büyük mü?", a > b);
console.log("Eşit mi?", a == 10);
console.log("Aynı tür mü?", a === 10);
</code-view>

<code-view name="Terminal" language="bash">
Büyük mü? true
Eşit mi? true
Aynı tür mü? false
</code-view>

# 🎯 7. Görev

``10n`` değerinin ``5n`` değerinden büyük olup olmadığını yazdıran programı yazar mısın?
Diğer iki satır aynı kalacak.

- files/main.js/.block
// 10n, 5n'den büyük mü?
let a = 10n;
let b = 5n;
console.log("Büyük mü?", a <<< ❓ >>> b);
console.log("Eşit mi?", a == 10);
console.log("Aynı tür mü?", a === 10);
---------------------
- tests/0/output
Büyük mü? true
Eşit mi? true
Aynı tür mü? false

---------------------
- tests/1/files/main.js/.block
// 2n, 5n'den büyük mü?
let a = 2n;
let b = 5n;
console.log("Büyük mü?", a <<< ❓ >>> b);
console.log("Eşit mi?", a == 10);
console.log("Aynı tür mü?", a === 10);
- tests/1/output
Büyük mü? false
Eşit mi? false
Aynı tür mü? false

---------------------
- parts/7:
- text
# ⚠️ Number.MAX_SAFE_INTEGER

``number`` türü belli bir büyüklükten sonra tam sayıları güvenle saklayamaz. Bu sınır
``Number.MAX_SAFE_INTEGER`` yani ``9007199254740991``'dir. Bu sınırın üstünde ``bigint``
kullanırız; bigint'te böyle bir sınır yoktur.

<code-view name="main.js" language="javascript">
console.log(Number.MAX_SAFE_INTEGER);
console.log(typeof Number.MAX_SAFE_INTEGER);
console.log(9007199254740993n);
</code-view>

<code-view name="Terminal" language="bash">
9007199254740991
number
9007199254740993
</code-view>

# 🎯 8. Görev

Güvenli en büyük tam sayıyı, türünü ve bigint ile sınırın üstündeki bir sayıyı yazdıran
programı yazar mısın?

- files/main.js/.block
// güvenli en büyük tam sayıyı yazar mısın?
console.log(<<< ❓ >>>);
console.log(typeof Number.MAX_SAFE_INTEGER);
// bigint ile sınırın üstüne çıkar mısın?
console.log(<<< ❓ >>>n);
---------------------
- tests/0/output
9007199254740991
number
9007199254740993

---------------------
- parts/8:
- text
# 🔄 BigInt() : Metinden bigint'e

Elimizdeki çok büyük sayı çoğu zaman bir metin (string) olarak gelir. ``BigInt("...")``
fonksiyonu metni gerçek bir bigint değerine çevirir. Böylece o sayıyla işlem
yapabiliriz.

<code-view name="main.js" language="javascript">
let metin = "9007199254740993";
let sayı = BigInt(metin);
console.log(sayı);
console.log(typeof sayı);
</code-view>

<code-view name="Terminal" language="bash">
9007199254740993
bigint
</code-view>

# 🎯 9. Görev

``"9007199254740993"`` metnini bigint'e çevirip değeri ve türünü yazdıran programı yazar
mısın?

- files/main.js/.block
// metni bigint'e çevirir misin?
let metin = "9007199254740993";
let sayı = <<< ❓ >>>(metin);
console.log(sayı);
console.log(typeof sayı);
---------------------
- tests/0/output
9007199254740993
bigint

---------------------
- tests/1/files/main.js/.block
// metni bigint'e çevirir misin?
let metin = "123456789012345678901234567890";
let sayı = <<< ❓ >>>(metin);
console.log(sayı);
console.log(typeof sayı);
- tests/1/output
123456789012345678901234567890
bigint

---------------------
- parts/9:
- text
# 🏆 String() : bigint'ten Metne

Bazen tersi gerekir: bigint değeri metne çevirip yazı içinde kullanmak isteriz.
``String(büyük)`` fonksiyonu bigint'i metne çevirir ve türü ``string`` olur. Böylece
birleştirme, ``toFixed`` gibi metin işlemleri yapılabilir.

<code-view name="main.js" language="javascript">
let büyük = 123n;
console.log("Metin:", String(büyük));
console.log(typeof String(büyük));
</code-view>

<code-view name="Terminal" language="bash">
Metin: 123
string
</code-view>

# 🎯 10. Görev

``123n`` değerini metne çevirip ``Metin: 123`` ve ``string`` yazdıran programı yazar
mısın?

- files/main.js/.block
// bigint değeri metne çevirir misin?
let büyük = 123n;
console.log("Metin:", <<< ❓ >>>(büyük));
console.log(typeof String(büyük));
---------------------
- tests/0/output
Metin: 123
string

---------------------
- tests/1/files/main.js/.block
// bigint değeri metne çevirir misin?
let büyük = 42n;
console.log("Metin:", <<< ❓ >>>(büyük));
console.log(typeof String(büyük));
- tests/1/output
Metin: 42
string

---------------------
