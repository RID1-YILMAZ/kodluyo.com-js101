# tools/ — JavaScript 101 ders araçları

Bu klasör, `app/@javascript101/` kursunun içeriğini üretmek ve doğrulamak için kullanılan
yardımcı araçları barındırır. Uygulamanın çalışması için gerekli değildir.

## Dosyalar

| Dosya | Açıklama |
|---|---|
| `javascript101-spec.md` | Ders yazım şartnamesi (format, üslup, kurallar) |
| `verify-lessons.js` | Dersleri Dion ile ayrıştırır, örnekleri ve testleri gerçek runner ile çalıştırır |
| `solutions/<ders>.json` | Her partın `<<< ❓ >>>` alanlarına yazılacak cevaplar |

## Doğrulama

```bash
# tüm kurs
node tools/verify-lessons.js

# tek ders
node tools/verify-lessons.js app/@javascript101/1051-node-fs.md

# yalnızca şema (örnek/test çalıştırmadan)
node tools/verify-lessons.js --structure-only

# testleri atla, sadece örnekleri çalıştır
node tools/verify-lessons.js --no-tests
```

Araç şunları denetler:

1. **Dion şeması** — front matter, `parts/N`, `files`, `tests`, editable bloklar,
   test çıktısının sonundaki boş satır.
2. **Örnekler** — her `<code-view>` kaynağı + `Terminal` çifti `app/source/javascript-runner.js`
   ile çalıştırılır ve çıktı birebir karşılaştırılır (çok dosyalı Node.js örnekleri dahil).
3. **Testler** — `solutions/` içindeki cevaplarla blok doldurulur, çalıştırılır ve
   `tests/N/output` ile karşılaştırılır. Platformun `Terminal` panelindeki
   (`app/source/terminal.js`) davranışının aynısı taklit edilir.

Hedef: `0 hata`. Değişiklikten sonra bu komutu çalıştırmadan ders dosyalarını gönderme.
