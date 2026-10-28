- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "🧠 Operatörler : Mantıksal"
- run = "node main.js"

- parts/0:
- text
# 🧠 **Mantıksal** Operatörler

Mantıksal operatörler koşulları birleştirmemizi sağlar: ``&&`` (ve), ``||`` (veya) ve
``!`` (değil). Bu derste önce ``&&`` ile başlıyoruz. ``&&`` iki tarafı da doğruysa
``true`` verir.

<code-view name="main.js" language="javascript">
let yaş = 20;
let ehliyet = true;
console.log(yaş >= 18 && ehliyet);
</code-view>

<code-view name="Terminal" language="bash">
true
</code-view>

# 🎯 1. Görev

``yaş`` 18'den büyük **ve** ehliyeti varsa terminale ``true`` yazdıran programı yazar mısın?

- files/main.js/.block
// iki koşulu "ve" ile birleştirir misin?
let yaş = 20;
let ehliyet = true;
console.log(yaş >= 18 <<< ❓ >>> ehliyet);
---------------------
- tests/0/output
true

---------------------
- tests/1/files/main.js/.block
// iki koşulu "ve" ile birleştirir misin?
let yaş = 15;
let ehliyet = true;
console.log(yaş >= 18 <<< ❓ >>> ehliyet);
- tests/1/output
false

---------------------
- parts/1:
- text
# ✅ Tebrikler : ``||`` (Veya)

``||`` operatörü iki koşuldan **en az biri** doğruysa ``true`` verir. Kahve ya da çay
içebilirsin; ikisinden birinin olması yeterlidir. İkisi de yoksa sonuç ``false`` olur.

<code-view name="main.js" language="javascript">
let çay = false;
let kahve = true;
console.log(çay || kahve);
</code-view>

<code-view name="Terminal" language="bash">
true
</code-view>

# 🎯 2. Görev

Çay **veya** kahve varsa ``true`` yazdıran programı yazar mısın?

- files/main.js/.block
// iki koşulu "veya" ile birleştirir misin?
let çay = false;
let kahve = true;
console.log(çay <<< ❓ >>> kahve);
---------------------
- tests/0/output
true

---------------------
- tests/1/files/main.js/.block
// iki koşulu "veya" ile birleştirir misin?
let çay = false;
let kahve = false;
console.log(çay <<< ❓ >>> kahve);
- tests/1/output
false

---------------------
- parts/2:
- text
# ✅ Tebrikler : ``!`` (Değil)

``!`` operatörü bir değeri tersine çevirir: doğruysa ``false``, yanlışsa ``true`` olur.
Boş olmayan her metin doğru sayıldığı için ``!"merhaba"`` sonucu ``false`` çıkar.

<code-view name="main.js" language="javascript">
let açık = true;
console.log(!açık);
console.log(!"merhaba");
</code-view>

<code-view name="Terminal" language="bash">
false
false
</code-view>

# 🎯 3. Görev

``açık`` değişkenini tersine çevirip ``!"merhaba"`` sonucunu da yazdıran programı yazar
mısın?

- files/main.js/.block
// değeri tersine çevirir misin?
let açık = true;
console.log(<<< ❓ >>>açık);
console.log(<<< ❓ >>>"merhaba");
---------------------
- tests/0/output
false
false

---------------------
- tests/1/files/main.js/.block
// değeri tersine çevirir misin?
let açık = false;
console.log(<<< ❓ >>>açık);
console.log(<<< ❓ >>>"merhaba");
- tests/1/output
true
false

---------------------
- parts/3:
- text
# ✅ Tebrikler : Kısa Devre (short-circuit)

``&&`` soldaki değer yanlışsa sağ tarafa hiç bakmaz. Bu özelliğe **kısa devre** denir ve
var olmayan bir nesnenin özelliğine uzanırken programı hatadan korur. ``kullanıcı``
``null`` olduğu için ``kullanıcı && kullanıcı.ad`` ifadesi durur ve ``null`` döner.

