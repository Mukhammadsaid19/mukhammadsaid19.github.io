# Sonar Xazinalar Ovi

Ushbu bobdagi "Sonar xazinalar ovi" o'yini birinchi bo'lib siz 12-bobda bilib olgan dekart koordinatalar tizimidan foydalanadi. Ushbu o'yinda ma'lumotlar tuzilmalaridan ham foydalaniladi, bu shunchaki xayoliy uslub bo'lib, unda boshqa ro'yxatlar va shunga o'xshash murakkab o'zgaruvchilarni o'z ichiga olgan ro'yxat qiymatlari mavjud. Siz dasturlashtirgan o'yinlar murakkablashganda, ma'lumotlaringizni ma'lumotlar tuzilmalarida tartibga solishingiz kerak bo'ladi.

Ushbu bobning o'yinida o'yinchi cho'kib ketgan xazina sandiqlarini topish uchun sonar moslamalarini okeanning turli joylariga tashlaydi. Sonar - bu kemalar dengiz ostidagi narsalarni topish uchun foydalanadigan texnologiya. Ushbu o'yindagi sonar qurilmalari o'yinchiga eng yaqin xazina sandig'i qancha masofani ko'rsatib beradi, ammo qaysi yo'nalishda emas. Ammo bir nechta sonar moslamalarini joylashtirish orqali o'yinchi xazina sandig'ining joylashishini aniqlay oladi.

Ushbu bobda yoritilgan mavzular:

* Ma'lumotlar tuzilmalari
* Pifagor teoremasi
* `Remove()` ro'yxati usuli
* `isdigit()` qator usuli
* `sys.exit()` funktsiyasi

To'plash uchun 3 ta sandiq bor va ularni topish uchun o'yinchida atigi 20 ta sonar moslama mavjud. 13-1-rasmda xazina sandig'ini ko'rmaganingizni tasavvur qiling. Chunki, har bir sonar moslamasi masofani sandig' yo'nalishidan emas, balki faqat sandig'dan topishi mumkinligi sababli, xazina sonar moslamasi atrofidagi halqaning istalgan joyida bo'lishi mumkin.

Ammo birgalikda ishlaydigan bir nechta sonar qurilmalar sandiq joylashgan joyni halqalarni kesib o'tadigan aniq koordinatalarga qadar toraytirishi mumkin (13-2-rasmga qarang).

Quyida "Sonar xazinalar ovi" dasturini ishga tushirganda foydalanuvchi nimani ko'rishi ko'rsatilgan. Foydalanuvchi kiritgan matn qalin harflar bilan beilgilangan.

```
S O N A R !
Would you like to view the instructions? (yes/no)
no
             1         2         3         4         5
   012345678901234567890123456789012345678901234567890123456789
 0 ~`~``~``~``~`~`~```~`~``````~```~`~~~`~~```~~`~~~~~`~~`~~~~` 0
 1 ~~~~~`~~~~~````~``~~```~``~`~`~`~``~~```~~~`~`~```~~~~`~`~~` 1
 2 ```~````~``~`~`~~~``~~`````~~``~``~``~~```~~``~~`~~~````~~`~ 2
 3 `````~~``````~`~~~~~```~~``~~~`~`~~~~~~`````~`~```~~~``~``~` 3
 4 ~~~`~~~`~`~~~``~~~`~`~``~~~~``~~~~``~~~~`~`~``~~```~``~~`~`~ 4
 5 `~``~````~`~`~~``~~~~``````~```~~~~````````~``~~~`~~``~~```` 5
 6 ~`~```~~`~~```~````````~~```~```~~~~``~~~`~`~~`~``~~~`~~`~`` 6
 7 ~`~~~```~``~```~`~```~~~~~~~`~~`~`~~~~``~```~~~`~```~``~``~` 7
 8 `~``~~`~`~~`~~`~~``~```~````~`~```~``~````~~~````~~``~~``~~` 8
 9 ~`~``~~````~~```~`~~```~~`~``~`~~``~`~`~~~~`~`~~`~`~```~~``` 9
10 `~~~~~~`~``~``~~~``~``~~~~`~``~```~`~~``~~~~~~``````~~`~``~~ 10
11 ~``~~~````~`~~`~~~`~~~``~``````~`~``~~~~`````~~~``````~`~`~~ 11
12 ~~~~~``~`~````~```~`~`~`~~`~~`~``~~~~~~~`~~```~~``~~`~~~~``` 12
13 `~~```~~````````~~~`~~~```~~~~~~~~`~~``~~`~```~`~~````~~~``~ 13
14 ```~``~`~`~``~```~`~``~`~``~~```~`~~~``~~``~```~`~~`~``````~ 14
   012345678901234567890123456789012345678901234567890123456789
             1         2         3         4         5
            
You have 20 sonar device(s) left. 3 treasure chest(s) remaining.
Where do you want to drop the next sonar device? (0-59 0-14) (or type quit)
25 5

             1         2         3         4         5
   012345678901234567890123456789012345678901234567890123456789
 0 ~`~``~``~``~`~`~```~`~``````~```~`~~~`~~```~~`~~~~~`~~`~~~~` 0
 1 ~~~~~`~~~~~````~``~~```~``~`~`~`~``~~```~~~`~`~```~~~~`~`~~` 1
 2 ```~````~``~`~`~~~``~~`````~~``~``~``~~```~~``~~`~~~````~~`~ 2
 3 `````~~``````~`~~~~~```~~``~~~`~`~~~~~~`````~`~```~~~``~``~` 3
 4 ~~~`~~~`~`~~~``~~~`~`~``~~~~``~~~~``~~~~`~`~``~~```~``~~`~`~ 4
 5 `~``~````~`~`~~``~~~~````5`~```~~~~````````~``~~~`~~``~~```` 5
 6 ~`~```~~`~~```~````````~~```~```~~~~``~~~`~`~~`~``~~~`~~`~`` 6
 7 ~`~~~```~``~```~`~```~~~~~~~`~~`~`~~~~``~```~~~`~```~``~``~` 7
 8 `~``~~`~`~~`~~`~~``~```~````~`~```~``~````~~~````~~``~~``~~` 8
 9 ~`~``~~````~~```~`~~```~~`~``~`~~``~`~`~~~~`~`~~`~`~```~~``` 9
10 `~~~~~~`~``~``~~~``~``~~~~`~``~```~`~~``~~~~~~``````~~`~``~~ 10
11 ~``~~~````~`~~`~~~`~~~``~``````~`~``~~~~`````~~~``````~`~`~~ 11
12 ~~~~~``~`~````~```~`~`~`~~`~~`~``~~~~~~~`~~```~~``~~`~~~~``` 12
13 `~~```~~````````~~~`~~~```~~~~~~~~`~~``~~`~```~`~~````~~~``~ 13
14 ```~``~`~`~``~```~`~``~`~``~~```~`~~~``~~``~```~`~~`~``````~ 14
   012345678901234567890123456789012345678901234567890123456789
             1         2         3         4         5

Treasure detected at a distance of 5 from the sonar device.
You have 19 sonar device(s) left. 3 treasure chest(s) remaining.
Where do you want to drop the next sonar device? (0-59 0-14) (or type quit)
30 5

             1         2         3         4         5
   012345678901234567890123456789012345678901234567890123456789
 0 ~`~``~``~``~`~`~```~`~``````~```~`~~~`~~```~~`~~~~~`~~`~~~~` 0
 1 ~~~~~`~~~~~````~``~~```~``~`~`~`~``~~```~~~`~`~```~~~~`~`~~` 1
 2 ```~````~``~`~`~~~``~~`````~~``~``~``~~```~~``~~`~~~````~~`~ 2
 3 `````~~``````~`~~~~~```~~``~~~`~`~~~~~~`````~`~```~~~``~``~` 3
 4 ~~~`~~~`~`~~~``~~~`~`~``~~~~``~~~~``~~~~`~`~``~~```~``~~`~`~ 4
 5 `~``~````~`~`~~``~~~~````5`~``3~~~~````````~``~~~`~~``~~```` 5
 6 ~`~```~~`~~```~````````~~```~```~~~~``~~~`~`~~`~``~~~`~~`~`` 6
 7 ~`~~~```~``~```~`~```~~~~~~~`~~`~`~~~~``~```~~~`~```~``~``~` 7
 8 `~``~~`~`~~`~~`~~``~```~````~`~```~``~````~~~````~~``~~``~~` 8
 9 ~`~``~~````~~```~`~~```~~`~``~`~~``~`~`~~~~`~`~~`~`~```~~``` 9
