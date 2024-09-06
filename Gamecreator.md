# <center>BUDAPESTI KOMPLEX SZAKKÉPZÉSI CENTRUM WEISS MANFRÉD SZAKGIMNÁZIUMA, SZAKKÖZÉPISKOLÁJA ÉS KOLLÉGIUMA</center> 
<br></br>
<br></br>
# <center>GAMECREATOR</center>
<br></br>
<br></br>

Témavezető: <span style="text-align: center;">Készítette:</span>

Kovács László Béres-Osztermann Ádám

Szoftverfejlesztő OKJ esti tagozat
<center>
Budapest<br>
2018
</center>

## Tartalom


- Köszönetnyilvánítás
- 1. Bevezetés
- 2. A szöveges kalandjáték története Magyarországon
- 3. Felhasználói dokumentáció
   - 3.1. Hardware és Software igény
   - 3.2. Oldal elérése
   - 3.3. Lehetőségek regisztráció előtt és után
   - 3.4. Főoldal és tartalma
   - 3.5. Navigációs sáv és funkciók ismertetése
      - 3.5.1. A főoldal
      - 3.5.2. Útmutató a regisztrációhoz
      - 3.5.3. Útmutató a bejelentkezéshez
      - 3.5.4. Az újjáték létrehozása
      - 3.5.5. A játék szerkesztése
- 4. Fejlesztői dokumentáció
   - 4.1. Az adatbázis különböző táblái és azok mezői
      - 4.1.1. A user tábla
      - 4.1.2. A game tábla
      - 4.1.3. A story tábla
   - 4.2. A weboldalon használt változók
   - 4.3. Algoritmusok az oldalon
      - 4.3.1. Regisztráció
      - 4.3.2. Belépés
      - 4.3.3. Játék létrehozása
      - 4.3.4. Képek
      - 4.3.5. Adatbázis feltöltése
      - 4.3.6. A game editor felület
      - 4.3.7. A Profil felülete
   - 4.4. Tesztdokumentáció
   - 4.5. A programozásban nem jártas felhasználó véleménye
- 5. Az oldal design-ja
- 6. Összefoglalás
   - 6.1. A szakdolgozat célja
   - 6.2. Megvalósítása
   - 6.3. Célok, amelyeket nem sikerült teljesíteni
   - 6.4. Fejlesztési lehetőségek
- 7. Irodalomjegyzék


## Köszönetnyilvánítás

Ezúton szeretnék köszönetet mondani osztályfőnökömnek és témavezetőmnek, Kovács
Lászlónak, Kiss Mazák Csilla tanárnőnek, és Vonyigás István tanár úrnak, akik
szakértelmükkel, hasznos magyarázataikkal és a konzultációk során biztosított létfontosságú
tanácsaikkal hatalmas segítséget nyújtottak szakdolgozatom elkészüléséhez. Hálával tartozom
továbbá kollegáimnak és szaktársaimnak, akik nélkül ez a szakdolgozat nem jöhetett volna
létre. Köszönöm nekik, hogy tanulmányaim során türelemmel és megértéssel támogattak, és
minden helyzetben mellettem álltak.

Külön köszönöm páromnak Áginak, hogy iskolai éveim során végtelen kitartással és
szeretettel támogatta céljaim elérését, és nélkülözhetetlen tanácsaival valamint segítségével
hozzájárult e dolgozat megírásához.

Köszönöm mindenkinek!


## 1. Bevezetés

A 2018-as záróvizsgám beadandójához témának egy egyéni szöveg alapú játék készítő oldalt
választottam, melynek a fő célja nem egy játék elkészítése, hanem lehetőség a felhasználók
számára, hogy létrehozzák a sajátjukat. A történetet megadva a különböző opciók és
választások más és más eredménnyel végződhetnek, így a játék nem egy fix befejezéssel
rendelkezik, hanem több alternatív véges kimenetele is lehet.

A választásom azért esett erre a projektre mert már korábban is próbáltam hasonló játékokat,
amelyben nagyon élveztem a lehetőségeket, hogy kifejezzem a saját kreativitásomat. továbbá
a másik motivációm az volt, hogy egyik általam nézett sorozatban a főszereplő hasonló
játékkal játszott, ebből merítettem ihletet. Lehetőségem nyílt arra, hogy ne egy megalkotott
képvilágot lássak, hanem egy sajátot képzeljek el a cselekményhez. A játék során inspirálónak
éreztem, hogy bármilyen lehetőséget választhatok, a cselekmény abban az irányban halad
tovább.

Továbbá habár most már rendelkezem programozási ismeretekkel, sokan nem értenek hozzá,
akiknek emiatt a hasonló játékok készítése elérhetetlen. Régebben magam is vágytam rá, ezért
választottam a mindenki számára könnyen elérhető platformot, a weboldalt.

