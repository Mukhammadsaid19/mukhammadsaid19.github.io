# Sonni top!

Ushbu bobda siz Sonni top! nomli o'yinni yaratasiz. Kompyuter 1 dan 20 gacha bo'lgan maxfiy sonni o'ylab topadi va foydalanuvchidan taxmin qilishni so'raydi. Har bir taxmindan so'ng, kompyuter foydalanuvchiga bu son juda katta yoki kamligini aytadi. Agar foydalanuvchi olti urinishda raqamni topib olsa, foydalanuvchi g'olib chiqadi.

Bu kodlash uchun yaxshi o'yin, chunki u qisqa dasturda ko'plab dasturlash tushunchalarini qamrab oladi. Siz qiymatlarni turli xil ma'lumotlar turlariga qanday o'zgartirishni va qachon buni amalga oshirishingiz kerakligini bilib olasiz. Ushbu dastur o'yin ekan, bundan buyon biz foydalanuvchini o'yinchi deb ataymiz.

Ushbu bobda yoritilgan mavzular:

* ```import``` ifodasi
* Modullar
* ```randint()``` funktsiyasi
* ```for``` ifodasi
* Bloklar
* ```str()```, ```int()``` va ```float()``` funktsiyalari
* Mantiqiy ma'lumot turlari
* Taqqoslash operatorlari
* Shartlar
* = va == orasidagi farq
* ```if``` ifodasi
* ```break``` ifodasi

"Sonni top!" o'yining ishlash namunasi:

Bu yerda "Sonni top!" dasturi ishga tushirilganda o'yinchi nimani ko'rishi ko'rsatilgan. O'yinchi kiritgan ma'lumot qalin bilan belgilangan.

```python
Salom! Ismingiz nima?
Anvar
Anvar, men 1 dan 20 gacha bo'lgan sonni o'yladim.
Topib ko'ringchi.
10
Sizning taxminingiz juda yuqori.
Taxmin qiling.
2
Sizning taxminingiz juda past.
Taxmin qiling.
4
Barakalla, Anvar! Siz mening sonimni 3 ta taxminda topdingiz!
```

"Sonni top!" uchun manba kodi

Pythonning IDLEda Fayl - New File bosish orqali yangi fayl muharriri oynasini oching. Ko'rsatilgan bo'sh oynada manba kodini kiriting va uni ```guess.py``` sifatida saqlang. Keyin F5 tugmachasini bosib dasturni ishga tushiring.

Ushbu kodni fayl muharririga kiritganingizda, satrlarning old qismidagi bo'shliqqa e'tibor bering. Ba'zi satrlarni to'rt yoki sakkiz bo'shliq bilan ajratish kerak.

```guess.py```
```python
# Bu "Sonni top" o'yini
import random

guessesTaken = 0

print('Salom! Ismingiz nima?')
myName = input()

number = random.randint(1, 20)
print(myName + ', men 1 dan 20 gacha bo\'lgan sonni o\'yladim.')

guess = 0

for guessesTaken in range(6):
    print('Taxmin qiling.')  # print oldida 4ta bo'sh joy bor
    guess = input()
    guess = int(guess)

    if guess < number:
        print('Sizning taxminingiz juda past.')  # Eight spaces in front of "print"

    if guess > number:
        print('Sizning taxminingiz juda yuqori.')

    if guess == number:
        break

if guess == number:
    guessesTaken = str(guessesTaken + 1)
    print('Barakalla, ' + myName + '! Siz mening sonimni ' + guessesTaken + ' ta taxminda topdingiz!')

if guess != number:
    number = str(number)
    print('Yo\'q. Man o\'ylagan son ' + number + ' edi.')
```

## ```random``` modulni import qilish
Keling, ushbu dasturning dastlabki ikkita satrini ko'rib chiqamiz:

```python
# Bu "Sonni top" o'yini
import random
```
Birinchi satr - bu sharhdir. Python ```#``` belgidan keyin hamma narsani e'tiborsiz qoldirishini unutmang. Bu yerdagi sharh bizga ushbu dastur nima qilishini eslatib turadi.

