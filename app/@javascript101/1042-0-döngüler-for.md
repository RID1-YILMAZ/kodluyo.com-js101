- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "🔂 Döngüler : for"
- run = "node main.js"

- parts/0:
- text
# 🔂 **for** : 0'dan 9'a Yazdırma

``for`` döngüsü parantez içinde **üç** parça alır: başlangıç, koşul ve artış. Parçalar
noktalı virgülle ayrılır: ``for (let i = 0; i < 10; i++)``. ``i`` sıfırdan başlar, ``10``dan
küçük olduğu sürece döner ve her turda bir artar; yani ekrana ``0``dan ``9``a kadar yazar.

<code-view name="main.js" language="javascript">
for (let i = 0; i < 10; i++) {
  console.log(i);
}
</code-view>

<code-view name="Terminal" language="bash">
0
1
2
3
4
5
6
7
8
9
</code-view>

# 🎯 1. Görev

``0``dan ``9``a kadar olan sayıları alt alta yazdıran programı yazar mısın?

- files/main.js/.block
// 0'dan 9'a kadar yazdırır mısın?
for (let i = 0; i <<< ❓ >>> 10; i++) {
  console.log(i);
}
---------------------
- tests/0/output
0
1
2
3
4
5
6
7
8
9

---------------------
- tests/1/files/main.js/.block
// 0'dan 4'e kadar yazdırır mısın?
for (let i = 0; i <<< ❓ >>> 5; i++) {
  console.log(i);
}
- tests/1/output
0
1
2
3
4

---------------------
- parts/1:
- text
# ⏬ Geriye Doğru for

Artış kısmına ``i--`` yazarsak döngü geriye doğru sayar. Bu durumda koşulu da
``i >= 1`` yapmak gerekir; yoksa ``i`` küçülürken koşul hiç bozulmaz ve döngü bitmez.

<code-view name="main.js" language="javascript">
for (let i = 5; i >= 1; i--) {
  console.log(i);
}
console.log("Kalkış!");
</code-view>

<code-view name="Terminal" language="bash">
5
4
3
2
1
Kalkış!
</code-view>

# 🎯 2. Görev

``5``ten ``1``e kadar geriye sayan ve sonunda ``Kalkış!`` yazan programı yazar mısın?

- files/main.js/.block
// geriye doğru sayan koşulu tamamlar mısın?
for (let i = 5; i <<< ❓ >>> 1; i--) {
  console.log(i);
}
console.log("Kalkış!");
---------------------
- tests/0/output
5
4
3
2
1
Kalkış!

---------------------
- tests/1/files/main.js/.block
// geriye doğru sayan koşulu tamamlar mısın?
for (let i = 3; i <<< ❓ >>> 1; i--) {
  console.log(i);
}
console.log("Kalkış!");
- tests/1/output
3
2
1
Kalkış!

---------------------
- parts/2:
- text
# 🦘 Artış Adımı

Artış kısmı sadece ``i++`` olmak zorunda değildir. ``i += 2`` yazarsak döngü ikişer ikişer
ilerler ve sadece çift sayıları yazdırır. ``+=`` yerine ``-=`` ya da ``*=`` de yazabiliriz.

<code-view name="main.js" language="javascript">
for (let i = 0; i <= 10; i += 2) {
  console.log(i);
}
</code-view>

<code-view name="Terminal" language="bash">
0
2
4
6
8
10
</code-view>

# 🎯 3. Görev

``0``dan ``10``a kadar **ikişer ikişer** sayan programı yazar mısın?

- files/main.js/.block
// ikişer ikişer artırır mısın?
for (let i = 0; i <= 10; i <<< ❓ >>> 2) {
  console.log(i);
}
---------------------
- tests/0/output
0
2
4
6
8
10

---------------------
- tests/1/files/main.js/.block
// üçer üçer artırır mısın?
for (let i = 0; i <= 10; i <<< ❓ >>> 3) {
  console.log(i);
}
- tests/1/output
0
3
6
9