Az elméleti jelentősége az volt, hogy ne csak a létező játékokkal lehessen játszani, hanem ha
valaki indíttatást érez, hogy létrehozza a saját játékát, találjon hozzá egy oldalt, amelynek
felépítése és kezelése lényegesen könnyebb és egyszerűbb, mint az interneten található
oldalak nagy része.


A program tervezése során a webfejlesztési ismereteimet, amíg a készítése során a PHP-ban,
szerzett programozási tapasztalataimat, továbbá a regisztrációhoz és a mentett játék tárolására
mySQL adatbázis-kezelési ismereteimet tudtam felhasználni.

- A program fejlesztése Atom 1.25 verziójú szövegszerkesztőjében, PHP, HTML és
CSS nyelveken, Bootstrap 4 keretrendszer segítségével történt.
- AppServ 8.6.0 a lokális környezet kialakításhoz.
- A DB Designer 4 nevű programmal terveztem meg, és generáltam az adatbázist.
- Az adatok tárolása MySQL szerverben történik.

## 2. A szöveges kalandjáték története Magyarországon

Magyarországon a Commodore 64-os számítógépre Rátkai István négy szöveges
kalandjátékkal írta be magát a játéktörténelembe: az 1987-ben megjelent Időrégésszel, amit
egy évvel később követett a Bosszú, 1989-ben pedig az Új Vadnyugat első és második része.

Ezekben az volt az újdonság, hogy habár grafikailag és zenei aláfestéssel nem érték utol a
nyugati programokat, magyar nyelven lehetett őket játszani, remek történetvezetése és fejtörői
voltak, így igen hamar a hazai közönség kedvencévé vált. Programozás szempontjából pedig a
begépelt szövegértelmező rész volt az eltérő, ige-főnév-másodikfőnév sémával dolgozott.

1990 - ben még ígérte volt további folytatásra, azonban ezeket érdeklődés és idő hiányában.
Rátkai már nem fejezte be. A vizuális játékok megjelenése óta a műfaj hanyatlóban volt,
azonban manapság újra divatba jött. Ezért is esett erre a választásom.


## 3. Felhasználói dokumentáció

A weboldal célja egy olyan szöveg alapú játékszerkesztő, ahol a saját történetet hozhatunk
létre, több választási lehetőséggel és több végkimenetellel.

Lehetőségeink a következők:


- Új történet létrehozása
- Képfeltöltés
- Végtelen számú lépéslehetőség
- Játék kipróbálása
- Mások játékainak megtekintése

### 3.1. Hardware és Software igény

Az oldal használatához egy internet kapcsolattal rendelkező okostelefonra vagy egy
számítógépre, és egy böngészőre lesz szükség, (mint a Firefox, a Mozilla, az Opera, a Safari,
a Google Chrome stb.) Az oldal magától alkalmazkodik a képernyő méretéhez,emiatt nem
szükséges a képernyőbeállításokat módosítani, mert a weblap a megjelenítő eszköz méretéhez
igazodik.

### 3.2. Oldal elérése

Eléréshez a (a fent említett és korábban már telepített böngésző) URL sávjába kell a
következőt beírni:

## <center><a href="http://gamecreator.nhely.hu/">http://gamecreator.nhely.hu/</a></center>


### 3.3. Lehetőségek regisztráció előtt és után

A weboldalon regisztráció nélkül is van lehetőség a következőre:


- A főoldalon lévő játékok megtekintése
- Játékok kipróbálása

A felhasználók számára a regisztráció után a következő funkciók vállnak elérhetővé:


- Bejelentkezés
- Képfeltöltés
- Új játék létrehozása
- Saját játékok megtekintése
- Saját játékok későbbi szerkesztése

### 3.4. Főoldal és tartalma


### 3.5. Navigációs sáv és funkciók ismertetése

#### 3.5.1. A főoldal

A navigációs sávon található „**home**” gomb minden esetben a főoldalra visz vissza.Ennek az
oldalnak a lényegi tartalma, a felhasználók által létrehozott játékok gyűjteménye ahol a
hozzájuk feltöltött képek és leírások is láthatóak. Itt az „**Play**” gombra kattintva lehetősége
van kipróbálni a játékokat akár regisztráció nélkül is. Azonban más játékát szerkeszteni nem
lehet csak a sajátunkat.

#### 3.5.2. Útmutató a regisztrációhoz

Az oldal betöltődésekor láthatunk egy navigációs sávot három menüponttal (Home, Create
Your Own, My Profile), illetve a jobb oldalon regisztráció és a bejelentkezési lehetőségeket.

