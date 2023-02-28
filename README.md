# Adatbázis tervezés labor

## Felkészülés
A laborra felkészüléshez olvassa el a segédletet és próbáljon meg válaszolni az ellenőrző kérdésekre.

## Útmutató
Ebbe a könyvtárba készítse el az adatbázis tervezés labor megoldásait. A megoldásokat pull request formájában adja be a határidőre úgy, hogy reviewerként hozzárendeli a laborvezetőjét.
Figyeljen rá a labor elején, hogy hozzon létre egy új git branchet, mert a pull request létrehozásánal azt tudja majd a master ággal összehasonlítani.

Amennyiben a labor szöveges válaszokat kér kérdésekre, azokat a válaszokat ide írja be!

## 1. Közösen megoldandó feladatok

MySQL Workbench segítségével tervezze meg az alábbi specifikációknak megfelelő adatbázis sémákat:

1. Egy autókölcsönző vállalatnál nyilvántartják az autókategóriákat (azonosító, név,leírás) valamint a vállalatnál megtalálható autókat (azonosító, rendszám, márka, típus, szín). Egy autókategóriába, több autó is tartozhat, de nem feltétlenül tartozik hozzá autó, az autók mindenképp kategóriához tartoznak.
2. Egy tárgy nagyházijait (azonosító, tárgy, cím, leírás) szeretnénk nyilvántartani. Az adott tárgyból nem kötelező nagyházit készíteni, de egy diák (azonosító, név) több házit is készíthet. Egy nagyházit több diák is készíthet közösen.
3. Egy építőanyag kereskedés szeretné nyilvántartani az egyes termékeit, és azokból rendelkezésre álló raktárkészletet, valamint a megrendelőit. Egy megrendelőnek több telephelye is lehet, az egyes megrendeléseket a megadott telephelyre szállítják ki. Egy vevő egyszerre több terméket is megrendelhet. A termékek egy részét a kereskedés saját maga állítja elő a raktárban lévő termékekből. A rendszerben ezeket is nyilván szeretnénk tartani, valamint az ezek előállításához szükséges anyagmennyiségeket. Természetesen az előállított termékekből is rendelkezünk raktárkészlettel.

Hajtsa végre a saját adatbázisában az alábbi feladatokat:

1. Az előző példában megtervezett sémát generálja le a saját adatbázisában!
2. Vegye fel a termékek közé a téglát 500 db-os raktárkészlettel. Saját magát adja hozzá a vevőkhöz és rendeljen 40 db téglát.
3. Módosítsa a rendelését 50 db-ra.
4. Listázza ki azon termékeket, melyből több mint 200 db van raktáron!

## 2. Önállóan megoldandó feladatok

1. Tervezze meg az alábbi specifikáció alapján az adatbázis sémáját és hozza is létre a saját adatbázisában!

 Egy hallgatói információs rendszert szeretnénk fejleszteni, amelyben a következő adatokat szeretnénk nyilvántartani. Minden diákról nyilvántartjuk a törzsszámát (ez egy egyedi azonosító), a nevét, címét, telefonszámát, születési dátumát. Az oktatókról nyilvántartjuk a nevüket, valamint a tanszék kódját, ahol dolgoznak. A tárgyakról nyilvántartjuk a kódjukat, a nevüket, és egy rövid leírást. Nyilván kell tartanunk, hogy melyik tárgyat ki oktatja. Egy tárgyat több oktató is oktathat, és az is lehetséges, hogy egy adott tárgy nem indul ebben a félévben. Azt is tároljuk, hogy melyik diák milyen tárgyakra jár.


2. Töltse fel az Informatika 2 tárgy adatait (a tárgy leírását ne adja meg), majd vegye is fel a tárgyat!
3. Módosítsa a tárgy nevét Info 2-re!
4. Listázza ki a rendszerben található oktatókat!
5. Listázza ki a V-betűvel kezdődő oktatók nevét!
6. Jelentkezzen le a tárgyról!
7. Listázza ki azokat a tárgyakat, melynek nincs leírása!