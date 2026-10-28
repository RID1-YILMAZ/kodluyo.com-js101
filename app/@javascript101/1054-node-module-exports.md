- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "📦 module.exports : Modül Yazmak"
- run = "node main.js"

- parts/0:
- text
# 📦 **module.exports** : Kendi Modülünü Yazmak

Bir projede bütün kodu ``main.js`` içine yazmak karışıklık yaratır. Kodumuzu birden
fazla dosyaya böler, her dosyaya bir iş veririz. Bir dosyanın dışarıya açtığı şeylere
**modül** (module) denir; dışarıya açmak için ``module.exports`` ya da kısaca
``exports`` kullanırız. Diğer dosya bu modülü ``require("./dosya.js")`` ile çağırır.

``selam.js`` bir fonksiyonu dışa aktarıyor, ``main.js`` onu kullanıyor:

<code-view name="main.js" language="javascript">
// main.js
const { selamVer } = require("./selam.js");

selamVer("Ada");
</code-view>

<code-view name="selam.js" language="javascript">
// selam.js
function selamVer(ad) {
  console.log("Merhaba", ad);
}

exports.selamVer = selamVer;
</code-view>

<code-view name="Terminal" language="bash">
Merhaba Ada
</code-view>

# 🎯 1. Görev

``selam.js`` modülünü ``main.js`` içinden çağıran programı tamamlar mısın?

- files/main.js/.block
const { selamVer } = require(<<< ❓ >>>);

selamVer("Ada");
---------------------
- files/selam.js/.block
function selamVer(ad) {
  console.log("Merhaba", ad);
}

// fonksiyonu dışa aktarır mısın?
exports.selamVer = <<< ❓ >>>;
---------------------
- tests/0/output
Merhaba Ada

---------------------
- parts/1:
- text
# ✅ Tebrikler

``exports.`` ön ekiyle birden çok şeyi dışa aktarabiliriz: her satır bir isim ekler.
``main.js`` modülü bir nesne gibi çağırır ve ``hesap.topla``, ``hesap.çıkar`` gibi
nokta ile erişir. Bu şekilde bir dosyada küçük bir araç kutusu (utility) oluşur.

<code-view name="main.js" language="javascript">
// main.js
const hesap = require("./hesap.js");

console.log("Topla:", hesap.topla(3, 4));
console.log("Çıkar:", hesap.çıkar(10, 4));
</code-view>

<code-view name="hesap.js" language="javascript">
// hesap.js
function topla(a, b) {
  return a + b;
}

function çıkar(a, b) {
  return a - b;
}

exports.topla = topla;
exports.çıkar = çıkar;
</code-view>

<code-view name="Terminal" language="bash">
Topla: 7
Çıkar: 6
</code-view>

# 🎯 2. Görev

İki fonksiyonu dışa aktarıp kullanan programı tamamlar mısın?

- files/main.js/.block
const hesap = require("./hesap.js");

console.log("Topla:", hesap.topla(3, 4));
// çıkarma fonksiyonunu çağırır mısın?
console.log("Çıkar:", hesap.<<< ❓ >>>(10, 4));
---------------------
- files/hesap.js/.block
function topla(a, b) {
  // iki sayıyı toplar mısın?
  return <<< ❓ >>>;
}

function çıkar(a, b) {
  return a - b;
}

exports.topla = topla;
exports.çıkar = çıkar;
---------------------
- tests/0/output
Topla: 7
Çıkar: 6

---------------------
- tests/1/files/main.js/.block
const hesap = require("./hesap.js");

console.log("Topla:", hesap.topla(12, 8));
// çıkarma fonksiyonunu çağırır mısın?
console.log("Çıkar:", hesap.<<< ❓ >>>(9, 4));
- tests/1/output
Topla: 20
Çıkar: 5

---------------------
- parts/2:
- text
# 🧰 module.exports = { ... }

``exports.topla = topla`` satırlarını uzun bulursan tüm modülü tek seferde bir nesne
olarak da verebilirsin: ``module.exports = { topla, çarp }``. Buradaki kısa yazım
``topla: topla`` demektir. Artık ``exports`` yerine ``module.exports`` kullanıyoruz;
ikisi aynı nesneyi gösterir.

<code-view name="main.js" language="javascript">
// main.js
const hesap = require("./hesap.js");