Az oldal fő funkciójának eléréséhez a legfontosabb lépés a regisztráció, csak ez után válik
elérhetővé a játék létrehozása. A „**Register**” gomb lehetőséget ad az oldalhoz tartozó
regisztrációs menü kitöltésére. Meg kell adni egy még nem létező felhasználó nevet, egy


érvényes email címet és egy jelszót. Mivel az oldal nem kívánja megkeresni a felhasználóit,
így sem hírlevélre való feliratkozás sem lakcím megadása nem elérhető. Ezzel a felület
egyszerű és gyors elérést biztosít. Hiba esetén különböző tájékoztató üzenetek jelennek meg a
képernyőn. Sikeres regisztráció esetén egy ablak ugrik elő, amely megerősíti a regisztrációt,
nem kell visszaigazoló email-re várni, vagy azon keresztül megerősíteni az email címet. Ezen
a felugró ablakon található Ok gomb megnyomásával visszatér a főoldalra, itt már be is lehet
jelentkezni a felhasználói fiókba.

#### 3.5.3. Útmutató a bejelentkezéshez

A „<span style="color: blue;">**Log in**</span>” gomb lenyomása után lehetősége van bejelentkezni a weboldalra, a regisztrált
email címe és jelszava helyes megadása után. Hiba esetén egy figyelmeztető ablak jelenik
meg a képernyőn.


Sikeres bejelentkezés esetén visszatér a főoldalra és egy piros „<span style="color: blue;">**Log out**</span>” feliratú gomb látható
a navigációs sáv jobb szélén mellyel ki lehet jelentkezi a felhasználói fiókból.

A „<span style="color: blue;">**Create Your Own**</span>” menüpont mindaddig nem használható, amíg a felhasználó

regisztráció után be nem jelentkezik az oldalra. Ha ez nem történt meg hibaüzenet jelzi: „You
must be logged in!” az ez alatt lévő Ok-gombra kattintva visszatér a főoldalra, ahol be tud
jelentkezni, majd ez után ismét rákattintva, van lehetőség elérni a szerkesztő oldalt.

A bejelentkezés után elérhetővé válik a „<span style="color: blue;">My Profile</span>” gomb, amely megnyitásakor láthatjuk a
saját adatainkat és a korában már elkészített játékainkat.


#### 3.5.4. Az újjáték létrehozása

Bejelentkezés után elérhetővé vált „<span style="color: blue;">**Create Your Own**</span>” menüpont ad lehetőséget a saját
játékunk elkészítésre.

Az oldal betöltődése utáni lehetőségek:


- A legfelső „name” beviteli mezőben lehet megadni a játék címét. Ez majd a saját
profilón és a főoldalon lesz fontos, a játékok megkülönböztetésében.
- A középen található Cover Art lesz a játékhoz tartozó „fedőlap”. A „Choose File”
gombra kattintva lehetőség adódik egy képet feltölteni a játékához, ami majd
szintén a főképernyőn és a profilon fogmegjelenni, a játékok listázásánál. Fontos
hogy csak ’*.jpg’ formátumú képet lehet feltölteni! A kép feltöltésénél ügyeljen a
kép méretére ugyanis a program nagyobb méret esetén automatikusan kivág belőle
egy 300 x 300 pixel méretű részt. Így javasolt egy ilyen méretű kép feltöltése. De
ez az oldalon fel van tüntetve.


- „Description” mező kitöltésénél lehet megadni a játék rövid (2-3 mondat)
jellemzését, ami meg fog jelenni a kész játéknál a kép alatt, ez alapján fogják kipróbálni a játékot az oldal látogatói.
- Ha kitöltöttük az adatokat, utána a „<span style="color: blue;">**Start**</span>” megnyomásakor figyelmeztető
üzenet jelzi a sikeres mentést, az eddig beírt adatok automatikusan
elmentődnek és megjelenik a tényleges szerkesztő felületünk, ahol el tudjuk
kezdeni megírni a játékunkat.

#### 3.5.5. A játék szerkesztése

Az alapadatok megadása és a kép feltöltése után felugrott oldalon lehet elkezdeni a történek
lépéseinek beírását. Ajánlatos előre tudni a történetet, és hogy melyik történt résznek mennyi
opciója lesz.

Érdemes egy bevezető szöveggel kezdeni, amiben a helyzet leírást adunk meg, amellyel
felvezetjük a játék hangulatát. Ez a szöveg lehet bármilyen hosszú, a példán látható mondat
segítségül szolgál.


A későbbi értelmezhetőség kedvért érdemes egy kérdéssel zárni a bevezetést mely a játékos
cselekményére kérdez rá.