Ikkinchi qator - import ifodasi. Esingizda bo'lsin, ifodalar ba'zi bir harakatlarni amalga oshiradigan ko'rsatmalardir, ammo iboralar kabi qiymatga baho bermaydi. Siz allaqachon o'zgaruvchida qiymatni berish ifodanini ko'rgansiz.
Python tarkibida ko'plab o'rnatilgan funktsiyalar mavjud bo'lsa, ba'zi funktsiyalar modul deb nomlangan alohida dasturlarda yoziladi. Ushbu funktsiyalardan, ularning modullarini import ifodasi bilan dasturingizga import qilish orqali foydalanishingiz mumkin.
2-qator tasodifiy random modulni import qiladi, shunda dastur ```randint()``` funktsiyasini chaqira oladi. Ushbu funksiya o'yinchi taxmin qilish uchun tasodifiy raqamni ishlab chiqaradi.

Endi siz tasodifiy modulni import qilganingizdan so'ng, keyinchalik sizning dasturingiz foydalanadigan qiymatlarni saqlash uchun ba'zi o'zgaruvchilarni o'rnatishingiz kerak.
4-qator taxmin qilingan yangi o'zgaruvchini yaratadi guessesTaken:

```python
guessesTaken = 0
```

Siz ushbu o'zgaruvchida o'yinchi tomonidan qilingan taxminlar sonini saqlaysiz. O'yinchi dasturning ushbu nuqtasida hech qanday taxmin qilmagani uchun, 0 butun sonini shu erda saqlang.

```python
print('Salom! Ismingiz nima?')
myName = input()
```

6 va 7-satrlar 2-bobdagi ```"Hello World"``` dasturidagi satrlar bilan bir xil. Dasturchilar o'z ishlarini saqlab qolish uchun ko'pincha boshqa dasturlarning kodlarini qayta ishlatadilar.
6-qator - ```print()``` ni funktsiya chaqiruvi. Shuni esda tutingki, funktsiya sizning dasturingizdagi mini-dasturga o'xshaydi. Sizning dasturingiz funktsiyani chaqirganda, ushbu mini-dasturni ishlatadi. ```print()``` ichidagi kod siz bergan mag'lubiyat argumentini ekranda aks ettiradi.
7-qatorda o'yinchi o'z nomini kiritishga imkon beradi va uni myName o'zgaruvchisiga saqlaydi. Esingizda bo'lsin, mag'lubiyat chindan ham o'yinchining nomi bo'lmasligi mumkin; bu shunchaki o'yinchi turidagi har qanday mag'lubiyat. Kompyuterlar soqov va nima bo'lishidan qat'iy nazar ularning ko'rsatmalariga amal qilishadi.

## ```random.randint()``` funktsiyasi bilan tasodifiy raqamlarni yaratish

Endi boshqa o'zgaruvchilaringiz o'rnatilganda, siz kompyuterning maxfiy raqamini sozlash uchun tasodifiy modul funktsiyasidan foydalanishingiz mumkin:

```python
number = random.randint(1, 20)
```

9-qatorda ```randint()``` nomli yangi funktsiya chaqiriladi va qaytish qiymati sonda saqlanadi. Esingizda bo'lsin, funktsiya chaqiruvlari iboralarning bir qismi bo'lishi mumkin, chunki ular
qiymatga baho bering.

```randint()``` funktsiyasi tasodifiy modul tomonidan ta'minlanadi, shuning uchun Pythonga ```randint()``` funktsiyasi tasodifiy modulda ekanligini aytish uchun uni ```random.randint()``` bilan chaqirishingiz kerak (davrni unutmang!).

Bir lahzaga interaktiv qobiqqa qayting va tasodifiy modulni import qilish uchun ```import random``` kiriting. So'ngra funktsiya chaqiruvi nimani baholashini ko'rish uchun ```random.randint (1, 20)``` kiriting. U ```1``` dan ```20``` gacha bo'lgan butun sonni qaytaradi, kodni yana takrorlang va funktsiya chaqiruvi yana bir butun sonni qaytaradi.
```randint()``` funktsiyasi har safar tasodifiy tamsayıni qaytaradi, xuddi o'limning siljishi har safar tasodifiy songa olib keladi. Masalan, quyidagilarni interaktiv qobiqga kiriting. ```randint()``` funktsiyasini chaqirganingizda, natijalar boshqacha bo'lishi mumkin (bu tasodifiy, axir!).

```python
>>> import random
>>> random.randint(1, 20)
12
>>> random.randint(1, 20)
18
>>> random.randint(1, 20)
3
>>> random.randint(1, 20)
18
>>> random.randint(1, 20)
7
```

