1. VÝZNAM SEMANTICKÉHO HTML

   Semantické HTML je spôsob písania HTML kódu, pri ktorom používame také značky (tagy), ktoré opisujú význam obsahu (napr. ```<header>, <nav>, <main>, <article>, <section>, <footer>``` a pod.). Tieto značky pomáhajú prehľadnosti kódu, lepšej prístupnosti pre čítačky obrazovky a efektívnejšiemu indexovaniu stránok vyhľadávačmi.

   - Príklady semantických značiek:
     - ```<header>``` – hlavička sekcie alebo celej stránky
     - ```<nav>``` – navigačné menu
     - ```<main>``` – hlavný obsah stránky
     - ```<section>``` – logická sekcia obsahu
     - ```<article>``` – nezávislá časť obsahu (napr. článok na blogu)
     - ```<aside>``` – vedľajší obsah, napríklad sidebar
     - ```<footer>``` – pätička sekcie alebo celej stránky

   - Príklady semantických značiek:
     - ```<div>``` – univerzálny blokový kontajner (bez špecifického významu)
     - ```<span>``` – univerzálny riadkový kontajner (takisto bez špecifického významu)
     - ```<b>``` – pôvodne na zvýraznenie tučným písmom (bez definície, prečo je text dôležitý)
     - ```<i>``` – pôvodne na zobrazenie textu kurzívou (opäť bez sémantického vysvetlenia)
     - ```<u>``` – podčiarknutie textu

   - Prečo je dôležité semantické HTML:
     1. **Zlepšená prístupnosť**: Čítačky obrazovky ľahšie rozumejú štruktúre obsahu a používatelia so zrakovým postihnutím sa v ňom lepšie orientujú.
     2. **SEO výhody**: Vyhľadávače dokážu lepšie pochopiť, o čom stránka je a lepšie ju zaradiť.
     3. **Lepšia udržiavateľnosť kódu**: Kód je prehľadnejší, a tak sa jednoduchšie rozvíja a upravuje.
     4. **Štandardy a budúca rozšíriteľnosť**: Použitie moderných značiek zvyšuje šancu, že kód bude kompatibilný aj s budúcimi technológiami.

3. ROZDIELY MEDZI INLINE, INTERNAL A EXTERNAL CSS

   - **Inline CSS**:
     - Deklarácie štýlov sú priamo v HTML elemente pomocou atribútu style.
     - Napr.: ```<p style="color: red; font-size: 16px;">Text</p>```
     - Výhodou je, že štýl sa uplatní iba na konkrétny prvok. Nevýhodou je neprehľadnosť a horšia udržiavateľnosť kódu.

   - **Internal (vložené) CSS**:
     - Definuje sa v hlavičke stránky v rámci značky <style>.
     - Napr.:
     ```html
       <head>
         <style>
           p {
             color: blue;
             font-size: 18px;
           }
         </style>
       </head>
     ```
     - Výhodou je, že všetky štýly sú na jednej stránke. Nevýhodou je, že sa štýly dajú použiť len na danú stránku a pri viacerých stránkach je to menej efektívne.

   - **External (externé) CSS**:
     - Používa sa samostatný súbor (napr. styles.css), ktorý sa linkuje v hlavičke HTML súboru.
     - Napr.:
      ```html
        <head>
         <link rel="stylesheet" href="styles.css">
       </head>
       ```
     - Výhodou je jednoduchšia údržba štýlov pre celý web a rýchlejšie načítavanie (keďže prehliadač môže stylesheet cacheovať). Je to považované za najlepšie riešenie vo väčšine prípadov.

   - **Prečo použiť external CSS**:
     1. **Čistota kódu**: HTML a CSS sú oddelené, kód je prehľadný.
     2. **Opätovná použiteľnosť**: Jeden CSS súbor na viac stránok.
     3. **Jednoduchá údržba**: Zmena v jednom CSS súbore sa prejaví na všetkých stránkach.
     4. **Rýchlosť načítania**: Prehliadač si štýlový súbor môže stiahnuť a uložiť do vyrovnávacej pamäte (cache).