---------------------
- parts/3:
- text
# 📚 Dizinin Toplamı

``for`` döngüsü dizilerle çok iyi çalışır. ``i`` indeksini ``0``dan başlatıp
``i < sayılar.length`` koşuluyla dolaşırız. ``sayılar[i]`` bize o anki elemanı verir, biz de
onu toplam kutusuna ekleriz.

<code-view name="main.js" language="javascript">
let sayılar = [5, 10, 15, 20];
let toplam = 0;
for (let i = 0; i < sayılar.length; i++) {
  toplam += sayılar[i];
}
console.log("Toplam:", toplam);
</code-view>

<code-view name="Terminal" language="bash">
Toplam: 50
</code-view>

# 🎯 4. Görev

``[5, 10, 15, 20]`` dizisinin elemanlarını toplayıp ``Toplam: 50`` yazdıran programı yazar
mısın?

- files/main.js/.block
// her elemanı toplam kutusuna ekler misin?
let sayılar = [5, 10, 15, 20];
let toplam = 0;
for (let i = 0; i < sayılar.length; i++) {
  toplam <<< ❓ >>> sayılar[i];
}
console.log("Toplam:", toplam);
---------------------
- tests/0/output
Toplam: 50

---------------------
- tests/1/files/main.js/.block
// her elemanı toplam kutusuna ekler misin?
let sayılar = [2, 4, 6];
let toplam = 0;
for (let i = 0; i < sayılar.length; i++) {
  toplam <<< ❓ >>> sayılar[i];
}
console.log("Toplam:", toplam);
- tests/1/output
Toplam: 12

---------------------
- parts/4:
- text
# 📊 Dizinin Ortalaması

Ortalama, toplamın eleman sayısına bölünmesiyle bulunur. ``sayılar.length`` dizinin
uzunluğunu verir; sabit bir sayı yazmaya gerek yoktur. Sonuç ondalıklı çıkabilir.

<code-view name="main.js" language="javascript">
let notlar = [80, 85, 90, 100];
let toplam = 0;
for (let i = 0; i < notlar.length; i++) {
  toplam += notlar[i];
}
let ortalama = toplam / notlar.length;
console.log("Ortalama:", ortalama);
</code-view>

<code-view name="Terminal" language="bash">
Ortalama: 88.75
</code-view>

# 🎯 5. Görev

``[80, 85, 90, 100]`` notlarının ortalamasını ``Ortalama: 88.75`` şeklinde yazdıran
programı yazar mısın?

- files/main.js/.block
// ortalamayı bulmak için toplamı neye bölersin?
let notlar = [80, 85, 90, 100];
let toplam = 0;
for (let i = 0; i < notlar.length; i++) {
  toplam += notlar[i];
}
let ortalama = toplam <<< ❓ >>> notlar.length;
console.log("Ortalama:", ortalama);
---------------------
- tests/0/output
Ortalama: 88.75

---------------------
- tests/1/files/main.js/.block
// ortalamayı bulmak için toplamı neye bölersin?
let notlar = [80, 90, 100];
let toplam = 0;
for (let i = 0; i < notlar.length; i++) {
  toplam += notlar[i];
}
let ortalama = toplam <<< ❓ >>> notlar.length;
console.log("Ortalama:", ortalama);
- tests/1/output
Ortalama: 90

---------------------
- parts/5:
- text
# 🍎 **for…of** : Elemanları Tek Tek Gez

``for...of`` dizi elemanlarını indeksle uğraşmadan gezer. ``for (const meyve of meyveler)``
demek "``meyveler`` dizisindeki her elemanı sırayla ``meyve`` değişkenine koy" demektir.
Okuması klasik ``for`` döngüsünden çok daha kolaydır.

<code-view name="main.js" language="javascript">
let meyveler = ["elma", "vişne", "çilek"];
for (const meyve of meyveler) {
  console.log(meyve);
}
</code-view>

<code-view name="Terminal" language="bash">
elma
vişne
çilek
</code-view>

# 🎯 6. Görev