Shuningdek, argumentlarni o'zgartirib, har xil raqamlar diapazonini sinab ko'rishingiz mumkin. Masalan, ```random.randint(1, 4)``` raqamini kiriting, faqat ```1``` dan ```4``` gacha (1 va 4 ikkalasini ham o'z ichiga olgan) butun sonlar olinadi. Yoki ```1000``` dan ```2000``` gacha bo'lgan butun sonlarni olish uchun ```random.randint (1000, 2000)``` ni sinab ko'ring. Ushbu kodni interaktiv qobiqga kiriting va qanday raqamlarni olganingizni ko'ring:

```python
>>> random.randint(1, 4)
3
>>> random.randint(1000, 2000)
1294
```

O'yin o'zini boshqacha tutishi uchun o'yin kodini biroz o'zgartirishingiz mumkin. Asl kodimizda biz 1 dan 20 gacha bo'lgan butun sonni ishlatamiz:

```python
number = random.randint(1, 20)
print('Well, ' + myName + ', I am thinking of a number between 1 and 20.')
```

Buning o'rniga butun sonni ```(1, 100)``` ga o'zgartiring:

```python
number = random.randint(1, 100)
print(myName + ', men 1 dan 100 gacha bo\'lgan sonni o\'yladim.')
```

Endi kompyuter 1 dan 20 gacha emas, balki 1 dan 100 gacha bo'lgan butun sonni o'ylaydi. 9-qatorni o'zgartirganda tasodifiy son oralig'i o'zgaradi, lekin 10-qatorni ham o'zgartirishni unutmang, shunda o'yin o'yinchiga o'rniga yangi diapazonni bildiradi. eski.

```randint()``` funktsiyasidan o'yinlaringizga tasodifiylik qo'shishni xohlagan vaqtingizda foydalanishingiz mumkin. Ko'p o'yinlarda tasodifiylikdan foydalanasiz. (Nardada shesh-beshlardan qancha foydalanilishini o'ylab ko'ring.)

## O'yinchini kutib olish

Kompyuter raqamni tasodifiy butun songa bergandan so'ng, u pleyerga salom beradi:

```
print(myName + ', men 1 dan 20 gacha bo\'lgan sonni o\'yladim.')
```

10-qatorda ```print()``` o'yinchini ism-shariflari bilan kutib oladi va ularga kompyuter tasodifiy son haqida o'ylayotganini aytadi.
Bir qarashda, 10-satrda bir nechta mag'lubiyat argumenti bor ko'rinishi mumkin, ammo satrni diqqat bilan o'rganib chiqing. Uch qator orasidagi ```+``` operatorlari ularni bir qatorga birlashtiradi. Va bu bitta satr chop etish uchun berilgan argumentdir ```()```. Agar siz diqqat bilan qarasangiz, vergullar tirnoqlarning ichida va satrlarning bir qismining o'zida joylashganligini ko'rasiz.

## Oqimlarni boshqarish bo'yicha bayonotlar

Oldingi boblarda dasturning bajarilishi dasturning yuqori buyrug'idan boshlanib, to'g'ridan-to'g'ri pastga siljiydi va har bir ko'rsatmani tartibda bajaradi. Ammo ```for```, ```if```, ```else``` va ```break``` bayonotlari bilan shartlarga asoslanib ijro etuvchi tsiklni yaratishingiz yoki ko'rsatmalarni o'tkazib yuborishingiz mumkin. Ushbu turdagi bayonotlar oqimlarni boshqarish bo'yicha bayonotlardir, chunki ular sizning dasturingiz atrofida harakat qilganda dasturning bajarilishini o'zgartiradi.

### Kodni takrorlash uchun tsikllardan foydalanish

12-satr ```for``` iborasi bo'lib, ```for``` tsiklining boshlanishini bildiradi:

```python
taxminlar uchun (6) oralig'ida olingan:
```

Loops sizga kodni qayta-qayta bajarishga imkon beradi. 12-qator o'z kodini olti marta takrorlanadi. ```for``` buyrug'i ```for``` kalit so'zidan boshlanadi, so'ngra yangi o'zgaruvchi nomi, ```in``` kalit so'zi, bajarilishi kerak bo'lgan tsikldan sonini aniqlaydigan ```range()``` funktsiyasiga murojaat qiladi. Keling, tsikllar bilan ishlashingiz uchun bir nechta qo'shimcha tushunchalarni ko'rib chiqaylik.

### Bloklar bilan guruhlash

Blokda bir nechta kod satrlari birlashtirilishi mumkin. Kod blokidagi har bir satr kamida blokdagi birinchi satr sifatida bo'sh joylar sonidan boshlanadi. Chiziqlar oldidagi bo'shliqlar soniga qarab blok qayerdan boshlanishini va tugashini aniqlash mumkin. Bu chiziq bo'sh joyi.

Blokni boshlash uchun Python dasturchilari odatda to'rtta qo'shimcha bo'shliqdan foydalanadilar. Xuddi shu miqdordagi har qanday keyingi chiziq blokning bir qismidir. Blok tugashi bilan blok boshlangunga qadar bir xil indentatsiyaga ega kod satri mavjud bo'lganda tugaydi. Boshqa bloklar ichida bloklar ham bo'lishi mumkin. Quyidagi kodda bloklar ko'rsatilgan va raqamlangan kod diagrammasi ko'rsatilgan.

```python
for guessesTaken in range(6):
    print('Taxmin qiling.')  # print oldida 4ta bo'sh joy bor
    guess = input()
    guess = int(guess)

    if guess < number:
        print('Sizning taxminingiz juda past.')  # Eight spaces in front of "print"

    if guess > number:
        print('Sizning taxminingiz juda yuqori.')

    if guess == number:
        break

```

Tepadagi kodda 12-qatorda hech qanday bo'sh joy yo'q va u hech qanday blok ichida emas.

13-qatorda to'rtta bo'shliq bo'sh joy mavjud. Ushbu satr avvalgi qatorga qaraganda ko'proq bo'sh joy bo'lgani uchun bu erda yangi blok boshlanadi. Xuddi shu miqdordagi yoki undan ko'p miqdordagi bo'sh joy keyin keladigan har bir satr blokning bir qismi hisoblanadi.

Agar Python blokning birinchi qatoriga qaraganda kamroq chiziqli boshqa qatorga duch kelsa, blok tugaydi. Bo'sh satrlarga e'tibor berilmaydi.

18-qatorda blokni boshlaydigan sakkizta bo'shliqning bo'sh joyi mavjud. Ushbu blok boshqa blok ichida. Ammo keyingi satr, 20-satr, faqat to'rtta bo'shliq bilan chegaralangan. Bo'shliq kamayganligi sababli, siz 18-satrning blok tugaganligini bilasiz va 20-satrda 13-satr bilan bir xil chuqurchaga ega bo'lganligi sababli, siz uning blokda ekanligini bilasiz.

21-satr yana sakkizta bo'shliqni ko'paytiradi, shuning uchun blok ichidagi yana bir yangi blok boshlandi: blok. 23-satrda biz w blokdan chiqamiz va 24-satrda x, blok ichidagi so'nggi blokga kiramiz. Ikkala blok va blok x ham 24-qatorda tugaydi.

### Ifodalarni tsiklga qo'yish

```for``` iborasi tsiklning boshlanishini bildiradi. Ko'chadanlar bir xil kodni qayta-qayta bajaradilar. Ijroiya for bayoniga yetganda, for operatoridan keyingi blokga kiradi. Ushbu blokdagi barcha kodlarni ishga tushirgandan so'ng, kodni qayta ishlash uchun ijro yana blokning yuqori qismiga o'tadi.

Interaktiv qobiqga quyidagilarni kiriting:
```
>>> for i in range(3):
    print('Salom! i endi bunga teng' , i)
Salom! i endi bunga teng 0
Salom! i endi bunga teng 1
Salom! i endi bunga teng 2
```

E'tibor bering, (3) diapazonida i uchun yozganingizdan va enter tugmachasini bosganingizdan so'ng, interaktiv qobiq boshqa ```>>>``` buyrug'ini ko'rsatmadi, chunki u sizdan kod blokini yozishni kutgan edi. Oxirgi ko'rsatmalardan so'ng Enter tugmasini yana bir marta bosib, kod blokiga kirishni tugatganligini aytib bering. (Bu faqat interaktiv qobiqda ishlayotganingizda qo'llaniladi. Fayl muharririga ```.py``` fayllarini yozishda bo'sh satr kiritishingiz shart emas.)

12-qatorda for tsiklini ko'rib chiqamiz ```guess.py```:
```python
for guessesTaken in range(6):
    print('Taxmin qiling.')  # print oldida 4ta bo'sh joy bor
    guess = input()
    guess = int(guess)

    if guess < number:
        print('Sizning taxminingiz juda past.')  # Eight spaces in front of "print"

    if guess > number:
        print('Sizning taxminingiz juda yuqori.')

    if guess == number:
        break

if guess == number:
```

## O'yinchi taxminini olish

13 va 14-qatorlar o'yinchidan maxfiy raqam nima ekanligini taxmin qilishni so'raydi va ularga o'z taxminlarini kiritishlariga ruxsat bering:

```python
    print('Taxmin qiling.')  # print oldida 4ta bo'sh joy bor
    guess = input()
```

O'yinchi kiritgan ushbu raqam taxmin nomidagi o'zgaruvchida saqlanadi.

## ```int()```, ```float()``` va ```str()``` funktsiyalari bilan qiymatlarni o'zgartirish

15-qator ```int()``` deb nomlangan yangi funktsiyani chaqiradi:

```python
guess = int(guess)
```

```int()``` funktsiyasi bitta argumentni oladi va argumentning qiymatini butun son sifatida qaytaradi.

```int()``` funktsiyasi qanday ishlashini ko'rish uchun quyidagilarni interaktiv qobiqga kiriting:

```python
>>> int('42')
42
```

```int('42')``` chaqiruvi ```42``` qiymatini qaytaradi.

```python
>>> 3 + int('2')
5
```

```3 + int('2')``` qatorida ```int()``` ning qaytish qiymatini ifodaning bir qismi sifatida ishlatadigan ifoda ko'rsatilgan. 

Agar satrni ```int()``` ga o'tkazishingiz mumkin bo'lsa ham, uni faqat biron bir ma'noli songa o'tkazib bo'lmaydi. `qirq ikki' ni ```int()``` ga o'tish xatolikka olib keladi:

```python
>>> int('forty-two')
Traceback (most recent call last):
 File "<pyshell#5>", line 1, in <module>
 int('forty-two')
ValueError: invalid literal for int() with base 10: 'forty-two'
```

Siz ```int()``` ga o'tkazadigan satr raqamlardan iborat bo'lishi kerak.
Raqamni taxmin qilishda biz ```input()``` funktsiyasi yordamida o'yinchi raqamini olamiz. Esingizda bo'lsin, ```input()``` funktsiyasi har doim o'yinchi kiritgan matn qatorini qaytaradi. Agar o'yinchi 5 ni yozsa, ```input()``` funktsiyasi 5-sonli qiymatni emas, balki '5' satrni qaytaradi. Ammo biz keyinchalik o'yinchi sonini butun son bilan taqqoslashimiz kerak bo'ladi va Python satrni va butun sonni taqqoslash uchun <and> taqqoslashdan foydalana olmaydi:

```python
>>> 4 < '5'
Traceback (most recent call last):
 File "<pyshell#0>", line 1, in <module>
 4 < '5'
TypeError: unorderable types: int() < str()
```

Shuning uchun biz satrni butun songa aylantirishimiz kerak:

```python
14. guess = input()
15. guess = int(guess)
```

14-qatorda biz taxminiy o'zgaruvchini o'yinchi qaysi raqamni kiritgan bo'lsa, satrni qiymatiga beramiz. 15-satr taxmin qilingan satr qiymatini ```int()``` tomonidan qaytarilgan butun son bilan yozadi. ```int(guess)``` kodi berilgan satr asosida yangi qiymatini qaytaradi va ```guess =``` ushbu yangi qiymatni taxmin qilish uchun tayinlaydi. Bu dasturdagi keyingi kod ```guess``` raqam o'zgaruvchisidagi maxfiy sondan katta, kichik yoki teng bo'lishini taqqoslash imkonini beradi.

```float()``` va ```str()``` funktsiyalari xuddi shu tarzda ularga berilgan argumentlarning ```float``` va ```string``` versiyalarini qaytaradi. Interaktiv qobiqga quyidagilarni kiriting:

```python
>>> float('42')
42.0
>>> float(42)
42.0
```

```float()``` ga ```'42'``` qatori yoki ```42``` soni berilganida, float ```42.0``` qaytariladi.

Endi ```str()``` funktsiyasidan foydalanishga harakat qiling:

```python
>>> str(42)
'42'
>>> str(42.0)
'42.0'
```

Butun 42 raqam ```str()``` ga o'tkazilganda, ```'42'``` qatori qaytariladi. Lekin float ```42.0``` ```str()``` ga o'tkazilganda ```'42 .0'``` qatori qaytariladi. ```int()```, ```float()``` va ```str()``` funktsiyalaridan foydalanib siz bitta ma'lumot turining qiymatini qabul qilishingiz va uni boshqa ma'lumot turining qiymati sifatida qaytarishingiz mumkin.

## Mantiqiy (Boolean) ma'lumotlar turi

Python-dagi har bir qiymat bitta ma'lumot turiga tegishli. Hozirgacha kiritilgan ma'lumotlar turlari - bu butun sonlar, suzuvchi nuqta raqami, satrlar va endi mantiqiy ma'lumotlar. Mantiqiy ma'lumotlar turi faqat ikkita qiymatga ega: ```True``` yoki ```False```. Mantiqiy qiymatlar katta T yoki F harflari bilan, qolgan qismi esa kichik harflar bilan kiritilishi kerak.

Mantiqiy qiymatlar boshqa ma'lumotlar turlari kabi o'zgaruvchilarda ham saqlanishi mumkin:

```python
>>> spam = True
>>> eggs = False
```

Ushbu misolda siz ```spam```ni ```True``` ga, tuxumni ```False```-ga o'rnatdingiz. Birinchi harfni katta harf bilan yozishni unutmang.
Shartlarni shakllantirish uchun siz taqqoslash operatorlari bilan mantiqiy qiymatlardan (qisqacha bools deb nomlanadi) foydalanasiz. Avval taqqoslash operatorlarini ko'rib chiqamiz va keyin shartlarni ko'rib chiqamiz.

### Taqqoslash operatorlari

Taqqoslash operatorlari ikkita qiymatni taqqoslaydilar va True yoki False Boolean qiymatiga baho berishadi. 3-1 jadvalda barcha taqqoslash operatorlari keltirilgan.

| Operator | Operatsiya        |
|----------|-------------------|
| <        | kamroq            |
| >        | ko'proq           |
| <=       | kamroq yoki teng  |
| >=       | ko'proq yoki teng |
| ==       | teng              |
| !=       | tengmas           |

Siz allaqachon +, -, * va / matematik operatorlar haqida o'qigansiz. Har qanday operator singari taqqoslash operatorlari ham qiymatlar bilan birlashib, ```guessesTaken < 6``` kabi iboralarni hosil qiladi.

Guess the Number dasturining 17-qatorida taqqoslashdan kamroq operatori ishlatiladi:
```python
17. if guess < number:
```

Yaqinda bayonotlar batafsilroq muhokama qilinadi; hozircha faqat if kalit so'zidan keyin keladigan iborani ko'rib chiqamiz (```guess < number``` qismi). Ushbu ifoda operator tomonidan bog'langan ikkita qiymatni (o'zgaruvchining ```guess``` soni va ```number``` qiymatlarni) o'z ichiga oladi (<, yoki undan kam belgisi).