10 `~~~~~~`~``~``~~~``~``~~~~`~``~```~`~~``~~~~~~``````~~`~``~~ 10
11 ~``~~~````~`~~`~~~`~~~``~``````~`~``~~~~`````~~~``````~`~`~~ 11
12 ~~~~~``~`~````~```~`~`~`~~`~~`~``~~~~~~~`~~```~~``~~`~~~~``` 12
13 `~~```~~````````~~~`~~~```~~~~~~~~`~~``~~`~```~`~~````~~~``~ 13
14 ```~``~`~`~``~```~`~``~`~``~~```~`~~~``~~``~```~`~~`~``````~ 14
   012345678901234567890123456789012345678901234567890123456789
             1         2         3         4         5

Treasure detected at a distance of 3 from the sonar device.
You have 18 sonar device(s) left. 3 treasure chest(s) remaining.
Where do you want to drop the next sonar device? (0-59 0-14) (or type quit)
25 10

             1         2         3         4         5
   012345678901234567890123456789012345678901234567890123456789
 0 ~`~``~``~``~`~`~```~`~``````~```~`~~~`~~```~~`~~~~~`~~`~~~~` 0
 1 ~~~~~`~~~~~````~``~~```~``~`~`~`~``~~```~~~`~`~```~~~~`~`~~` 1
 2 ```~````~``~`~`~~~``~~`````~~``~``~``~~```~~``~~`~~~````~~`~ 2
 3 `````~~``````~`~~~~~```~~``~~~`~`~~~~~~`````~`~```~~~``~``~` 3
 4 ~~~`~~~`~`~~~``~~~`~`~``~~~~``~~~~``~~~~`~`~``~~```~``~~`~`~ 4
 5 `~``~````~`~`~~``~~~~````5`~``3~~~~````````~``~~~`~~``~~```` 5
 6 ~`~```~~`~~```~````````~~```~```~~~~``~~~`~`~~`~``~~~`~~`~`` 6
 7 ~`~~~```~``~```~`~```~~~~~~~`~~`~`~~~~``~```~~~`~```~``~``~` 7
 8 `~``~~`~`~~`~~`~~``~```~````~`~```~``~````~~~````~~``~~``~~` 8
 9 ~`~``~~````~~```~`~~```~~`~``~`~~``~`~`~~~~`~`~~`~`~```~~``` 9
10 `~~~~~~`~``~``~~~``~``~~~4`~``~```~`~~``~~~~~~``````~~`~``~~ 10
11 ~``~~~````~`~~`~~~`~~~``~``````~`~``~~~~`````~~~``````~`~`~~ 11
12 ~~~~~``~`~````~```~`~`~`~~`~~`~``~~~~~~~`~~```~~``~~`~~~~``` 12
13 `~~```~~````````~~~`~~~```~~~~~~~~`~~``~~`~```~`~~````~~~``~ 13
14 ```~``~`~`~``~```~`~``~`~``~~```~`~~~``~~``~```~`~~`~``````~ 14
   012345678901234567890123456789012345678901234567890123456789
             1         2         3         4         5
             
Treasure detected at a distance of 4 from the sonar device.
You have 17 sonar device(s) left. 3 treasure chest(s) remaining.
Where do you want to drop the next sonar device? (0-59 0-14) (or type quit)
29 8

             1         2         3         4         5
   012345678901234567890123456789012345678901234567890123456789
 0 ~`~``~``~``~`~`~```~`~``````~```~`~~~`~~```~~`~~~~~`~~`~~~~` 0
 1 ~~~~~`~~~~~````~``~~```~``~`~`~`~``~~```~~~`~`~```~~~~`~`~~` 1
 2 ```~````~``~`~`~~~``~~`````~~``~``~``~~```~~``~~`~~~````~~`~ 2
 3 `````~~``````~`~~~~~```~~``~~~`~`~~~~~~`````~`~```~~~``~``~` 3
 4 ~~~`~~~`~`~~~``~~~`~`~``~~~~``~~~~``~~~~`~`~``~~```~``~~`~`~ 4
 5 `~``~````~`~`~~``~~~~````X`~``X~~~~````````~``~~~`~~``~~```` 5
 6 ~`~```~~`~~```~````````~~```~```~~~~``~~~`~`~~`~``~~~`~~`~`` 6
 7 ~`~~~```~``~```~`~```~~~~~~~`~~`~`~~~~``~```~~~`~```~``~``~` 7
 8 `~``~~`~`~~`~~`~~``~```~````~X~```~``~````~~~````~~``~~``~~` 8
 9 ~`~``~~````~~```~`~~```~~`~``~`~~``~`~`~~~~`~`~~`~`~```~~``` 9
10 `~~~~~~`~``~``~~~``~``~~~X`~``~```~`~~``~~~~~~``````~~`~``~~ 10
11 ~``~~~````~`~~`~~~`~~~``~``````~`~``~~~~`````~~~``````~`~`~~ 11
12 ~~~~~``~`~````~```~`~`~`~~`~~`~``~~~~~~~`~~```~~``~~`~~~~``` 12
13 `~~```~~````````~~~`~~~```~~~~~~~~`~~``~~`~```~`~~````~~~``~ 13
14 ```~``~`~`~``~```~`~``~`~``~~```~`~~~``~~``~```~`~~`~``````~ 14
   012345678901234567890123456789012345678901234567890123456789
             1         2         3         4         5

You have found a sunken treasure chest!
You have 16 sonar device(s) left. 2 treasure chest(s) remaining.
Where do you want to drop the next sonar device? (0-59 0-14) (or type quit)
--snip--
```

"Sonar xazinalar ovi" uchun manba kodi

Pythonning IDLEda Fayl - New File bosish orqali yangi fayl muharriri oynasini oching. Ko'rsatilgan bo'sh oynada manba kodini kiriting va uni `sonar.py` sifatida saqlang. Keyin F5 tugmachasini bosib dasturni ishga tushiring.

Ushbu kodni fayl muharririga kiritganingizda, satrlarning old qismidagi bo'shliqqa e'tibor bering. Ba'zi satrlarni to'rt yoki sakkiz bo'shliq bilan ajratish kerak.

`sonar.py`
```python
# Sonar Xazinalar Ovi

import random
import sys
import math

def getNewBoard():
    # Yangi 60x15 taxta ma'lumotlar tuzilishini yaratish
    board = []
    for x in range(60): # 60 ta ro'yhatdan iborat asosiy ro'yhat
        board.append([])
        for y in range(15): # Har bir asosiy ro'yhatdagi ro'yhatda 15ta bitta-belgili satrlar bor
            # O'qishga oson bo'lishi uchun okeanga harhil belgilar ishlatamiz
            if random.randint(0, 1) == 0:
                board[x].append('~')
            else:
                board[x].append('`')
    return board

def drawBoard(board):
    # Taxtaning ma'lumotlar tuzilishini chizish. 
    tensDigitsLine = '    ' # Taxtaning chap tomonidagi raqamlar uchun dastlabki bo'sh joy
    for i in range(1, 6):
        tensDigitsLine += (' ' * 9) + str(i)

    # Raqamlarni taxtaning yuqori qismiga bosib chiqaramz.
    print(tensDigitsLine)
    print('   ' + ('0123456789' * 6))
    print()

    # 15 qatorning har birini chop etamiz
    for row in range(15):
        # Bir xonali raqamlarni qo'shimcha joy bilan to'ldirish kerak.
        if row < 10:
            extraSpace = ' '
        else:
            extraSpace = ''

        # Ushbu qator uchun satrni taxtada yaratish.
        boardRow = ''
        for column in range(60):
            boardRow += board[column][row]

        print('%s%s %s %s' % (extraSpace, row, boardRow, row))

    # Raqamlarni taxtaning pastki qismida bosib chiqarish.
    print()
    print('   ' + ('0123456789' * 6))
    print(tensDigitsLine)

def getRandomChests(numChests):
    # Sandiq ma'lumotlari tuzilmalari ro'yxatini yaratish (x, y int koordinatalarining ikki elementli ro'yxati).
    chests = []
    while len(chests) < numChests:
        newChest = [random.randint(0, 59), random.randint(0, 14)]
        if newChest not in chests: # Sandiq allaqachon bu erda emasligiga ishonch hosil qilamiz.
            chests.append(newChest)
    return chests

def isOnBoard(x, y):
    # Agar koordinatalar doskada bo'lsa, True-ni, aks holda, False-ni qaytaramiz.
    return x >= 0 and x <= 59 and y >= 0 and y <= 14

def makeMove(board, chests, x, y):
    # Sonar qurilmasi belgisi bilan taxta ma'lumotlar tuzilishini o'zgartiring. Xazina sandiqlarini topilgandek sandiqlar ro'yxatidan olib tashlaymiz.
    # Agar bu noto'g'ri harakat bo'lsa, False(yolg'on)ni qaytaramiz.
    # Aks holda, ushbu harakat natijasini qaytaramiz.
    smallestDistance = 100 # Har qanday sandiq 100 dan yaqinroq bo'ladi.
    for cx, cy in chests:
        distance = math.sqrt((cx - x) * (cx - x) + (cy - y) * (cy - y))

        if distance < smallestDistance: # Bizga eng yaqinda joylashgan xazina sandig'i kerak
            smallestDistance = distance

    smallestDistance = round(smallestDistance)

    if smallestDistance == 0:
        # xy to'g'ridan-to'g'ri xazina sandig'ida!
        chests.remove([x, y])
        return 'Siz cho\'kib ketgan xazina sandig\'ini topdingiz!'
    else:
        if smallestDistance < 10:
            board[x][y] = str(smallestDistance)
            return 'Sonar qurilmasidan %s masofada xazina aniqlandi.' % (smallestDistance)
        else:
            board[x][y] = 'X'
            return 'Sonar hech narsani aniqlamadi. Barcha xazina sandiqlari doiradan tashqarida.'

