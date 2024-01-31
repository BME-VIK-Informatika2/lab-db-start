# Adatbázis tervezés labor

## Felkészülés
A laborra felkészüléshez olvasd el a segédletet és próbálj meg válaszolni az ellenőrző kérdésekre.

## A labor teljesítése
Ebbe a könyvtárba készítsd el az **adatbázis tervezés labor** megoldásait. A labor teljesítéséhez a jelenléten felül az összes közös és önálló feladat elkészítésére szükség van. A gyakorlat két közösen megoldott feladattal indul, a további feladatot önállóan kell megoldani.

> [!IMPORTANT]
> A megoldásokat pull request formájában kell beadni a határidő előtt a Moodle alatt található **Git tudnivalók** leírásban található utasítások alapján.
> - Hozz létre egy **új branchet** `megoldas` néven, és ezen dolgozz.
> - Töltsd ki a `neptun.txt` fájlt a saját Neptun kódoddal.
> - Minden feladat után kommitolj, és használj értelmes kommit üzeneteket.
> - A feladat végeztével vagy a labor végén **pushold** a megoldásodat és hozz létre egy **pull requestet**.
> - Ellenőrizd a pull request tartalmát és rendeld hozzá a laborvezetődet **reviewernek**.

> [!CAUTION]
> A nem ilyen formában megadott megoldások nem lesznek értékelve!

## Előkészítés

A labor során szükségünk lesz egy adatbázis szerverre, ami tárolja az adatokat. Ehhez használhatjuk a már előző órán megismert XAMPP szoftvert.
- Nyissuk meg az XAMPP programot és indítsuk el a MySQL szervert.

> [!NOTE]
> Laborgépeken az XAMPP szoftvert a `C:/Tools/xampp/xampp-control.exe` állománnyal tudjuk elindítani.

A feladatokat a MySQL Workbench program segítségével fogjuk megoldani:

> [!CAUTION]
> Mindig kövessétek a laborvezető utasításait a szoftver használatával kapcsolatban, különben könnyen adatvesztés történhet!

- Nyisd meg a MySQl Workbench programot.
- A főoldalon a MySQL Connections alatt vegyél fel egy új kapcsolatot a `+` segítségével (ha még nincs):
    - A `Connection Name` legyen `localhost`, minden más maradhat alapértelmezett, és menjünk az `OK` gombra!
- Készíts egy új modelt a `File` > `New Model` menüpont kiválasztásával.
- Nevezd át az adatbázist a saját neptun kódodra.
- Navigálj el `Model` > `Model Options` > `MySQL` menübe, és vedd ki a pipát a `Use defaults from global settings` mellől, majd írd át a MySQL verziót `5.7`-re.

## 1. Adatbázis tervezés

MySQL Workbench segítségével tervezd meg az alábbi specifikációknak megfelelő adatbázis sémákat. Minden feladatnak hozz létre saját diagramot!

### I. Autókölcsönző

Egy autókölcsönző vállalatnál nyilvántartják az autókategóriákat (azonosító, név, leírás) valamint a vállalatnál megtalálható autókat (azonosító, rendszám, márka, típus, szín). Egy autókategóriába, több autó is tartozhat, de nem feltétlenül tartozik hozzá autó, az autók mindenképp kategóriához tartoznak.

### II. Házi feladatok

Egy tárgy nagyházijait (azonosító, tárgy, cím, leírás) szeretnénk nyilvántartani. Az adott tárgyból nem kötelező nagyházit készíteni, de egy diák (azonosító, név) több házit is készíthet. Egy nagyházit több diák is készíthet közösen.

### III. Építőanyag kereskedés

Egy építőanyag kereskedés szeretné nyilvántartani az egyes termékeit, és azokból rendelkezésre álló raktárkészletet, valamint a megrendelőit. Egy megrendelőnek több telephelye is lehet, az egyes megrendeléseket a megadott telephelyre szállítják ki. Egy vevő egyszerre több terméket is megrendelhet. A termékek egy részét a kereskedés saját maga állítja elő a raktárban lévő termékekből. A rendszerben ezeket is nyilván szeretnénk tartani, valamint az ezek előállításához szükséges anyagmennyiségeket. Természetesen az előállított termékekből is rendelkezünk raktárkészlettel.

### :bookmark_tabs: Beadandó

- [ ] Az elkészült sémákról készíts egy-egy képernyőképet.
- [ ] Mentsd el a képeket `schema-1.png`, `schema-2.png` és `schema-3.png` néven a repository gyökerébe.
- [ ] Kommitold a változtatásokat.

## 2. Adatbázis létrehozás és feltöltés

Ebben a feladatban az előző példában megtervezett építőanyag kereskedés tervét fogjuk használni:
- Generáld le a táblák sémáját a saját adatbázisodba.
- A generált sql fájlt mentsd el `schema-3.sql` néven!
- Készítsd el a következő feladatokhoz szükséges queryket a `query-3.sql` fájlba:
  - Vedd fel a termékek közé a téglát 500 db-os raktárkészlettel.
  - Add hozzá saját magadat a vevőkhöz és rendelj 40 db téglát.
  - Módosítsd a rendelést 50 db-ra.
  - Listázd ki azon termékeket, amelyekből több mint 200 db van raktáron.

### :bookmark_tabs: Beadandó

- [ ] Mentsd el a `schema-3.sql` és `query-3.sql` fájlokat a repository gyökerébe.
- [ ] Kommitold a változtatásokat.

## 3. Önállóan megoldandó feladat

Hozz létre egy új diagramot, és tervezd meg az alábbi specifikáció alapján az adatbázis sémáját.

### IV. Hallgatói információs rendszer

 Egy hallgatói információs rendszert szeretnénk fejleszteni, amelyben a következő adatokat szeretnénk nyilvántartani. Minden diákról nyilvántartjuk a törzsszámát (ez egy egyedi azonosító), a nevét, címét, telefonszámát, születési dátumát. Az oktatókról nyilvántartjuk a nevüket, valamint a tanszék kódját, ahol dolgoznak. A tárgyakról nyilvántartjuk a kódjukat, a nevüket, és egy rövid leírást. Nyilván kell tartanunk, hogy melyik tárgyat ki oktatja. Egy tárgyat több oktató is oktathat, és az is lehetséges, hogy egy adott tárgy nem indul ebben a félévben. Azt is tároljuk, hogy melyik diák milyen tárgyakra jár.

- Generáld le a sémát a saját adatbázisodban és mentsd el a generált sql fájlt `schema-4.sql` néven!
- Készítsd el a következő feladatokhoz szükséges queryket a `query-4.sql` fájlba:
  - Vedd fel az adatbázisba az Informatika 2 tárgy adatait (a tárgy leírását ne add meg), oktatóit és néhány hallgatót (beleértve téged is).
  - Módosítsd a tárgy nevét Info 2-re.
  - Listázd ki a rendszerben található oktatókat.
  - Listázd ki a V-betűvel kezdődő oktatók nevét.
  - Jelentkezz le a tárgyról.
  - Listázd ki azokat a tárgyakat, amelyeknek nincs leírása.

### :bookmark_tabs: Beadandó

- [ ] Az elkészült sémáról készíts egy képernyőképet.
- [ ] Mentsd el a képet `schema-4.png` néven a repository gyökerébe.
- [ ] Mentsd el a `schema-4.sql` és `query-4.sql` fájlokat a repository gyökerébe.
- [ ] Kommitold a változtatásokat.