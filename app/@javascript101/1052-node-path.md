- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "🧭 path : Dosya Yolları"
- run = "node main.js"

- parts/0:
- text
# 🧭 **path** : Dosya Yolları

Bir dosyanın yerini gösteren metne **yol** (path) denir: ``/app/ders/main.js`` gibi.
Windows yolları ters eğik çizgi (``\``), Linux ve macOS eğik çizgi (``/``) kullanır.
Bu farkları elle yönetmek yerine Node.js'in ``path`` modülünü kullanırız; modül
doğru ayırıcıyı kendisi seçer. ``require("path")`` ile çağırırız.

İlk ve en çok kullanılan fonksiyon ``path.join()``'dur: parçaları tek bir yola
birleştirir.

<code-view name="main.js" language="javascript">
const path = require("path");

console.log(path.join("ders", "main.js"));
</code-view>

<code-view name="Terminal" language="bash">
ders/main.js
</code-view>

# 🎯 1. Görev

``ders`` klasörü ile ``main.js`` dosyasını birleştiren programı yazar mısın?

- files/main.js/.block
const path = require("path");

// iki parçayı birleştirir misin?
console.log(path.join("ders", <<< ❓ >>>));
---------------------
- tests/0/output
ders/main.js

---------------------
- parts/1:
- text
# 🔗 join : Çok Parça ve ".."

``path.join()`` istediğin kadar parça alabilir ve aradaki fazla eğik çizgileri
temizler. ``..`` parçası "bir üst klasöre çık" demektir; ``join`` bunu hesaplayıp
yolu kısaltır. Böylece yolu elle metin birleştirerek değil, parçalar hâlinde yazarız.

<code-view name="main.js" language="javascript">
const path = require("path");

console.log(path.join("app", "ders", "main.js"));
console.log(path.join("app", "ders", "..", "veri.txt"));
</code-view>

<code-view name="Terminal" language="bash">
app/ders/main.js
app/veri.txt
</code-view>

# 🎯 2. Görev

``app/ders`` klasöründen bir üst klasöre çıkıp ``veri.txt`` yolunu üreten programı
yazar mısın?

- files/main.js/.block
const path = require("path");

// bir üst klasöre çıkar mısın?
console.log(path.join("app", "ders", <<< ❓ >>>, "veri.txt"));
---------------------
- tests/0/output
app/veri.txt

---------------------
- parts/2:
- text
# 📄 basename : Dosya Adı

``path.basename()`` yolun **sonundaki** dosya adını verir, klasörleri atar. İkinci
parametreye bir uzantı yazarsak o uzantıyı da siler. Uzantıyı bulmak için
``path.extname()`` kullanılır.

<code-view name="main.js" language="javascript">
const path = require("path");

let yol = "/app/ders/notlar.txt";
console.log(path.basename(yol));
console.log(path.basename(yol, ".txt"));
</code-view>

<code-view name="Terminal" language="bash">
notlar.txt
notlar
</code-view>

# 🎯 3. Görev

Yoldan dosya adını ve uzantısız adını yazdıran programı tamamlar mısın?

- files/main.js/.block
const path = require("path");

let yol = "/app/ders/notlar.txt";
console.log(path.basename(yol));
// uzantıyı siler misin?
console.log(path.basename(yol, <<< ❓ >>>));
---------------------
- tests/0/output
notlar.txt
notlar

---------------------
- parts/3:
- text
# 📁 dirname : Klasör Yolu

``path.dirname()`` dosya adını atar, geriye kalan klasör yolunu verir. ``basename``
ile birlikte kullanınca bir yolu ikiye ayırmış oluruz: klasör ve dosya. Dosyanın
bulunduğu klasöre başka dosyalar eklemek için çok kullanışlıdır.

<code-view name="main.js" language="javascript">
const path = require("path");

let yol = "/app/ders/src/main.js";
console.log(path.dirname(yol));
console.log(path.basename(yol));
</code-view>

<code-view name="Terminal" language="bash">
/app/ders/src
main.js
</code-view>

# 🎯 4. Görev

Yolun klasör kısmını yazdıran programı yazar mısın?

- files/main.js/.block
const path = require("path");

let yol = "/app/ders/src/main.js";
// klasör yolunu bulur musun?
console.log(path.<<< ❓ >>>(yol));
console.log(path.basename(yol));
---------------------
- tests/0/output
/app/ders/src
main.js