def enterPlayerMove(previousMoves):
    # O'yinchi o'z harakatini kirishiga ruxsat bering. Int xy koordinatalarining ikki elementli ro'yxatini qaytaring.
    print('Keyingi sonar qurilmasini qaerga tashlamoqchisiz? (0-59 0-14) (yoki chiqish deb yozing)')
    while True:
        move = input()
        if move.lower() == 'chiqish':
            print('O\'ynaganingiz uchun tashakkur!')
            sys.exit()

        move = move.split()
        if len(move) == 2 and move[0].isdigit() and move[1].isdigit() and isOnBoard(int(move[0]), int(move[1])):
            if [int(move[0]), int(move[1])] in previousMoves:
                print('Siz allaqachon u yerga yurgansiz.')
                continue
            return [int(move[0]), int(move[1])]

        print('0 dan 59 gacha raqamni, bo\'sh joyni, keyin 0 dan 14 gacha bo\'lgan raqamni kiriting.')

def showInstructions():
    print('''Ko'rsatmalar:
Siz xazina qidiradigan kemaning Simon kapitansiz. Sizning hozirgi vazifangiz
pastki qismida cho'kkan uchta xazina sandig'ini topish uchun sonar asboblaridan foydalanish
okean. Ammo sizda faqat arzon sonar bor, u yo'nalishni emas, balki masofani topadi.

Sonar qurilmasini tushirish uchun koordinatalarni kiriting. Okean xaritasi bilan belgilanadi
eng yaqin ko'krak qafasi qanchalik uzoq bo'lsa yoki X sonar moslamasidan tashqarida bo'lsa
oralig'i. Masalan, S belgilar ko'krak qafasi joylashgan joy. Sonar qurilmasi a ni ko'rsatadi
3 chunki eng yaqin ko'krak qafasi 3 bo'shliqda.

            1         2         3
  012345678901234567890123456789012

0 ~~~~`~```~`~``~~~``~`~~``~~~``~`~ 0
1 ~`~`~``~~`~```~~~```~~`~`~~~`~~~~ 1
2 `~`C``3`~~~~`C`~~~~`````~~``~~~`` 2
3 ````````~~~`````~~~`~`````~`~``~` 3
4 ~`~~~~`~~`~~`C`~``~~`~~~`~```~``~ 4

  012345678901234567890123456789012
            1         2         3
(Haqiqiy o'yinda sandiqlar okeanda ko'rinmaydi.)

Davom ettirish uchun Enter tugmasini bosing...''')
    input()

    print('''Sonar moslamasini to'g'ridan-to'g'ri sandiqqa tashlaganingizda, 
    uni olasiz va boshqa sonar qurilmalar yangilanadi, keyingi eng yaqin sandiq qancha masofada joylashganligini ko'rsatadi. 
    Sandiq chap tomonda joylashgan sonar moslamasi chegarasidan tashqarida, shuning uchun u X ni ko'rsatadi.

            1         2         3
  012345678901234567890123456789012

0 ~~~~`~```~`~``~~~``~`~~``~~~``~`~ 0
1 ~`~`~``~~`~```~~~```~~`~`~~~`~~~~ 1
2 `~`X``7`~~~~`C`~~~~`````~~``~~~`` 2
3 ````````~~~`````~~~`~`````~`~``~` 3
4 ~`~~~~`~~`~~`C`~``~~`~~~`~```~``~ 4

  012345678901234567890123456789012
            1         2         3

Xazina sandiqlari aylanib yurmaydi. Sonar qurilmalari xazina qutilarini 9 bo'shliqgacha aniqlay oladi. 
Sonar qurilmalari tugamasdan oldin barcha 3 sandiqni yig'ishga harakat qiling. Omad!

Davom ettirish uchun Enter tugmasini bosing...''')
    input()



print('S O N A R !')
print()
print('Ko\'rsatmalarni ko\'rishni xohlaysizmi? (ha yoki yo\'q)')
if input().lower().startswith('h'):
    showInstructions()

while True:
    # Game setup
    sonarDevices = 20
    theBoard = getNewBoard()
    theChests = getRandomChests(3)
    drawBoard(theBoard)
    previousMoves = []

    while sonarDevices > 0:
        # Sonar moslamasi va sandiq holatini ko'rsating.
        print('Sizda %s sonar moslama(lar) qoldi. %s xazina quti(lar) qoldi.' % (sonarDevices, len(theChests)))

        x, y = enterPlayerMove(previousMoves)
        previousMoves.append([x, y]) # Sonar qurilmalari yangilanishi uchun biz barcha harakatlarni kuzatib borishimiz kerak.

        moveResult = makeMove(theBoard, theChests, x, y)
        if moveResult == False:
            continue
        else:
            if moveResult == 'Siz cho\'kib ketgan xazina sandig\'ini topdingiz!':
                # Hozirda xaritada mavjud barcha sonar qurilmalarini yangilaymiz.
                for x, y in previousMoves:
                    makeMove(theBoard, theChests, x, y)
            drawBoard(theBoard)
            print(moveResult)

        if len(theChests) == 0:
            print('Siz cho\'kib ketgan barcha xazina qutilarini topdingiz! Tabriklayman, yaxshi o\'yin bo\'ldi!')
            break

        sonarDevices -= 1

    if sonarDevices == 0:
        print('Sonar qurilmalarimiz tugadi! Endi biz kemani aylantirib, xazina sandiqlari bilan')
        print('uyimiz tomon yo\'l olishimiz kerak! O\'yin tugadi.')
        print(' Qolgan sandiqlar bu yerda edi:')
        for x, y in theChests:
            print(' %s, %s' % (x, y))

    print('Qayta o\'ynashni xohlaysizmi? (ha yoki yo\'q)')
    if not input().lower().startswith('h'):
        sys.exit()

```

# Dasturni loyihalash
Manba kodini tushunishga urinishdan oldin, nima bo'layotganini bilish uchun o'yinni bir necha marta o'ynang. "Sonar xazinalar ovi" o'yini ma'lumotlar tuzilmalari deb nomlangan ro'yxatlar va boshqa murakkab o'zgaruvchilar ro'yxatlaridan foydalanadi. Ma'lumotlar tuzilmalari biror narsani ifodalash uchun qiymatlar tartibini saqlaydi. Masalan, 10-bobda "Krestik Nolik" taxtasining ma'lumotlar tuzilishi qatorlarning ro'yxati edi. Satr X, O yoki bo'sh joyni, ro'yxatdagi satrning ko'rsatkichi esa taxtadagi bo'sh joyni ifodalaydi. "Sonar xazinalar ovi" o'yini xazina sandiqlari va sonar qurilmalari joylashgan joylari uchun shunga o'xshash ma'lumotlar tuzilmalariga ega bo'ladi.
 
# random, sys va math modullarini import qilamiz
Dastur boshida biz `random`, `sys` va `math` modullarini import qilamiz:
```python
# Sonar Treasure Hunt

import random
import sys
import math
```
`sys` moduli `exit()` funktsiyasini o'z ichiga oladi, ushbu funksiya dasturni darhol tamomlaydi.
`sys.exit()` chaqiruvidan keyin kod satrlarining hech biri ishlamaydi; Dastur shunchaki oxirigacha to'xtaydi. Ushbu funktsiya keyinchalik dasturda qo'llaniladi. Matematik modulda sonning kvadrat ildizini topish uchun foydalaniladigan `sqrt()` funktsiyasi mavjud. Kvadrat ildizlar ortidagi matematik 186-betdagi "Eng yaqin xazina sandig'ini topish" da izohlangan.

# Yangi o'yin taxtasini yaratish
Har bir yangi o'yinni boshlash uchun `getNewBoard()` tomonidan yaratilgan yangi `board` ma'lumotlar tuzilishi kerak. "Sonar xazinalar ovi" o'yin taxtasi - atrofida x va y koordinatalari bo'lgan ASCII Art okeanidir. Biz `board` ma'lumotlar tuzilmasidan foydalanganda dekart koordinatalariga kirishimiz kabi uning koordinatalar tizimiga kirishni xohlaymiz. Buning uchun biz har bir koordinatani taxtada quyidagicha chaqirish uchun ro'yxatlar ro'yxatidan foydalanamiz: `board [x][y]`.  x koordinatasi y koordinatasidan oldin keladi - (26, 12) koordinatadagi satrni olish uchun siz `board[12][26]` ga emas, balki `board[26][12]` kirasiz.

```python
def getNewBoard():
    # Yangi 60x15 taxta ma'lumotlar tuzilishini yaratish
    board = []
    for x in range(60): # 60 ta ro'yhatdan iborat asosiy ro'yhat
        board.append([])
        for y in range(15): # Har bir asosiy ro'yhatdagi ro'yhatda 15ta bitta-belgili satrlar bor
            # O'qishga oson bo'lishi uchun okeanga harhil belgilar ishlatamiz
            if random.randint(0, 1) == 0:
                board[x].append('~')
            else:
                board[x].append('`')
    return board