Fontos információ, a játék kezdeténél illetve azoknál a történet daraboknál ahol több lépés
lesz az option mezőt mindenképpen hagyjuk üresen, mert az első opciót amit adunk nem
fogjuk tudni tovább fűzni, kivéve akkor a első lépésnek csak egy választható cselekménye
van, ekkor nyugodtan töltsük ki a mezőt.

A „<span style="color: blue;">**Save**</span>” gomb megnyomásakor felugrik a játék lehetőségeinek oldala. Ez az oldal ahol a
cselekmény követhető, lépésről, lépésre. A mentés után erre az oldalra a „<span style="color: blue;">**Countinue Story**</span>”
gombbal lehet visszajutni, és szerkeszteni a történetet.


A következő lépés hozzáadásához az „<span style="color: blue;">**add option**</span>” gombot kell megnyomni, ahol az oldal
visszaugrik az előző szerkesztő képernyőre. Itt újabb lépést és kimenetelt tudunk hozzáadni.
Mindig arra az „<span style="color: blue;">**add option**</span>” –re kattintsunk, amelyik szöveghez plusz lépést akarunk adni.

A példával élve az erőben három út van, tehát az erdő melletti „<span style="color: blue;">**add option**</span>” –re kattintva
adhatjuk meg a lehetőségeket. Az itt fölugró oldalon a story részt hagyjuk üresen, és csak
opciót adunk meg. Hiszen a történetrész már adott lehetőségeket adunk hozzá.


Az „opcióhoz adott opció” apró nyilakkal fog a szöveg elején megjelenni, ezzel tudjuk
nyomon követni, hogy az adott lehetőség melyik törtnet darabhoz tartozik. Tehát ha egy nyilat
látunk, az azt jelenti, hogy az elő story részhez tartozó opció, de egy nyilat több lehetőség
előtt is láthatunk.

A képen látható az erőben állsz, részhez tartozik az előre, jobbra és balra, míg az előréhez
tartozik, a látsz magad előtt egy házat- hoz tartozik a bekopogsz vagy elmész mellette sor.

Az megadható utak száma végtelen, a történet bármerre mehet, csak a képzelet szab neki
határt.


## 4. Fejlesztői dokumentáció

### 4.1. Az adatbázis különböző táblái és azok mezői


Az oldalra beérkező adatok tárolására a gamecreator nevű adatbázis nyújt lehetőséget. Az
adatok külön általam létrehozott feldolgozó programokon keresztül jutnak ebbe az
adatbázisba.

#### 4.1.1. A user tábla


- Elsősorban a felhasználók adatainak tárolására szolgál. Az első mezője az user_id, ez
egy szám típusú mező. Ez a tábla elsődleges kulcsa, automatikusan növekszik és
generálódik, ahányszor egy új felhasználó regisztrál. Ebből a számból akár
megállapíthatjuk a regisztrált felhasználók számát. Ez a mező azért fontos, mert a
beléptetés és a játék és a saját adatok lekérdezése során tudjuk a felhasználót
beazonosítani.
- A második mező user_name varchar mező ezért szöveget és számot is tartalmazhat. Ez
egy másodlagos megkülönböztetése a felhasználónak regisztrációnál kötelező
megadni, mely felhasználó közelibbé teszi az oldalt.
- A harmadik mező a user_password ami szintén egy vegyes karakterű mező (számot és
szöveget is tartalmazhat). Itt nem adtam meg sem karakteri hosszbeli
meghatározottságot, ugyanis az oldal nem tartalmaz bizalmas adatokat. Így a feltörés
veszélye sem áll fent. A felhasználó bármit megadhat jelszóként, annak egyeznie kell
a bejelentkezésnél használt jelszóval. Elfelejtett jelszó esetén új regisztráció
szükséges.
- A negyedik mező a user_email ami a felhasználói email címeket tartalmazza. Ez a
második adat, amire szükség van a bejelentkezésnél.
- Az ötödik mező a user_regdate ami a felhasználók regisztrációjának időpontját
tartalmazza. Automatikusan adódik hozzá a táblához.
- A user_status mező a felhasználók státuszát tárolja rövid szöveges típusban, adatai az
felhasználók megkülönböztetésére szolgál az oldalon, azonban egyenlőre még nincs
használatban.

#### 4.1.2. A game tábla