console.log(hesap.topla(2, 3));
console.log(hesap.çarp(2, 3));
</code-view>

<code-view name="hesap.js" language="javascript">
// hesap.js
function topla(a, b) {
  return a + b;
}

function çarp(a, b) {
  return a * b;
}

module.exports = {
  topla: topla,
  çarp: çarp
};
</code-view>

<code-view name="Terminal" language="bash">
5
6
</code-view>

# 🎯 3. Görev

Modülü tek bir nesne olarak dışa aktaran programı tamamlar mısın?

- files/main.js/.block
const hesap = require(<<< ❓ >>>);

console.log(hesap.topla(2, 3));
console.log(hesap.çarp(2, 3));
---------------------
- files/hesap.js/.block
function topla(a, b) {
  return a + b;
}

function çarp(a, b) {
  return a * b;
}

module.exports = {
  topla: <<< ❓ >>>,
  çarp: çarp
};
---------------------
- tests/0/output
5
6

---------------------
- parts/3:
- text
# 🔢 Fonksiyon Export Etmek

Bir modül tek bir şey yapıyorsa doğrudan bir **fonksiyon** dışa aktarabilir.
``module.exports = function ...`` yazınca ``require`` doğrudan fonksiyonu döndürür;
artık nokta ile alan çağırmayız. Bu yöntem küçük yardımcı fonksiyonlar için çok temizdir.

<code-view name="main.js" language="javascript">
// main.js
const kare = require("./kare.js");

console.log("Kare:", kare(6));
</code-view>

<code-view name="kare.js" language="javascript">
// kare.js
module.exports = function (sayı) {
  return sayı * sayı;
};
</code-view>

<code-view name="Terminal" language="bash">
Kare: 36
</code-view>

# 🎯 4. Görev

Tek bir fonksiyonu dışa aktaran modülü tamamlar mısın?

- files/main.js/.block
const kare = require(<<< ❓ >>>);

console.log("Kare:", kare(6));
---------------------
- files/kare.js/.block
module.exports = function (sayı) {
  // sayının karesini alır mısın?
  return <<< ❓ >>>;
};
---------------------
- tests/0/output
Kare: 36

---------------------
- tests/1/files/main.js/.block
const kare = require(<<< ❓ >>>);

console.log("Kare:", kare(9));
- tests/1/output
Kare: 81

---------------------
- parts/4:
- text
# 🔁 require Önbelleği (Cache)

Bir modül ilk ``require`` çağrısında çalışır ve **hatırlanır** (cache). İkinci kez
``require`` ettiğimizde dosya yeniden çalışmaz, aynı nesne geri gelir. Bu yüzden
modül içindeki bir değişken iki kullanımda da aynı kalır. Test etmek için modülün
en üstüne bir ``console.log`` koyabiliriz.

<code-view name="main.js" language="javascript">
// main.js
const sayac = require("./sayac.js");
const sayac2 = require("./sayac.js");

console.log(sayac.artır());
console.log(sayac.artır());
console.log("Aynı modül mü?", sayac === sayac2);
</code-view>

<code-view name="sayac.js" language="javascript">
// sayac.js
console.log("sayac.js yüklendi");

let sayı = 0;

module.exports = {
  artır: function () {
    return ++sayı;
  }
};
</code-view>

<code-view name="Terminal" language="bash">
sayac.js yüklendi
1
2
Aynı modül mü? true
</code-view>

# 🎯 5. Görev

Aynı modülü ikinci kez çağırıp sayacı artıran programı tamamlar mısın?

- files/main.js/.block
const sayac = require("./sayac.js");
// aynı modülü bir kez daha çağırır mısın?
const sayac2 = <<< ❓ >>>;

console.log(sayac.artır());
console.log(sayac.artır());
console.log("Aynı modül mü?", sayac === sayac2);
---------------------
- files/sayac.js/.block
console.log("sayac.js yüklendi");

let sayı = 0;

module.exports = {
  artır: function () {
    // sayacı bir artırır mısın?
    return <<< ❓ >>>;
  }
};
---------------------
- tests/0/output
sayac.js yüklendi
1
2
Aynı modül mü? true

---------------------
- parts/5:
- text
# ⚠️ exports ve module.exports Farkı