```

Ma'lumotlarning taxtasi `board` - bu satrlar ro'yxati. Birinchi ro'yxat x koordinatasini aks ettiradi. O'yin taxtasi bo'ylab 60 ta belgi bo'lganligi sababli, ushbu birinchi ro'yxatda 60 ta ro'yxat bo'lishi kerak. 10-qatorda biz unga 60 ta bo'sh ro'yxatni qo'shadigan `for` tsiklini yaratamiz.

Ammo `board` shunchaki 60 ta bo'sh ro'yxatlarning ro'yxatidan ko'proq. 60 ro'yxatning har biri o'yin taxtasining x koordinatasini aks ettiradi. Taxtada 15 ta qator bor, shuning uchun ushbu 60 ta ro'yxatning har birida 15 ta satr bo'lishi kerak. 12-satr - bu okeanni aks ettiruvchi 15 ta bitta simli satrlarni qo'shadigan yana bir `for` tsikli.

Okean tasodifiy tanlangan '~' va '\`' qatorlar to'plami bo'ladi. Klaviaturangizdagi 1 tugmachaning yonida joylashgan tilda (~) va orqa belgi (\`) belgilar okean to'lqinlari uchun ishlatiladi. Qaysi belgidan foydalanilishini aniqlash uchun 14 dan 17 gacha bo'lgan satrlarda ushbu mantiq qo'llaniladi: agar `random.randint()` ning qaytish qiymati 0 ga teng bo'lsa, '~' qatorini qo'shing; aks holda, '\`' qatorini qo'shing. Bu okeanga tasodifiy, bo'g'iq ko'rinish beradi.

Kichikroq misol uchun, agar `board` [['~', '~', '' '], [[' ~ ',' ~ ',' ''], [['~', '~ ',' "'], [' ~ ',' '', ''], ['"', '~', '' ']] u holda chizilgan taxta quyidagicha ko'rinishga ega bo'ladi:

```
~~~~`
~~~`~
.`````
```

Va ohiri, funktsiya 18-qatorda `board` o'zgaruvchisidagi qiymatni qaytaradi:
```python
return board
```

# O'yin taxtasini chizish
Keyin biz yangi taxta chizganimizda chaqiradigan `drawBoard()` usulini aniqlaymiz:
```python
def drawBoard(board):
```
Koordinatalari bilan to'liq o'yin taxtasi quyidagicha ko'rinadi:
```
             1         2         3         4         5
   012345678901234567890123456789012345678901234567890123456789
 0 ~~~`~``~~~``~~~~``~`~`~`~`~~`~~~`~~`~``````~~`~``~`~~```~`~` 0
 1 `~`~````~~``~`~```~```~```~`~~~``~~`~~~``````~`~``~~``~~`~~` 1
 2 ```~~~~`~`~~```~~~``~````~~`~`~~`~`~`~```~~`~``~~`~`~~~~~~`~ 2
 3 ~~~~`~~~``~```~``~~`~`~~`~`~~``~````~`~````~```~`~`~`~`````~ 3
 4 ~```~~~~~`~~````~~~~```~~~`~`~`~````~`~~`~`~~``~~`~``~`~``~~ 4
 5 `~```~`~`~~`~~~```~~``~``````~~``~`~`~~~~`~~``~~~~~~`~```~~` 5
 6 ``~~`~~`~``~`````~````~~``~`~~~~`~~```~~~``~`~`~~``~~~```~~~ 6
 7 ``~``~~~~~~```~`~```~~~``~`~``~`~~~~~~```````~~~`~~`~~`~~`~~ 7
 8 ~~`~`~~```~``~~``~~~``~~`~`~~`~`~```~```~~~```~~~~~~`~`~~~~` 8
 9 ```~``~`~~~`~~```~``~``~~~```~````~```~`~~`~~~~~`~``~~~~~``` 9
10 `~~~~```~`~````~`~`~~``~`~~~~`~``~``~```~~```````~`~``~````` 10
11 ~~`~`~~`~``~`~~~````````````````~~`````~`~~``~`~~~~`~~~`~~`~ 11
12 ~~`~~~~```~~~`````~~``~`~`~~``````~`~~``~```````~~``~~~`~~`~ 12
13 `~``````~~``~`~~~```~~~~```~~`~`~~~`~```````~~`~```~``~`~~~~ 13
14 ~~~``~```~`````~~`~`~``~~`~``~`~~`~`~``~`~``~~``~`~``~```~~~ 14
   012345678901234567890123456789012345678901234567890123456789
             1         2         3         4         5
```
`DrawBoard()` funktsiyasidagi rasm to'rt bosqichdan iborat:
1. Keng bo'shliqlar bilan oraliqda 1, 2, 3, 4 va 5 gacha bo'lgan qatorning o'zgaruvchisini yarating. Ushbu raqamlar x o'qi bo'yicha 10, 20, 30, 40 va 50 koordinatalarini belgilaydi.
2. Ushbu o'q yordamida x o'qi koordinatalarini yuqori qismi bo'ylab aks ettiring
ekran.
3. Okeanning har bir satrini ekranning ikkala tomonidagi y o'qi koordinatalari bilan birga chop eting.
4. X o'qini pastki qismida yana chop eting. Har tomondan koordinatalarga ega bo'lish sonar qurilmani qaerga joylashtirishni ko'rishni osonlashtiradi.

#### X-koordinatalarini doskaning yuqori qismida chizish
`DrawBoard()` ning birinchi qismi taxtaning yuqori qismidagi x o'qini bosib chiqaradi. Biz taxtaning har bir qismi teng bo'lishini istaganimiz uchun har bir koordinata yorlig'i faqat bitta belgi maydonini egallashi mumkin. Koordinatali raqamlash 10 ga etganida, har bir raqam uchun ikkita raqam mavjud, shuning uchun biz o'nlikdagi raqamlarni 13-3-rasmda ko'rsatilgandek alohida chiziqqa qo'yamiz. X o'qi shunday joylashtirilganki, birinchi satrda o'nli o'rinli raqamlar, ikkinchi satrda esa raqamlar ko'rsatiladi.
```
+++++++++++++1+++++++++2+++++++++3              # Birinchi qator
+++0123456789012345678901234567890123456789     # Ikkinchi qator
+0 ~`~``~``~``~`~`~```~`~``````~```~`~~~`~~ 0   # Uchinchi qator
```

22 dan 24 gacha bo'lgan qatorlar taxtaning birinchi qatori uchun qatorni hosil qiladi, bu o'nlab joylarga ega bo'lgan x o'qi qismidir:
```python
    # Taxtaning ma'lumotlar tuzilishini chizish. 
    tensDigitsLine = '    ' # Taxtaning chap tomonidagi raqamlar uchun dastlabki bo'sh joy
    for i in range(1, 6):
        tensDigitsLine += (' ' * 9) + str(i)
```

Birinchi satrda o'nlik pozitsiyasini belgilaydigan raqamlarning barchasi o'rtasida 9 ta bo'shliq bor va 1-ning oldida 13 ta bo'shliq mavjud. 22 dan 24 gacha bo'lgan qatorlar shu qator bilan satr hosil qiladi va uni `tensDigitsLine` nomli o'zgaruvchida saqlaydi:
```python
    # Raqamlarni taxtaning yuqori qismiga bosib chiqaramz.
    print(tensDigitsLine)
    print('   ' + ('0123456789' * 6))
    print()
```

Raqamlarni o'yin taxtasining yuqori qismida chop etish uchun avval `tensDigitsLine` o'zgaruvchisining tarkibini chop eting. So'ngra, keyingi satrda uchta bo'sh joyni bosib chiqaring (shu qator to'g'ri kelishi uchun), so'ngra `'0123456789'` qatorini olti marta bosib chiqaring: `('0123456789' * 6)`.

#### Okeanni chizish
32 dan 44 gacha bo'lgan satrlar okean to'lqinlarining har bir satrini, shu qatorda y o'qini belgilash uchun yon tomonidagi raqamlarni bosib chiqaradi:

```python
    # 15 qatorning har birini chop etamiz
    for row in range(15):
        # Bir xonali raqamlarni qo'shimcha joy bilan to'ldirish kerak.
        if row < 10:
            extraSpace = ' '
        else:
            extraSpace = ''
