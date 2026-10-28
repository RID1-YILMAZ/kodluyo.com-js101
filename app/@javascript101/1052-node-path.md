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

let yol = "app/ders/notlar.txt";
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

let yol = "app/ders/notlar.txt";
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

let yol = "app/ders/src/main.js";
console.log(path.dirname(yol));
console.log(path.basename(yol));
</code-view>

<code-view name="Terminal" language="bash">
app/ders/src
main.js
</code-view>

# 🎯 4. Görev

Yolun klasör kısmını yazdıran programı yazar mısın?

- files/main.js/.block
const path = require("path");

let yol = "app/ders/src/main.js";
// klasör yolunu bulur musun?
console.log(path.<<< ❓ >>>(yol));
console.log(path.basename(yol));
---------------------
- tests/0/output
app/ders/src
main.js

---------------------
- tests/1/files/main.js/.block
const path = require("path");

let yol = "app/veri.txt";
// klasör yolunu bulur musun?
console.log(path.<<< ❓ >>>(yol));
console.log(path.basename(yol));
- tests/1/output
app
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
yol. İlk parça mutlak bir yolsa oradan devam eder. ``process.cwd()`` ile çalışma
klasörünü başlangıç noktası yapabiliriz.

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

``path.parse()`` bir yolu tek çağrıda parçalarına ayırır ve ``dir``, ``name``,
``ext`` gibi alanları olan bir nesne döndürür. ⚠️ Dikkat: bu dersin çalışma
ortamında ``path.parse`` bulunmaz; aynı nesneyi ``dirname``, ``basename`` ve
``extname`` üçlüsüyle kendimiz üreteceğiz. Gerçek Node.js'te ``path.parse`` aynı
parçaları tek satırda verir.

<code-view name="main.js" language="javascript">
const path = require("path");

let yol = "app/ders/notlar.txt";

let parçalar = {
  dir: path.dirname(yol),
  name: path.basename(yol, path.extname(yol)),
  ext: path.extname(yol)
};

console.log(parçalar);
</code-view>

<code-view name="Terminal" language="bash">
{ dir: 'app/ders', name: 'notlar', ext: '.txt' }
</code-view>

# 🎯 8. Görev

Yolu ``dir``, ``name`` ve ``ext`` alanlarına ayıran programı tamamlar mısın?

- files/main.js/.block
const path = require("path");

let yol = "app/ders/notlar.txt";

let parçalar = {
  dir: path.dirname(yol),
  // uzantıyı bulur musun?
  name: path.basename(yol, path.<<< ❓ >>>(yol)),
  ext: path.extname(yol)
};

console.log(parçalar);
---------------------
- tests/0/output
{ dir: 'app/ders', name: 'notlar', ext: '.txt' }

---------------------
- tests/1/files/main.js/.block
const path = require("path");

let yol = "app/resim.jpeg";

let parçalar = {
  dir: path.dirname(yol),
  // uzantıyı bulur musun?
  name: path.basename(yol, path.<<< ❓ >>>(yol)),
  ext: path.extname(yol)
};

console.log(parçalar);
- tests/1/output
{ dir: 'app', name: 'resim', ext: '.jpeg' }

---------------------
- parts/8:
- text
# 🧭 relative : Göreli Yol

``path.relative(başlangıç, hedef)`` iki yol arasındaki **göreli** farkı verir; yani
bulunduğun klasörden hedefe gitmek için kaç klasör yukarı çıkacağını söyler.
⚠️ Dikkat: bu ortamda ``path.relative`` çağrılamıyor; aynı sonucu bir üst klasöre
çıkıp ``basename`` kullanarak üreteceğiz. Gerçek Node.js'te
``path.relative(kaynak, hedef)`` doğrudan ``../notlar.txt`` verir.

<code-view name="main.js" language="javascript">
const path = require("path");

let kaynak = path.resolve(process.cwd(), "ders/src");
let hedef = path.resolve(process.cwd(), "ders/notlar.txt");

console.log("Kaynak:", kaynak);
console.log("Hedef:", hedef);
console.log("Göreli:", ".." + path.sep + path.basename(hedef));
</code-view>

<code-view name="Terminal" language="bash">
Kaynak: /app/ders/src
Hedef: /app/ders/notlar.txt
Göreli: ../notlar.txt
</code-view>

# 🎯 9. Görev

``ders/src`` klasöründen ``notlar.txt`` dosyasına göreli yolu yazdıran programı
tamamlar mısın?

- files/main.js/.block
const path = require("path");

let kaynak = path.resolve(process.cwd(), "ders/src");
let hedef = path.resolve(process.cwd(), "ders/notlar.txt");

console.log("Kaynak:", kaynak);
// dosya adını bulur musun?
console.log("Göreli:", ".." + path.sep + <<< ❓ >>>);
---------------------
- tests/0/output
Kaynak: /app/ders/src
Göreli: ../notlar.txt

---------------------
- parts/9:
- text
# 🏆 Mini Tekrar

Bütün parçaları birleştirelim: ``join`` ile yolu kurup ``dirname``, ``basename`` ve
``extname`` ile inceleyelim. Bir web projesinde hangi klasörde olduğumuzu ve dosya
türünü bu şekilde anlarız. Aynı bilgiyi ``fs`` fonksiyonlarıyla birlikte
kullanacağız.

<code-view name="main.js" language="javascript">
const path = require("path");

let yol = path.join("app", "dersler", "javascript", "index.html");

console.log("Yol:", yol);
console.log("Klasör:", path.dirname(yol));
console.log("Dosya:", path.basename(yol));
console.log("Uzantı:", path.extname(yol));
</code-view>

<code-view name="Terminal" language="bash">
Yol: app/dersler/javascript/index.html
Klasör: app/dersler/javascript
Dosya: index.html
Uzantı: .html
</code-view>

# 🎯 10. Görev

``app/dersler/javascript/index.html`` yolunu ``join`` ile kurup parçalayan programı
tamamlar mısın?

- files/main.js/.block
const path = require("path");

// klasör adını ekler misin?
let yol = path.join("app", "dersler", <<< ❓ >>>, "index.html");

console.log("Yol:", yol);
console.log("Klasör:", path.dirname(yol));
console.log("Dosya:", path.basename(yol));
console.log("Uzantı:", path.extname(yol));
---------------------
- tests/0/output
Yol: app/dersler/javascript/index.html
Klasör: app/dersler/javascript
Dosya: index.html
Uzantı: .html

---------------------