- Az első mezője az game_id, szintén egy szám típusú mező. Ez a tábla elsődleges
kulcsa, automatikusan növekszik és generálódik minden létrehozott játék után. Ez a
szám felhasználónként sem egyezik, hanem mint az user_id, minden játék egyedi
számot kap, mely nem egyezhet, így mindegyik játéknak van a nevén kívül egy
teljesen egyedi azonosítója.
- A második mezője az user_id ami idegen kulcsként funkcionál, ez alapján lehet
kapcsolatot kialakítani a két tábla között, illetve ez alapján lehet látni a profil
megtekintésekor a saját létrehozott játékokat.
- A harmadik mező a game_name ami a játék felhasználó által megadott nevét
tartalmazza. Ezt a nevet a játék szerkesztése első lépéseinél lehet megadni. Ez
megjelenik a játékok ki listázásakor.
- A harmadik mező a game_picture ami a játék felhasználó által feltöltött képet
tartalmazza. A képek mérete 300x300 pixel. Ez szintén látszódik a játékok
listázásakor.
- A game_info mező tartalmazza a játék leírását. Ez egy hosszabb tartalmú szöveg ahol
meg tudjuk adni a játék leírását. Ez csak egy megjelenő információ lesz a felhasználó
számára. Nem használjuk lekérdezéshez vagy összekapcsoláshoz.

#### 4.1.3. A story tábla



- Első mezőként tartalmazza a játék azonosító kulcsát. Ez szintén egy kapcsolatként
szolgál a táblák között, és később a szerkesztésnél is nagy szerepet játszik. A jelen
mező hozza létre a kapcsolatot a szerkesztett történet mezőjét a game táblában
található adatokkal.
- A stoy_idaz új létrehozott játéknál 0-val indul, és minden elmentett történet résszel,
eggyel növekszik. Ez a mező szintén egy azonosítóként szolgál, de itt már nem a
történetet „számozzuk” csak a történet részeket.
- A story_line mezőalkalmas hosszabb szövegrészek tárolására, maga a történet ezeken
a mezőkön keresztül bontakozik ki, ennek beírására a „Story” beíró mező alkalmas a
felhasználói felületen. A story_id alapján ezt a mező fog megjelenni a játék
lejátszásakor, és ezekhez a mezőkhöz fognak az opciók kapcsolódni.
- A story_option ugyanúgy longtext mező melyek a történet haladására adott reakció
lesz, melyet a szerkesztő a járték megírásakor adhat meg minden történet részhez.
Ebből azonban nem egy tartozhat minden történet részhez, hanem szabadon
választható és szerkeszthető számú.
- A parent_id a story_id egy szám alapú változata. Megjelenítésnél ez a szám segít az
adott történetrészhez, egy szinten lévő opciók listázásához. Tehát a story_line-hoz
megadott két-három opció ugyan azon a szinten fog megjelenni.

### 4.2. A weboldalon használt változók

Az weblapon használt$_SESSION[uid] változó az oldalra való belépéstől az oldalról való
kijelentkezésig él. Minden egyes regisztrációnál generálódik. Ez segít meghatározni, hogy egy
felhasználó be van-e jelentkezve az oldalra.

Az oldalon továbbá $_GET[] illetve $_POST[] változókat is használunk. A $_GET[]
változókat az oldal paraméterezésére, míg a $_POST[] változókat a feldolgozó programokhoz


való adatok eljuttatására használjuk fel.A feldolgozó programok ezeket az adatokat küldik
tovább az adatbázisba illetve amennyiben feltölteni kívánt képről van szó a képeknek
létrehozott mappába.

### 4.3. Algoritmusok az oldalon

#### 4.3.1. Regisztráció

Feladata a felhasználó által megadott email cím, név és jelszó hozzáadása az adatbázishoz és
majd lehetőséget biztosítson a bejelentkezésre.A regisztráció algoritmusa lépésenként:


- A felhasználó kitölti mind a három kötelezően kitöltendő mezőt. Ha valami üresen
maradt, akkor azt az oldal hibaüzenettel jelzi.
- A megadott email cím formátumának ellenőrzése.
- A mezők kitöltése után a „<span style="color: blue;">**Register**</span>” gomb lenyomásával a megadott adatok
tárolódnak az adatbázisban. A folyamat sikerességét felugró ablakban lévő köszönő
üzenet igazolja.

#### 4.3.2. Belépés

A célja, hogy a felhasználó biztonságosan be tudjon lépni az oldalra a regisztrációt követően
és ezt követően a saját nevében tudjon játékszerkesztést kezdeményezni.


- A felhasználó megadja a regisztrációnál használt email címét és jelszavát. Ha valami
üresen maradt, vagy hibásan lett beírva azt hibaüzenettel jelzi.
- A beírt email cím ellenőrzése. Az előbbi fejezetben említett $_POST[useremail]
összehasonlítása az adatbázis user táblájának az user_email mezőjével.
- A jelszó ellenőrzése szintén az adatbázisban tárolt adat összehasonlításával történik.
Abban az esetben, ha a beléptetés sikeresen zárult, akkor az oldal frissül a főoldalra,
ahol a navigációs sáv jobb sarkában látható a „<span style="color: blue;">**LogOut**</span>” gomb.


#### 4.3.3. Játék létrehozása