```

`For` tsikli taxtaning har ikki tomonidagi qator raqamlari bilan birga 0 dan 14 gacha qatorlarni bosib chiqaradi.
Ammo bizda x o'qi bilan bir xil muammo bor. Faqat bitta raqamga ega bo'lgan raqamlar (masalan, 0, 1, 2 va hokazo) bosilganda faqat bitta bo'sh joyni egallaydi, ammo ikkita raqamli raqamlar (masalan, 10, 11 va 12) ikkita bo'sh joyni egallaydi. Agar koordinatalar har xil o'lchamlarga ega bo'lsa, qatorlar qatorga qo'shilmaydi. Kengash shunday ko'rinadi:
```
 8 ~~`~`~~```~``~~``~~~``~~`~`~~`~`~```~```~~~```~~~~~~`~`~~~~` 8
 9 ```~``~`~~~`~~```~``~``~~~```~````~```~`~~`~~~~~`~``~~~~~``` 9
10 `~~~~```~`~````~`~`~~``~`~~~~`~``~``~```~~```````~`~``~````` 10
11 ~~`~`~~`~``~`~~~````````````````~~`````~`~~``~`~~~~`~~~`~~`~ 11
```
Yechish oson: barcha bitta raqamli raqamlar oldida bo'sh joy qo'shing. 34 dan 37 gacha bo'lgan qatorlar `ExtraSpace` o'zgaruvchisini bo'sh joyga yoki bo'sh satrga o'rnatadi. `ExtraSpace` o'zgaruvchisi har doim bosilib chiqadi, lekin u faqat bitta raqamli qator raqamlari uchun bo'shliq belgisiga ega. Aks holda, bu bo'sh satr. Shunday qilib, barcha qatorlar ularni bosib chiqarishda bir qatorga to'g'ri keladi.

#### Okeandagi qatorni chop etish
Kengash parametri - bu butun okean to'lqinlari uchun ma'lumotlar tuzilishi. 39 dan 44 gacha bo'lgan satrlar taxtaning o'zgaruvchisini o'qiydi va bitta qatorni bosib chiqaradi:
```python
        # Ushbu qator uchun satrni taxtada yaratish.
        boardRow = ''
        for column in range(60):
            boardRow += board[column][row]

        print('%s%s %s %s' % (extraSpace, row, boardRow, row))
```

40-qatorda `boardRow` bo'sh satr sifatida boshlanadi. 32-satrda `for` tsikli okean to'lqinlarining hozirgi qatori uchun o'zgaruvchini o'rnatadi. 41-satrda ushbu tsiklning ichida joriy satrning har bir ustuni bo'ylab takrorlanadigan yana bir `for` tsikli mavjud. Biz ushbu taxtada `taxta[column][row]`ni biriktirib, `boardRow` hosil qilamiz, bu `board[0][row]`, `board[1][row]`, `board[2][satr]`larni birlashtirish degan ma'noni anglatadi va shunga o'xshash narsalar uchun  `board[59][row]`. Bu qatorda 0 indeksidan 59 indeksigacha 60 ta belgi borligi sababli.
41-satrdagi `for` tsikli 0 dan 59 gacha bo'lgan butun sonlar bo'ylab takrorlanadi. Har bir takrorlashda doska ma'lumotlari tarkibidagi keyingi belgi `boardRow` oxiriga ko'chiriladi. Tsikl tugaguncha, `boardRow` qatorning to'liq ASCII sa'nat to'lqinlariga ega bo'ladi. Keyin `boardRow` dagi satr 44-qatordagi qator raqamlari bilan birga chop etiladi.

#### X-koordinatalarini taxtaning pastki qismida chizish
46 dan 49 gacha bo'lgan satrlar 26 dan 29 gacha bo'lgan satrlarga o'xshaydi:
```python
    # Raqamlarni taxtaning pastki qismida bosib chiqarish.
    print()
    print('   ' + ('0123456789' * 6))
    print(tensDigitsLine)
```
Ushbu satrlar taxtaning pastki qismidagi x-koordinatalarini bosib chiqaradi.

# Tasodifiy xazina sandiqlarini yaratish
O'yin tasodifiy ravishda yashirin xazina sandiqlari qaerdaligini hal qiladi. Xazina qutilari ikkita butun sonli ro'yxatlar ro'yxati sifatida taqdim etilgan. Ushbu ikkita butun son bitta x ning x va y koordinatalari. Masalan, agar ko'krak qafasi ma'lumotlarining tuzilishi `[[2, 2], [2, 4], [10, 0]]` bo'lsa, demak, uchta xazina sandig'i bor edi, ulardan biri (2, 2), ikkinchisi (2, 4), uchinchisi (10, 0) da.
`GetRandomChests()` funktsiyasi tasodifiy tayinlangan koordinatalarda ma'lum miqdordagi ko'krak ma'lumotlari tuzilishini yaratadi:
```python
def getRandomChests(numChests):
    # Sandiq ma'lumotlari tuzilmalari ro'yxatini yaratish (x, y int koordinatalarining ikki elementli ro'yxati).
    chests = []
    while len(chests) < numChests:
        newChest = [random.randint(0, 59), random.randint(0, 14)]
        if newChest not in chests: # Sandiq allaqachon bu erda emasligiga ishonch hosil qilamiz.
            chests.append(newChest)
    return chests
```

`NumChests` parametri funktsiyaga qancha xazina qutisi yaratish kerakligini aytadi. 54-qator `while` tsikli barcha koordinatalar berilgunga qadar takrorlanadi. 55-chiziqdagi koordinatalar uchun ikkita tasodifiy butun son tanlangan. X-koordinatasi 0 dan 59 gacha, y koordinatasi esa 0 dan 14 gacha bo'lishi mumkin. `[random.randint (0, 59), random.randint (0, 14)]` ifodasi `[2, 2]` yoki `[2, 4]` yoki `[10, 0]` kabi ro'yxat qiymatiga qarab baholanadi. Agar ushbu koordinatalar `chests` ro'yxatida mavjud bo'lmasa, ular 57-qatorda `chests` ga qo'shiladi.

# Ko'chirishning haqiqiyligini aniqlash
O'yinchi sonar qurilmani tushirmoqchi bo'lgan joy uchun x- va y-koordinatalarini kiritganda, biz raqamlarning haqiqiyligiga ishonch hosil qilishimiz kerak. Yuqorida aytib o'tilganidek, harakatning amal qilishi uchun ikkita shart mavjud: x koordinatasi 0 dan 59 gacha, y koordinatasi esa 0 dan 14 gacha bo'lishi kerak.
`IsOnBoard()` funktsiyasi oddiy ifodadan foydalanadi va operatorlar ushbu shartlarni bitta ifodaga birlashtirish uchun `and` ifodaning har bir qismi `True` bo'lishini ta'minlash uchun:
```python
def isOnBoard(x, y):
    # Agar koordinatalar doskada bo'lsa, True-ni, aks holda, False-ni qaytaramiz.
    return x >= 0 and x <= 59 and y >= 0 and y <= 14
```
Biz `and` mantiqiy operatoridan foydalanayotganimiz sababli, hatto koordinatalardan biri yaroqsiz bo'lsa, u holda butun ifoda `False`ga baholanadi.

# Harakatni taxtaga joylashtirish
"Sonar xazinalar ovi" o'yinida o'yin taxtasi har bir sonar moslamasining eng yaqin xazina sandig'iga bo'lgan masofasini ko'rsatadigan raqamni ko'rsatish uchun yangilanadi. Shunday qilib, o'yinchi dasturni x va y koordinatalarini berib harakat qilganda, xazina sandiqlari pozitsiyalariga qarab taxta o'zgaradi.
```python
def makeMove(board, chests, x, y):
    # Sonar qurilmasi belgisi bilan taxta ma'lumotlar tuzilishini o'zgartiring. Xazina sandiqlarini topilgandek sandiqlar ro'yxatidan olib tashlaymiz.
    # Agar bu noto'g'ri harakat bo'lsa, False(yolg'on)ni qaytaramiz.
    # Aks holda, ushbu harakat natijasini qaytaramiz.