<code-view name="main.js" language="javascript">
let kullanıcı = null;
console.log(kullanıcı && kullanıcı.ad);
console.log("Ali" && "Veli");
</code-view>

<code-view name="Terminal" language="bash">
null
Veli
</code-view>

# 🎯 4. Görev

Kullanıcı yokken programın hata vermemesini sağlayıp ``null`` ve ``Veli`` yazdıran
programı yazar mısın?

- files/main.js/.block
// kısa devre ile güvenli erişim sağlar mısın?
let kullanıcı = null;
console.log(kullanıcı <<< ❓ >>> kullanıcı.ad);
console.log("Ali" <<< ❓ >>> "Veli");
---------------------
- tests/0/output
null
Veli

---------------------
- tests/1/files/main.js/.block
// kısa devre ile güvenli erişim sağlar mısın?
let kullanıcı = { ad: "Ayşe" };
console.log(kullanıcı <<< ❓ >>> kullanıcı.ad);
console.log("Ali" <<< ❓ >>> "Veli");
- tests/1/output
Ayşe
Veli

---------------------
- parts/4:
- text
# ✅ Tebrikler : Sonuç Her Zaman ``true`` / ``false`` Değildir

Mantıksal operatörler boolean değil, **karşı taraftaki değeri** döndürür. ``&&`` ilk
yanlış değeri, ``||`` ilk doğru değeri verir. Bu yüzden ``"a" || "b"`` sonucu ``a``'dır;
``a`` doğru olduğu için sağ tarafa hiç bakılmaz.

<code-view name="main.js" language="javascript">
console.log("a" || "b");
console.log(0 && "b");
console.log(1 && "b");
</code-view>

<code-view name="Terminal" language="bash">
a
0
b
</code-view>

# 🎯 5. Görev

``a``, ``0`` ve ``b`` yazdıran programı yazar mısın? Mantıksal operatörleri sırayla
kullanman gerekiyor.

- files/main.js/.block
// mantıksal operatörler değeri olduğu gibi döndürür
console.log("a" <<< ❓ >>> "b");
console.log(0 <<< ❓ >>> "b");
console.log(1 <<< ❓ >>> "b");
---------------------
- tests/0/output
a
0
b

---------------------
- tests/1/files/main.js/.block
// mantıksal operatörler değeri olduğu gibi döndürür
console.log("kalem" <<< ❓ >>> "silgi");
console.log(0 <<< ❓ >>> "silgi");
console.log(7 <<< ❓ >>> "silgi");
- tests/1/output
kalem
0
silgi

---------------------
- parts/5:
- text
# ✅ Tebrikler : Doğru ve Yanlış Sayılan Değerler

JavaScript her değeri doğru (truthy) ya da yanlış (falsy) kabul eder. Yanlış sayılanlar
``false``, ``0``, ``""``, ``null``, ``undefined`` ve ``NaN``'dır. Geri kalan her şey
doğrudur; ``"0"`` metni ve ``" "`` bile doğru kabul edilir.

<code-view name="main.js" language="javascript">
console.log(Boolean(0), Boolean(""), Boolean("0"));
console.log(Boolean(1), Boolean(" "), Boolean([]));
</code-view>

<code-view name="Terminal" language="bash">
false false true
true true true
</code-view>

# 🎯 6. Görev

İki satır ``false true`` ve ``true false`` yazdıran programı yazar mısın?

- files/main.js/.block
// 0 sayısı yanlış, 1 sayısı doğrudur
console.log(Boolean(<<< ❓ >>>), Boolean("0"));
console.log(Boolean(<<< ❓ >>>), Boolean(""));
---------------------
- tests/0/output
false true
true false

---------------------
- parts/6:
- text
# ✅ Tebrikler : Varsayılan Değer Verme

Kullanıcı bir değer girmediyse onun yerine bir varsayılan kullanmak isteriz. ``||``
operatörü bu iş için en pratik araçtır: sol taraf yanlışsa sağ taraftaki yedek değer gelir.