Dizideki meyveleri alt alta yazdıran ``for...of`` döngüsünü kurar mısın?

- files/main.js/.block
// dizinin elemanlarını gezen döngüyü tamamlar mısın?
let meyveler = ["elma", "vişne", "çilek"];
for (const meyve <<< ❓ >>> meyveler) {
  console.log(meyve);
}
---------------------
- tests/0/output
elma
vişne
çilek

---------------------
- tests/1/files/main.js/.block
// dizinin elemanlarını gezen döngüyü tamamlar mısın?
let meyveler = ["muz", "kavun", "kiraz", "nar"];
for (const meyve <<< ❓ >>> meyveler) {
  console.log(meyve);
}
- tests/1/output
muz
kavun
kiraz
nar

---------------------
- parts/6:
- text
# 🔤 **for…of** ve Metinler

Metinler de harflerden oluşan bir dizi gibi davranır. ``for...of`` ile bir kelimenin
harflerini tek tek yazdırabiliriz. Döngü değişkeni her turda sıradaki harfi taşır.

<code-view name="main.js" language="javascript">
let kelime = "kod";
for (const harf of kelime) {
  console.log(harf);
}
</code-view>

<code-view name="Terminal" language="bash">
k
o
d
</code-view>

# 🎯 7. Görev

``"kod"`` kelimesinin harflerini alt alta yazdıran programı yazar mısın?

- files/main.js/.block
// sıradaki harfi yazdırır mısın?
let kelime = "kod";
for (const harf of kelime) {
  console.log(<<< ❓ >>>);
}
---------------------
- tests/0/output
k
o
d

---------------------
- tests/1/files/main.js/.block
// sıradaki harfi yazdırır mısın?
let kelime = "kal";
for (const harf of kelime) {
  console.log(<<< ❓ >>>);
}
- tests/1/output
k
a
l

---------------------
- parts/7:
- text
# 🗝️ **for…in** : Nesne Anahtarları

Nesnelerde anahtar (key) ve değer (value) vardır. ``for...in`` döngüsü nesnenin
**anahtarlarını** dolaşır; değere ulaşmak için ``nesne[anahtar]`` yazarız. Aşağıdaki örnek
``ad: Ayşe`` gibi satırlar üretir.

<code-view name="main.js" language="javascript">
let kişi = { ad: "Ayşe", yaş: 30, şehir: "İzmir" };
for (const anahtar in kişi) {
  console.log(anahtar + ":", kişi[anahtar]);
}
</code-view>

<code-view name="Terminal" language="bash">
ad: Ayşe
yaş: 30
şehir: İzmir
</code-view>

# 🎯 8. Görev

Nesnenin anahtarlarını ve değerlerini alt alta yazdıran programı yazar mısın?

- files/main.js/.block
// anahtarları gezen döngüyü tamamlar mısın?
let kişi = { ad: "Ayşe", yaş: 30, şehir: "İzmir" };
for (const anahtar <<< ❓ >>> kişi) {
  console.log(anahtar + ":", kişi[anahtar]);
}
---------------------
- tests/0/output
ad: Ayşe
yaş: 30
şehir: İzmir

---------------------
- tests/1/files/main.js/.block
// anahtarları gezen döngüyü tamamlar mısın?
let kişi = { ad: "Mehmet", meslek: "öğretmen" };
for (const anahtar <<< ❓ >>> kişi) {
  console.log(anahtar + ":", kişi[anahtar]);
}
- tests/1/output
ad: Mehmet
meslek: öğretmen

---------------------
- parts/8:
- text
# 🧩 İç İçe for

Bir ``for`` döngüsünün içine başka bir ``for`` koyabiliriz. Dıştaki döngü her tur attığında
içteki döngü **baştan** çalışır; böylece bütün kombinasyonlar elde edilir. Aşağıdaki örnek
iki renk ile iki nesneyi eşleştiriyor.