---------------------
- tests/1/files/main.js/.block
const path = require("path");

let yol = "/app/veri.txt";
// klasör yolunu bulur musun?
console.log(path.<<< ❓ >>>(yol));
console.log(path.basename(yol));
- tests/1/output
/app
veri.txt

---------------------
- parts/4:
- text
# 🏷️ extname : Uzantı

``path.extname()`` yolun uzantısını **nokta ile birlikte** verir. Uzantısı olmayan
bir dosyada boş metin (``""``) döner; bu yüzden uzantı var mı diye kontrol ederken
``!== ""`` karşılaştırması kullanırız.

<code-view name="main.js" language="javascript">
const path = require("path");

console.log("Uzantı:", path.extname("notlar.txt"));
console.log("Uzantı:", path.extname("resim.jpeg"));
console.log("Uzantı var mı?", path.extname("README") !== "");
</code-view>

<code-view name="Terminal" language="bash">
Uzantı: .txt
Uzantı: .jpeg
Uzantı var mı? false
</code-view>

# 🎯 5. Görev

``notlar.txt`` dosyasının uzantısını yazdıran programı yazar mısın?

- files/main.js/.block
const path = require("path");

// uzantıyı bulur musun?
console.log("Uzantı:", path.<<< ❓ >>>("notlar.txt"));
console.log("Uzantı var mı?", path.extname("README") !== "");
---------------------
- tests/0/output
Uzantı: .txt
Uzantı var mı? false

---------------------
- tests/1/files/main.js/.block
const path = require("path");

// uzantıyı bulur musun?
console.log("Uzantı:", path.<<< ❓ >>>("resim.jpeg"));
console.log("Uzantı var mı?", path.extname("README") !== "");
- tests/1/output
Uzantı: .jpeg
Uzantı var mı? false

---------------------
- parts/5:
- text
# 🧱 sep : Ayırıcı Karakter

``path.sep`` işletim sisteminin yol ayırıcısını verir: Linux ve macOS'ta ``/``,
Windows'ta ters eğik çizgi. Yolları elle birleştirirken ``"/"`` yazmak yerine
``path.sep`` kullanmak programı her sistemde çalışır hâle getirir. Zaten ``join``
bu ayırıcıyı bizim için koyar.

<code-view name="main.js" language="javascript">
const path = require("path");

console.log("Ayırıcı:", path.sep);
console.log("app" + path.sep + "main.js");
console.log(path.join("app", "main.js"));
</code-view>

<code-view name="Terminal" language="bash">
Ayırıcı: /
app/main.js
app/main.js
</code-view>

# 🎯 6. Görev

Sistemin ayırıcısını kullanarak ``app/main.js`` yazan programı yazar mısın?

- files/main.js/.block
const path = require("path");

console.log("Ayırıcı:", path.sep);
// ayırıcıyı kullanır mısın?
console.log("app" + <<< ❓ >>> + "main.js");
---------------------
- tests/0/output
Ayırıcı: /
app/main.js

---------------------
- parts/6:
- text
# 🎯 resolve : Mutlak Yol

Göreli (relative) bir yol tek başına nerede olduğumuzu söylemez. ``path.resolve()``
parçaları birleştirip **mutlak** (absolute) yol üretir; yani ``/`` ile başlayan tam
yol. Parçaları sağdan sola ekler ve ilk mutlak parçada durur. ``process.cwd()`` ile
çalışma klasörünü başlangıç noktası yapabiliriz.

<code-view name="main.js" language="javascript">
const path = require("path");

console.log(path.resolve(process.cwd(), "veri.txt"));
console.log(path.resolve("/app", "ders", "main.js"));
</code-view>

<code-view name="Terminal" language="bash">
/app/veri.txt
/app/ders/main.js
</code-view>

# 🎯 7. Görev

Çalışma klasörünü kullanarak ``veri.txt`` dosyasının mutlak yolunu üreten programı
yazar mısın?

- files/main.js/.block
const path = require("path");

// mutlak yolu üretir misin?
console.log(path.resolve(process.cwd(), <<< ❓ >>>));
---------------------
- tests/0/output
/app/veri.txt

---------------------
- parts/7:
- text
# 🔍 parse : Yolu Parçalara Ayırmak