<code-view name="main.js" language="javascript">
let kullanıcıAdı = "";
let ad = kullanıcıAdı || "Misafir";
console.log("Merhaba", ad);
</code-view>

<code-view name="Terminal" language="bash">
Merhaba Misafir
</code-view>

# 🎯 7. Görev

Adı girilmemişse ``Merhaba Misafir`` yazdıran programı yazar mısın?

- files/main.js/.block
// ad boşsa yedek değer verir misin?
let kullanıcıAdı = "";
let ad = kullanıcıAdı <<< ❓ >>> "Misafir";
console.log("Merhaba", ad);
---------------------
- tests/0/output
Merhaba Misafir

---------------------
- tests/1/files/main.js/.block
// ad boşsa yedek değer verir misin?
let kullanıcıAdı = "Ayşe";
let ad = kullanıcıAdı <<< ❓ >>> "Misafir";
console.log("Merhaba", ad);
- tests/1/output
Merhaba Ayşe

---------------------
- parts/7:
- text
# ✅ Tebrikler : ``??`` (null Birleştirme)

``??`` operatörü yalnızca **null** ve **undefined** için devreye girer. ``0``, ``""`` ve
``false`` gibi değerleri geçerli sayar. Bu yüzden ``0 ?? 99`` sonucu ``0``'dır.

<code-view name="main.js" language="javascript">
let hiç = null;
let tanımsız;
console.log(hiç ?? "varsayılan");
console.log(tanımsız ?? "varsayılan");
console.log(0 ?? 99);
</code-view>

<code-view name="Terminal" language="bash">
varsayılan
varsayılan
0
</code-view>

# 🎯 8. Görev

``varsayılan``, ``varsayılan`` ve ``0`` yazdıran programı yazar mısın?

- files/main.js/.block
// sadece null ve undefined'da yedek değer verir misin?
let hiç = null;
let tanımsız;
console.log(hiç <<< ❓ >>> "varsayılan");
console.log(tanımsız <<< ❓ >>> "varsayılan");
console.log(0 <<< ❓ >>> 99);
---------------------
- tests/0/output
varsayılan
varsayılan
0

---------------------
- parts/8:
- text
# ✅ Tebrikler : ``??`` ve ``||`` Farkı

``??`` sadece null ya da undefined gördüğünde devreye girer, ``||`` ise tüm yanlış
değerlerde. Bu yüzden ``0`` ve ``""`` korunmak istendiğinde ``??`` kullanılır. ``0 ?? 5``
``0`` verirken ``0 || 5`` ``5`` verir.

<code-view name="main.js" language="javascript">
let sıfır = 0;
let metin = "";
console.log(sıfır ?? 5);
console.log(sıfır || 5);
console.log(metin || "boş");
</code-view>

<code-view name="Terminal" language="bash">
0
5
boş
</code-view>

# 🎯 9. Görev

``0``, ``5`` ve ``boş`` yazdıran programı yazar mısın?

- files/main.js/.block
// ?? geçerli değerleri korur, || onları da ezer
let sıfır = 0;
console.log(sıfır <<< ❓ >>> 5);
console.log(sıfır <<< ❓ >>> 5);

let metin = "";
console.log(metin <<< ❓ >>> "boş");
---------------------
- tests/0/output
0
5
boş

---------------------
- tests/1/files/main.js/.block
// ?? geçerli değerleri korur, || onları da ezer
let sıfır = 0;
console.log(sıfır <<< ❓ >>> 8);
console.log(sıfır <<< ❓ >>> 8);

let metin = "";
console.log(metin <<< ❓ >>> "boş");
- tests/1/output
0
8
boş

---------------------
- parts/9:
- text
# ✅ Tebrikler : Nesnede Eksik Özellik

