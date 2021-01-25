# Hangman uchun manba kodi

Ushbu bobning o'yini avvalgi o'yinlarga qaraganda bir oz kattaroq, lekin uning aksariyati "Hangman" rasmlari uchun ASCII san'ati.
Fayl muharririga quyidagilarni kiriting va hangman.py sifatida saqlang. Agar siz quyidagi kodni kiritgandan so'ng xatolarga duch kelsangiz, siz kiritilgan kodni kitobning kodi bilan onlayn diff vositasi bilan taqqoslang.

```python
import random
HANGMAN_PICS = ['''
  +---+
      |
      |
      |
     ===''', '''
  +---+
  O   |
      |
      |
     ===''', '''
  +---+
  O   |
  |   |
      |
     ===''', '''
  +---+
  O   |
 /|   |
      |
     ===''', '''
  +---+
  O   |
 /|\  |
      |
     ===''', '''
  +---+
  O   |
 /|\  |
 /    |
     ===''', '''
  +---+
  O   |
 /|\  |
 / \  |
     ===''']
words = 'ant baboon badger bat bear beaver camel cat clam cobra cougar coyote crow deer dog donkey duck eagle ferret fox frog goat goose hawk lion lizard llama mole monkey moose mouse mule newt otter owl panda parrot pigeon python rabbit ram rat raven rhino salmon seal shark sheep skunk sloth snake spider stork swan tiger toad trout turkey turtle weasel whale wolf wombat zebra'.split()

def getRandomWord(wordList):
    # Ushbu funktsiya tasodifiy qatorni uzatilgan qatorlar qatoridan qaytaradi..
    wordIndex = random.randint(0, len(wordList) - 1)
    return wordList[wordIndex]

def displayBoard(missedLetters, correctLetters, secretWord):
    print(HANGMAN_PICS[len(missedLetters)])
    print()

    print('O'tkazib yuborilgan harflar:', end=' ')
    for letter in missedLetters:
        print(letter, end=' ')
    print()

    blanks = '_' * len(secretWord)

    for i in range(len(secretWord)): # bo'sh joylarni to'g'ri taxmin qilingan harflar bilan almashtiring
        if secretWord[i] in correctLetters:
            blanks = blanks[:i] + secretWord[i] + blanks[i+1:]

    for letter in blanks: # har bir harf orasidagi bo'shliqlar bilan maxfiy so'zni ko'rsating
        print(letter, end=' ')
    print()

def getGuess(alreadyGuessed):
    # O'yinchi kiritilgan xarfni qaytaradi. Ushbu funktsiya o'yinchining bitta harfni kiritganiga ishonch hosil qiladi, boshqa narsani emas.
    while True:
        print('Guess a letter.')
        guess = input()
        guess = guess.lower()
        if len(guess) != 1:
            print('Iltimos, bitta harfni kiriting.')
        elif guess in alreadyGuessed:
            print('Siz allaqachon bu xatni taxmin qilgansiz. Qayta tanlang.')
        elif guess not in 'abcdefghijklmnopqrstuvwxyz':
            print('Iltimos, faqat harf kiriting.')
        else:
            return guess

def playAgain():
    # Agar o'yinchi yana o'ynashni xohlasa, bu funktsiya True qiymatini qaytaradi; aks holda, False qaytadi.
    print('Yana o\'ynashni istaysizmi? (ha or yo'q)')
    return input().lower().startswith('h')


print('H A N G M A N')
missedLetters = ''
correctLetters = ''
secretWord = getRandomWord(words)
gameIsDone = False

while True:
    displayBoard(missedLetters, correctLetters, secretWord)

    # O'yinchinga xarf kirishiga ruxsat bering.
    guess = getGuess(missedLetters + correctLetters)

    if guess in secretWord:
        correctLetters = correctLetters + guess

        # O'yinchining g'alaba qozonganligini tekshiring.
        foundAllLetters = True
        for i in range(len(secretWord)):
            if secretWord[i] not in correctLetters:
                foundAllLetters = False
                break
        if foundAllLetters:
            print('Ha! Mahfiy so\'z "' + secretWord + '"! Siz yutdingiz!')
            gameIsDone = True
    else:
        missedLetters = missedLetters + guess

        # O'yinchi juda ko'p marta taxmin qilgani va yutqazganligini tekshiring.
        if len(missedLetters) == len(HANGMAN_PICS) - 1:
            displayBoard(missedLetters, correctLetters, secretWord)
            print('Sizda taxminlar tugadi!\n' str(len(missedLetters)) + ' noto\'g\'ri tahminlardan keyin va ' + str(len(correctLetters)) + ' to\'g\'ri tahminlardan keyin, mahfiy so\'z"' + secretWord + '" edi')
            gameIsDone = True

    # O'yinchidan yana o'ynashni xohlashlarini so'rang (lekin agar o'yin tugagan bo'lsa).
    if gameIsDone:
        if playAgain():
            missedLetters = ''
            correctLetters = ''
            gameIsDone = False
            secretWord = getRandomWord(words)
        else:
            break
```

## ```random``` modulni import qilish

Hangman dasturi tasodifiy ravishda so'zlar ro'yxatidan o'yinchi uchun taxminiy sirni tanlaydi. random modul ushbu qobiliyatni ta'minlaydi, shuning uchun 1-qator uni import qiladi.

```python
 1. import random
```

Ammo 2-chiziqdagi ```HANGMAN_PICS``` o'zgaruvchisi biz hozirgacha ko'rgan o'zgaruvchilardan biroz farq qiladi. Ushbu kod nimani anglatishini tushunish uchun yana bir nechta tushunchalarni o'rganishimiz kerak.

## Doimiy o'zgaruvchilar

2 dan 37 gacha bo'lgan satrlar ```HANGMAN_PICS``` o'zgaruvchisi uchun bitta uzoq tayinlash bayonotidir.

```python
2. HANGMAN_PICS = ['''
 3. +---+
 4. |
 5. |
 6. |
 7. ===''', '''
 --yana satrlar--
 37. ===''']
 ```

