- show_content = true
- show_editor = true
- show_terminal = true
- language = "javascript"
- title = "🔁 Döngüler : while"
- run = "node main.js"

- parts/0:
- text
# 🔁 **while** : Koşul Doğru Oldukça Tekrarla

``while`` döngüsü, parantez içindeki koşul **doğru** olduğu sürece süslü parantez
içindeki kodları tekrar tekrar çalıştırır. Koşul yanlış olduğunda döngü biter ve program
aşağıdan devam eder. Döngünün bir gün bitebilmesi için içeride sayacı değiştirmemiz
gerekir.

<code-view name="main.js" language="javascript">
let sayı = 1;
while (sayı <= 5) {
  console.log(sayı);
  sayı++;
}
</code-view>

<code-view name="Terminal" language="bash">
1
2
3
4
5
</code-view>

# 🎯 1. Görev

``1``den ``5``e kadar olan sayıları alt alta yazdıran programı yazar mısın? Döngü koşulunu
tamamen doldurman gerekiyor.

- files/main.js/.block
// 1'den 5'e kadar sayan bir while döngüsü kurar mısın?
let sayı = 1;
while (sayı <<< ❓ >>> 5) {
  console.log(sayı);
  sayı++;
}
---------------------
- tests/0/output
1
2
3
4
5

---------------------
- tests/1/files/main.js/.block
// 1'den 3'e kadar sayan bir while döngüsü kurar mısın?
let sayı = 1;
while (sayı <<< ❓ >>> 3) {
  console.log(sayı);
  sayı++;
}
- tests/1/output
1
2
3

---------------------
- parts/1:
- text
# ➕ Toplam Biriktirme

Döngünün en yaygın kullanımı bir toplamı biriktirmektir. Döngüden **önce** ``toplam = 0``
diye boş bir kutu açarız, döngünün **içinde** her adımda ``+=`` ile kutuya ekleriz. Döngü
bitince kutuda tüm sayıların toplamı olur.

<code-view name="main.js" language="javascript">
let toplam = 0;
let sayı = 1;
while (sayı <= 10) {
  toplam += sayı;
  sayı++;
}
console.log("Toplam:", toplam);
</code-view>

<code-view name="Terminal" language="bash">
Toplam: 55
</code-view>

# 🎯 2. Görev

``1``den ``10``a kadar olan sayıları toplayıp ``Toplam: 55`` yazdıran programı yazar mısın?

- files/main.js/.block
// her adımda sayıyı toplama ekler misin?
let toplam = 0;
let sayı = 1;
while (sayı <= 10) {
  toplam <<< ❓ >>> sayı;
  sayı++;
}
console.log("Toplam:", toplam);
---------------------
- tests/0/output
Toplam: 55

---------------------
- tests/1/files/main.js/.block
// her adımda sayıyı toplama ekler misin?
let toplam = 0;
let sayı = 1;
while (sayı <= 5) {
  toplam <<< ❓ >>> sayı;
  sayı++;
}
console.log("Toplam:", toplam);
- tests/1/output
Toplam: 15

---------------------
- parts/2:
- text
# ⏬ Geriye Sayma

Sayaç her zaman artmak zorunda değildir. ``sayaç--`` ile birer birer azaltıp koşulu da
``sayaç > 0`` yaparsak döngü geriye doğru sayar. Döngü bittikten sonra normal kod
çalışmaya devam eder.

<code-view name="main.js" language="javascript">
let sayaç = 5;
while (sayaç > 0) {
  console.log(sayaç);
  sayaç--;
}
console.log("Bitiş!");
</code-view>

<code-view name="Terminal" language="bash">
5
4
3
2
1
Bitiş!
</code-view>

# 🎯 3. Görev

``5``ten ``1``e kadar geriye sayan, sonra ``Bitiş!`` yazan programı yazar mısın?

- files/main.js/.block
// sayaç sıfırdan büyük olduğu sürece devam etsin
let sayaç = 5;
while (sayaç <<< ❓ >>> 0) {
  console.log(sayaç);
  sayaç--;
}
console.log("Bitiş!");
---------------------
- tests/0/output
5
4
3
2
1
Bitiş!