<code-view name="main.js" language="javascript">
let renkler = ["kırmızı", "yeşil"];
let nesneler = ["elma", "bayrak"];
for (const renk of renkler) {
  for (const nesne of nesneler) {
    console.log(renk, nesne);
  }
}
</code-view>

<code-view name="Terminal" language="bash">
kırmızı elma
kırmızı bayrak
yeşil elma
yeşil bayrak
</code-view>

# 🎯 9. Görev

Bütün renk-nesne kombinasyonlarını alt alta yazdıran iç içe döngüyü kurar mısın?

- files/main.js/.block
// içteki döngünün başını yazar mısın?
let renkler = ["kırmızı", "yeşil"];
let nesneler = ["elma", "bayrak"];
for (const renk of renkler) {
  <<< ❓ >>> (const nesne of nesneler) {
    console.log(renk, nesne);
  }
}
---------------------
- tests/0/output
kırmızı elma
kırmızı bayrak
yeşil elma
yeşil bayrak

---------------------
- tests/1/files/main.js/.block
// içteki döngünün başını yazar mısın?
let renkler = ["kırmızı", "yeşil", "beyaz"];
let nesneler = ["elma", "bayrak"];
for (const renk of renkler) {
  <<< ❓ >>> (const nesne of nesneler) {
    console.log(renk, nesne);
  }
}
- tests/1/output
kırmızı elma
kırmızı bayrak
yeşil elma
yeşil bayrak
beyaz elma
beyaz bayrak

---------------------
- parts/9:
- text
# 🛑 **break** : Erken Çık

``for`` döngüsünde ``break`` gördüğümüz anda döngü tamamen biter; kalan elemanlar hiç
işlenmez. Aşağıdaki örnek ``10``dan büyük ilk sayıya gelince duruyor, o yüzden sadece
``3`` ve ``7`` yazılıyor.

<code-view name="main.js" language="javascript">
let sayılar = [3, 7, 12, 5, 9];
for (const sayı of sayılar) {
  if (sayı > 10) {
    break;
  }
  console.log(sayı);
}
</code-view>

<code-view name="Terminal" language="bash">
3
7
</code-view>

# 🎯 10. Görev

``10``dan büyük bir sayı görünce döngüden çıkan programı yazar mısın?

- files/main.js/.block
// 10'dan büyük sayıda döngüyü bitirir misin?
let sayılar = [3, 7, 12, 5, 9];
for (const sayı of sayılar) {
  if (sayı > 10) {
    <<< ❓ >>>;
  }
  console.log(sayı);
}
---------------------
- tests/0/output
3
7

---------------------
- tests/1/files/main.js/.block
// 10'dan büyük sayıda döngüyü bitirir misin?
let sayılar = [1, 2, 20, 4];
for (const sayı of sayılar) {
  if (sayı > 10) {
    <<< ❓ >>>;
  }
  console.log(sayı);
}
- tests/1/output
1
2

---------------------
- parts/10:
- text
# ⏭️ **continue** : Adımı Atla

``continue`` döngüyü bitirmez, yalnızca o turu atlar. Aşağıdaki örnekte ``i`` üç olduğunda
``console.log`` çalışmaz ama döngü kaldığı yerden devam eder. Böylece ``3`` yazdırılmadan
diğer sayılar yazılır.

<code-view name="main.js" language="javascript">
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    continue;
  }
  console.log(i);
}
</code-view>

<code-view name="Terminal" language="bash">
1
2
4
5
</code-view>

# 🎯 11. Görev

``3`` hariç ``1``den ``5``e kadar olan sayıları yazdıran programı yazar mısın?

- files/main.js/.block
// 3'ü atlayıp devam eder misin?
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    <<< ❓ >>>;
  }
  console.log(i);
}
---------------------
- tests/0/output
1
2
4
5

---------------------
- tests/1/files/main.js/.block
// 4'ü atlayıp devam eder misin?
for (let i = 1; i <= 5; i++) {
  if (i === 4) {
    <<< ❓ >>>;
  }
  console.log(i);
}
- tests/1/output
1
2
3
5

---------------------