### Shartlar bilan rost yoki yolg'on ekanligini tekshirish

Shart - bu ikki qiymatni taqqoslash operatori bilan birlashtirgan (<or> kabi) va mantiqiy qiymatga baho beradigan ifoda. Shart - bu "rost" yoki "yolg'on" deb baholanadigan ifodaning yana bir nomi. Shartlardan foydalanadigan bitta joy ```if``` ifodalarida.

Masalan, 17-satrdagi ```guess < number``` shartini qilishda «```guess```da saqlanadigan qiymat ```number```daa saqlangan qiymatdan kammi?» deb so'raydi. Agar shunday bo'lsa, unda shart ```True``` ga to'g'ri keladi. Agar yo'q bo'lsa, shart ```False``` deb baholanadi.

### Booleans, taqqoslash operatorlari va shartlari bilan tajriba o'tkazish
Mantiqiy natijalarini ko'rish uchun interaktiv qobiqga quyidagi ifodalarni kiriting:

```python
>>> 0 < 6
True
>>> 6 < 0
False
```

```0 < 6``` sharti ```True``` mantiqiy qiymatni qaytaradi, chunki 0 raqami 6 sonidan kichik, ammo 6 soni 0 dan kam bo'lmaganligi sababli ```6 < 0``` sharti ```False``` deb baholanadi.