Ebben a menüpontban többféle algoritmust használunk mind a kép feltöltéséhez,
átméretezéséhez, és az adatbázisból való lekérdezésekhez, amiket a későbbiek során
részletesebben is kifejtünk. A bejelentkezést követően aktívvá vált menüpontunk segítségével
meg tudjuk nyitni a szerkesztőoldalt.


- Első lépésnél ki kell tölteni mindkét mezőt, és az upload gomb segítségével fel kell
tölteni egy képet. A start feliratú submit gomb lenyomásakor két algoritmus, a kép
átméretezése és a bevitt adatok adatbázisba írása fog lefutni.

#### 4.3.4. Képek

A funkciókat az általam létrehozott picuploadandresize.php file látja el. Célja, hogy minden
egyes felhasználó jóvoltából feltöltött képet egy maximális 300x300pixel nagyságú képre
maximalizáljunk.


- A $_FILES[gamepicture] nevű változó tartalmazza a kiválasztott kép adatait.
Bevezetünk egy $v nevű változót, ami az angol abc betűit és számokat tartalmaz 0- 9 -
ig, majd ezekből egy karakter értéket kap véletlenszerűen (rand() függvény)képek
közti azonos név elkerülése végett.
- A kép feltöltése move_uploaded_file() segítségével, a gyökérkönyvtárba
automatikusan létrehozott picturesmappába. A file nevének a végére hozzáfűzzük a $v
véletlenszerűen generált karakter értékét.
- Ha a kép típusa nem felel meg az if feltételben megadott ’.jpg’ –nek akkor törlésre
kerül az unlink() parancs használatával, amit hibaüzenet kísér.
- Amennyiben a fent említett feltétel teljesül, de kisebb, mint 300x300 egy hibaüzenet
kíséretében törlésre kerül.
- Következő lépésekben a kép méretét vizsgáljuk és vágjuk le a kívánt méretre.



- Mindezek végeztével az átméretezett képünk bekerül a harmadik pontban létrehozott
mappába, file nevének a végén egy random karakterrel.

#### 4.3.5. Adatbázis feltöltése

Ez az algoritmus fut le másodszor mert már tartalmaznia kell az átméretezett kép adatait a
megjelenítési hibák kizárása végett. Ennek a funkcióját a gameform_ir.php nevű file látja el


- Kezdésként egy feltételnek kell megfelelnie ahol a $_POST változóként beérkező
adatok tartalmát vizsgáljuk. Ahhoz hogy a feltétel teljesüljön, a gamename és a
gameinfo nem lehet üres. Felugró ablakban hibaüzenetet kapunk ha mégis.
- Következő lépésként kapcsolódunk az adatbázisunkhoz a mysqli_connect()
segítségével, és egy mysqli_query() fügvénnyel indítjuk az adatbázisba game táblájába
való beillesztést.
- Itt eltároljuk a tábla megfelelő mezőibe a $_SESSION[uid]-t, játék nevét, a képet és a
rövid leírást.



- Amennyiben a folyamat sikeresen zárult egy előugró ablak tájékoztat minket a mentés
sikerességéről.
- Az oldalról való továbblépés automatikusan történik a szerkesztőfelületre. Ezért a
következő javascript funkció a felelős:
*parent.location.href='index.php?p=editor&game_id=". mysqli_insert_id($gcdb).
"&parent_id=0'*
paraméterként eltárolja a játék azonosítóját és a parent_id értékét beállítja 0 ra.

#### 4.3.6. A game editor felület

Ezen az oldalon tudjuk a korábban elmentett játékot lényegi információkkal feltölteni. Az
adatok tárolására a story táblát használjuk. Két input mezőnk található a felületen, ami a
felhasználó számára is látható, ezen felül két darab hidden input mező van elhelyezve, ami az
előbbi adatbázisba való íráskor megadott paraméterek tárolására és továbbítására szolgál.


- Miután kitöltöttük a mezőket, (mindig az épp megfelelőt, story vagy option) a „<span style="color: blue;">**Save**</span>”
gomb aktiválásával indítjuk el a programunkat. Az előző oldalról paraméterként
beérkezett adatok eltárolódnak a hidden input mezőkben. ($_GET[game_id] és
$_GET[parent_id] ). Az oldalról való továbblépést egy javascript funkció intézi.


- A submit után egy általam megírt funkció, ami egy rekurzív lekérdezést és kiírást
tartalmaz,és fut le, aminek a feltételében az adatbázisunk game_id és parant_id celláit
hasonlítjuk a $_GET ként továbbadott változók értékeivel.