---------------------
- tests/1/files/main.js/.block
// sayaç sıfırdan büyük olduğu sürece devam etsin
let sayaç = 3;
while (sayaç <<< ❓ >>> 0) {
  console.log(sayaç);
  sayaç--;
}
console.log("Bitiş!");
- tests/1/output
3
2
1
Bitiş!

---------------------
- parts/3:
- text
# 🔢 Sadece Çift Sayılar

Döngünün içine ``if`` koyarak yalnızca istediğimiz adımları yazdırabiliriz. ``%`` (mod)
operatörü bir sayının çift olup olmadığını anlamanın en kolay yoludur; ``sayı % 2 === 0``
ise sayı çifttir.

<code-view name="main.js" language="javascript">
let sayı = 0;
while (sayı < 10) {
  sayı++;
  if (sayı % 2 === 0) {
    console.log(sayı);
  }
}
</code-view>

<code-view name="Terminal" language="bash">
2
4
6
8
10
</code-view>

# 🎯 4. Görev

``1``den ``10``a kadar olan **çift** sayıları alt alta yazdıran programı yazar mısın?

- files/main.js/.block
// sayının çift olup olmadığını anlar mısın?
let sayı = 0;
while (sayı < 10) {
  sayı++;
  if (sayı % <<< ❓ >>> === 0) {
    console.log(sayı);
  }
}
---------------------
- tests/0/output
2
4
6
8
10

---------------------
- parts/4:
- text
# 🔄 **do…while** : Önce Çalış, Sonra Sor

``do...while`` döngüsünde koşul **sonda** kontrol edilir. Bu yüzden kod **en az bir kez**
çalışır. Aşağıdaki örnekte koşul baştan yanlış olmasına rağmen döngü gövdesi bir kez
çalıştı ve ekrana bir satır yazdı.

<code-view name="main.js" language="javascript">
let sayı = 10;
do {
  console.log("Bir kez çalıştı:", sayı);
  sayı++;
} while (sayı < 3);
</code-view>

<code-view name="Terminal" language="bash">
Bir kez çalıştı: 10
</code-view>

# 🎯 5. Görev

Koşul yanlış olsa bile döngünün bir kez çalıştığı programı yazar mısın? ``do...while``
koşulunu tamamla.

- files/main.js/.block
// koşul sonda kontrol edilir, döngü en az bir kez çalışır
let sayı = 10;
do {
  console.log("Bir kez çalıştı:", sayı);
  sayı++;
} while (sayı <<< ❓ >>> 3);
---------------------
- tests/0/output
Bir kez çalıştı: 10

---------------------
- tests/1/files/main.js/.block
// koşul sonda kontrol edilir, döngü en az bir kez çalışır
let sayı = 1;
do {
  console.log("Bir kez çalıştı:", sayı);
  sayı++;
} while (sayı <<< ❓ >>> 3);
- tests/1/output
Bir kez çalıştı: 1
Bir kez çalıştı: 2

---------------------
- parts/5:
- text
# 🛑 **break** : Döngüyü Hemen Bitir

``break`` döngüyü ortasında durdurur. ``while (true)`` koşulu hep doğru olduğu için tek
başına sonsuz döngüdür; içeride ``break`` ile çıkmak yaygın bir kalıptır. Aşağıdaki örnek
``4``e gelince döngüden çıkar.

<code-view name="main.js" language="javascript">
let sayı = 1;
while (true) {
  if (sayı === 4) {
    break;
  }
  console.log(sayı);
  sayı++;
}
</code-view>

<code-view name="Terminal" language="bash">
1
2
3
</code-view>

# 🎯 6. Görev

``1``, ``2``, ``3`` yazdıktan sonra ``4``e gelince döngüden çıkan programı yazar mısın?