E'tibor bering, ```10 < 10``` ```False``` qiymatini beradi, chunki 10 raqami 10 sonidan kichik emas:

```python
>>> 10 < 10
False
```

Qadriyatlar bir xil. Agar Elis Bob bilan bir xil balandlikda bo'lsa, siz Elis Bobdan balandroq yoki Elis Bobdan pastroq deb aytolmaysiz. Ushbu ikkala bayonot ham yolg'ondir.
Endi ushbu iboralarni interaktiv qobiqga kiriting:

```python
>>> 10 == 10
True
>>> 10 == 11
False
>>> 11 == 10
False
>>> 10 != 10
False
```

Ushbu misolda ```10 10``` ga teng, shuning uchun ```10 == 10``` ```True``` qiymatiga baho beradi. Ammo ```10 11``` ga teng emas, shuning uchun ```10 == 11``` bu ```False```. Buyurtma aylantirilgan bo'lsa ham, ```11``` hali ```10``` ga teng emas, shuning uchun ```11 == 10 False```. Nihoyat, 10 10 ga teng, shuning uchun ```10! = 10``` False. 
Siz qatorli ifodalarni taqqoslash operatorlari bilan baholashingiz mumkin:

```python
>>> 'Salom' == 'Salom'
True
>>> 'Xayr' != 'Salom'
True
>>> 'Salom' == 'SALOM'
False
```