```

`MakeMove()` funktsiyasi to'rt parametrni oladi: o'yin taxtasining ma'lumotlar tuzilishi, xazina sandig'ining ma'lumotlar tuzilishi, x koordinatasi va y koordinatasi. `MakeMove()` funktsiyasi harakatga javoban nima bo'lganligini tavsiflovchi satr qiymatini qaytaradi:
 -  Agar koordinatalar to'g'ridan-to'g'ri xazina qutisiga tushsa, `makeMove()` `'Siz cho'kib ketgan xazina sandig'ini topdingiz!'` satrini qaytaradi.
 -  Agar koordinatalar sandiqdan 9 yoki undan kam masofada bo'lsa, `makeMove()` `'Sonar qurilmasidan %s masofada xazina aniqlandi.'` (bu erda %s butun masofa bilan almashtiriladi).
 -  Aks holda, `makeMove()` `'Sonar hech narsani aniqlamadi. Barcha xazina sandiqlari doiradan tashqarida.'`ni qaytaradi.

O'yinchi sonarni tushirmoqchi bo'lgan joyning koordinatalarini hisobga olgan holda qurilma va xazinalar uchun x va y koordinatalarining ro'yxati, qaysi xazina sandig'i eng yaqin ekanligini aniqlash uchun algoritm kerak bo'ladi.

#### Eng yaqin xazina sandig'ini topish
68 dan 75 gacha bo'lgan satrlar sonar moslamasiga qaysi xazina sandig'ining yaqinligini aniqlash algoritmidir.
```python
    smallestDistance = 100 # Har qanday sandiq 100 dan yaqinroq bo'ladi.
    for cx, cy in chests:
        distance = math.sqrt((cx - x) * (cx - x) + (cy - y) * (cy - y))

        if distance < smallestDistance: # Bizga eng yaqinda joylashgan xazina sandig'i kerak
            smallestDistance = distance
```
x va y parametrlari tamsayılar (masalan, 3 va 5) bo'lib, ular birgalikda o'yinchi taxmin qilgan o'yin taxtasida joylashgan joyni anglatadi. `chests` o'zgaruvchisi uchta xazinaning joylashishini ifodalovchi `[[5, 0], [0, 2], [4, 2]]` kabi qiymatga ega bo'ladi. 13-4-rasmda ushbu qiymat ko'rsatilgan.
Sonar moslamasi va xazina sandig'i orasidagi masofani topish uchun ikkita x- va y-koordinatalar orasidagi masofani topish uchun matematikadan o'tishimiz kerak bo'ladi. Aytaylik, biz sonar moslamasini (3, 5) joylashtiramiz va (4, 2) da xazina sandig'iga masofani topishni xohlaymiz.

x va y koordinatalarining ikkita to'plami orasidagi masofani topish uchun biz Pifagor teoremasidan foydalanamiz. Ushbu teorema to'g'ri burchakli uchburchakka taalluqlidir - bir burchagi 90 daraja bo'lgan uchburchaklar, xuddi shu to'rtburchakda topilgan burchak. Pifagor teoremasi uchburchakning diagonal tomonini gorizontal va vertikal tomonlari uzunliklaridan hisoblash mumkin, deydi. 13-5-rasmda sonar moslamasi (3, 5) va xazina sandig'i (4, 2) da tortilgan to'rtburchak uchburchak ko'rsatilgan.

Pifagor teoremasi a^2 + b^2 = c^2, unda a gorizontal tomonning uzunligi, b vertikal tomonning uzunligi va c diagonal tomonning yoki gipotenuzaning uzunligi. Ushbu uzunliklar kvadratga bo'linadi, ya'ni bu raqam o'zi bilan ko'paytiriladi. Raqamni "kvadratga tortmaslik" raqamning kvadrat ildizini topish deb ataladi, chunki biz c2 dan c olishimiz kerak bo'ladi.

Pifagor teoremasidan sonar moslama (3, 5) va sandiq (4, 2) orasidagi masofani topish uchun foydalanamiz:
1. A ni topish uchun birinchi x koordinatasidan ikkinchi x-koordinatani 4 ni chiqaring, 3: 3 - 4 = –1.
2. a^2 ni topish uchun a ni a ga ko'paytiring: –1 × –1 = 1. (manfiy son, salbiy son har doim musbat songa teng bo'ladi.)
3. B ni topish uchun birinchi y koordinatasidan ikkinchi y-koordinatani 2, 5: 5 - 2 = 3 ayirib tashlang.
4. b^2 ni topish uchun b ni b ga ko'paytiring: 3 × 3 = 9.
5. c^2 ni topish uchun a^2 va b^2 ni qo'shing: 1 + 9 = 10.
6. c^2 dan c ni olish uchun c^2 ning kvadrat ildizini topish kerak.

Biz 5-qatorga import qilgan `math` modulda `sqrt()` nomli kvadrat ildiz funktsiyasi mavjud. Interaktiv qobiqga quyidagilarni kiriting:
```
>>> import math
>>> math.sqrt(10)
3.1622776601683795
>>> 3.1622776601683795 * 3.1622776601683795
10.000000000000002
```

E'tibor bering, kvadrat ildizni o'zi ko'paytirganda kvadrat son hosil bo'ladi. (10-ning oxiridagi qo'shimcha 2, `sqrt()` funktsiyasidagi muqarrar yengil noaniqlikdandir.)
c^2 ni `sqrt()` ga o'tkazib, sonar qurilmasi xazina sandig'idan 3,16 birlik masofada ekanligini aytishimiz mumkin. O'yin buni 3 gacha yaxlitlaydi.
Keling, yana 68 dan 70 gacha chiziqlarni ko'rib chiqaylik:
```python
    smallestDistance = 100 # Har qanday sandiq 100 dan yaqinroq bo'ladi.
    for cx, cy in chests:
        distance = math.sqrt((cx - x) * (cx - x) + (cy - y) * (cy - y))
```
`For` chizig'i ichidagi kod har bir sandiqning masofasini hisoblab chiqadi. 68-qator `smallesDistance` 100 ta eng kichik masofani beradi, shunda siz topgan xazinalar qutilaridan kamida bittasi 73-qatorga `smallestDistance`ga qo'yiladi. *cx - x* gorizontal masofani *a* sandiq va sonar moslamasi o'rtasida, *(cx - x) \* (cx - x)* bizning Pifagor teoremasi hisob-kitobining a^2-si. U *(cy - y) \* (cy - y)* ga qo'shiladi, b2. Ushbu summa c^2 ga teng va sandiq va sonar moslamasi orasidagi masofani olish uchun `sqrt()` ga uzatiladi.
Biz sonar moslamasi va eng yaqin ko'krak qafasi orasidagi masofani topmoqchimiz, shuning uchun agar bu masofa eng kichik masofadan kichik bo'lsa, u 73-qatorda eng yangi masofa sifatida saqlanadi:
```python
        if distance < smallestDistance: # Bizga eng yaqinda joylashgan xazina sandig'i kerak
            smallestDistance = distance
```

`For` tsikli tugagach, siz `smallestDistance` ning sonar moslamasi va o'yindagi barcha xazinalar orasidagi eng qisqa masofani ushlab turishini bilasiz.

#### Ro'yhat usuli remove() bilan qiymatlarni olib tashlash
`remove()` list usuli o'tgan argumentga mos keladigan qiymatning birinchi paydo bo'lishini olib tashlaydi. Masalan, interaktiv qobiqga quyidagilarni kiriting:
```
>>> x = [42, 5, 10, 42, 15, 42]
>>> x.remove(10)
>>> x
[42, 5, 42, 15, 42]
```
10 qiymat x ro'yxatidan olib tashlandi.
Endi interaktiv qobiqga quyidagilarni kiriting:
```
>>> x = [42, 5, 10, 42, 15, 42]
>>> x.remove(42)
>>> x
[5, 10, 42, 15, 42]
```
E'tibor bering, faqat birinchi 42 qiymat o'chirilgan, ikkinchisi va uchinchisi esa hanuzgacha mavjud. `remove()` usuli siz o'tkazgan qiymatning birinchi va faqat birinchisini olib tashlaydi.
Agar siz ro'yxatdagi qiymatni olib tashlamoqchi bo'lsangiz, xatoga yo'l qo'yasiz:
```
>>> x = [5, 42]
>>> x.remove(10)
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
ValueError: list.remove(x): x not in list
```
`append()` usuli singari, `remove()` usuli ham ro'yxatda chaqiriladi va ro'yxatni qaytarmaydi. Siz `x = x.remove(42)` emas, balki `x.remove(42)` kabi koddan foydalanmoqchisiz.
Keling, o'yindagi sonar qurilmalari va xazina sandiqlari orasidagi masofani topishga qaytaylik. Sonar qurilmaning x va y-koordinatalari xazinalar x va y-koordinatalari bilan bir xil bo'lganida, eng kichik masofa 0 ga teng bo'lgan yagona vaqt. Bu shuni anglatadiki, o'yinchi xazina sandig'ining o'rnini to'g'ri taxmin qilgan.

```python
    if smallestDistance == 0:
        # xy to'g'ridan-to'g'ri xazina sandig'ida!
        chests.remove([x, y])
        return 'Siz cho\'kib ketgan xazina sandig\'ini topdingiz!'