- files/main.js/.block
// 4'e gelince döngüyü sonlandırır mısın?
let sayı = 1;
while (true) {
  if (sayı === 4) {
    <<< ❓ >>>;
  }
  console.log(sayı);
  sayı++;
}
---------------------
- tests/0/output
1
2
3

---------------------
- tests/1/files/main.js/.block
// 3'e gelince döngüyü sonlandırır mısın?
let sayı = 1;
while (true) {
  if (sayı === 3) {
    <<< ❓ >>>;
  }
  console.log(sayı);
  sayı++;
}
- tests/1/output
1
2

---------------------
- parts/6:
- text
# ⏭️ **continue** : Bu Adımı Atla

``continue`` o adımda kalan kodları atlar ve döngünün başına döner. ``while`` içinde
``continue`` kullanırken ⚠️ dikkat: sayacı **continue'dan önce** artırmazsan koşul hiç
değişmez ve döngü sonsuza gider. Aşağıdaki örnekte ``sayı++`` yukarıda olduğu için
sorun yok.

<code-view name="main.js" language="javascript">
let sayı = 0;
while (sayı < 5) {
  sayı++;
  if (sayı === 3) {
    continue;
  }
  console.log(sayı);
}
</code-view>

<code-view name="Terminal" language="bash">
1
2
4
5
</code-view>

# 🎯 7. Görev

``3`` hariç ``1``den ``5``e kadar olan sayıları yazdıran programı yazar mısın?

- files/main.js/.block
// 3'e gelince bu adımı atlar mısın?
let sayı = 0;
while (sayı < 5) {
  sayı++;
  if (sayı === 3) {
    <<< ❓ >>>;
  }
  console.log(sayı);
}
---------------------
- tests/0/output
1
2
4
5

---------------------
- tests/1/files/main.js/.block
// 4'e gelince bu adımı atlar mısın?
let sayı = 0;
while (sayı < 5) {
  sayı++;
  if (sayı === 4) {
    <<< ❓ >>>;
  }
  console.log(sayı);
}
- tests/1/output
1
2
3
5

---------------------
- parts/7:
- text
# ⚠️ Sonsuz Döngü Uyarısı

Sayaç satırını yazmayı unutursan koşul hiç değişmez ve döngü **sonsuz** çalışır; program
kilitlenir. Kural basit: döngü gövdesinde koşulu etkileyen değişkeni mutlaka değiştir.
Aşağıdaki yorum satırı sana bu hatırlatmayı yapıyor.

<code-view name="main.js" language="javascript">
let sayı = 1;
while (sayı <= 3) {
  console.log("Sayaç:", sayı);
  sayı++; // bu satır olmazsa döngü sonsuz çalışır!
}
console.log("Döngü bitti.");
</code-view>

<code-view name="Terminal" language="bash">
Sayaç: 1
Sayaç: 2
Sayaç: 3
Döngü bitti.
</code-view>

# 🎯 8. Görev

Döngünün sonsuza gitmemesi için eksik olan sayaç satırını yazar mısın?

- files/main.js/.block
// eksik satırı yaz, yoksa döngü sonsuz çalışır!
let sayı = 1;
while (sayı <= 3) {
  console.log("Sayaç:", sayı);
  <<< ❓ >>>; // bu satır olmazsa döngü sonsuz çalışır!
}
console.log("Döngü bitti.");
---------------------
- tests/0/output
Sayaç: 1
Sayaç: 2
Sayaç: 3
Döngü bitti.

---------------------
- tests/1/files/main.js/.block
// eksik satırı yaz, yoksa döngü sonsuz çalışır!
let sayı = 1;
while (sayı <= 2) {
  console.log("Sayaç:", sayı);
  <<< ❓ >>>; // bu satır olmazsa döngü sonsuz çalışır!
}
console.log("Döngü bitti.");
- tests/1/output
Sayaç: 1
Sayaç: 2
Döngü bitti.

---------------------
- parts/8:
- text
# 📚 Dizi Üzerinde while

Dizilerin de bir uzunluğu vardır. ``i`` indeksini ``0``dan başlatıp ``i < dizi.length``
koşuluyla ilerleyerek bütün elemanları tek tek okuyabiliriz. Bu, ``for`` döngüsünü
öğrenmeden önceki en temel dolaşma yöntemidir.