```"Salom"``` ```"Salom"``` ga teng, shuning uchun "Salom" == "Salom" to'g'ri. ```"Xayr"``` so'zi ```"Salom"``` ga teng emas, shuning uchun ```"Xayr" ! = "Salom"``` ham to'g'ri.
E'tibor bering, oxirgi satr ```False``` deb baholanadi. Pythonda katta va kichik harflar bir xil emas, shuning uchun ```"Salom"``` va ```"SALOM"``` ga teng emas.

Satr va butun son qiymatlari hech qachon bir-biriga teng bo'lmaydi. Masalan, interaktiv qobiqga quyidagilarni kiriting:

```python
>>> 42 == 'Hello'
False
>>> 42 != '42'
True
```
Birinchi misolda 42 - butun son, ```'Salom'``` - satr, shuning uchun qiymatlar teng emas va ifoda False deb baholanadi. Ikkinchi misolda "42" qatori hali ham butun son emas, shuning uchun "42 butun son" 42 "qatoriga teng emas" iborasi ```True``` qiymatiga baho beradi.

### ```=``` va ```==``` orasidagi farq

Topshirish operatori, ```=``` va taqqoslash operatori == bilan adashtirmaslik uchun ehtiyot bo'ling. Teng belgisi, ```=``` o'zgaruvchiga qiymatni saqlash uchun tayinlash bayonotlarida, ikkilangan teng belgisi ```==```, ikkita qiymat teng yoki yo'qligini ifodalashda ishlatiladi. Ikkinchisini ishlatmoqchi bo'lganingizda tasodifan foydalanish oson.
Ikkala taqqoslash operatori, ```==``` va taqqoslagichga teng bo'lmagan operator, ```!=``` ikkala belgidan iborat ekanligini eslashda yordam berishi mumkin.