```
Bu sodir bo'lganda, dastur `remove()` ro'yxati usuli bilan ushbu sandiqning ikki raqamli ro'yxatini ma'lumotlar tuzilmasidan o'chirib tashlaydi. Keyin funktsiya "Siz cho'kib ketgan xazina sandig'ini topdingiz!" satrini qaytaradi.

Ammo `smallestDistance` 0 ga teng bo'lmasa, o'yinchi xazina sandig'ining aniq joyini taxmin qilmadi va 81-qatordan boshlangan else bloki quyidagilarni bajaradi:
```python
    else:
        if smallestDistance < 10:
            board[x][y] = str(smallestDistance)
            return 'Sonar qurilmasidan %s masofada xazina aniqlandi.' % (smallestDistance)
        else:
            board[x][y] = 'X'
            return 'Sonar hech narsani aniqlamadi. Barcha xazina sandiqlari doiradan tashqarida.'
```
Agar sonar moslamasining xazina qutisiga bo'lgan masofasi 10 dan kam bo'lsa, 83-satr doskada `smallestDistance`ning simli versiyasi bilan belgilanadi. Agar shunday bo'lmasa, taxta "X" belgisi bilan belgilanadi. Shunday qilib, o'yinchi har bir sonar moslamasining xazina sandig'iga qanchalik yaqinligini biladi. Agar o'yinchi *0* ni ko'rsa, ular ketish yo'llarini bilishadi.

#### O'yinchini harakatini olish
`enterPlayerMove()` funktsiyasi o'yinchining keyingi harakatining x va y koordinatalarini to'playdi:
```python
def enterPlayerMove(previousMoves):
    # O'yinchi o'z harakatini kirishiga ruxsat bering. Int xy koordinatalarining ikki elementli ro'yxatini qaytaring.
    print('Keyingi sonar qurilmasini qaerga tashlamoqchisiz? (0-59 0-14) (yoki chiqish deb yozing)')
    while True:
        move = input()
        if move.lower() == 'chiqish':
            print('O\'ynaganingiz uchun tashakkur!')
            sys.exit()
```

`previousMoves` parametri - bu sonar moslamasini qo'ygan oldingi joylarning ikki tamsayıli ro'yxatlarining ro'yxati. Ushbu ma'lumot o'yinchi sonar moslamasini allaqachon o'rnatilgan joyga joylashtirmasligi uchun ishlatiladi.
`while` tsikli o'yinchidan sonar qurilmasi bo'lmagan joy uchun koordinatalarni kiritguncha keyingi harakatlarini so'rab turadi. Shuningdek, o'yinchi o'yinni tark etish uchun "chiqish"ni kiritishi mumkin. Bunday holda, 96-qator dasturni darhol tugatish uchun `sys.exit()` funktsiyasini chaqiradi.
Agar o'yinchi "chiqish"ni kiritmagan deb hisoblasak, kod kiritilgan bo'shliq bilan ajratilgan ikkita butun son ekanligini tekshiradi. 98-qator `move`da `split()` usulini `move`ning yangi qiymati sifatida chaqiradi:

```python
        move = move.split()
        if len(move) == 2 and move[0].isdigit() and move[1].isdigit() and isOnBoard(int(move[0]), int(move[1])):
            if [int(move[0]), int(move[1])] in previousMoves:
                print('Siz allaqachon u yerga yurgansiz.')
                continue
            return [int(move[0]), int(move[1])]

        print('0 dan 59 gacha raqamni, bo\'sh joyni, keyin 0 dan 14 gacha bo\'lgan raqamni kiriting.')
```
Agar o'yinchi "1 2 3" qiymatini yozgan bo'lsa, `split()` bilan qaytarilgan ro'yxat ['1', '2', '3'] bo'ladi. Bunday holda, `len(move) == 2` ifodasi `False` (harakatdagi ro'yxat faqat ikkita raqamdan iborat bo'lishi kerak, chunki u koordinatani bildiradi) va butun ifoda darhol `False`ga baholanadi. Python qisqa tutashuv sababli qolgan ifodani tekshirmaydi (bu "Qisqa tutashuvni baholash" da 139-betda tasvirlangan).
Agar ro'yxatning uzunligi 2 ga teng bo'lsa, u holda ikkita qiymat `move[0]` va `move[1]` harakatlanish indekslarida bo'ladi. Ushbu qiymatlar raqamlar (masalan, '2' yoki '17') ekanligini tekshirish uchun siz `isOnlyDigits()` kabi funktsiyani "Satrda faqat raqamlar borligini tekshirish" 158 sahifasida ishlatishingiz mumkin. Ammo Pythonda allaqachon shunday usul mavjud bu.
Satr usuli `isdigit()`, agar satr faqat raqamlardan iborat bo'lsa, `True` qiymatini qaytaradi. Aks holda, `False`ni qaytaradi. Interaktiv qobiqga quyidagilarni kiriting:
```
>>> '42'.isdigit()
True
>>> 'forty'.isdigit()
False
>>> ''.isdigit()
False
>>> 'hello'.isdigit()
False
>>> x = '10'
>>> x.isdigit()
True
```
Har ikkala `move[0].isdigit()` va `move[1].isdigit()` butun holat `True` bo'lishi uchun `True` bo'lishi kerak. 99-satr holatining yakuniy qismi taxtada x va y-koordinatalarining mavjudligini tekshirish uchun `isOnBoard()` funktsiyasini chaqiradi.
Agar butun shart `True` bo'lsa, 100-qator bu harakatning `previousMoves` ro'yxatida mavjudligini tekshiradi. Agar shunday bo'lsa, 102-qatorning `continue` buyrug'i ijroning 92-qatordagi `while` tsiklining boshlanishiga qaytishiga olib keladi va keyin o'yinchining harakatini yana so'raydi. Agar shunday bo'lmasa, 103-qatorda x va y koordinatalarining ikki *integer* ro'yxati beriladi.

# O'yinchi uchun o'yin ko'rsatmalarini chop etish
`showInstructions()` funktsiyasi - bu ko'p satrli satrlarni bosib chiqaradigan `print()` chaqiruvlarining juftligi:
```python
def showInstructions():
    print('''Ko'rsatmalar:
Siz xazina qidiradigan kemaning Simon kapitansiz. Sizning hozirgi vazifangiz

--kesik--

Davom ettirish uchun Enter tugmasini bosing...''')
    input()
```

`input()` funktsiyasi o'yinchiga keyingi qatorni bosib chiqarishdan oldin *Enter* tugmasini bosish imkoniyatini beradi. Buning sababi shundaki, IDLE oynasi bir vaqtning o'zida shunchaki juda ko'p matnni ko'rsatishi mumkin va biz matnning boshini o'qish uchun o'yinchi yuqoriga o'girilishini xohlamaymiz. Foydalanuvchi *Enter* tugmachasini bosgandan so'ng, funktsiya funktsiyani chaqirgan qatorga qaytadi.

# O'yin davri
Endi biz o'yinimiz chaqiradigan barcha funktsiyalarni kiritdik, keling, o'yinning asosiy qismiga kiraylik. Dasturni ishga tushirgandan so'ng o'yinchi ko'radigan birinchi narsa - bu 159-qator bilan bosilgan o'yin sarlavhasi. Bu dasturning asosiy qismidir, u o'yinchi ko'rsatmalarini berish va keyin o'yin foydalanadigan o'zgaruvchilarni sozlash bilan boshlanadi.

```python
print('S O N A R !')
print()
print('Ko\'rsatmalarni ko\'rishni xohlaysizmi? (ha yoki yo\'q)')
if input().lower().startswith('h'):
    showInstructions()

while True:
    # Game setup
    sonarDevices = 20
    theBoard = getNewBoard()
    theChests = getRandomChests(3)
    drawBoard(theBoard)
    previousMoves = []
```
`input().Lower().startwith('h')` iborasi o'yinchiga ko'rsatmalarni so'rashga imkon beradi va agar o'yinchi "h" yoki "H" bilan boshlanadigan satrga kirsa, u `True` qiymatiga to'g'ri keladi. Masalan:

    illustration here

Agar bu shart `True` bo'lsa, 163-qatorda `showInstructions()` chaqiriladi. Aks holda, o'yin boshlanadi.
167 dan 171 gacha bo'lgan qatorlarda bir nechta o'zgaruvchilar o'rnatildi; bular 13-1-jadvalda tasvirlangan.

    table here
    
Yaqinda biz ushbu o'zgaruvchilardan foydalanamiz, shuning uchun davom etishdan oldin ularning tavsiflarini ko'rib chiqing!

#### O'yinchi uchun o'yin holatini ko'rsatish
173-chi qatorda, agar o'yinchida sonar moslamalari qolgan bo'lsa va ularga qancha sonar qurilmalar va xazina qutilari qolganligi haqida xabar yozib bersa, ishlaydi.
```python
    while sonarDevices > 0:
        # Sonar moslamasi va sandiq holatini ko'rsating.
        print('Sizda %s sonar moslama(lar) qoldi. %s xazina quti(lar) qoldi.' % (sonarDevices, len(theChests)))