``exports`` başlangıçta ``module.exports`` ile aynı nesneyi gösterir. Ama
``module.exports = { ... }`` yazdığında artık **yeni** bir nesne gösterir; eski
``exports`` bağlantısı kopar. Bu yüzden ``module.exports``'u değiştirdikten sonra
``exports.`` ile ekleme yapmak işe yaramaz. Aşağıdaki modülde ``yarı`` fonksiyonu
bu yüzden görünmez.

<code-view name="main.js" language="javascript">
// main.js
const hesap = require("./hesap.js");

console.log(Object.keys(hesap));
console.log("yarı var mı?", hesap.yarı === undefined);
</code-view>

<code-view name="hesap.js" language="javascript">
// hesap.js
function ikiKat(n) {
  return n * 2;
}

module.exports = { ikiKat: ikiKat };

// Dikkat: module.exports yukarıda değişti, bu satır işe yaramaz.
exports.yarı = function (n) {
  return n / 2;
};
</code-view>

<code-view name="Terminal" language="bash">
[ 'ikiKat' ]
yarı var mı? true
</code-view>

# 🎯 6. Görev

Modülün yalnızca ``ikiKat`` fonksiyonunu taşımasını sağlar mısın?

- files/main.js/.block
const hesap = require("./hesap.js");

console.log(Object.keys(hesap));
// yarı fonksiyonu görünmüyor mu?
console.log("yarı var mı?", hesap.yarı <<< ❓ >>> undefined);
---------------------
- files/hesap.js/.block
function ikiKat(n) {
  return n * 2;
}

// tüm modülü ikiKat içeren nesne yapar mısın?
<<< ❓ >>>;

// Dikkat: module.exports yukarıda değişti, bu satır işe yaramaz.
exports.yarı = function (n) {
  return n / 2;
};
---------------------
- tests/0/output
[ 'ikiKat' ]
yarı var mı? true

---------------------
- parts/6:
- text
# 🚦 require.main === module

Bir dosya hem başka dosyadan ``require`` edilebilir hem de doğrudan çalıştırılabilir.
``require.main === module`` kontrolü "bu dosya doğrudan mı çalıştırıldı?" sorusunu
sorar. Doğrudan çalıştırıldığında ``true`` olur ve dosya kendi deneme kodunu çalıştırır;
``require`` ile çağrıldığında ise bu blok atlanır.

<code-view name="main.js" language="javascript">
// main.js
const { selamVer } = require("./selam.js");

selamVer("Ada");
</code-view>

<code-view name="selam.js" language="javascript">
// selam.js
function selamVer(ad) {
  console.log("Merhaba", ad);
}

module.exports = { selamVer };

// Bu dosya doğrudan çalıştırılırsa da çalışsın
if (require.main === module) {
  selamVer("Dünya");
}
</code-view>

<code-view name="Terminal" language="bash">
Merhaba Ada
</code-view>

# 🎯 7. Görev

Modülü doğrudan çalıştırma kontrolünü ekler misin?

- files/main.js/.block
const { selamVer } = require(<<< ❓ >>>);

selamVer("Ada");
---------------------
- files/selam.js/.block
function selamVer(ad) {
  console.log("Merhaba", ad);
}

module.exports = { selamVer };

// Bu dosya doğrudan çalıştırılırsa da çalışsın
if (<<< ❓ >>>) {
  selamVer("Dünya");
}
---------------------
- tests/0/output
Merhaba Ada

---------------------
- parts/7:
- text
# ⚙️ Ayar Modülü

Modüller yalnızca fonksiyon değil, veri de saklayabilir. Ayarları (dil, sürüm gibi)
bir nesnede toplayıp dışa aktarmak yaygın bir alışkanlıktır. ``main.js`` bu değerleri
nokta ile okur; değerleri değiştirmek için tek bir yeri düzenlemek yeterlidir.

<code-view name="ayar.js" language="javascript">
// ayar.js
module.exports = {
  dil: "Türkçe",
  sürüm: 2
};
</code-view>

<code-view name="main.js" language="javascript">
// main.js
const ayar = require("./ayar.js");

console.log("Dil:", ayar.dil);
console.log("Sürüm:", ayar.sürüm);
</code-view>

<code-view name="Terminal" language="bash">
Dil: Türkçe
Sürüm: 2
</code-view>