```HANGMAN_PICS``` o'zgaruvchisi nomi barcha katta harflarda. Bu doimiy o'zgaruvchilar uchun dasturlash konvensiyasi. Konstantalar - bu birinchi tayinlash bayonotidan hech qachon o'zgarmaydigan qiymatlarga ega bo'lgan o'zgaruvchilar. ```HANGMAN_PICS``` dagi qiymatni boshqa har qanday o'zgaruvchiga iloji boricha o'zgartirishingiz mumkin bo'lsa-da, katta harf nomi buni qilmasligingizni eslatib turadi.

Barcha anjumanlarda bo'lgani kabi, siz ham bunga rioya qilishingiz shart emas. Ammo buni amalga oshirish boshqa dasturchilar uchun sizning kodingizni o'qishni osonlashtiradi. Ular ```HANGMAN_PICS``` har doim 2 dan 37 gacha bo'lgan qatorlarda tayinlangan qiymatga ega bo'lishini bilishadi.

## Ma'lumotlar turi -- ```list```

```HANGMAN_PICS``` tarkibida bir nechta ko'p qatorli satrlar mavjud. Buni amalga oshirishi mumkin, chunki bu ro'yxat. Ro'yxatlarda bir nechta boshqa qiymatlarni o'z ichiga oladigan ro'yxat qiymati mavjud. Buni interaktiv qobiqga kiriting:

```python
>>> animals = ['aardvark', 'anteater', 'antelope', 'albert']
>>> animals
['aardvark', 'anteater', 'antelope', 'albert']
```

