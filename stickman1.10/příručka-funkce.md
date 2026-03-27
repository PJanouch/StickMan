# 📚 Příručka 2

*Technický slovníček pro orientaci ve zdrojovém kódu.*

Tato sekce popisuje klíčové datové struktury a funkce, které tvoří mozek celé hry.

### 📊 Klíčové Objekty a Proměnné

* **`playerStats` (Objekt):** Uchovává RPG prvky hráče.
  * `.hp` / `.maxHp`: Aktuální a maximální zdraví.
  * `.baseMaxSpeed`: Maximální rychlost běhu (zvyšuje se v obchodě).
  * `.acceleration`: Rychlost, jakou se postava rozbíhá (zrychlení).
  * `.baseJump`: Základní síla skoku.
* **`config` (Objekt):** Fyzikální zákony herního světa.
  * `.gravity` (0.65): Síla, která táhne hráče k zemi.
  * `.friction` (0.85): Tření; zajišťuje, že postava po puštění klávesy plynule zastaví (neklouže jako na ledě).
* **`player` (Objekt):** Fyzický stav postavičky v prostoru.
  * `.x` / `.y`: Aktuální souřadnice na plátně.
  * `.velX` / `.velY`: Vektory rychlosti (Velocity). Určují, kam a jak rychle se hráč pohne v dalším snímku.
  * `.invulnerable` (Boolean): Stav "nesmrtelnosti" (I-Frames) po zásahu.
* **`cameraX` (Číslo):** Globální offset. Určuje, o kolik pixelů je herní svět posunutý doleva, aby hráč zůstal vždy v levé třetině obrazovky.

### 🛠️ Hlavní Metody (Funkce)

* **`update()`:** *Srdce herní logiky.* Volá se 60x za vteřinu. Počítá novou pozici hráče, detekuje kolize (nárazy do kamenů, sběr mincí) a maže staré částice. Nemanipuluje přímo s grafikou!
* **`draw()`:** *Vykreslovací engine.* Volá se hned po `update()`. Kompletně smaže plátno a na základě nových dat z `update()` vykreslí celou scénu odznova (slunce, hory, mraky, hlínu, objekty, panáčka a UI).
* **`spawnWorld()`:** *Algoritmus level designu.* Sleduje pozici kamery a pokud se blíží neprobádanému území, náhodně vygeneruje nové kameny, ostny nebo zlaté bloky do pole `items`.
* **`createDirtPattern()`:** Skrytá metoda, která při startu hry vygeneruje pixelovou texturu hlíny a uloží ji do paměti jako "tapetu" pro extrémně rychlé vykreslování v `draw()`.