# 🎯 8. Görev

Ayar nesnesini dışa aktarıp kullanan programı tamamlar mısın?

- files/main.js/.block
const ayar = require("./ayar.js");

// dil bilgisini okur musun?
console.log("Dil:", ayar.<<< ❓ >>>);
console.log("Sürüm:", ayar.sürüm);
---------------------
- files/ayar.js/.block
// tüm ayarları dışa aktarır mısın?
module.exports = <<< ❓ >>>;
---------------------
- tests/0/output
Dil: Türkçe
Sürüm: 2

---------------------
- parts/8:
- text
# 🔗 Modüller Zinciri

Bir modül başka bir modülü ``require`` edebilir; böylece küçük parçalardan büyük
işler kurulur. ``hesap.js`` içindeki ``util.js``'i kullanıyor, ``main.js`` de
``hesap.js``'i kullanıyor. Her dosya yalnızca kendi işini bilir, bu da kodu
okunur ve test edilebilir yapar.

<code-view name="main.js" language="javascript">
// main.js
const { dörtKat } = require("./hesap.js");

console.log("Sonuç:", dörtKat(5));
</code-view>

<code-view name="util.js" language="javascript">
// util.js
function ikiKat(n) {
  return n * 2;
}

module.exports = { ikiKat };
</code-view>

<code-view name="hesap.js" language="javascript">
// hesap.js
const { ikiKat } = require("./util.js");

function dörtKat(n) {
  return ikiKat(n) * 2;
}

module.exports = { dörtKat };
</code-view>

<code-view name="Terminal" language="bash">
Sonuç: 20
</code-view>

# 🎯 9. Görev

Alt modülü kullanarak sayının dört katını hesaplayan programı tamamlar mısın?

- files/main.js/.block
const { dörtKat } = require(<<< ❓ >>>);

console.log("Sonuç:", dörtKat(5));
---------------------
- files/hesap.js/.block
const { ikiKat } = require("./util.js");

function dörtKat(n) {
  // önce iki katını al, sonra bir kez daha iki katına çıkar
  return <<< ❓ >>> * 2;
}

module.exports = { dörtKat };
---------------------
- files/util.js
function ikiKat(n) {
  return n * 2;
}

module.exports = { ikiKat };
---------------------
- tests/0/files/util.js
function ikiKat(n) {
  return n * 2;
}

module.exports = { ikiKat };
- tests/0/output
Sonuç: 20

---------------------
- tests/1/files/main.js/.block
const { dörtKat } = require(<<< ❓ >>>);

console.log("Sonuç:", dörtKat(3));
- tests/1/files/util.js
function ikiKat(n) {
  return n * 2;
}

module.exports = { ikiKat };
- tests/1/output
Sonuç: 12

---------------------
- parts/9:
- text
# 🏆 Mini Tekrar

Küçük bir matematik modülü yazalım. ``kare`` ve ``küp`` fonksiyonları tek bir nesnede
dışa aktarılıyor; ``main.js`` ikisini de kullanıyor. Kendi modüllerini yazmak,
kodunu dosyalara bölmek ve tekrar kullanmak için artık gereken her şeyi biliyorsun.

<code-view name="matematik.js" language="javascript">
// matematik.js
function kare(n) {
  return n * n;
}

function küp(n) {
  return n * n * n;
}

module.exports = { kare, küp };
</code-view>

<code-view name="main.js" language="javascript">
// main.js
const { kare, küp } = require("./matematik.js");

console.log("Kare:", kare(4));
console.log("Küp:", küp(2));
</code-view>

<code-view name="Terminal" language="bash">
Kare: 16
Küp: 8
</code-view>

# 🎯 10. Görev

İki fonksiyonu dışa aktaran matematik modülünü tamamlar mısın?

- files/main.js/.block
const { kare, küp } = require("./matematik.js");

console.log("Kare:", kare(4));
// küp fonksiyonunu çağırır mısın?
console.log("Küp:", <<< ❓ >>>(2));
---------------------
- files/matematik.js/.block
function kare(n) {
  return n * n;
}

function küp(n) {
  return n * n * n;
}

module.exports = { kare, <<< ❓ >>> };
---------------------
- tests/0/output
Kare: 16
Küp: 8

---------------------