<code-view name="main.js" language="javascript">
let sayılar = [4, 8, 15, 16, 23, 42];
let toplam = 0;
let i = 0;
while (i < sayılar.length) {
  toplam += sayılar[i];
  i++;
}
console.log("Toplam:", toplam);
</code-view>

<code-view name="Terminal" language="bash">
Toplam: 108
</code-view>

# 🎯 9. Görev

Dizideki bütün sayıları toplayıp ``Toplam: 108`` yazdıran programı yazar mısın?

- files/main.js/.block
// her elemanı toplama ekler misin?
let sayılar = [4, 8, 15, 16, 23, 42];
let toplam = 0;
let i = 0;
while (i < sayılar.length) {
  toplam <<< ❓ >>> sayılar[i];
  i++;
}
console.log("Toplam:", toplam);
---------------------
- tests/0/output
Toplam: 108

---------------------
- tests/1/files/main.js/.block
// her elemanı toplama ekler misin?
let sayılar = [1, 2, 3];
let toplam = 0;
let i = 0;
while (i < sayılar.length) {
  toplam <<< ❓ >>> sayılar[i];
  i++;
}
console.log("Toplam:", toplam);
- tests/1/output
Toplam: 6

---------------------
- parts/9:
- text
# 🔟 Basamak Toplama

``% 10`` bir sayının son basamağını verir, ``Math.floor(sayı / 10)`` ise son basamağı
siler. Bu ikisini ``while`` içinde kullanarak bir sayının bütün basamaklarını toplarız.
Sayı ``0`` olunca döngü kendiliğinden biter.

<code-view name="main.js" language="javascript">
let sayı = 1234;
let toplam = 0;
while (sayı > 0) {
  toplam += sayı % 10;
  sayı = Math.floor(sayı / 10);
}
console.log("Basamak toplamı:", toplam);
</code-view>

<code-view name="Terminal" language="bash">
Basamak toplamı: 10
</code-view>

# 🎯 10. Görev

``1234`` sayısının basamaklarını toplayıp ``Basamak toplamı: 10`` yazdıran programı yazar
mısın?

- files/main.js/.block
// son basamağı silmek için 10'a böler misin?
let sayı = 1234;
let toplam = 0;
while (sayı > 0) {
  toplam += sayı % 10;
  sayı = Math.floor(sayı / <<< ❓ >>>);
}
console.log("Basamak toplamı:", toplam);
---------------------
- tests/0/output
Basamak toplamı: 10

---------------------
- parts/10:
- text
# 🏆 Mini Tekrar : Faktöriyel

``while`` ile çarpma da biriktirebiliriz. Faktöriyel, ``5 * 4 * 3 * 2 * 1`` demektir ve
``1``den başlayan bir çarpım kutusuyla hesaplanır. Sayaç ``1``e inince döngü biter.

<code-view name="main.js" language="javascript">
let n = 5;
let faktöriyel = 1;
while (n > 1) {
  faktöriyel *= n;
  n--;
}
console.log("5! =", faktöriyel);
</code-view>

<code-view name="Terminal" language="bash">
5! = 120
</code-view>

# 🎯 11. Görev

``5``in faktöriyelini hesaplayıp ``5! = 120`` yazdıran programı yazar mısın?

- files/main.js/.block
// her adımda çarpım kutusunu günceller misin?
let n = 5;
let faktöriyel = 1;
while (n > 1) {
  faktöriyel <<< ❓ >>> n;
  n--;
}
console.log("5! =", faktöriyel);
---------------------
- tests/0/output
5! = 120

---------------------
- tests/1/files/main.js/.block
// her adımda çarpım kutusunu günceller misin?
let n = 4;
let faktöriyel = 1;
while (n > 1) {
  faktöriyel <<< ❓ >>> n;
  n--;
}
console.log("4! =", faktöriyel);
- tests/1/output
4! = 24

---------------------