- A fenti példában jól látszik, hogy a függvény annyiszor fog lefutni, ahány darab
story_id található az adatbázisban, ezáltal újabb cellákkal egészítve ki az adatbázist.
- Az átláthatóság érdekében egy „>” –jel adódik hozzá a kilistázáshoz, ami alapján,
nyomon tudjuk követni, hogy épp melyik ’szinten’ járunk.
- A ciklus utolsó soraiban található <span style="color: blue;">add option</span>link paraméterekként felveszi az épp
aktuális játék és storyazonosítót. a href="index.php?p=editor&game_id='.
$_GET[game_id]. '&parent_id='. $item[story_id]. '
- A fent bemutatott link tartalmazza a szerkesztő oldalt eléréséi útját.

#### 4.3.7. A Profil felülete

A kattintás után ezen a felületen kilistázódnak a felhasználó korábban mentett játékai amik
mind tartalmaznak egy játékazonosítót (game_id). A continue gombbal átveszi
játékazonosítót és a következő funkció fog lefutni, aminek a működését a korábbiakban már
ismertettem.


Összefoglalásként azt tudom mondani, hogy ez az algoritmus a program lelke. Feladataként
biztosítja, hogy az akár nem sorrendben megírt történet darabok és a hozzájuk tartozó n darab
választási lehetőség mindenképp a jó helyre kerüljön az adatbázison belül a megfelelő
azonosító számokkal ellátva.

### 4.4. Tesztdokumentáció

Az oldal a következő böngészőkben lett tesztelve:


- Google Chrome (Version 65.0.3325.181 (Official Build) (64-bit))
- Mozilla Firefox Develpoer Edition (Version 59.0b11 (64-bit))
- Microsoft Edge (Version 41.16299.371.0)

A következő képernyő felbontásokban:


- Iphone 5/se 320x568 pixel
- Nexus 5 360x640 pixel
- Iphone 6/7/8 375x667pixel
- Iphone 6/7/8 plus 414x736pixel
- Ipad Pro 1024x1366 pixel

Az oldal támogatja képernyő mind a portré és fektetett nézetét.


Figyelemreméltó eltérés nem volt tapasztalható köszönhetően annak, hogy a Bootstrap 4- es
keretrendszer a böngészők natív elemeit használja, amit a fejlesztőik maguk által megírt CSS
file módosít. Köszönhetően a rács rendszernek az oldalon @media parancsok segítségével
töréspontok lettek elhelyezve, ami az alábbi méretek esetén eltérő CSS formázásokat tesz
lehetővé:


- **Extra Small**<576px
- **Small**>= 576px
- **Medium**>= 768px
- **Large**>= 992px
- **Extra Large**>= 1200px

### 4.5. A programozásban nem jártas felhasználó véleménye

Az oldal felhasználók által való tesztelésében egy ember segítségét kértem, aki az
informatikai dolgokhoz kevésbé ért.

Az oldal megnyitásakor, könnyen zökkenőmentesen betöltött, nem voltak hiányzó képek, az
oldal alkalmazkodott az 1366*768 pixel méretű képernyőfelbontáshoz. A regisztráció után a
szerkesztő oldalra vezető link színe megváltozott és az oldal elérhető vált. A mezők
egyértelműek voltak, a képfeltöltés könnyedén ment. A játék szerkesztésével nem volt
akadály, könnyen új lehetőségeket tudott megadni, és mindent el is tudott menteni.

Meglátásai szerint a képek lehetnének nagyobbak, és másabb fajta átméretező algoritmust
lehetne használni.

## 5. Az oldal design-ja

Az oldal a mai kor elvárásainak megfelelő, a web felületletisztult, behatásoktól mentes
környezet mely áttekinthető és mindig a lényegi, a felhasználókat leginkább érdeklő
információkra fókuszál. Nincsenek színes vibráló felületek, képek vagy látványos elemek,


nélkülözi a „csilli-villi” hatásvadász elemeket és azt a minőséget és színvonalat tükrözni, amit
az oldal készítője és az oldal célja képvisel.

Ezzel az egyszerű megjelenéssel érhető el a legkönnyebben, hogy a felhasználó azt kapja,
amiért az oldalt betöltötte, a képzelet alapú játék örömét. Így nem egy előre megalkotott képi
világot tárunk a felhasználónak, sőt megadjuk a lehetőségét és „kényszerítjük” a
képzelőerejének fejlesztésére.

Az oldal reszponzivítása biztosítja, hogy a weboldal észleli milyen eszközről szeretnénk
megtekinteni azt, és az adott felbontáshoz igazítja a kialakítást, betűméreteket, képeket. Így a
honlap mindig jól használható, kényelmes és könnyen kezelhető.

A legszembetűnőbb részen, a fejlécben megtalálható minden lényegi oldal elérhetősége, a
főoldaltól kezdve a regisztráción át a kijelentkezésig. Ezek a gombok minden oldalon
elérhetőek és ugyan ott találhatóak.

