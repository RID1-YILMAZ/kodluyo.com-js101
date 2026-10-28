- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "🧾 Merhaba Dünya : Virgülle Çoklu Değer"
- run = "node main.js"

- parts/0:
- text
# 🎯 Birden Fazla Değer

``console.log`` fonksiyonuna virgülle ayırarak birden fazla değer verebiliriz.
Fonksiyon bütün değerleri **aynı satıra** yazar. Sıralama da verdiğimiz sırayla olur.

<code-view name="main.js" language="javascript">
console.log("Merhaba", "Dünya");
</code-view>

<code-view name="Terminal" language="bash">
Merhaba Dünya
</code-view>

# 🎯 1. Görev

Terminale ``Merhaba Dünya`` yazdıran programı yazar mısın? İki değeri ayrı ayrı ver.

- files/main.js/.block
// iki değeri virgülle ayırır mısın?
console.log("Merhaba", <<< ❓ >>>);
---------------------
- tests/0/output
Merhaba Dünya

---------------------
- parts/1:
- text
# ✅ Tebrikler

Virgülle verilen değerlerin arasına **otomatik olarak bir boşluk** konur. Sen boşluk
yazmasan da ``console.log`` değerleri tek boşlukla ayırır. Bu yüzden virgül, ``+`` ile
birleştirmekten daha kolaydır.

<code-view name="main.js" language="javascript">
console.log("bir", "iki", "üç");
</code-view>

<code-view name="Terminal" language="bash">
bir iki üç
</code-view>

# 🎯 2. Görev

Terminale ``bir iki üç`` yazdıran programı yazar mısın?

- files/main.js/.block
// üç değeri virgülle yazdırır mısın?
console.log(<<< ❓ >>>, "iki", "üç");
---------------------
- tests/0/output
bir iki üç

---------------------
- parts/2:
- text
# 🔢 Sayı ve Metin Birlikte

Sayılar tırnaksız, metinler tırnaklı yazılır; ama aynı ``console.log`` içinde yan yana
durabilirler. Araya yine otomatik olarak boşluk konur. Böylece cümle içinde sayı
kullanmak çok kolaylaşır.

<code-view name="main.js" language="javascript">
console.log("Kedi", 4, "ayaklıdır.");
</code-view>

<code-view name="Terminal" language="bash">
Kedi 4 ayaklıdır.
</code-view>

# 🎯 3. Görev

``Kedi 4 ayaklıdır.`` yazdıran programı yazar mısın?

- files/main.js/.block
// kedinin ayak sayısını yazdırır mısın?
console.log("Kedi", <<< ❓ >>>, "ayaklıdır.");
---------------------
- tests/0/output
Kedi 4 ayaklıdır.

---------------------
- parts/3:
- text
# 🧮 console.log İçinde Hesap

Virgülden sonra hesap yazabiliriz. JavaScript önce hesabı yapar, sonra sonucu yazdırır.
Böylece işlemin kendisini ve sonucunu tek satırda gösterebiliriz.

<code-view name="main.js" language="javascript">
console.log("2 + 3 =", 2 + 3);
</code-view>

<code-view name="Terminal" language="bash">
2 + 3 = 5
</code-view>

# 🎯 4. Görev

``2 + 3 = 5`` yazdıran programı yazar mısın?

- files/main.js/.block
// toplama işlemini console.log içinde yapar mısın?
console.log("2 + 3 =", 2 <<< ❓ >>> 3);
---------------------
- tests/0/output
2 + 3 = 5

---------------------
- tests/1/files/main.js/.block
// toplama işlemini console.log içinde yapar mısın?
console.log("10 + 5 =", 10 <<< ❓ >>> 5);
- tests/1/output
10 + 5 = 15

---------------------
- parts/4:
- text
# 📦 Değişkeni Araya Koymak

Değişkeni de değerlerin arasına koyabiliriz. Değişkenin içindeki değer yazdırılır.
Tırnak koymadığımız için JavaScript onu değişken olarak okur, adını değil değerini
yazdırır.

<code-view name="main.js" language="javascript">
let fiyat = 45;
console.log("Fiyat:", fiyat, "TL");
</code-view>

<code-view name="Terminal" language="bash">
Fiyat: 45 TL
</code-view>

# 🎯 5. Görev

``Fiyat: 45 TL`` yazdıran programı yazar mısın?

- files/main.js/.block
// fiyat değişkenini yazdırır mısın?
let fiyat = 45;
console.log("Fiyat:", <<< ❓ >>>, "TL");
---------------------
- tests/0/output
Fiyat: 45 TL

---------------------
- parts/5:
- text
# ⚖️ Virgül mü, Artı mı?

İki yöntem de çalışır ama farklıdır: virgül değerleri ayrı ayrı verir ve araya boşluk
koyar; ``+`` ise metinleri yapıştırır, boşluğu sen koyarsın. Aşağıdaki iki satırın
çıktısı da aynıdır.

<code-view name="main.js" language="javascript">
let ad = "Ayşe";
console.log("Merhaba", ad);
console.log("Merhaba " + ad);
</code-view>

<code-view name="Terminal" language="bash">
Merhaba Ayşe
Merhaba Ayşe
</code-view>

# 🎯 6. Görev

``Merhaba Ali`` satırını hem virgülle hem de ``+`` ile iki kez yazdıran programı yazar
mısın?

- files/main.js/.block
// aynı cümleyi iki yöntemle yazdırır mısın?
let ad = "Ali";
console.log("Merhaba", <<< ❓ >>>);
console.log("Merhaba " + ad);
---------------------
- tests/0/output
Merhaba Ali
Merhaba Ali