Bir nesnede olmayan özelliğin değeri ``undefined`` olur. ``??`` ile bu eksik alana hemen
bir varsayılan değer verebiliriz. Böylece ekrana ``undefined`` yazmak yerine anlamlı bir
metin çıkar.

<code-view name="main.js" language="javascript">
let kullanıcı = { ad: "Ali" };
console.log(kullanıcı.ad ?? "Bilinmiyor");
console.log(kullanıcı.soyad ?? "Bilinmiyor");
</code-view>

<code-view name="Terminal" language="bash">
Ali
Bilinmiyor
</code-view>

# 🎯 10. Görev

``Ali`` ve ``Bilinmiyor`` yazdıran programı yazar mısın?

- files/main.js/.block
// eksik soyad için varsayılan değer verir misin?
let kullanıcı = { ad: "Ali" };
console.log(kullanıcı.ad <<< ❓ >>> "Bilinmiyor");
console.log(kullanıcı.soyad <<< ❓ >>> "Bilinmiyor");
---------------------
- tests/0/output
Ali
Bilinmiyor

---------------------
- tests/1/files/main.js/.block
// eksik soyad için varsayılan değer verir misin?
let kullanıcı = { ad: "Zeynep", soyad: "Kaya" };
console.log(kullanıcı.ad <<< ❓ >>> "Bilinmiyor");
console.log(kullanıcı.soyad <<< ❓ >>> "Bilinmiyor");
- tests/1/output
Zeynep
Kaya

---------------------
- parts/10:
- text
# ✅ Tebrikler : ``!!`` ile Boolean'a Çevirme

``!`` operatörü sonucu boolean yapar; iki kere kullanınca (``!!``) değer bozulmadan sadece
türü ``boolean`` olur. ``Boolean()`` fonksiyonu da tam olarak aynı işi yapar.

<code-view name="main.js" language="javascript">
console.log(!!"0");
console.log(!!0);
console.log(typeof !!"merhaba");
</code-view>

<code-view name="Terminal" language="bash">
true
false
boolean
</code-view>

# 🎯 11. Görev

``true``, ``false`` ve ``boolean`` yazdıran programı yazar mısın?

- files/main.js/.block
// değeri boolean'a çevirir misin?
console.log(<<< ❓ >>>"0");
console.log(<<< ❓ >>>0);
console.log(typeof <<< ❓ >>>"merhaba");
---------------------
- tests/0/output
true
false
boolean

---------------------
- parts/11:
- text
# 🏆 Mini Tekrar

Öğrendiklerini birleştirelim: eksik adı ``||`` ile, eksik yaşı ``??`` ile dolduralım.
``ad`` boş metin olduğu için yerine ``Misafir`` gelir. ``yaş`` ise ``0`` olduğu için
``??`` onu geçerli sayar ve korur.

<code-view name="main.js" language="javascript">
let kullanıcı = { ad: "", yaş: 0 };
let ad = kullanıcı.ad || "Misafir";
let yaş = kullanıcı.yaş ?? 18;
console.log(ad, yaş);
</code-view>

<code-view name="Terminal" language="bash">
Misafir 0
</code-view>

# 🎯 12. Görev

``Misafir 0`` yazdıran programı yazar mısın?

- files/main.js/.block
// ad boşsa "Misafir", yaş yoksa 18 olsun
let kullanıcı = { ad: "", yaş: 0 };
let ad = kullanıcı.ad <<< ❓ >>> "Misafir";
let yaş = kullanıcı.yaş <<< ❓ >>> 18;
console.log(ad, yaş);
---------------------
- tests/0/output
Misafir 0

---------------------
- tests/1/files/main.js/.block
// ad boşsa "Misafir", yaş yoksa 18 olsun
let kullanıcı = { ad: "Ali", yaş: null };
let ad = kullanıcı.ad <<< ❓ >>> "Misafir";
let yaş = kullanıcı.yaş <<< ❓ >>> 18;
console.log(ad, yaş);
- tests/1/output
Ali 18

---------------------
