<div align="center">

# ⌨️ kodluyo.com

**Tarayıcıda çalışan, oyunlaştırılmış programlama eğitimi.**
Kurulum yok, hesap yok: sayfayı aç, kodu yaz, çalıştır.

[Canlı site](https://kodluyo.com) · [JavaScript 101 demosu](https://rid1-yilmaz.github.io/kodluyo.com-js101/) · [Kurslar](#-kurslar) · [Yerelde çalıştırma](#-yerelde-çalıştırma) · [Katkı](#-katkı)

![Lisans: MIT](https://img.shields.io/badge/lisans-MIT-blue)
![Python](https://img.shields.io/badge/python-3-3776AB?logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-node.js-F7DF1E?logo=javascript&logoColor=black)

</div>

---

## 📖 Nedir?

**kodluyo.com**, programlama öğrenmeye yeni başlayanlar için hazırlanmış bir web uygulamasıdır.
Ders sayfası üç panelden oluşur: solda **açıklama**, ortada **kod editörü**, altta **terminal**.
Kullanıcı dersin istediği kodu yazar, `F8` (veya ▶) ile çalıştırır ve çıktıyı gerçek bir terminal
gibi görür. Doğru cevap verildiğinde ders otomatik olarak bir sonraki bölüme geçer ve yıldız kazanılır.

Kod **tarayıcının içinde** çalışır:

| Dil | Çalıştırıcı | Nerede |
|---|---|---|
| Python 3 | [Skulpt](https://skulpt.org) | `app/api-python-skulpt.html` |
| JavaScript / Node.js | Projeye ait mini Node.js ortamı | `app/api-javascript.html` |

Sunucu tarafındaki PHP **yalnızca** ders dosyasını okumak ve "sıradaki ders"i bulmak için vardır;
derleme/yorumlama tamamen istemcide yapılır. Bu sayede site sunucusuz (statik olarak) da
yayınlanabilir — bkz. [GitHub Pages demosu](#-github-pages-demosu).

## ✨ Özellikler

- 🎮 **Oyunlaştırma** — her ders bir görev; çözünce `★` kazanılır ve ilerleme `localStorage`'da saklanır.
- 🧠 **Monaco editörü** — VS Code'un editörü; satır numaraları, sözdizimi renklendirme, otomatik tamamlama.
- 💻 **xterm.js terminali** — gerçek terminal görünümü, renkli çıktı, yazdırma/indirme.
- 🔒 **Düzenlenebilir bloklar** — ders dosyası hangi satırların yazılabilir olduğunu `<<< ❓ >>>` ile belirler;
  öğrenci yalnızca istenen yeri düzenler (Monaco `constrained-editor-plugin`).
- 📦 **Çoklu dosya desteği** — `main.js` + `selam.js` gibi birden fazla dosyayla Node.js örnekleri.
- 🖱️ **Kodsuz dersler** — bazı dersler (ör. `1001-merhaba-dünya-terminal`) editör yerine yalnızca
  terminal kullanır; kullanıcı komutu kendisi yazar.
- 📱 **Tek sayfa, tek bağımlılık yok** — kurulum, hesap veya API anahtarı gerekmez.

## 📚 Kurslar

### `@javascript101` — JavaScript ve Node.js (32 ders)

| Grup | Dersler |
|---|---|
| **console.log** | Merhaba Dünya · Çoklu Değer Yazdırma · Kaçış Karakterleri ve Uygulama |
| **Değişkenler** | `number` tam sayı · `number` ondalıklı · `bigint` · `boolean` · `string` · `string` (devam) |
| **Koleksiyonlar** | `Set` · Değiştirilemez diziler (`Object.freeze`) · `Array` · `Array` metotları · `Object` / `Map` |
| **Operatörler** | Aritmetik · Karşılaştırma · Mantıksal · Bitsel · Atama · Aitlik (`in`) · Kimlik (`===`) |
| **Koşullar / Döngüler / Fonksiyonlar** | `if`-`else`-`switch` · `while` · `for` · `function` · Ok fonksiyonlar · `try`-`catch` |
| **Node.js** | `require` · `fs` · `path` · `process` · `module.exports` |

Kurs toplam **352 bölüm**, **352 çalışan örnek** ve **538 otomatik test** içerir.
Her bölüm şu akışı izler: *açıklama → örnek (`main.js` + `Terminal` çıktısı) → 🎯 görev → test(ler)*.

### `@python101` — Python 3 (25 ders)

`Merhaba Dünya`'dan başlayıp sayılar, metinler, listeler, sözlükler, operatörler, koşullar,
döngüler ve fonksiyonlara kadar ilerler. Arayüz dili gibi içerik dili de Türkçedir.

## 🗂️ Depo yapısı

```
.
├── index.html                  # anasayfa (kurs kartları)
├── app/
│   ├── index.php               # uygulama kabuğu (dile göre runner seçer)
│   ├── frame.php               # kurs sayfası kabuğu (/app/@kurs/)
│   ├── app.php                 # ders sayfası: .md dosyasını okur, sıradakini bulur
│   ├── .htaccess               # /app/@kurs/ders → app.php yönlendirmesi
│   ├── api-javascript.html     # JavaScript/Node.js çalıştırıcı (iframe)
│   ├── api-python-skulpt.html  # Python/Skulpt çalıştırıcı (iframe)
│   ├── skulpt.js               # Skulpt derleyicisi
│   ├── source/                 # editör, terminal, JavaScript runner, görseller
│   ├── views/                  # panel, ders listesi, tema
│   ├── library/                # monaco, xterm, marked, dion, jQuery, highlight.js…
│   ├── @python101/             # 25 ders (Dion formatında .md)
│   └── @javascript101/         # 32 ders (Dion formatında .md)
├── tools/                      # ders doğrulama ve statik site üreticisi
├── python101.png               # kurs kapak görseli
├── javascript101.svg           # kurs kapak görseli
└── LICENSE                     # MIT
```

## 🚀 Yerelde çalıştırma

Site PHP tabanlıdır ve URL'leri `.htaccess` ile yönlendirir. En kolay yol, proje kökünü bir
Apache + PHP ortamına (XAMPP, Laragon, MAMP, `php-apache` vb.) koymaktır:

```bash
# proje kökünü web sunucusunun kök dizinine kopyalayın, sonra:
http://localhost/
http://localhost/app/@javascript101/
```

> ℹ️ `php -S` (PHP'nin yerleşik sunucusu) `.htaccess` dosyalarını okumaz; bu yüzden
> `php -S localhost:8000` ile `/app/@kurs/ders` gibi adresler çalışmaz. Hızlı bir önizleme
> için aşağıdaki statik sürümü kullanın.

### Statik önizleme (PHP olmadan)

```bash
node tools/build-pages.js      # statik siteyi docs/ içine üretir
npx serve docs                 # ya da: python3 -m http.server -d docs 8080
```

Statik sürümde dersler dosya olarak değil, sayfaya gömülü olarak gelir; yönlendirme ve
"sonraki ders" bağlantıları JavaScript ile kurulur. Python ve JavaScript çalıştırıcıları
zaten tarayıcıda çalıştığı için site tamamen sunucusuz çalışır.

## 🌐 GitHub Pages demosu

`tools/build-pages.js`, uygulamayı PHP'siz çalışan statik bir siteye dönüştürür:

- her ders için `/app/@kurs/<ders>/index.html` üretir (ders içeriği sayfaya gömülür),
- kurs listelerini ve anasayfayı kopyalar,
- `app/library`, `app/views`, `app/source` ve iki çalıştırıcıyı olduğu gibi taşır,
- GitHub Pages'in Jekyll işlemesini kapatmak için `.nojekyll` ekler,
- üretilen tüm sayfalarda yerel bağlantıların/varlıkların var olduğunu doğrular.

```bash
node tools/build-pages.js
# çıktı: docs/  (git'e eklenmez — .gitignore içinde)
```

Yayınlamak için `docs/` içeriği bir `gh-pages` dalına gönderilir ve depo ayarlarından
**Settings → Pages → Source: Deploy from a branch → `gh-pages` / (root)** seçilir:

```bash
git worktree add /tmp/gh-pages --detach
cd /tmp/gh-pages && git checkout --orphan gh-pages
git rm -rf . && cp -r <proje>/docs/. . && git add -A
git commit -m "GitHub Pages: statik site" && git push <remote> gh-pages
```

Mevcut demo: **https://rid1-yilmaz.github.io/kodluyo.com-js101/**

## 📝 Ders formatı

Dersler [Dion](https://github.com/HasanDelibas/dion) adlı küçük bir işaretleme dilinde yazılır.
Dosya adının sayısal öneki sıralamayı belirler (`1000-`, `1010-`, `1014-0-` …).

```markdown
- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "👋 Merhaba Dünya"
- run = "node main.js"

- parts/0:
- text
# 🎯 **console.log** : Ekrana Yazdırma

Metni çift tırnak içine yazarız.

<code-view name="main.js" language="javascript">
console.log("Merhaba Dünya");
</code-view>

<code-view name="Terminal" language="bash">
Merhaba Dünya
</code-view>

# 🎯 1. Görev

Terminale ``Merhaba Dünya`` yazdıran programı yazar mısın?

- files/main.js/.block
console.log("<<< ❓ >>>");
---------------------
- tests/0/output
Merhaba Dünya

---------------------
```

- `<<< ❓ >>>` → öğrencinin dolduracağı boşluk (düzenlenebilir blok).
- `tests/N/output` → beklenen terminal çıktısı; platform bunu **birebir** karşılaştırır.
- `files/<dosya>/.block` → aynı bölümde birden fazla dosya (`main.js`, `selam.js` …) tanımlanabilir.

## ✅ Doğrulama

Ders dosyalarına dokunduktan sonra testleri çalıştırmadan göndermeyin:

```bash
node tools/verify-lessons.js                 # tüm JavaScript 101 kursu
node tools/verify-lessons.js app/@javascript101/1051-node-fs.md   # tek ders
node tools/verify-lessons.js --structure-only                     # yalnızca şema
```

Araç (1) Dion şemasını, (2) her örneği gerçek runner ile çalıştırıp `Terminal` çıktısıyla
karşılaştırmayı, (3) her testi `tools/solutions/*.json` cevaplarıyla doldurup beklenen
çıktıya karşı denetlemeyi yapar. Hedef: **0 hata**.

## 🧩 Yeni ders ekleme

1. `app/@<kurs>/` içine sıradaki numarayla bir `.md` dosyası ekleyin
   (ör. `app/@javascript101/1055-node-os.md`).
2. Dosyanın başlığına front matter yazın (`language`, `title`, `run`, `show_*`).
3. Bölümleri `parts/N`, örnekleri `<code-view>`, görevleri `<<< ❓ >>>`, testleri `tests/N/output` ile tanımlayın.
4. Kurs sayfasındaki (`app/@<kurs>/index.html`) ilgili gruba kart ekleyin.
5. `node tools/verify-lessons.js` ile doğrulayın.

## 🤝 Katkı

1. Depoyu forklayın, `main`'den bir dal açın: `feature/kisa-ad`.
2. Değişikliğinizi yapın, `node tools/verify-lessons.js` çalıştırın.
3. Anlamlı commit mesajlarıyla gönderin ve `main`'e pull request açın.

Kod stili: mevcut dosyaların sadeliğini koruyun; yeni bağımlılık eklemekten kaçının.
Projede CDN'den yüklenen tek şeyler Monaco editörü, Asenac görünüm kütüphanesi ve
Skulpt'ın standart kütüphanesidir; geri kalan her şey `app/library` altında yereldir.

## 📄 Lisans

[MIT](LICENSE) © 2023 Hasan Delibaş

---

<div align="center">
<sub>Python tarafı <a href="https://skulpt.org">Skulpt</a>, editör <a href="https://microsoft.github.io/monaco-editor/">Monaco</a>, terminal <a href="https://xtermjs.org">xterm.js</a>, işaretleme dili <a href="https://github.com/HasanDelibas/dion">Dion</a> ile.</sub>
</div>