```

Qancha qurilma qolganligini chop etgandan so'ng, `while` tsikli bajarilishini davom ettiradi.

#### Aktyorning harakatini boshqarish
177 qator hali ham `while` tsiklining bir qismidir va x va y o'zgaruvchilarni `enterPlayerMove()` tomonidan qaytarilgan o'yinchining harakat koordinatalarini ifodalovchi ikkita element ro'yxatiga tayinlash uchun bir nechta topshiriqlardan foydalanadi. `enterPlayerMove()` kodi o'yinchi oldingi harakatni takrorlamasligini ta'minlashi uchun biz avvalgi harakatlarga o'tamiz.
```python
        x, y = enterPlayerMove(previousMoves)
        previousMoves.append([x, y]) # Sonar qurilmalari yangilanishi uchun biz barcha harakatlarni kuzatib borishimiz kerak.

        moveResult = makeMove(theBoard, theChests, x, y)
        if moveResult == False:
            continue
```
Keyin x va y o'zgaruvchilar `previousMoves` ro'yxatining oxiriga qo'shiladi. `previousMoves` o'zgaruvchisi bu o'yindagi har bir harakatning `x` va `y` koordinatalari ro'yxati. Ushbu ro'yxat keyinchalik dasturda 177 va 186 satrlarda ishlatiladi.
`x`, `y`, `theBoard` va `theChests` o'zgaruvchilari barchasi 180-satrdagi `makeMove()` funktsiyasiga uzatiladi. Ushbu funktsiya sonar qurilmani taxtaga joylashtirish uchun zarur modifikatsiyalarni amalga oshiradi.

Agar `makeMove()` `False`ni qaytarsa, unda unga berilgan x va y qiymatlarida muammo yuzaga keladi. `continue` operatori ijrochini yana x va y-koordinatalarini so'rash uchun 173-satrda `while` tsiklining boshiga yuboradi.

#### Cho'kib ketgan xazina sandig'ini topish
Agar `makeMove()` `False`ni qaytarmasa, u ushbu harakat natijalarining qatorini qaytaradi. Agar bu satr "Siz cho'kib ketgan xazina sandig'ini topdingiz!" Bo'lsa, unda taxtadagi barcha sonar qurilmalar keyingi eng yaqin xazina sandig'ini aniqlash uchun yangilanishi kerak:
```python
        else:
            if moveResult == 'Siz cho\'kib ketgan xazina sandig\'ini topdingiz!':
                # Hozirda xaritada mavjud barcha sonar qurilmalarini yangilaymiz.
                for x, y in previousMoves:
                    makeMove(theBoard, theChests, x, y)
            drawBoard(theBoard)
            print(moveResult)
```
Barcha sonar qurilmalarining x va y-koordinatalari `previousMoves`da joylashgan. 186-satrda `previousMoves` ustidan takrorlash orqali siz ushbu x va y-koordinatalarning barchasini yana `makeMove()` funktsiyasiga uzatishingiz mumkin. Dastur bu yerda hech qanday yangi matnni chop etmasligi sababli, o'yinchi dastur avvalgi harakatlarning barchasini takrorlashini tushunmaydi. Taxta o'zini yangilaydi.

#### O'yinchining g'alaba qozonganligini tekshirish
`makeMove()` funktsiyasi siz yuborgan `theChests` ro'yxatini o'zgartirishini unutmang. `theChests` ro'yxat bo'lganligi sababli, funktsiya ichida unga kiritilgan har qanday o'zgarishlar bajarilish funktsiyadan qaytgandan keyin ham saqlanib qoladi. `makeMove()` funktsiyasi xazina sandiqlari topilayotganda narsalarni `chests`dan olib tashlaydi, shuning uchun oxir-oqibat (agar o'yinchi to'g'ri taxmin qilsa) barcha xazinalar olib tashlanadi. (Esingizda bo'lsa, "xazina sandig'i" deganda biz `theChests` ro'yxatidagi x va y koordinatalarining ikki elementli ro'yxatini nazarda tutamiz.)
```python
        if len(theChests) == 0:
            print('Siz cho\'kib ketgan barcha xazina qutilarini topdingiz! Tabriklayman, yaxshi o\'yin bo\'ldi!')
            break
```
Barcha xazina sandiqlari taxtada topilib, `theChests`dan olib tashlanganida, `theChests` ro'yxatining uzunligi 0 ga teng bo'ladi. Bu sodir bo'lganda, kod o'yinchiga tabrik xabarini namoyish etadi va undan keyin `while` tsiklidan chiqib ketish uchun `break` bayonotini bajaradi. Keyin ijro 197-qatorga, `while` blokidan keyingi birinchi qatorga o'tadi.

#### O'yinchining yutqizganligini tekshirish
195-qator - bu 173-qatorda boshlangan `while` tsiklining so'nggi satri.
```python
        sonarDevices -= 1
```
Dastur `sonarDevices` o'zgaruvchisini kamaytiradi, chunki `o'yinchi` bitta sonar qurilmani ishlatgan. Agar o'yinchi xazina qutilarini sog'inishni davom ettirsa, natijada `sonarDevices` 0 ga kamayadi. Ushbu qatordan keyin ijro 173 qatorga ko'tariladi va u `while` holatining holatini qayta ko'rib chiqishi mumkin (bu `sonarDevices > 0`).
Agar `sonarDevices` 0 ga teng bo'lsa, u holda shart `False` bo'ladi va uning bajarilishi 197 qatoridagi `while` blokidan tashqarida davom etadi. Ammo shu vaqtgacha shart `True` bo'lib qoladi va o'yinchi taxminlarni davom ettirishi mumkin:

```python
    if sonarDevices == 0:
        print('Sonar qurilmalarimiz tugadi! Endi biz kemani aylantirib, xazina sandiqlari bilan')
        print('uyimiz tomon yo\'l olishimiz kerak! O\'yin tugadi.')
        print(' Qolgan sandiqlar bu yerda edi:')
        for x, y in theChests:
            print(' %s, %s' % (x, y))
```
197-qator - `while` tsiklining tashqarisidagi birinchi satr. Qatl qilish shu darajaga yetganda, o'yin tugaydi. Agar `sonarDevices` 0 ga teng bo'lsa, bilasizki, o'yinchi barcha sonlarni topishdan oldin sonar qurilmalari tugagan va yo'qolgan.
198 dan 200 gacha bo'lgan chiziqlar o'yinchiga yutqazganligini aytadi. 201 chizig'idagi `for` loop `theChests`da qolgan xazina qutilaridan o'tadi va ularning joylashuvini namoyish etadi, shunda o'yinchi xazina sandiqlari qaerda turganini ko'rishi mumkin.

#### sys.exit() funktsiyasi bilan dasturni tugatish
Yutish yoki yutqazish, dastur o'yinchiga o'ynashni davom ettirish to'g'risida qaror qabul qilishga imkon beradi. Agar o'yinchi "ha" yoki "yo'q"ni kiritmasa yoki "y" harfi bilan boshlanmaydigan boshqa bir qatorni kiritsa, u holda `not input.lower().startswith("h")` bilan `True` va `sys.exit()` funktsiyasi bajariladi. Bu dasturni tugatilishiga olib keladi.
```python
    print('Qayta o\'ynashni xohlaysizmi? (ha yoki yo\'q)')
    if not input().lower().startswith('h'):
        sys.exit()
```
Aks holda, ijro 165 qatoridagi `while` tsiklining boshiga o'tadi va yangi o'yin boshlanadi.

# Xulosa
Bizning "Krestik Nolik" o'yinimiz qanday qilib "Krestik Nolik" taxtasidagi bo'shliqlarni 1 dan 9 gacha raqamlashini eslaysizmi? Bunday koordinatalar tizimi 10 dan kam bo'shliqli taxta uchun yaxshi bo'lishi mumkin edi. Ammo "Sonar Xazinalar Ovi" taxtasida 900 ta bo'sh joy mavjud! 12-bobda biz bilgan dekartian koordinatalar tizimi haqiqatan ham bu bo'shliqlarni boshqariladigan qiladi, ayniqsa, o'yinimiz taxtada ikkita nuqta orasidagi masofani topishi kerak bo'lganda.
Dekart koordinatalari tizimidan foydalanadigan o'yinlardagi joylar ro'yxatlari ro'yxatida saqlanishi mumkin, unda birinchi indeks x koordinatasi, ikkinchi indeks esa y koordinatadir. Bu `[x][y]` taxtasi yordamida koordinataga kirishni osonlashtiradi.
Ushbu ma'lumotlar tuzilmalari (masalan, okean va xazina sandiqlari uchun ishlatiladigan narsalar) murakkab tushunchalarni ma'lumotlar sifatida ifodalashga imkon beradi va sizning o'yin dasturlaringiz asosan ushbu ma'lumotlar tuzilmalarini o'zgartirish bilan shug'ullanadi.
Keyingi bobda biz harflarni raqam sifatida namoyish etamiz. Matnni raqamlar sifatida ko'rsatish orqali biz ulardagi maxfiy xabarlarni shifrlash yoki parolini hal qilish bo'yicha matematik operatsiyalarni bajarishimiz mumkin.