## if ifodasi

17-qator - if ifodasi:

```python
    if guess < number:
        print('Sizning taxminingiz juda past.')
```

```if``` iborasidan keyingi kod bloki ishlaydi, agar ```if``` iborasining holati ```True``` bo'lsa. Agar shart ```False``` bo'lsa, if blokidagi kod o'tkazib yuboriladi. ```if``` operatorlari yordamida dasturni ma'lum bir kodni faqat xohlagan vaqtingizda bajarishingiz mumkin.

17-qatorda o'yinchining taxminlari kompyuterning maxfiy raqamidan kamligini tekshiradi. Agar shunday bo'lsa, unda ijro 18 satrdagi if blok ichida harakat qiladi va o'yinchining taxminlari juda past bo'lganligi haqida xabar chiqaradi.
20-qatorda o'yinchi taxminining maxfiy raqamdan kattaroqligini tekshiradi:

```python
    if guess > number:
        print('Sizning taxminingiz juda yuqori.')
```

Agar bu holat ```True``` bo'lsa, ```print()``` funktsiyasiga qo'ng'iroq o'yinchilarga ularning taxminlari juda yuqori ekanligini aytadi.

## break bilan tsikllarni erta tark etish

23-satrdagi ```if``` ifodasi o'yinchi taxmin qilgan raqam maxfiy raqamga tengligini tekshiradi. Agar shunday bo'lsa, dastur ```break``` qatorini 24-qatorda ishlaydi:

