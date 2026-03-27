# 🏃‍♂️ Zlatá Horečka: Nekonečná cesta

Vítejte na startovní čáře. 

Svět před vámi je chladný, nekompromisní a nekonečný. Jste jen malý stickman, pouhá črta na digitálním plátně, ale ve vaší hrudi bije srdce rváče. Země pod vašima nohama ubíhá neúprosným tempem a s každým dalším metrem přitvrzuje. Tyčí se před vámi obří balvany, ze země trčí smrtící ostny a jediný špatný krok znamená bolest. 

Ale není to jen o přežití. Ve vzduchu se třpytí zlato. Každý přesný skok, každý riskantní manévr vás posouvá blíž k bohatství. A když už si myslíte, že nemůžete dál, otevře se před vámi Černý trh – místo, kde můžete za nasbírané mince překročit své vlastní limity. Koupíte si nadlidskou rychlost? Nebo nohy s pružinami, které vás vynesou až do oblak?

Zhluboka se nadechněte. Cesta začíná. Jak daleko dokážete dojít, než vás svět zlomí?

---

## 🛠️ Pod pokličkou: Jak hra funguje (Technický popis)

Tato hra je ukázkou moderního webového vývoje, navržená tak, aby běžela hladce přímo v prohlížeči **bez nutnosti stahovat jakékoliv externí soubory, obrázky nebo hudbu**. Veškerá logika, grafika i zvuky jsou obsaženy v jednom jediném HTML souboru.

### 🎮 Použité technologie a mechaniky:

* **HTML5 Canvas & JavaScript:** Srdcem hry je element `<canvas>`, do kterého JavaScript vykresluje grafiku snímek po snímku. O plynulý běh se stará herní smyčka (Game Loop) využívající metodu `requestAnimationFrame`.
* **Procedurální generování světa:** Mapa není nikde předem nakreslená. Překážky, mince a zlaté bloky se generují algoritmicky za běhu hry podle toho, jak daleko hráč došel. S rostoucí vzdáleností roste obtížnost.
* **Vlastní fyzikální engine:** Hra obsahuje na míru napsaný fyzikální model. Počítá s gravitací, akcelerací, třením (setrvačností) a pokročilou detekcí kolizí (Hitboxy) mezi hráčem a okolním světem.
* **Web Audio API (Generativní zvuk):** Hra neobsahuje žádné MP3 soubory! Veškeré zvukové efekty (skok, cinknutí mince, zranění, nákup) jsou syntetizovány v reálném čase přímo procesorem pomocí matematických oscilátorů (sinusoidy, čtvercové a pilovité vlny).
* **Parallax Scrolling:** Pro vytvoření iluze hloubky a 3D prostoru se různé vrstvy pozadí (mraky, hory) pohybují odlišnou rychlostí nezávisle na pohybu kamery.
* **Částicové efekty (Particle System):** Pro lepší herní dynamiku (tzv. "game feel") hra obsahuje systém částic, který generuje prach při běhu a dopadu, nebo zlaté jiskry a létající texty při sebrání pokladu.
* **Vektorová grafika (SVG) & Pokročilé UI:** Uživatelské rozhraní a obchod využívají CSS (včetně efektů jako `backdrop-filter` pro skleněný efekt). Ikonky v obchodě jsou čistě matematicky vykreslené křivky (SVG), čímž se šetří paměť a data.
* **I-Frames (Invincibility Frames):** Tradiční herní mechanika – po zranění získá hráč na krátkou chvíli nesmrtelnost (signalizováno zprůhledněním postavy), aby nepřišel o všechny životy při jediném zaseknutí v překážce.