Hayvonlarda ro'yxat qiymati to'rtta qiymatni o'z ichiga oladi. Ro'yxat qiymatlari chap kvadrat qavs bilan boshlanib, [va o'ng kvadrat qavs bilan tugaydi,]. Bu xuddi satrlarning tirnoq bilan boshlanishi va tugashiga o'xshaydi.

Vergullar ro'yxat ichidagi alohida qiymatlarni ajratib turadi. Ushbu qiymatlar elementlar deb ham ataladi. ```HANGMAN_PICS```-dagi har bir element ko'p satrli mag'lubiyatdir.

Ro'yxatlar bir nechta qiymatlarni har biri uchun o'zgaruvchini ishlatmasdan saqlashga imkon beradi. Ro'yxatlarsiz kod quyidagicha ko'rinadi:

```python
>>> animals1 = 'aardvark'
>>> animals2 = 'anteater'
>>> animals3 = 'antelope'
>>> animals4 = 'albert'
```

Agar sizda yuzlab yoki minglab simlar bo'lsa, ushbu kodni boshqarish qiyin bo'lar edi. Ammo ro'yxat osongina istalgan qiymatlarni o'z ichiga olishi mumkin.

### Indeksli narsalarga kirish

Ro'yxat o'zgaruvchisining oxiriga to'rtburchak qavslarni qo'shib, ular orasidagi raqam bilan ro'yxat ichidagi elementga kirishingiz mumkin. Kvadrat qavslar orasidagi raqam indeksdir. Python-da, ro'yxatdagi birinchi elementning ko'rsatkichi 0 ga teng. Ikkinchi element 1-indeksda, uchinchi element 2-indeksda va hokazo. Indekslar 1 emas, 0 dan boshlanganligi sababli, biz Python ro'yxatlari nolga indekslangan deb aytamiz.

Biz hali ham interaktiv qobiqda va hayvonlar ro'yxati bilan ishlayotganimizda, ```animals[0], animals[1], animals[2] va animals[3]``` ni qanday baholashlarini ko'rish uchun kiriting:
```python
>>> animals[0]
'aardvark'
>>> animals[1]
'anteater'
>>> animals[2]
'antelope'
>>> animals[3]
'albert'
```

E'tibor bering, ro'yxatdagi birinchi qiymat ```"aardvark"``` 1-indeksda emas, 0-indeksda saqlanadi. Ro'yxatdagi har bir element ```0``` dan boshlab tartibda raqamlangan.

Kvadrat qavslardan foydalanib, siz ro'yxatdagi narsalarni boshqa har qanday qiymat kabi ko'rib chiqishingiz mumkin. Masalan, ```animals[0] + animals[2]``` ni interaktiv qobiqqa kiriting:

```python
>>> animals[0] + animals[2]
'aardvarkantelope'
```

#### Chegaradan chiqib ketgan indekslar va IndexError

Agar siz ro'yxatdagi ko'rsatkichdan yuqori ko'rsatkichga kirishga harakat qilsangiz, dasturingizni buzadigan ```IndexError```ni olasiz. Ushbu xatoning namunasini ko'rish uchun quyidagilarni interfaol qobiqga kiriting:

```python
>>> animals = ['aardvark', 'anteater', 'antelope', 'albert']
>>> animals[9999]
Traceback (most recent call last):
     File "", line 1, in
     animals[9999]
    IndexError: list index out of range
```

```9999``` indeksida qiymat yo'qligi sababli siz xatoga yo'l qo'yasiz.

Indeksni tayinlash orqali ro'yxat elementlarini o'zgartirish

Ro'yxatdagi element qiymatini indeks belgilash yordamida ham o'zgartirishingiz mumkin. Interaktiv qobiqga quyidagilarni kiriting:

```python
>>> animals = ['aardvark', 'anteater', 'antelope', 'albert']
>>> animals[1] = 'ANTEATER'
>>> animals
['aardvark', 'ANTEATER', 'antelope', 'albert']
```

Yangi "ANTEATER" (ya'ni chumolixo'r) qatori ```animals``` ro'yxatidagi ikkinchi element ustiga yoziladi. Shunday qilib, ```animals[1]``` o'z-o'zidan ro'yxatning joriy ikkinchi elementini baholaydi, ammo uni tayinlash operatorining chap tomonida ishlatib, ro'yxatning ikkinchi bandiga yangi qiymat belgilaydi.

### Ro'yxatni birlashtirish

```+``` operatori yordamida bir nechta ro'yxatlarni bitta ro'yxatga qo'shishingiz mumkin, xuddi satrlar kabi. Bunday qilish ro'yxat birikmasi deb ataladi. Buni amalda ko'rish uchun quyidagilarni interaktiv qobiqga kiriting:

```python
>>> [1, 2, 3, 4] + ['apples', 'oranges'] + ['Alice', 'Bob']
[1, 2, 3, 4, 'apples', 'oranges', 'Alice', 'Bob']
```

### ```in``` operatori

```in``` operatori qiymatning ro'yxatda bor-yo'qligini aytib berishi mumkin. ```in``` operatoridan foydalanadigan iboralar mantiqiy qiymatni qaytaradi: agar qiymat ro'yxatda bo'lsa ```True```, agar yo'q bo'lsa ```False```. Interaktiv qobiqga quyidagilarni kiriting:

```python
>>> animals = ['aardvark', 'anteater', 'antelope', 'albert']
>>> 'antelope' in animals
True
>>> 'ant' in animals
False
```

```animals```dagi ```'antilope'``` iborasi To'g'ri qaytadi, chunki ```'antilope'``` qatori ```animals``` ro'yxatidagi qiymatlardan biridir. U 2-indeksda joylashgan. Ammo hayvonlarga ```'ant'``` iborasini kiritganingizda, False-ni qaytaradi, chunki ```'ant'``` qatori ro'yxatda yo'q.

```in``` operatori qatorlar uchun ham ishlaydi, bitta satr boshqasida mavjudligini tekshiradi. Interaktiv qobiqga quyidagilarni kiriting:

```python
>>> 'hello' in 'Alice said hello to Bob.'
True
```

## Funksiyani chaqirish usullari

Metod - bu qiymatga biriktirilgan funktsiya. Metodni chaqirish uchun uni nuqta yordamida ma'lum bir qiymatga qo'shishingiz kerak. Pythonda juda ko'p foydali metodlar mavjud va biz ulardan ba'zilarini __Hangman__ dasturida qo'llaymiz.

Ammo oldin, ba'zi bir ro'yxat va mag'lubiyat metodlarni ko'rib chiqamiz.

### ```reverse()``` va ```append()``` ro'yxat usullari

Ro'yxat ma'lumotlari turida siz juda ko'p ishlatadigan ikkita usul mavjud: ```reverse()``` va ```append()```. ```reverse()``` usuli ro'yxatdagi elementlarning tartibini o'zgartiradi. ```spam = [1, 2, 3, 4, 5, 6, 'meow', 'woof']``` kiritib ko'ring, so'ngra ```spam.reverse()``` ro'yxatni teskari yo'naltirish uchun. Keyin o'zgaruvchining tarkibini ko'rish uchun ```spam``` kiriting.
```python
>>> spam = [1, 2, 3, 4, 5, 6, 'meow', 'woof']
>>> spam.reverse()
>>> spam
['woof', 'meow', 6, 5, 4, 3, 2, 1]
```

Siz foydalanadigan eng keng tarqalgan ro'yxat usuli bu ```append()```. Ushbu usul siz kiritgan qiymatni ro'yxat oxiriga qo'shadi. Interaktiv qobiqga quyidagilarni kiritib ko'ring:
```python
>>> eggs = []
>>> eggs.append('hovercraft')
>>> eggs
['hovercraft']
>>> eggs.append('eels')
>>> eggs
['hovercraft', 'eels']
```

Ushbu usullar ular chaqirilgan ro'yxatlarni o'zgartiradi. Ular yangi ro'yxatni qaytarishmaydi. Ushbu usullar ro'yxatni joyida o'zgartiradi, deymiz.

### ```split()``` String usuli

Ma'lumotlarning mag'lubiyat turi ```split()``` usuliga ega, bu esa ajratilgan satrdan qilingan satrlar ro'yxatini qaytaradi. Interaktiv qobiqga quyidagilarni kiritish orqali ```split()``` usulidan foydalanib ko'ring:

```python
>>> sentence = input()
My very energetic mother just served us nachos.
>>> sentence.split()
['My', 'very', 'energetic', 'mother', 'just', 'served', 'us', 'nachos.']
```

Natijada sakkiz qatorli ro'yxat, asl satrdagi har bir so'z uchun bitta satr. Ipdagi bo'sh joy bo'lgan joyda bo'linish sodir bo'ladi. Bo'sh joylar ro'yxatdagi biron bir narsaga kiritilmagan.

Hangman dasturining 38-qatorida keyingi qismda ko'rsatilganidek, ```split()``` usuli ham qo'llaniladi. Kod uzun, ammo bu shunchaki oddiy tayinlash bayonoti bo'lib, unda bo'sh joylar bilan ajratilgan bitta uzun so'zlar qatori mavjud va oxirida ```split()``` usul chaqiruvi mavjud. ```split()``` usuli satrdagi har bir so'z bilan ro'yxatni bitta ro'yxat elementi sifatida baholaydi.

```python
38. words = 'ant baboon badger bat bear beaver camel cat clam cobra cougar coyote crow deer dog donkey duck eagle ferret fox frog goat goose hawk lion lizard llama mole monkey moose mouse mule newt otter owl panda parrot pigeon python rabbit ram rat raven rhino salmon seal shark sheep skunk sloth snake spider stork swan tiger toad trout turkey turtle weasel whale wolf wombat zebra'
.split()
```

Ushbu dasturni ```split()``` yordamida yozish osonroq. Agar siz boshlash uchun ro'yxat tuzgan bo'lsangiz, har bir so'z uchun qo'shtirnoq va vergul bilan ```['ant', 'baboon', 'badger',``` va boshqalarni yozishingiz kerak edi. Shuningdek, siz o'zingizning so'zlaringizni 38-satrdagi satrga qo'shishingiz yoki o'yinda bo'lishni istamagan narsalarni olib tashlashingiz mumkin. Bo'shliqlarning so'zlarni ajratishiga ishonch hosil qiling.

## So'zlar ro'yxatidan maxfiy so'zni olish

40-qator ```getRandomWord()``` funktsiyasini belgilaydi. ```wordList``` parametri uchun ro'yxat argumenti beriladi. Ushbu funktsiya ro'yxatdan bitta maxfiy so'zni ```wordList```ga qaytaradi.
```python
40. def getRandomWord(wordList):
41.     # Ushbu funktsiya tasodifiy qatorni uzatilgan qatorlardan qaytaradi.
42.     wordIndex = random.randint(0, len(wordList) - 1)
43.     return wordList[wordIndex]
```
42-qatorda biz ushbu ro'yxat uchun tasodifiy indeksni ikkita argument bilan ```randint()``` ni chaqirib ```wordIndex``` o'zgaruvchisida saqlaymiz. Birinchi argument ```0``` (birinchi mumkin bo'lgan indeks uchun), ikkinchisi -- ```len (wordList) - 1``` ifodasi (```wordList```dagi so'nggi mumkin bo'lgan indeks uchun) baholaydigan qiymat.

Ro'yxat indekslari ```1```dan emas, ```0```dan boshlanishini unutmang, agar sizda uchta element ro'yxati bo'lsa, birinchi elementning indeksi ```0```ga, ikkinchi elementning indeksi esa ```1```ga, uchinchi elementning indeksi esa ```2```ga teng.  Ushbu ro'yxatning usunligi 3, ammo 3-indeks oxirgi indeksdan keyin bo'ladi. Shuning uchun 42-qator ```wordList``` uzunligidan ```1```ni olib tashlaydi. ```wordList``` o'lchamidan qat'i nazar, 42-satrdagi kod ishlaydi. Agar xohlasangiz, endi ```wordList```ga qatorlarni qo'shishingiz yoki olib tashlashingiz mumkin.

```wordIndex``` o'zgaruvchisi ```wordList``` parametri sifatida berilgan ro'yxat uchun tasodifiy indeksga o'rnatiladi. 43-qator elementni ```wordList```da ```wordIndex```da saqlangan butun sonni qaytaradi.

Keling, ```['olma', 'mandarin', 'uzum']``` ```getRandomWord()``` argumenti sifatida qabul qilinganligini va ```randint(0, 2)``` butun sonni 2 qaytarganligini ko'rsataylik. Bu degani, bu 43 satr ```wordList[2]``` ni qaytaradi va undan keyingina ```"uzum"``` ni qaytaradi. ```getRandomWord()``` ```wordList```da tasodifiy qatorni shunday qaytaradi.

O'yinchiga stolni ko'rsatish

Keyinchalik, Hangman stolini ekranda chop etish uchun bizga funktsiya kerak. Shuningdek, o'yinchi qancha harfni to'g'ri (va noto'g'ri) taxmin qilganligini ko'rsatishi kerak.
```python
45. def displayBoard(missedLetters, correctLetters, secretWord):
46. print(HANGMAN_PICS[len(missedLetters)])
47. print()
 ```
Ushbu kod `displayBoard()` nomli yangi funktsiyani belgilaydi. Ushbu funktsiya uchta parametrga ega:

- `missedLetters` O'yinchi maxfiy so'zda bo'lmagan harflar qatorini taxmin qilgani
- `correctLetters` O'yinchi maxfiy so'zda taxmin qilgan harflar
- `secretWord` O'yinchi taxmin qilmoqchi bo'lgan maxfiy so'z

`print()` funktsiyasining birinchi chaqiruvi stolni aks ettiradi. `HANGMAN_PICS` global o'zgaruvchisi har bir mumkin bo'lgan stol uchun satrlar ro'yxatiga ega. (Shuni esda tutingki, global o'zgaruvchilar funktsiya ichidan o'qilishi mumkin.) `HANGMAN_PICS[0]` bo'sh daralarni, `HANGMAN_PICS[1]` boshni (o'yinchi bitta harfni o'tkazib yuborganda), `HANGMAN_PICS [2]` boshni va tanani ko'rsatadi (qachon o'yinchi ikkita harfni o'tkazib yuborganda) va shunga o'xshash `HANGMAN_PICS[6]` ga qadar, bu to'liq osilgan odamni ko'rsatadi

`missedLetters`dagi harflar soni o'yinchining qancha noto'g'ri taxminlar qilganligini aks ettiradi. Ushbu raqamni bilish uchun `len(missedLetters)`ni chaqiring. Shunday qilib, agar `missedLetters`da `'aetr'` bo'lsa, u holda `len('aetr')` `4`ni qaytaradi. `HANGMAN_PICS[4]` ni bosib chiqarish to'rtta o'tkazib yuborish uchun mos keladigan osilgan odam rasmini aks ettiradi. 46-qatorda `HANGMAN_PICS[len (missedLetters)]` stolni variantiga teng bo'ladi.

49-satrda yangi satr o'rniga bo'sh joy belgisi qo'yilgan 'O'tkazib yuborilgan harflar:' qatori chop etiladi:

```python
49.    print('O'tkazib yuborilgan harflar:', end=' ')
50.    for letter in missedLetters:
51.        print(letter, end=' ')
52.    print()
```

50-satrda ```for loop```i `missedLetters` satridagi har bir belgi ustida takrorlanadi va uni ekranga chiqaradi. `end = ''` satrdan keyin bosilgan yangi satr belgisini bitta bo'shliq belgisi bilan almashtirishini unutmang. Masalan, agar `missedLetters 'ajtw'` bo'lsa, bu `for loop a j t w` ni aks ettiradi.

`displayBoard()` funktsiyasining qolgan qismi (54 dan 62 gacha chiziqlar) o'tkazib yuborilgan harflarni aks ettiradi va barcha taxmin qilinmagan harflar bilan maxfiy so'zning satrini bo'sh joy sifatida yaratadi. Buni `range()` funktsiyasi va ro'yxatni `slice()` qilish yordamida amalga oshiradi.

`list()` va `range()` funktsiyalar

Bitta argument bilan chaqirilganda, `range()` butun sonlar oralig'idagi ob'ektni `0` dan argumentgacha (lekin shu jumladan emas) qaytaradi. Ushbu diapazon ob'ekti `for loop` uchun ishlatiladi, lekin `list()` funktsiyasi bilan tanish bo'lgan ma'lumotlar turiga aylantirilishi mumkin. `list(range(10))` interaktiv qobiqga kiriting

```python
>>> list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> list('Hello')
['H', 'e', 'l', 'l', 'o']
```

`list()` funktsiyasi `str()` yoki `int()` funktsiyalariga o'xshaydi. Bu o'tgan qiymatni oladi va ro'yxatni qaytaradi. `range()` funktsiyasi bilan katta ro'yxatlarni yaratish oson. Masalan, `list(range(1000))` interaktiv qobiqga kiriting:

```python
>>> list(range(10000))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15,...
 --ko'p sonlar--
...9989, 9990, 9991, 9992, 9993, 9994, 9995, 9996, 9997, 9998, 9999]
```

Ushbu ro'yxat juda katta, hatto ekranga ham sig'maydi. Ammo siz ro'yxatni o'zgaruvchida saqlashingiz mumkin:

```python
>>> spam = list(range(10000))
```

Agar `range()` ikkita butun son argumentini o'tkazsangiz, u qaytaradigan qator ob'ekti birinchi butun son argumentidan ikkinchi butun son argumentigacha (lekin uni ichiga olmasdan) bo'lgan barcha butun sonlar bo'ladi. Keyin `list(range(10, 20))` interaktiv qobiqqa quyidagicha kiriting:

```python
>>> list(range(10, 20))
[10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
```

Ko'rib turganingizdek, bizning ro'yxatimiz faqat 19taga yetadi va 20 ga o'z ichiga olmaydi.

### Ro'yxat va satrlarni kesish

Ro'yxatni kesish boshqa ro'yxat elementlari to'plamidan foydalangan holda yangi ro'yxat qiymatini yaratadi. Ro'yxatni kesish uchun, ro'yxat nomidan keyin to'rtburchak qavsda ikki nuqta qo'yilgan ikkita indeksni (boshi va oxiri) ko'rsating. Masalan, interaktiv qobiqga quyidagilarni kiriting:

```python
>>> spam = ['apples', 'bananas', 'carrots', 'dates']
>>> spam[1:3]
['bananas', 'carrots']
```

`spam[1:3]` iborasi `spam`dagi ma'lumotlar ro'yxatiga 1-indeksdan 3-indeksgacha (lekin uni ichiga olmasdan) qadar baholanadi.

Agar siz birinchi indeksni qoldirsangiz, Python avtomatik ravishda birinchi indeks uchun `0` indeksini xohlaysiz deb o'ylaydi:

```python
>>> spam = ['apples', 'bananas', 'carrots', 'dates']
>>> spam[:2]
['apples', 'bananas']
```

Agar siz ikkinchi indeksni qoldirsangiz, Python avtomatik ravishda ro'yxatning qolgan qismini xohlaysiz deb o'ylaydi:

```python
>>> spam = ['apples', 'bananas', 'carrots', 'dates']
>>> spam[2:]
['carrots', 'dates']
```

Shuningdek, siz chiziqlar bilan bo'laklarni ro'yxatlar bilan ishlatganingiz kabi ishlatishingiz mumkin. Satrdagi har bir belgi ro'yxatdagi narsaga o'xshaydi. Interaktiv qobiqga quyidagilarni kiriting:

```python
>>> myName = 'Zophie the Fat Cat'
>>> myName[4:12]
'ie the F'
>>> myName[:10]
'Zophie the'
>>> myName[7:]
'the Fat Cat'

```

### Bo'shliqlar bilan maxfiy so'zni ko'rsatish

Endi siz maxfiy so'zni chop etmoqchisiz, ammo taxmin qilinmagan harflar uchun bo'sh satrlar bilan. Buning uchun pastki chiziq belgisini (_) ishlatishingiz mumkin. Dastlab maxfiy so'zdagi har bir harf uchun bitta chiziqdan boshqa hech narsa bo'lmagan qatorni yarating. Keyin har bir harf uchun bo'sh joylarni correctLetters-ga almashtiring.

Agar maxfiy so'z "otter" bo'lsa, bo'sh satr '_ _ _ _ _' (beshta pastki chiziq) bo'ladi. Agar correctLetters 'rt' qatori bo'lsa, siz satrni '_tt_r' ga o'zgartirasiz. 54 dan 58 gacha bo'lgan satrlar quyidagilarni bajaradigan kodning bir qismidir:

```python
54. blanks = '_' * len(secretWord)
55.
56. for i in range(len(secretWord)): # bo'sh joylarni to'g'ri taxmin qilingan harflar bilan almashtiring
57.     if secretWord[i] in correctLetters:
58.           blanks = blanks[:i] + secretWord[i] + blanks[i+1:]
 ```

54-qatorda satrlarni takrorlash yordamida pastki chiziqlar bilan to'ldirilgan bo'shliq o'zgaruvchisi yaratiladi. `*` operatori satrda va butun sonda ishlatilishi mumkinligini yodda tuting, shuning uchun `'_' * 5` ifodasi `'_ _ _ _ _'` ga teng bo'ladi. Bu bo'shliqlar maxfiy so'zlaridagi harflar bilan bir xil miqdordagi pastki chiziqlarga ega bo'lishini ta'minlaydi.

56-satrda har bir harfni `secretWord` orqali o'tadigan va pastki chiziqni to'g'ri harflarda mavjud bo'lsa, haqiqiy harf bilan almashtiradigan `for loop`i mavjud. `secretWord` qiymati `'otter'` va `correctLetters`-dagi qiymat `'tr'` bo'lgan oldingi misolni yana bir ko'rib chiqamiz. Siz `'_tt_r'` qatorini o'yinchiga ko'rsatilishini xohlaysiz. Keling, ushbu satrni qanday yaratishni aniqlaylik.

56-qatorning `len(secretWord)` chaqiruvi 5 ga qaytadi. `range(len(secretWord))` chaqiruvi `range(5)`ga aylanadi, bu esa `for loop`ini 0, 1, 2, 3 va 4 dan takrorlaydi.

`i` qiymati [0, 1, 2, 3, 4] har bir qiymatni qabul qilishi sababli `for loop`idagi kod quyidagicha ko'rinadi:

```python
if secretWord[0] in correctLetters:
    blanks = blanks[:0] + secretWord[0] + blanks[1:]
if secretWord[1] in correctLetters:
    blanks = blanks[:1] + secretWord[1] + blanks[2:]
```

Biz `for loop`ining faqat dastlabki ikki takrorlanishini ko'rsatmoqdamiz, lekin `0` dan boshlab `i` diapazondagi har bir raqamning qiymatini oladi. Birinchi takrorlashda `i` `0` qiymatini qabul qiladi, shuning uchun `if` ifodasi `0` indeksidagi `secretWord`dagi harfning `correctLetters`-da ekanligini tekshiradi. Buni tsikl har bir harf uchun, bir vaqtning o'zida bitta harf uchun bajaradi.

Keyingi bir necha satr bo'shliqlarning yangi qiymatini har bir harf orasidagi bo'shliqlar bilan bosib chiqaradi:

```python
60. for letter in blanks: # har bir harf orasidagi bo'shliqlar bilan maxfiy so'zni ko'rsating
61.     print(letter, end=' ')
62. print()
 ```

E'tibor bering, 60-qatorda `for loop` `range()` funktsiyasini chaqirmaydi. Ushbu funktsiya chaqiruvi intervalli ob'ektida takrorlash o'rniga, `blanks` o'zgaruvchisidagi satr qiymatida takrorlanadi. Har bir takrorlashda harf o'zgaruvchisi `blanks`dagi `"otter"` qatoridan yangi belgini oladi.

Bo'shliqlar qo'shilgandan keyin bosma nashr `'_ t t _ r'` bo'ladi.

## O'yinchi taxminini olish

`getGuess()` funktsiyasi chaqirilganda, o'yinchi taxmin qilish uchun harf kiritishi mumkin. Funksiya o'yinchining mag'lubiyat deb taxmin qilgan harfini qaytaradi. Bundan tashqari, `getGuess()` funktsiyadan qaytib kelguncha o'yinchi to'g'ri harfni yozishiga ishonch hosil qiladi.

```python
64. def getGuess(alreadyGuessed):
65.     # O'yinchi kiritilgan xarfni qaytaradi. Ushbu funktsiya o'yinchining bitta harfni kiritganiga ishonch hosil qiladi, boshqa narsani emas.
```

O'yinchi taxmin qilgan harflar qatori `alreadyGuessed` parametri uchun argument sifatida qabul qilinadi. Keyin `getGuess()` funktsiyasi o'yinchidan bitta harfni taxmin qilishni so'raydi. Ushbu bitta harf `getGuess()` ning qaytish qiymati bo'ladi. Endi, Python kichik harflar sezgirligi sababli, biz o'yinchining taxminlari kichik harf ekanligiga ishonch hosil qilishimiz kerak, shunda biz uni maxfiy so'z bilan tekshirib ko'rishimiz mumkin. Bu erda `lower()` usuli to'g'ri keladi.

```python
66.     while True:
67.        print('Guess a letter.')
68.        guess = input()
69.        guess = guess.lower()
```


### `while` tsiklidan chiqib ketish

66-qator `while` esa ilgari taxmin qilinmagan bitta harfni kiritmaguncha o'yinchidan xarf so'raydi. 

`while` tsiklining sharti shunchaki mantiqiy qiymati `True`. Bu shuni anglatadiki, ijro etilish ushbu tsiklni tark etishning yagona usuli bu loopdagi `break` operatorini yoki faqat loopni emas, balki butun funktsiyani yakunlaydigan `return` operatorini bajarishdir.

Tsikl ichidagi kod o'yinchidan o'zgaruvchini taxminida saqlanadigan harfni kiritishni so'raydi. Agar o'yinchi katta harfni kiritgan bo'lsa, unda 69-qatorda kichik harf bilan yozilgan bo'lar edi.

## elif bayonotlari

Hangman dasturining keyingi qismida elif so'zlari ishlatiladi. Siz elif yoki "else-if" so'zlarini "Agar bu haqiqat bo'lsa, buni qiling. Yoki agar bu keyingi shart to'g'ri bo'lsa, buni bajaring. Yoki agar ularning hech biri haqiqat bo'lmasa, oxirgi narsani qiling" deb tushunish mumkin. Quyidagi kodni ko'rib chiqing:

```python
if catName == 'Fuzzball':
    print('Your cat is fuzzy.')
elif catName == 'Spots':
    print('Your cat is spotted.')
else:
    print('Your cat is not fuzzy or spotted.')
```

Agar `catName` o'zgaruvchisi `'Fuzzball'` qatoriga teng bo'lsa, u holda if iborasining holati `True` va if bloki foydalanuvchiga ularning mushuklari loyqa ekanligini aytadi. Ammo, agar bu shart `False` bo'lsa, u holda Python `elif` bayonotining holatini keyinroq sinab ko'radi. Agar `catName "Spots"` bo'lsa, u holda `"Sizning mushukingiz dog'."` ekranga chiqadi. Agar ikkalasi ham `False` bo'lsa, unda kod foydalanuvchiga ularning mushuklari loyqa yoki dog' emasligini aytadi.

Siz xohlagancha elif bayonotlariga ega bo'lishingiz mumkin.

`elif` shartlaridan biri `True` bo'lsa, uning kodi bajariladi, so'ngra bajarilish `else` blokidan o'tib birinchi qatorga o'tadi. Shunday qilib `if-elif-else` iboralaridagi bloklardan bittasi va bittasi bajariladi. Agar sizga kerak bo'lmasa va faqat `if-elif` so'zlari bo'lsa, siz `else` blokini yozmasiligingiz ham mumkin.

## O'yinchi aniq taxminni kiritganiga ishonch hosil qilish

`guess` o'zgaruvchisi o'yinchining harf tahminini o'z ichiga oladi. Dastur ular to'g'ri taxminni kiritganligiga ishonch hosil qilishlari kerak: bitta va bitta, hali taxmin qilinmagan harf. Agar ular bunday qilmagan bo'lsalar, ijro etilishi orqaga qaytadi va ulardan yana harf so'raydi.

```python
70.        if len(guess) != 1:
71.            print('Iltimos, bitta harfni kiriting.')
72.        elif guess in alreadyGuessed:
73.            print('Siz allaqachon bu xatni taxmin qilgansiz. Qayta tanlang.')
74.        elif guess not in 'abcdefghijklmnopqrstuvwxyz':
75.            print('Iltimos, faqat harf kiriting.')
76.        else:
77.            return guess
```            

70-satrning sharti `guess` bir belgidan iborat emasligini, 72-satrning holati `alreadyGuessed` o'zgaruvchining ichida taxmin mavjudligini yoki 74-qatorning holati taxminiy ingliz alifbosidagi harf emasligini tekshiradi. Agar ushbu shartlarning birortasi `True` bo'lsa, o'yin o'yinchini yangi taxminni kiritishga undaydi.

Agar ushbu shartlarning barchasi `False` bo'lsa, `else` operatorining bloki bajariladi va `getGuess()` qiymati 77-satrda taxminiy qiymatni qaytaradi.

Esingizda bo'lsin, `if-elif-else` bayonotidagi bloklardan faqat bittasi bajariladi.

## O'yinchidan yana o'ynashni so'rash

`playAgain()` funktsiyasi faqat `print()` funktsiyasi chaqiruviga va qaytish bayonotiga ega:
```python
79. def playAgain():
80.    # Agar o'yinchi yana o'ynashni xohlasa, bu funktsiya True qiymatini qaytaradi; aks holda, False qaytadi.
81.    print('Yana o\'ynashni istaysizmi? (ha or yo'q)')
82.    return input().lower().startswith('h')
```

`playAgain()` funktsiyasining mohiyati shundaki, agar o'yinchi yana bir turda o'ynashni xohlasa, dasturga "ha" yoki "yo'q" kiritishi kerak. O'yinchi "HA", "ha" degan ma'noni anglatishi uchun `HA`, `ha`, `H` yoki `h` bilan boshlanadigan boshqa narsalarni terishi kerak. Agar o'yinchi `HA` ga kirsa, u holda `input()` ning qaytish qiymati `'YES'` qatoridir. Va `"HA".lower()` biriktirilgan qatorning kichik versiyasini qaytaradi. Shunday qilib `'HA'.lower()` ning qaytish qiymati `"ha"`dir.

## O'yinimizning funktsiyalarni ko'rib chiqamiz
Quyidagilar ushbu o'yin uchun yaratadigan barcha funktsiyalar! Keling, ularni ko'rib chiqaylik:

`getRandomWord(wordList)` Unga berilgan satrlar ro'yxatini oladi va undan bitta qatorni qaytaradi. Shu tarzda o'yinchi taxmin qilishi uchun so'z tanlanadi.

`displayBoard(missedLetters, correctLetters, secretWord)` stolning hozirgi holatini, shu jumladan, o'yinchi shu paytgacha qancha maxfiy so'zni taxmin qilganini va noto'g'ri harflarni o'yinchi taxmin qilganligini ko'rsatadi. Ushbu funktsiya to'g'ri ishlashi uchun unga berilgan uchta parametr kerak. `correctLetters` and `missedLetters` - bu o'yinchi o'zboshimchalik bilan maxfiy so'zda emas, balki taxmin qilgan harflardan tashkil topgan satrlar. `secretWord` - bu o'yinchi taxmin qilmoqchi bo'lgan maxfiy so'z. Ushbu funktsiya qaytish qiymatiga ega emas.

`getGuess(alreadyGuessed)` O'yinchi allaqachon taxmin qilgan harflar qatorini oladi va o'yinchidan `alreadyGuessed`da bo'lmagan harfni so'rashda davom etadi.

`playAgain()` O'yinchi yana bir marta o'ynashni xohlashini deb so'raydi. Ushbu funktsiya o'yinchi bajarsa `True`, agar yo'q bo'lsa `False`-ni qaytaradi.

## O'yin tsikli

`Hangman` dasturining asosiy qismi o'yin nomini ko'rsatadi, ba'zi o'zgaruvchilarni o'rnatadi va `while` tsiklini bajaradi. Ushbu bo'lim dasturning qolgan qismini bosqichma-bosqich o'tib boradi.

```python
85. print('H A N G M A N')
86. missedLetters = ''
87. correctLetters = ''
88. secretWord = getRandomWord(words)
89. gameIsDone = False
```

85-qator - o'yin tugagandan so'ng amalga oshiriladigan birinchi `print()` chaqiruvi. Unda o'yin nomi ko'rsatiladi. Keyin bo'sh satrlar
o'yinchi hali o'tkazib yuborilgan yoki to'g'ri harflarni taxmin qilmaganligi sababli o'tkazib yuborilgan va to'g'ri harflar.

88-qatorda `getRandomWord(so'zlar)` chaqiruvi so'zlar ro'yxatidan tasodifiy tanlangan so'zga baho beradi.

89-qator `gameIsDone`ni "False"-ga o'rnatadi. Kod o'yinni tugatganligi to'g'risida signal berib, o'yinchidan yana o'ynashni xohlaysizmi, deb so'raganda, `gameIsDone`-ni True-ga o'rnatadi.

### `displayBoard()` funktsiyasini chaqirish

Dasturning qolgan qismi `while` siklidan iborat. `Loop`ning holati har doim `True` bo'ladi, demak u `break` operatoriga duch kelguncha abadiy davom etadi. (Bu keyinchalik 126-satrda sodir bo'ladi.)

```python
91. while True:
92. displayBoard(missedLetters, correctLetters, secretWord)
```

92-qator `displayBoard()` funktsiyasini chaqiradi, unga 86, 87 va 88-qatorlarda o'rnatilgan uchta o'zgaruvchini uzatadi. Aktyor qancha harfni to'g'ri taxmin qilgani va o'tkazib yuborganiga asoslanib, ushbu funktsiya pleyerga tegishli Hangman taxtasini aks ettiradi.

### O'yinchining o'z taxminiga kirishiga ruxsat berish

Keyin `getGuess()` funktsiyasi chaqiriladi, shuning uchun o'yinchi o'z taxminlarini kiritishi mumkin.

```python
94. # O'yinchinga xarf kirishiga ruxsat bering.
95. guess = getGuess(missedLetters + correctLetters)
```
`getGuess()` funktsiyasi `alreadyGuessed` parametrini talab qiladi, shuning uchun o'yinchi allaqachon taxmin qilgan harfni kiritadimi yoki yo'qligini tekshirishi mumkin. 95-qator `missedLetters` va `correctLetters` o'zgaruvchilar qatorlarini birlashtiradi va natijani `alreadyGuessed` parametri argumenti sifatida beradi.

### Harfning maxfiy so'zda ekanligini tekshirish

Agar taxmin satri `secretWord`-da mavjud bo'lsa, u holda bu kod `correctLetters` satrining oxirigacha taxminni birlashtiradi:

```python
97. if guess in secretWord:
98. correctLetters = correctLetters + guess
 ```
 
### O'yinchining g'alaba qozonganligini tekshirish

Dastur qanday qilib o'yinchi maxfiy so'zdagi har bir harfni taxmin qilganligini biladi? Xullas, `correctLetters`-da o'yinchi to'g'ri taxmin qilgan har bir harf bor va `secretWord` bu maxfiy so'zning o'zi. Ammo shunchaki `correctLetters == secretWord` ekanligini tekshirib bo'lmaydi. Agar `secretWord` `"otter"` qatori va `correctLetters 'orte'` qatori bo'lgan bo'lsa, o'yinchi maxfiy so'zdagi har bir harfni taxmin qilgan bo'lsa ham, `to'g'riLetters == secretWord` yolg'on bo'ladi.
 
O'yinchining yutganiga ishonch hosil qilishning yagona usuli bu `secretWord`-dagi har bir harfni takrorlash va uning `correctLetters`-da mavjudligini ko'rishdir. Agar `secretWord`-dagi har bir harf to'g'ri harflarda bo'lsa, o'yinchi g'alaba qozongan bo'ladi.

```python
100.    # O'yinchining g'alaba qozonganligini tekshiring.
101.    foundAllLetters = True
102.    for i in range(len(secretWord)):
103.        if secretWord[i] not in correctLetters:
104.            foundAllLetters = False
105.            break
```
 
Agar `correctLetters`-da mavjud bo'lmagan `secretWord`-da harf topsangiz, bilasizki, o'yinchi barcha harflarni taxmin qilmagan. Yangi `foundAllLetters` tsikl boshlanishidan oldin 101 satrda `True`ga o'rnatiladi. Ko'chadan maxfiy so'zdagi barcha harflar topilgan deb taxmin qilinadi. Ammo 104-satrdagi tsiklning kodi `foundAllLetters`-ni `False`-ga o'zgartiradi, birinchi marta `secretWord`-da `correctLetters`-da bo'lmagan harfni topganda.
 
Agar maxfiy so'zdagi barcha harflar topilgan bo'lsa, o'yinchiga ular g'olib bo'lganligi aytiladi va `gameIsDone True`-ga o'rnatiladi:
 
```python
        if foundAllLetters:
            print('Ha! Mahfiy so\'z "' + secretWord + '"! Siz yutdingiz!')
            gameIsDone = True
```
 
### Noto'g'ri taxminni tekshirish

109-qator - bu `else` blokning boshlanishi.

```python
109.    else:
110.        missedLetters = missedLetters + guess
```

Esingizda bo'lsa, agar ushbu shart noto'g'ri bo'lsa, ushbu blokdagi kod bajariladi. Ammo qaysi shart? Buni bilish uchun barmog'ingizni `else` kalit so'zining boshiga yo'naltiring va uni yuqoriga ko'taring. 
 
### O'yinchining yutqizganligini tekshirish

O'yinchi har safar noto'g'ri taxmin qilganda, kod `missedLetters`-dagi satrga noto'g'ri harfni biriktiradi. Shunday qilib, `missedLetters` uzunligi - yoki kodda `len(missedLetters)` - bu noto'g'ri taxminlarning soni.

```python
        # O'yinchi juda ko'p marta taxmin qilgani va yutqazganligini tekshiring.
        if len(missedLetters) == len(HANGMAN_PICS) - 1:
            displayBoard(missedLetters, correctLetters, secretWord)
            print('Sizda taxminlar tugadi!\n' str(len(missedLetters)) + ' noto\'g\'ri tahminlardan keyin va ' + str(len(correctLetters)) + ' to\'g\'ri tahminlardan keyin, mahfiy so\'z"' + secretWord + '" edi')
            gameIsDone = True
```

`HANGMAN_PICS` ro'yxatida yettita `ASCII` badiiy satrlari mavjud. Shunday qilib, missedLetters mag'lubiyatining uzunligi `len(HANGMAN_PICS) - 1` ga teng bo'lganda (ya'ni 6), o'yinchining taxminlari tugadi. Siz o'yinchi yutqazganini bilasiz, chunki osilgan odamning surati tugaydi. Esingizda bo'lsin, `HANGMAN_PICS[0]` ro'yxatdagi birinchi element, `HANGMAN_PICS[6]` esa oxirgisi.

```python
    # O'yinchidan yana o'ynashni xohlashlarini so'rang (lekin agar o'yin tugagan bo'lsa).
        if gameIsDone:
            if playAgain():
                missedLetters = ''
                correctLetters = ''
                gameIsDone = False
                secretWord = getRandomWord(words)
```