``path.parse()`` bir yolu tek çağrıda parçalarına ayırır. Dönen nesnede ``root``
(kök), ``dir`` (klasör), ``base`` (dosya adı ve uzantı), ``ext`` (uzantı) ve ``name``
(uzantısız ad) alanları bulunur. ``dir``, ``basename`` ve ``extname``'i tek tek
çağırmak yerine tek satırda bütün parçaları elde ederiz.

<code-view name="main.js" language="javascript">
const path = require("path");

let parçalar = path.parse("/app/ders/notlar.txt");

console.log(parçalar);
console.log("Klasör:", parçalar.dir);
console.log("Dosya adı:", parçalar.name);
console.log("Uzantı:", parçalar.ext);
</code-view>

<code-view name="Terminal" language="bash">
{ root: '/', dir: '/app/ders', base: 'notlar.txt', ext: '.txt', name: 'notlar' }
Klasör: /app/ders
Dosya adı: notlar
Uzantı: .txt
</code-view>

# 🎯 8. Görev

Yolu ``path.parse`` ile parçalayıp uzantısız dosya adını yazdıran programı tamamlar
mısın?

- files/main.js/.block
const path = require("path");

let parçalar = path.parse("/app/ders/notlar.txt");

console.log(parçalar);
// uzantısız dosya adını yazar mısın?
console.log("Dosya adı:", parçalar.<<< ❓ >>>);
console.log("Uzantı:", parçalar.ext);
---------------------
- tests/0/output
{ root: '/', dir: '/app/ders', base: 'notlar.txt', ext: '.txt', name: 'notlar' }
Dosya adı: notlar
Uzantı: .txt

---------------------
- tests/1/files/main.js/.block
const path = require("path");

let parçalar = path.parse("/app/belge/rapor.pdf");

console.log(parçalar);
// uzantısız dosya adını yazar mısın?
console.log("Dosya adı:", parçalar.<<< ❓ >>>);
console.log("Uzantı:", parçalar.ext);
- tests/1/output
{ root: '/', dir: '/app/belge', base: 'rapor.pdf', ext: '.pdf', name: 'rapor' }
Dosya adı: rapor
Uzantı: .pdf

---------------------
- parts/8:
- text
# 🧭 relative : İki Yol Arasındaki Fark

``path.relative(başlangıç, hedef)`` iki yol arasındaki **göreli** yolu verir; yani
bulunduğun klasörden hedefe gitmek için kaç klasör yukarı çıkacağını söyler. Hedef
alt klasördeyse sonuç yalnızca klasör adı olur. Dosya taşıma ve bağlantı kurma
işlerinde çok işe yarar.

<code-view name="main.js" language="javascript">
const path = require("path");

console.log(path.relative("/app/ders/src", "/app/ders/veri.txt"));
console.log(path.relative("/app/ders/src", "/app/veri.txt"));
console.log(path.relative("/app/ders", "/app/ders/src"));
</code-view>

<code-view name="Terminal" language="bash">
../veri.txt
../../veri.txt
src
</code-view>

# 🎯 9. Görev

``ders/src`` klasöründen ``ders/veri.txt`` dosyasına göreli yolu yazdıran programı
tamamlar mısın?

- files/main.js/.block
const path = require("path");

// iki yol arasındaki göreli yolu bulur musun?
console.log(<<< ❓ >>>("/app/ders/src", "/app/ders/veri.txt"));
console.log(path.relative("/app/ders/src", "/app/veri.txt"));
---------------------
- tests/0/output
../veri.txt
../../veri.txt

---------------------
- tests/1/files/main.js/.block
const path = require("path");

// iki yol arasındaki göreli yolu bulur musun?
console.log(<<< ❓ >>>("/app/belge", "/app/belge/resim.png"));
console.log(path.relative("/app/belge", "/app"));
- tests/1/output
resim.png
..

---------------------
- parts/9:
- text
# ✅ isAbsolute : Mutlak Yol mu?

Bir yol ``/`` ile başlıyorsa **mutlak** (absolute), başlamıyorsa **göreli** (relative)
yoldur. ``path.isAbsolute()`` bu kontrolü yapar ve ``true`` / ``false`` döndürür.
Dosya işlemlerinden önce yolu kontrol etmek, yanlış klasörde dosya aramayı önler.