```python
23. if guess == number:
24. break
```

```break``` bayonoti ijroning ```for``` blokidan darhol blok tugagandan so'ng birinchi qatorga o'tishini aytadi. ```break``` operatori faqat ```tsikl``` ichida, masalan ```for``` for blokida joylashgan.

## O'yinchining g'alaba qozonganligini tekshirish

```for``` bloki kodning keyingi satrida indentsiyasiz tugaydi, ya'ni 26 satr:

```python
26. if guess == number:
```
Amalga oshirilish for blokni olti marta aylanib chiqqani uchun (o'yinchi taxminlari tugagach) yoki 24-satrdagi tanaffus bayonoti bajarilganligi sababli (o'yinchi raqamni to'g'ri taxmin qilganda) qoldiradi.

26-qatorda o'yinchi to'g'ri taxmin qilganligini tekshiradi. Agar shunday bo'lsa, ijro 27-qatorga ```if``` blokini kiritadi:

```python
    guessesTaken = str(guessesTaken + 1)
    print('Barakalla, ' + myName + '! Siz mening sonimni ' + guessesTaken + ' ta taxminda topdingiz!')
```

27 va 28-qatorlar faqat 26-satrda ```if``` ifodasidagi shart To'g'ri bo'lsa (ya'ni, o'yinchi kompyuterning raqamini to'g'ri taxmin qilgan bo'lsa) bajariladi.

27-qator ```str()``` funktsiyasini chaqiradi, bu ```guessesTaken + 1``` satr shaklini qaytaradi (chunki ```range``` funktsiyasi 1 dan 6 gacha emas, balki 0 dan 5 gacha).
28-qatorda o'yinchiga g'alaba qozonganligi va qancha taxmin qilinganligini aytib berish uchun satrlar birlashtiriladi. Faqatgina satr qiymatlari boshqa satrlarni birlashtirishi mumkin. Shuning uchun 27-satrda ```guessesTaken + 1``` qatorini satrga almashtirish kerak edi. Aks holda, satr butun son bilan birlashtirishdagi urinish Python-da xatolikni keltirib chiqaradi.

## O'yinchining yo'qolganligini tekshirish
Agar o'yinchining taxminlari tugasa, ijro ushbu kod satriga o'tadi:
```python
30. if guess != number:
```
30-qatorda o'yinchining so'nggi taxminlari maxfiy raqamga teng emasligini tekshirish uchun teng bo'lmagan operator ```!=``` foydalaniladi. Agar bu shart ```True``` bo'lsa, ijro 31-satrdagi ```if``` blokiga o'tadi.

31 va 32-qatorlar if blokining ichida joylashgan bo'lib, faqat 30-satrdagi shart To'g'ri bo'lsa bajariladi:

```python
31.    number = str(number)
32.    print('Yo\'q. Man o\'ylagan son ' + number + ' edi.')
```

Ushbu blokda dastur o'yinvhi maxfiy raqam nima ekanligini aytadi. Bu satrlarni birlashtirishni talab qiladi, ammo ```number``` butun sonni saqlaydi. 31-qatorda 'Yo\'q. Man o\'ylagan son ' + number + ' edi.'.

Shu nuqtada ijro kodning oxiriga yetdi va dastur tugaydi. Tabriklaymiz! Siz hozirgina birinchi haqiqiy o'yinni dasturlashtirdingiz!

Siz o'yinchi olgan taxminlar sonini o'zgartirib, o'yinning qiyinligini sozlashingiz mumkin. Aktyorga atigi to'rtta taxminni berish uchun 12-satrdagi kodni o'zgartiring:

```python
12. for guessesTaken in range(4):
```

4-ni ```range()```ga o'tkazib, tsikl ichidagi kodning oltita o'rniga to'rt marta ishlashini ta'minlaysiz. Bu o'yinni ancha qiyinlashtiradi. O'yinni osonlashtirish uchun ```range()``` funktsiya chaqiruviga kattaroq butun sonni o'tkazing. Bu tsiklni yana bir necha bor ishlashiga va o'yinchidan ko'proq taxminlarni qabul qilishga olib keladi.