# Tic-Tac-Toe

Ushbu bobda Tic-Tac-Toe o'yini yoritiladi. Tic-Tac-Toe odatda ikki kishi bilan o'ynaydi. Bir o'yinchi X, ikkinchisi esa O. O'yinchilar navbat bilan o'zlarining X yoki O-larini qo'yishadi. Agar o'yinchi uchta belgini ketma-ket, ustun yoki diagonalda taxtaga qo'ysa, ular g'alaba qozonishadi. Taxtada boshqa g'olibli kataklar qolmaganida, o'yin durang bilan tugaydi.

Ushbu bobda ko'pgina yangi narsalar kiritilmagan
dasturlash tushunchalari mavjud. Foydalanuvchi oddiy sun'iy intellektga qarshi o'ynaydi, biz uni mavjud dasturlash bo'yicha bilimlarimiz yordamida yozamiz. Sun'iy intellekt (AI) - bu o'yinchi harakatiga aql bilan javob bera oladigan kompyuter dasturi. Tic-Tac-Toe o'ynaydigan AI murakkab emas; bu haqiqatan ham kodning bir necha satrlari.
Dasturning namunaviy ishlashini ko'rib chiqishni boshlaymiz. O'yinchi o'z harakatlarini kerakli bo'sh joy sonini kiritish orqali amalga oshiradi. Ro'yxatdagi qaysi indeks qaysi maydon uchun ekanligini eslab qolishimiz uchun biz 10-1-rasmda ko'rsatilgandek, taxtani klaviatura raqamlari qatori kabi raqamlaymiz.

## Tic-Tac-Toe-ning namunaviy o'ynalishi

Tic-Tac-Toe dasturini ishga tushirganda foydalanuvchi nimani ko'radi. Aktyor kiritgan matn qalin harf bilan yozilgan.

## Dasturni loyihalash

10-2-rasmda Tic-Tac-Toe dasturining blok-sxemasi ko'rsatilgan. Dastur o'yinchidan X yoki O harflarini tanlashini so'rab boshlanadi, birinchi gali kim kelishi tasodifiy tanlanadi. Keyin o'yinchi va kompyuter navbatma-navbat harakat qilishadi.

Blok-sxemaning chap tomonidagi katakchalar o'yinchining gali paytida nima sodir bo'lishini, o'ng tomonda esa kompyuterning gali paytida nima bo'lishini ko'rsatadi. O'yinchi yoki kompyuter harakat qilgandan so'ng, dastur ularning g'alaba qozonganligini yoki tenglikni keltirib chiqarganligini tekshiradi, so'ngra o'yin o'zgaradi. O'yin tugagandan so'ng, dastur o'yinchidan yana o'ynashni xohlaysizmi, deb so'raydi.

### Ma'lumot sifatida o'yin stolini taqdim etish

Birinchidan, qanday qilib o'zgaruvchida ma'lumot sifatida taxtani ko'rsatishni tushunishingiz kerak. Qog'ozda Tic-Tac-Toe taxtasi gorizontal va vertikal chiziqlar jufti sifatida chizilgan bo'lib, to'qqizta bo'shliqning har birida X, O yoki bo'sh joy mavjud. Dasturda Tic-Tac-Toe taxtasi Hangman ASCII san'ati kabi torlar ro'yxati sifatida namoyish etilgan. Har bir ip taxtadagi to'qqiz bo'shliqdan birini aks ettiradi. Iplar X pleyer uchun 'X', O pleyer uchun 'O' yoki bo'sh joy uchun bitta bo'shliq ' '.

Biz klaviaturadagi raqamlar taxtasi kabi taxtamizni yotqizayotganimizni unutmang. Shunday qilib, agar 10 ta satrdan iborat ro'yxat taxtali nomidagi o'zgaruvchida saqlangan bo'lsa, u holda `board[7]` taxtaning yuqori chap qismidir, `board[8]` eng o'rta bo'shliq, `board[9]` yuqori bo'ladi. to'g'ri joy va boshqalar. Dastur ro'yxatdagi `0` indeksidagi qatorni e'tiborsiz qoldiradi. O'yinchi qaysi maydonga o'tishni xohlashini aytib berish uchun o'yinchi `1` dan `9` gacha raqamni kiritadi.