---------------------
- parts/6:
- text
# 🧾 Beş Değerli Satır

Değer sayısı ikiden fazla olabilir; istediğimiz kadar değeri virgülle ayırırız.
Böylece ``5 + 3 = 8`` gibi okunaklı satırlar kurarız.

<code-view name="main.js" language="javascript">
console.log(5, "+", 3, "=", 5 + 3);
</code-view>

<code-view name="Terminal" language="bash">
5 + 3 = 8
</code-view>

# 🎯 7. Görev

``5 + 3 = 8`` yazdıran programı yazar mısın?

- files/main.js/.block
// sonucu console.log içinde hesaplar mısın?
console.log(5, "+", 3, "=", 5 <<< ❓ >>> 3);
---------------------
- tests/0/output
5 + 3 = 8

---------------------
- tests/1/files/main.js/.block
// sonucu console.log içinde hesaplar mısın?
console.log(12, "+", 8, "=", 12 <<< ❓ >>> 8);
- tests/1/output
12 + 8 = 20

---------------------
- parts/7:
- text
# 🕳️ Boş console.log

``console.log()`` parantezine hiç değer vermezsek terminale sadece bir boş satır yazar.
Çıktı gruplarını birbirinden ayırmak için sıkça kullanılır.

<code-view name="main.js" language="javascript">
console.log("Üst satır");
console.log();
console.log("Alt satır");
</code-view>

<code-view name="Terminal" language="bash">
Üst satır

Alt satır
</code-view>

# 🎯 8. Görev

İki satırın arasına boş bir satır koyan programı yazar mısın?

- files/main.js/.block
// araya boş bir satır koyar mısın?
console.log("Üst satır");
<<< ❓ >>>
console.log("Alt satır");
---------------------
- tests/0/output
Üst satır

Alt satır

---------------------
- parts/8:
- text
# 💡 İpucu : %s ve %d

Metnin içine ``%s`` ve ``%d`` yer tutucuları koyabiliriz. ``%s`` yerine metin, ``%d``
yerine sayı yazılır. Uzun cümlelerde bu yöntem daha okunaklıdır.

<code-view name="main.js" language="javascript">
console.log("%s %d yaşındadır.", "Ayşe", 20);
</code-view>

<code-view name="Terminal" language="bash">
Ayşe 20 yaşındadır.
</code-view>

# 🎯 9. Görev

``Mehmet 20 yaşındadır.`` yazdıran programı yazar mısın?

- files/main.js/.block
// %s yerine adı yazdırır mısın?
console.log("%s %d yaşındadır.", <<< ❓ >>>, 20);
---------------------
- tests/0/output
Mehmet 20 yaşındadır.

---------------------
- parts/9:
- text
# 🛒 Alışveriş Fişi

Birkaç değeri virgülle vererek küçük bir fiş satırı oluşturalım. Değişkenlerle
hesap yapmak da burada işimize yarar.

<code-view name="main.js" language="javascript">
let ürün = "Kalem";
let adet = 3;
let fiyat = 12;
console.log(ürün, adet, "adet", fiyat * adet, "TL");
</code-view>

<code-view name="Terminal" language="bash">
Kalem 3 adet 36 TL
</code-view>

# 🎯 10. Görev

``Kalem 3 adet 36 TL`` yazdıran programı yazar mısın?

- files/main.js/.block
// toplam tutarı hesaplar mısın?
let ürün = "Kalem";
let adet = 3;
let fiyat = 12;
console.log(ürün, adet, "adet", fiyat <<< ❓ >>> adet, "TL");
---------------------
- tests/0/output
Kalem 3 adet 36 TL

---------------------
- tests/1/files/main.js/.block
// toplam tutarı hesaplar mısın?
let ürün = "Defter";
let adet = 4;
let fiyat = 25;
console.log(ürün, adet, "adet", fiyat <<< ❓ >>> adet, "TL");
- tests/1/output
Defter 4 adet 100 TL

---------------------
- parts/10:
- text
# 🏆 Mini Tekrar

Virgülü, otomatik boşluğu ve hesabı birleştirelim. Aşağıdaki örnek küçük bir tanıtım
kartı yazdırıyor.

<code-view name="main.js" language="javascript">
let ad = "Zeynep";
let yaş = 22;
console.log("Ad:", ad, "| Yaş:", yaş, "| Seneye:", yaş + 1);
</code-view>

<code-view name="Terminal" language="bash">
Ad: Zeynep | Yaş: 22 | Seneye: 23
</code-view>

# 🎯 11. Görev

``Ad: Zeynep | Yaş: 22 | Seneye: 23`` yazdıran programı yazar mısın?

- files/main.js/.block
// seneye kaç yaşında olacağını hesaplar mısın?
let ad = "Zeynep";
let yaş = 22;
console.log("Ad:", ad, "| Yaş:", yaş, "| Seneye:", yaş <<< ❓ >>> 1);
---------------------
- tests/0/output
Ad: Zeynep | Yaş: 22 | Seneye: 23

---------------------
- tests/1/files/main.js/.block
// seneye kaç yaşında olacağını hesaplar mısın?
let ad = "Mert";
let yaş = 35;
console.log("Ad:", ad, "| Yaş:", yaş, "| Seneye:", yaş <<< ❓ >>> 1);
- tests/1/output
Ad: Mert | Yaş: 35 | Seneye: 36

---------------------
