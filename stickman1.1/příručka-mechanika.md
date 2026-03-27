# ⚙️ Příručka 3

*Hlubší pohled na to, jak fungují fyzikální, zvukové a grafické systémy hry.*

### 🏃‍♂️ Kinematika a Pohyb (Vektorová fyzika)

Pohyb postavy není řešen pouhým přičítáním pixelů k pozici. Hra využívá profesionální kinematický model založený na **vektorech rychlosti (`velX`, `velY`)**. 

1. Když hráč stiskne šipku, kód neposune postavu hned o daný počet pixelů, ale zvýší její rychlost (`velX`) o hodnotu **akcelerace**.
2. V každém snímku se `velX` vynásobí **třením (friction, např. 0.85)**. To znamená, že po puštění klávesy rychlost postupně klesá a panáček realisticky a plynule zabrzdí.
3. Při skoku se vertikální rychlost (`velY`) nastaví na zápornou hodnotu, což vystřelí postavu vzhůru. Následně se k ní v každém snímku přičítá **gravitace**, čímž vznikne přirozená oblouková křivka (parabola) letu a dopadu.

### 🎵 Generativní Audio (Web Audio API)

Hra neobsahuje jedinou MP3 nebo WAV nahrávku! Veškeré zvuky jsou syntetizované matematicky v reálném čase, což hře zajišťuje nulovou latenci a minimální datovou velikost.

* Funkce `playSound(type)` inicializuje digitální **oscilátor** (generátor zvukových vln).
* Například u zvuku **skoku** systém vygeneruje sinusoidu s frekvencí 300 Hz a během zlomku vteřiny ji plynule "vytáhne" na 600 Hz (technika zvaná *frequency ramp*). To vytváří ikonický retro "biu-íp" zvuk.
* K cinknutí mince se naopak používá čtvercová vlna (square wave), která zní ostřeji, jako ze starých arkádových automatů.

### 🏔️ Parallax Scrolling a Optické klamy

Ačkoliv je hra vykreslovaná čistě ve 2D prostředí na elementu `<canvas>`, vytváří pro oko silnou iluzi hloubky a 3D prostoru.

* Toho je dosaženo technikou **Parallax Scrolling**. Různé vrstvy světa se pohybují jinou rychlostí vůči kameře.
* Zatímco překážky na zemi se hýbou poměrem 1:1 k pohybu hráče, hory v pozadí se posouvají pouze o **5 %** rychlosti hráče (`cameraX * 0.05`). Mraky mají navíc vlastní nezávislou rychlost větru. Lidský mozek si tento rozdíl v rychlostech překládá jako perspektivu a vzdálenost.