### O'yinni AI bilan strategiklashtirish

AI o'yin stolga qarab, qaysi bo'shliqlar turiga o'tishini hal qilishi kerak. Aniqroq bo'lish uchun biz Tic-Tac-Toe taxtasida uch xil joyni belgilaymiz: burchaklar, yon tomonlar va markaz. 10-3-rasmdagi jadvalda har bir bo'shliq nima ekanligini ko'rsatadi.

Tic-Tac-Toe-ni o'ynash uchun AI strategiyasi oddiy algoritmga amal qiladi - natijani hisoblash uchun cheklangan ko'rsatmalar. Bitta dastur bir necha xil algoritmlardan foydalanishi mumkin. Algoritm blok sxemasi bilan ifodalanishi mumkin. Tic-Tac-Toe AI algoritmi 10-4-rasmda ko'rsatilgandek, eng yaxshi harakatni hisoblab chiqadi.

AI algoritmi quyidagi bosqichlarga ega:

1. O'yinda g'alaba qozonadigan kompyuterning biron bir harakati borligini tekshiring. Agar mavjud bo'lsa, bu harakatni bajaring. Aks holda, 2-bosqichga o'ting.
2. O'yinchining kompyuterda o'yinni yo'qotishiga olib keladigan biron bir harakati bor-yo'qligiga qarang. Agar mavjud bo'lsa, o'yinchini blokirovka qilish uchun u yerga o'ting. Aks holda, 3-bosqichga o'ting.
3. Burchak joylaridan (1, 3, 7 yoki 9) bo'sh joy mavjudligini tekshiring. Agar shunday bo'lsa, u erga ko'chiring. Agar burchakda bo'sh joy bo'lmasa, 4-bosqichga o'ting.
4. Markaz bepul yoki yo'qligini tekshiring. Agar shunday bo'lsa, u erga ko'chiring. Agar u bo'lmasa, 5-bosqichga o'ting.
   Har qanday yon bo'shliqqa o'ting (bo'shliqlar 2, 4, 6 yoki 8). 5. Boshqa qadamlar yo'q, chunki bajarilish 5-bosqichga etib boradigan bo'lsa, yon bo'shliqlar qoladi.

Bularning barchasi 10-2-rasmdagi bloklar jadvalidagi Get computer-ning harakatlanish oynasida sodir bo'ladi. Siz ushbu ma'lumotlarni 10-4-rasmdagi katakchalar bilan blok-sxemaga qo'shishingiz mumkin.
Ushbu algoritm `getComputerMove()` va `getComputerMove()` chaqiradigan boshqa funktsiyalarda amalga oshiriladi.

## `random` modulni import qilish

Birinchi juft satr sharh va tasodifiy modulni import qiladigan satrdan iborat bo'lib, keyinchalik `randint()` funktsiyasini chaqirishingiz mumkin:

```python
# Tic Tac Toe

import random
```

Siz ushbu ikkala tushunchani oldin ham ko'rgansiz, shuning uchun dasturning keyingi qismiga o'tamiz.

## O'yin stolini ekranga chop etish

Kodning keyingi qismida biz taxtani chizish funktsiyasini aniqlaymiz:

```python
def drawBoard(board):
    # Ushbu funktsiya o'yin stolini bosib o'tganligini yozib chiqadi.

    # "board" - bu o'yin stolini ifodalovchi 10 ta satr ro'yxati (0 indeksini e'tiborsiz qoldiring)
    print(board[7] + '|' + board[8] + '|' + board[9])
    print('-+-+-')
    print(board[4] + '|' + board[5] + '|' + board[6])
    print('-+-+-')
    print(board[1] + '|' + board[2] + '|' + board[3]
```

`drawBoard()` funktsiyasi `board` parametri bilan ifodalangan o'yin stolini bosib chiqaradi. Esda tutingki, taxta `10` ta satr ro'yxati sifatida namoyish etiladi, bu yerda `1`-indeksdagi satr Tic-Tac-Toe taxtasidagi `1`-bo'shliqdagi belgi va hk. 0 indeksidagi satr e'tiborga olinmaydi. O'yinning ko'plab funktsiyalari taxta sifatida 10 ta satr ro'yxatini o'tkazish orqali ishlaydi.

Qatorlarni oraliqda to'g'ri o'rnatganingizga ishonch hosil qiling; aks holda, taxta ekranda bosilganda kulgili ko'rinadi. Bu yerda `drawBoard()` ga chaqirishning ba'zi bir misollari (`board` uchun argument bilan) va funktsiya nimani bosib chiqarishi mumkin.

```python
>>> drawBoard([' ', ' ', ' ', ' ', 'X', 'O', ' ', 'X', ' ', 'O'])
X| |
-+-+-
X|O|
-+-+-
 | |
>>> drawBoard([' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '])
 | |
-+-+-
 | |
-+-+-
 | |
```

Dastur har bir satrni oladi va 10-1-rasmdan klaviatura raqamlari maydonchasiga muvofiq sonli tartibda doskaga joylashtiradi, shuning uchun dastlabki uchta satr taxtaning pastki qatori, keyingi uchta satr o'rtasi va oxirgi uchta satrlar - tepadir.

## Aktyorga X yoki O ni tanlashga ruxsat berish

Keyinchalik, o'yinchi uchun X yoki O ni tayinlash funktsiyasini aniqlaymiz:

```python
def inputPlayerLetter():
    # O'yinchi qaysi harfni tanlashini xohlasa, yozib beradi.
    # Ro'yxatni birinchi element sifatida o'yinchining xati, ikkinchisi sifatida kompyuterning xatini qaytaradi.
    letter = ''
    while not (letter == 'X' or letter == 'O'):
        print('Siz X yoki O bo\'lmoqchimisiz?')
        letter = input().upper()
```

`inputPlayerLetter()` funktsiyasi pleyer X yoki O bo'lishni xohlaydimi deb so'raydi. `while` tsiklining holati qavslarni o'z ichiga oladi, ya'ni avval qavs ichidagi ifoda baholanadi. Agar harf o'zgaruvchisi 'X' ga o'rnatilsa, ifoda quyidagicha baholanadi:

Agar harf `X` yoki `O` qiymatiga ega bo'lsa, u holda tsiklning holati `False` va dasturning bajarilishini while blokidan keyin davom ettirishga imkon beradi. Agar shart `True` bo'lsa, dastur o'yinchi X yoki O kiritmaguncha, o'yinchidan harf tanlashini so'raydi. 21-qatorda chaqiruv orqali qaytarilgan satr avtomatik ravishda `upper()` satr usuli bilan `input()` ga bosh harflarga o'zgartiriladi.

Keyingi funktsiya ikkita elementdan iborat ro'yxatni qaytaradi:

```python
     # ro'yxatdagi birinchi element - o'yinchining harfi, ikkinchisi - kompyuterning harfi.
        if letter == 'X':
            return ['X', 'O']
        else:
            return ['O', 'X']
```

Birinchi element (0 indeksidagi satr) o'yinchining harfi, ikkinchi element (1-indeksdagi satr) kompyuterning harfidir. `if` va `else` operatorlari qaytish uchun mos ro'yxatni tanlaydi.

## Kim birinchi bo'lib yurishini hal qilish

Keyin biz `randint()` dan foydalanib, pleyer yoki kompyuterning avval o'ynashini tanlash uchun funktsiyani yaratamiz:

```python
def whoGoesFirst():
    # Birinchi bo'lib ketadigan o'yinchini tasodifiy tanlash.
    if random.randint(0, 1) == 0:
        return 'computer'
    else:
        return 'player'
```

`whoGoesFirst()` funktsiyasi kompyuter yoki o'yinchni birinchi bo'lib ketishini aniqlash uchun virtual tanga aylanmasini amalga oshiradi. Tangalarni aylantirish `random.randint(0, 1)` ga qo'ng'iroq bilan amalga oshiriladi. Funktsiya `0` ga qaytish ehtimoli 50 foizga va funktsiya 1 qaytarish ehtimoli 50 foizga teng. Agar bu funktsiya chaqiruvi 0 ga qaytarsa, `whoGoesFirst()` funktsiyasi 'computer' qatorini qaytaradi. Aks holda, funktsiya "player" qatorini qaytaradi. Ushbu funktsiyani chaqiradigan kod o'yinning birinchi harakatini kim bajarishini aniqlash uchun qaytarish qiymatidan foydalanadi.

## O'yin stoliga belgi qo'yish

`makeMove()` funktsiyasi oddiy:

```python
def makeMove(board, letter, move):
    board[move] = letter
```

Parametrlar `board`, `letter` va `move`dir. O'zgaruvchan `board` - bu o'yin stiolini holatini ifodalovchi 10 qatorli ro'yxat. O'zgaruvchi `letter` - bu o'yinchining harfi (yoki 'X' yoki 'O'). O'zgaruvchi `move` - bu o'yinchi borishni istagan o'yin stolidagi joy (bu 1 dan 9 gacha bo'lgan butun son).

Ammo kuting - 37-qatorda, ushbu kod taxta ro'yxatidagi elementlardan birini harfdagi qiymatga o'zgartirganga o'xshaydi. Ushbu kod funktsiyada bo'lgani uchun, funktsiya qaytganda `board` parametri unutiladi. Xo'sh, `board` o'zgaruvchi ham unutmaslik kerakmi?

Aslida, bunday emas, chunki funktsiyalarga argument sifatida berganingizda ro'yxatlar alohida ahamiyatga ega. Siz aslida ro'yxatning o'ziga emas, balki ro'yxatga havola qilmoqdasiz. Ro'yxatlar va ro'yxatlarga havolalar o'rtasidagi farq haqida bilib olaylik.

### Ro'yxat havolalari

Interaktiv qobiqga quyidagilarni kiriting:

```python
>>> spam = 42
>>> cheese = spam
>>> spam = 100
>>> spam
100
>>> cheese
42
```

Ushbu natijalar hozirgacha bilganingizdan mantiqiy. Siz `spam` o'zgaruvchisiga `42` ni berasiz, keyin o'zgaruvchiga `cheese` uchun `spam` qiymatini belgilaysiz. Keyinchalik `spam`ni 100 ga yozganingizda, bu `cheese`dagi qiymatga ta'sir qilmaydi. Buning sababi shundaki, `spam` va `cheese` har xil qiymatlarni saqlaydigan har xil o'zgaruvchidir.

Ammo ro'yxatlar bu tarzda ishlamaydi. O'zgaruvchiga ro'yxatni tayinlaganingizda, siz aslida o'zgaruvchiga ro'yxat havolasini tayinlaysiz. Malumot - bu ma'lumotlarning bir qismi saqlanadigan joyga ishora qiluvchi qiymat. Buni tushunishni osonlashtiradigan ba'zi kodlarni ko'rib chiqamiz. Buni interaktiv qobiqga kiriting:

```python
 >>> spam = [0, 1, 2, 3, 4, 5]
>>> cheese = spam
>>> cheese[1] = 'Hello!'
>>> spam
[0, 'Hello!', 2, 3, 4, 5]
>>> cheese
[0, 'Hello!', 2, 3, 4, 5]

```

Kod faqat `cheese` ro'yxatini o'zgartirdi, ammo `cheese` ham, `spam` ro'yxatlar ham o'zgarganga o'xshaydi. Buning sababi shundaki, `spam` o'zgaruvchisi ro'yxat qiymatining o'zi emas, balki 10-5-rasmda ko'rsatilgandek, ro'yxatga havolani o'z ichiga oladi. Ro'yxatning o'zi hech qanday o'zgaruvchida mavjud emas, aksincha ular tashqarisida mavjud.

E'tibor bering, `cheese = spam` ro'yxat qiymatini o'zi nusxalash o'rniga, ro'yxat ma'lumotlarini `spam` da `cheese` ko'chiradi. Endi `spam` ham, `cheese` ham bir xil ro'yxat qiymatiga ishora qiluvchi ma'lumotnomani saqlaydi. Ammo bitta ro'yxat bor, chunki ro'yxatning o'zi ko'chirilmagan. 10-6-rasmda ushbu nusxa ko'chirish ko'rsatilgan

Demak, `cheese[1] = 'Salom!'` satridagi satr `spam`ga tegishli bo'lgan ro'yxatni o'zgartiradi. Shuning uchun `spam` pishloq ko'rsatadigan ro'yxat qiymatini qaytaradi. Ularning ikkalasida ham 10-7-rasmda ko'rsatilgandek, xuddi shu ro'yxatga havolalar mavjud.

Agar siz `spam` va `cheese` ikki xil ro'yxatni saqlashini istasangiz, yaratishingiz kerak ma'lumotnomani nusxalash o'rniga ikkita ro'yxat:

```python
>>> spam = [0, 1, 2, 3, 4, 5]
>>> cheese = [0, 1, 2, 3, 4, 5]
```

Oldingi misolda `spam` va `cheese` ikki xil ro'yxatni saqlaydi (garchi bu ro'yxatlar tarkibiga ko'ra bir xil bo'lsa ham). Endi siz ro'yxatlarning birini o'zgartirsangiz, ikkinchisiga ta'sir qilmaydi, chunki spam va pishloqda ikki xil ro'yxatga havolalar mavjud:

```python
>>> spam = [0, 1, 2, 3, 4, 5]
>>> cheese = [0, 1, 2, 3, 4, 5]
>>> cheese[1] = 'Hello!'
>>> spam
[0, 1, 2, 3, 4, 5]
>>> cheese
[0, 'Hello!', 2, 3, 4, 5]

```

10-8-rasmda ushbu misolda o'zgaruvchilar va ro'yxat qiymatlari qanday o'rnatilishi ko'rsatilgan.
Lug'atlar xuddi shu tarzda ishlaydi. O'zgaruvchilar **lug'atlarni** saqlamaydi; ular lug'atlarga havolalarni saqlaydi.

### `makeMove()` da ro'yxat havolalaridan foydalanish

```python
def makeMove(board, letter, move):
    board[move] = letter
```

Ro'yxat qiymati `board` parametri uchun berilganda, funktsiyaning mahalliy o'zgaruvchisi haqiqatan ham ro'yxatning o'zi emas, balki ro'yxatga havola nusxasi. Shunday qilib, ushbu funktsiyadagi paneldagi har qanday o'zgarishlar asl ro'yxatga ham kiritiladi. `board` mahalliy o'zgaruvchiga ega bo'lsa ham, `makeMove()` funktsiyasi asl ro'yxatni o'zgartiradi.

`letter` va `move` parametrlari - bu siz kiritgan qator va butun qiymatlarning nusxalari. Ular qiymatlarning nusxalari bo'lgani uchun, agar siz `letter` o'zgartirsangiz yoki ushbu funktsiyani o'zgartirsangiz, `makeMove()` ga chaqiruv qilganingizda foydalangan asl o'zgaruvchilar o'zgartirilmaydi.

## O'yinchining g'alaba qozonganligini tekshirish

```python
def isWinner(bo, le):
    # Agar o'yin stoli va o'yinchining xatini hisobga olgan holda, ushbu funktsiya, agar u g'olib chiqqan bo'lsa, True qiymatini qaytaradi.
    # Biz taxta o'rniga bo va harf o'rniga le ishlatamiz, shuning uchun ko'p yozishimiz shart emas.
    return ((bo[7] == le and bo[8] == le and bo[9] == le) or # tepada
    (bo[4] == le and bo[5] == le and bo[6] == le) or # o'rtada
    (bo[1] == le and bo[2] == le and bo[3] == le) or # pastda
    (bo[7] == le and bo[4] == le and bo[1] == le) or # chap past burchakda
    (bo[8] == le and bo[5] == le and bo[2] == le) or # o'rtada pastda
    (bo[9] == le and bo[6] == le and bo[3] == le) or # o'ng past burchakda
    (bo[7] == le and bo[5] == le and bo[3] == le) or # diagonal
    (bo[9] == le and bo[5] == le and bo[1] == le)) # diagonal
```

`Bo` va `le` nomlari `board` va `letter` parametrlari uchun yorliqlardir. Ushbu qisqartirilgan ismlar ushbu funktsiyani kiritish uchun kamroq narsangiz borligini anglatadi. Esingizda bo'lsa, Python sizning o'zgaruvchilaringizga qanday nom berishingizga ahamiyat bermaydi.

Tic-Tac Toe-da g'alaba qozonishning sakkizta usuli bor: siz yuqori, o'rta yoki pastki qatorlar bo'ylab chiziqqa ega bo'lishingiz mumkin; chap, o'rta yoki o'ng ustunlar bo'ylab chiziqqa ega bo'lishingiz mumkin; yoki ikkita diagonalning ikkalasi bo'ylab chiziqqa ega bo'lishingiz mumkin.

Shartning har bir satri berilgan satr uchun uchta bo'shliq berilgan harfga tengligini tekshiradi (va operator bilan birlashtirilgan). Siz har bir qatorni `or` operator yordamida birlashtirib, g'alaba qozonishning sakkiz xil usulini tekshirasiz. Demak, ushbu harfga egalik qilgan o'yinchi g'olib deb aytishimiz uchun sakkizta usuldan faqat bittasi to'g'ri bo'lishi kerak.

Keling, `le` 'O', `bo` esa `['', 'O', 'O', 'O', '', 'X', '', 'X', '', '']`. Kengash shunday ko'rinadi:

```python
X| |
-+-+-
 |X|
-+-+-
O|O|O
```

42-qatorda qaytish kalit so'zidan keyingi ibora qanday baholanadi. Birinchi Python o'zgaruvchilarni har bir o'zgaruvchining qiymatlari bilan almashtiradi:

```python
return (('X' == 'O' and ' ' == 'O' and ' ' == 'O') or
 (' ' == 'O' and 'X' == 'O' and ' ' == 'O') or
 ('O' == 'O' and 'O' == 'O' and 'O' == 'O') or
 ('X' == 'O' and ' ' == 'O' and 'O' == 'O') or
 (' ' == 'O' and 'X' == 'O' and 'O' == 'O') or
 (' ' == 'O' and ' ' == 'O' and 'O' == 'O') or
 ('X' == 'O' and 'X' == 'O' and 'O' == 'O') or
 (' ' == 'O' and 'X' == 'O' and 'O' == 'O'))
```

Keyinchalik, Python qavs ichidagi barcha `==` taqqoslashni mantiqiy qiymatlarga baholaydi:

```python
return ((False and False and False) or
 (False and False and False) or
 (True and True and True) or
 (False and False and True) or
 (False and False and True) or
 (False and False and True) or
 (False and False and True) or
 (False and False and True))

```

Keyin Python tarjimoni qavs ichidagi barcha ifodalarni baholaydi:

```python
return ((False) or
 (False) or
 (True) or
 (False) or
 (False) or
 (False) or
 (False) or
 (False))
```

Hozirda har bir ichki qavs ichida bitta qiymat bor, siz ulardan xalos bo'lishingiz mumkin:

```python
return (False or
 False or
 True or
 False or
 False or
 False or
 False or
 False)
```

Endi Python ushbu operatorlar yoki operatorlar tomonidan bog'langan ifodani baholaydi:

```python
 return (True)
```

Yana bir marta qavslardan xalos bo'ling, shunda bitta qiymat qoladi:

```python
 return True
```