## 6. Összefoglalás

### 6.1. A szakdolgozat célja

A szakdolgozatom célja egy olyan weboldal létrehozása volt ahol egy szabadon választott
történet hozható létre szerteágazó befejezésessel. Ezeket a játékokat megalkotni, és kipróbálni
is lehet.

### 6.2. Megvalósítása

Adatbázis megtervezése és létrehozása, majd ezt követően felületek elkészítése HTML-ben
egy alap CSS stílussal, ami alapján elkezdett körvonalazódni az oldal megjelenése.

Az első adatfeltöltéses felületek (form) elkészítése, ami a beléptetés, majd ezt követően a
regisztráció és az ehhez szükséges feldolgozó programok. Az adatfeltöltéses felületeken belül


érdemes lehet inkább a regisztrációval kezdeni, hogy az embernek lehetősége legyen már az
elején létrehozni egy profilt magának, és ne az adatbázist megnyitva kelljen manuálisan beírni
az adatokat.

A regisztrációt és a beléptetést követően a játék szerkesztéséhez használt (form) és annak
feldolgozó programja került elkészítésre.

Következett a játék alapadatait tartalmazó rész elkészítése, és az ahhoz tartozó feldolgozó
program megírása. Az első változatokban a (form) kitöltése és mentése után egy gomb
lenyomásával lehetett elérni a szerkesztőfelületet, amit későbbiekben egy automatikus
átirányításra módosítottam.

Ezután készült el a szerkesztő felületem (form) része, majd annak a feldolgozóprogramja,
valamint az opciók hozzáadásához szükséges program. Itt a leg átláthatóbb felületnek egy
táblázatot választottam, amiben nyomon lehet követni az egymásra épülő szinteket. A szintek
’eredetét’ a „>” jelek száma jelzi

A legutoljára elkészült nagy rész, a főoldalon megjelenítendő összes játék, kártyaszerű
listázása és a saját profil felület. Benne a felhasználó alap adatainak és játékainak kiírásához
szükséges programokkal, valamint a szerkesztés folytatásához szükséges programokkal.

### 6.3. Célok, amelyeket nem sikerült teljesíteni


- A játék elkészítésén kívül az egyik célom a játékok kipróbálását szerettem
volna elérni, hogy a felhasználók megnézhessek a mások által kitalált
történeteket.

- Megjelenítésnél szerettem volna elérni, hogy betöltődéskor a történet első
darabja jelenjen meg a felületen a hozzá tartozó n darab kattintható opcióval.


- Az opcióra való kattintás a többi azonos szinten lévő link inaktívvá változott
volna, és utána megjelent volna a hozzá tartozó rész a linkekkel együtt.


- A földal aljára egy lapozó sáv létrehozását, ami lehetővé tette volna az oldalon
megjelenítendő kártyák számának a maximalizálását és léptetését.

### 6.4. Fejlesztési lehetőségek


- A fent említett célok teljesítése és finomítása.

- Achievement rendszer:
Ez jutalomrendszer a felhasználóknak járó jutalmak a játékok létrehozása és teljesítése
után.


- Játékon belüli képek:
Mondjuk a terület térképe, ami jelölhetné a játékos által meglátogatott területeket.
Felugró képek a váratlan csavaroknál.


- Gyűjthető elemek:
Fegyverek, kulcsok életerő és varázslat visszatöltő italok.

- A főoldalon egy kategóriaválasztó, ami hatással lett volna a játékok rendezésénél.
Például ha Sci-Fi kategóriát választjuk ki, akkor csak a Sci-Fi témájú játékok
jelelnének meg az oldalon. Ezt a játék létrehozásánál lehetne beállítani, az előre
megadott kategóriákból.


- A már elkészült játékok pontozása és egy ranglista felállítása a pontok alapján.
- Fórum és hozzászólási lehetőség, ahol tanácsokat lehet megosztani egymással.


## 7. Irodalomjegyzék

Internetes irodalomjegyzék:


- INT01: http://textadventures.co.uk/forum/quest
- INT02: http://iddqd.blog.hu/2010/05/12/szerdai_retro_idoregesz
- INT03: https://stackoverflow.com/
- INT04: http://php.net/manual/en/index.php
- INT04: https://www.w3schools.com
- INT05: https://www.codecademy.com

Nyomtatott irodalomjegyzék:


- Laura Thomson · Luke Welling: PHP és MySQL webfejlesztőknek
- Lynn Beighley · Michael Morrison: Agyhullám: PHP & MySQL
- Wankyu Choi · Allan Kent · David Mercer · Dave W. Mercer · Steven D.
- Nowicki · Dan Squier PHP5 – Bevezetés a PHP5 programozásba