<code-view name="main.js" language="javascript">
const path = require("path");

console.log(path.isAbsolute("/app/veri.txt"));
console.log(path.isAbsolute("veri.txt"));
console.log(path.isAbsolute("./veri.txt"));
</code-view>

<code-view name="Terminal" language="bash">
true
false
false
</code-view>

# 🎯 10. Görev

Verilen yolun mutlak olup olmadığını yazdıran programı tamamlar mısın?

- files/main.js/.block
const path = require("path");

// mutlak yol mu diye kontrol eder misin?
console.log(path.<<< ❓ >>>("/app/veri.txt"));
console.log(path.isAbsolute("veri.txt"));
---------------------
- tests/0/output
true
false

---------------------
- tests/1/files/main.js/.block
const path = require("path");

// mutlak yol mu diye kontrol eder misin?
console.log(path.<<< ❓ >>>("/app/rapor.txt"));
console.log(path.isAbsolute("rapor.txt"));
- tests/1/output
true
false

---------------------
- parts/10:
- text
# 🧩 format : Parçalardan Yol

``path.format()`` ``parse``'ın tersini yapar: ``dir``, ``name`` ve ``ext`` alanları
olan bir nesneyi yeniden tek bir yol metnine çevirir. Yolu parçalayıp değiştirdikten
sonra geri birleştirmek istediğimizde kullanılır. ``dir`` verilmezse yalnızca dosya
adı döner.

<code-view name="main.js" language="javascript">
const path = require("path");

let parçalar = { dir: "/app/ders", name: "notlar", ext: ".txt" };
console.log(path.format(parçalar));

console.log(path.format({ dir: "/app/belge", name: "rapor", ext: ".pdf" }));
</code-view>

<code-view name="Terminal" language="bash">
/app/ders/notlar.txt
/app/belge/rapor.pdf
</code-view>

# 🎯 11. Görev

Parçalardan yeniden yol üreten programı tamamlar mısın?

- files/main.js/.block
const path = require("path");

let parçalar = { dir: "/app/ders", name: "notlar", ext: ".txt" };
// nesneyi yeniden yola çevirir misin?
console.log(path.<<< ❓ >>>(parçalar));

console.log(path.format({ dir: "/app/belge", name: "rapor", ext: ".pdf" }));
---------------------
- tests/0/output
/app/ders/notlar.txt
/app/belge/rapor.pdf

---------------------
- parts/11:
- text
# 🏆 Mini Tekrar

Bütün parçaları birleştirelim: ``join`` ile yolu kurup ``parse`` ile inceleyelim.
``parse`` bize kökü, klasörü, dosya adını ve uzantıyı tek seferde verir. Bir web
projesinde hangi klasörde olduğumuzu ve dosya türünü böyle anlarız. Aynı bilgiyi
``fs`` fonksiyonlarıyla birlikte kullanacağız.

<code-view name="main.js" language="javascript">
const path = require("path");

let yol = path.join("/app", "dersler", "javascript", "index.html");
let parçalar = path.parse(yol);

console.log("Yol:", yol);
console.log("Klasör:", parçalar.dir);
console.log("Dosya:", parçalar.base);
console.log("Uzantı:", parçalar.ext);
console.log("Mutlak mı?", path.isAbsolute(yol));
</code-view>

<code-view name="Terminal" language="bash">
Yol: /app/dersler/javascript/index.html
Klasör: /app/dersler/javascript
Dosya: index.html
Uzantı: .html
Mutlak mı? true
</code-view>

# 🎯 12. Görev

``/app/dersler/javascript/index.html`` yolunu kurup parçalayan programı tamamlar
mısın?

- files/main.js/.block
const path = require("path");

// klasör adını ekler misin?
let yol = path.join("/app", "dersler", <<< ❓ >>>, "index.html");
let parçalar = path.parse(yol);

console.log("Yol:", yol);
console.log("Klasör:", parçalar.dir);
console.log("Dosya:", parçalar.base);
console.log("Uzantı:", parçalar.ext);
console.log("Mutlak mı?", path.isAbsolute(yol));
---------------------
- tests/0/output
Yol: /app/dersler/javascript/index.html
Klasör: /app/dersler/javascript
Dosya: index.html
Uzantı: .html
Mutlak mı? true

---------------------