4. ČO SÚ MEDIA QUERIES A AKO ZABEZPEČIŤ RESPONSIVITU

   **Media queries** v CSS umožňujú aplikovať rôzne štýly v závislosti od vlastností zariadenia (napr. šírka obrazovky). Používajú sa pre responzívny dizajn, aby stránka vyzerala dobre na mobiloch, tabletoch, notebookoch či veľkých monitoroch.

   - **Základný príklad**:
     ```css
     /* Východiskové štýly platia pre všetky zariadenia */
     body {
       margin: 0;
       font-family: Arial, sans-serif;
     }

     /* Pre zariadenia, ktoré majú šírku menšiu ako 768px (napr. mobilné telefóny) */
     @media (max-width: 768px) {
       body {
         background-color: lightblue;
       }
       nav {
         display: none;
       }
     }
     ```

   - **Ako funguje responzivita**:
     1. Najprv sa nastaví základný štýl (desktop-first alebo mobile-first).
     2. Potom pomocou media queries upravujeme rozloženie pre rôzne šírky obrazovky (breakpointy).
     3. Zabezpečíme, aby dôležité prvky boli čitateľné a použiteľné na všetkých zariadeniach.

5. ROZDIEL MEDZI document.querySelector() A document.querySelectorAll()

   - **document.querySelector(selektor)**:
     - Vráti prvý element v dokumente, ktorý zodpovedá zadanému CSS selektoru.
     - Napr. `document.querySelector(".btn")` vráti prvý element s triedou "btn".
     - Vhodné, keď potrebujete manipulovať s jedným konkrétnym prvkom.

   - **document.querySelectorAll(selektor)**:
     - Vráti statický NodeList, čiže kolekciu všetkých prvkov zodpovedajúcich selektoru.
     - Napr. `document.querySelectorAll("li")` vráti všetky <li> elementy na stránke.
     - Ideálne, keď chcete pracovať s viacerými prvkami naraz (napr. zmena štýlu, textu, pridávanie event listenerov).

   - **Kedy použiť každý**:
     1. querySelector() – ak manipuluješ len s jedným (prvým nájdeným) prvkom.
     2. querySelectorAll() – ak potrebuješ získať a upraviť viac prvkov naraz (napr. pridanie triedy všetkým prvkom).

6. HLAVNÉ VÝHODY REACTU A ZÁKLADNÝ PRÍKLAD KOMPONENTU

   - **Hlavné výhody použitia Reactu**:
     1. **Komponentovo orientovaná architektúra**: Aplikácia je rozdelená na menšie, znovupoužiteľné časti (komponenty).
     2. **Virtuálny DOM**: React optimalizuje aktualizácie na základe rozdielov vo virtuálnom DOMe, čím zlepšuje výkon.
     3. **Jednosmerný tok dát (unidirectional data flow)**: Dáta tečú smerom z rodiča na dieťa, čo zjednodušuje debugovanie a udržiavateľnosť.
     4. **Bohatá ekosystémová podpora**: K dispozícii je množstvo knižníc a nástrojov (React Router, Redux, atď.).
     5. **Veľká komunita**: Veľa riešení, tutoriálov, podpory.

   - **Základný príklad použitia komponentu v Reacte** (JavaScript, ES6+):
     ```jsx
     import React from "react";

     // Definícia funkcionálneho komponentu
     function HelloWorld(props) {
       return <h1>Ahoj, {props.name}!</h1>;
     }

     // Hlavná aplikácia
     function App() {
       return (
         <div>
           <HelloWorld name="Svet" />
           <HelloWorld name="Peter" />
         </div>
       );
     }

     export default App;
     ```
     - V tomto príklade máme funkcionálny komponent *HelloWorld*, ktorý prijíma *props* (vlastnosti).
     - Komponent *App* využíva viac inštancií (komponentov) *HelloWorld* a tým demonštruje opakované použitie.
     - Po preložení (pomocou nástrojov ako Vite, Create React App či Webpack) sa aplikácia zobrazí v prehliadači.

