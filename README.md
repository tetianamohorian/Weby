# Webové technológie – Odpovede na otázky (Skupina B)
## 1. VÝZNAM SEMANTICKÉHO HTML

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

## 2. ROZDIELY MEDZI INLINE, INTERNAL A EXTERNAL CSS

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

## 3. ČO SÚ MEDIA QUERIES A AKO ZABEZPEČIŤ RESPONSIVITU

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

## 4. ROZDIEL MEDZI document.querySelector(), document.getElementById(), document.querySelectorAll()
   
   - ```document``` - Predstavuje celý dokument webovej stránky načítanej v prehliadači. Pomocou neho môžeme manipulovať s obsahom stránky, čítať údaje alebo ich upravovať.
   - ```.``` - Bodka slúži na prístup k vlastnostiam alebo metódam objektu. V tomto prípade sa používa na zavolanie metódy querySelector objektu document.
   - ```querySelector``` - Metóda objektu document, ktorá vyhľadáva prvý element na stránke, ktorý zodpovedá zadanému CSS selektoru. Ak takýto element neexistuje, metóda vráti null.


   - **document.querySelector(selektor)**:
     - Vráti prvý element v dokumente, ktorý zodpovedá zadanému CSS selektoru.
     - Napr. `document.querySelector(".btn")` vráti prvý element s triedou "btn".
     - Vhodné, keď potrebujete manipulovať s jedným konkrétnym prvkom.

   - **document.querySelectorAll(selektor)**:
     - Vráti statický NodeList, čiže kolekciu všetkých prvkov zodpovedajúcich selektoru.
     - Napr. `document.querySelectorAll("li")` vráti všetky <li> elementy na stránke.
     - Ideálne, keď chcete pracovať s viacerými prvkami naraz (napr. zmena štýlu, textu, pridávanie event listenerov).

   - document.getElementById("idPrvku")
     - Vráti element, ktorý má jedinečný atribút id (napr. document.getElementById("header")).
     - Vracia vždy iba jeden prvok (lebo hodnota id by mala byť jedinečná v rámci celej stránky).
     - Funguje rýchlejšie ako querySelector(), keďže prehliadač hľadá priamo konkrétne id (nie cez selektor).
       

   - **Kedy použiť každý**:
     1. querySelector() – ak manipuluješ len s jedným (prvým nájdeným) prvkom.
     2. querySelectorAll() – ak potrebuješ získať a upraviť viac prvkov naraz (napr. pridanie triedy všetkým prvkom).
     3. getElementById() – ak je na stránke element s jedinečným ID a potrebujete ho rýchlo získať.

## 5. HLAVNÉ VÝHODY REACTU A ZÁKLADNÝ PRÍKLAD KOMPONENTU

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



# Webové technológie – Odpovede na otázky (Skupina A)

## 1. Vysvetlite význam DOM a popíšte základné spôsoby tvorby responzívnej HTML5 stránky.

### DOM (Document Object Model):
DOM je rozhranie pre prácu s HTML a XML dokumentmi, ktoré predstavuje stromovú štruktúra, kde každý uzol reprezentuje prvok, atribút alebo text. DOM umožňuje dynamické manipulovanie so stránkou, ako napr.:
- Pridávanie, odstraňovanie a upravovanie elementov.
- Zmeny štýlov (CSS).
- Reakcie na udalosti (napr. kliknutie).

### Základné spôsoby tvorby responzívnej HTML5 stránky:
1. **Použitie meta tagu** v hlavičke:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
2. **Použitie flexbox a grid layoutov** na usporiadanie obsahu.
3. **Media queries** pre prispôsobenie štýlov podľa zariadenia:
   ```css
   @media (max-width: 768px) {
       body {
           font-size: 14px;
       }
   }
   ```
4. **Optimalizácia zdrojov** (obrazky s atribútom srcset alebo použitie formátov ako WebP).
5. **Používanie responzívnych rámcov**, napr. Bootstrap.

---

## 2. Popíšte základný syntax CSS. Definujte na jednoduchom príklade, čo je selektor, vlastnosti a hodnota CSS elementu.

### Základný syntax CSS:
CSS pravidlo sa skladá z:
- **Selektora**, ktorý určuje, na ktoré elementy sa pravidlo aplikuje.
- **Deklarácie**, ktorá obsahuje vlastnosť a hodnotu.

#### Príklad:
```css
p {
    color: blue; /* Vlastnosť: farba textu, Hodnota: modrá */
    font-size: 16px; /* Vlastnosť: veľkosť písma, Hodnota: 16 pixelov */
}
```
- **Selektor:** `p` (odkazuje na odsek `<p>`).
- **Vlastnosti:** `color`, `font-size`.
- **Hodnoty:** `blue`, `16px`.

---

## 3. Vymenujte základné väzby medzi jednotlivými komponentami modelu MVC (Model-View-Controller).

### Model:
- Obsahuje logiku aplikácie a pracuje s dátami (napr. databázovými záznamami).
- Poskytuje dáta na zobrazenie vo View.

### View:
- Zodpovedá za vizuálne zobrazenie dát užívateľovi.
- Prijíma dáta z Modelu a zobrazuje ich vo vhodnej forme.

### Controller:
- Riadí interakcie medzi Modelom a View.
- Spracováva vstupy užívateľa a aktualizuje Model alebo View podľa potreby.

### Väzby:
- **Model ↔ Controller:** Controller mení stav Modelu a číta jeho dáta.
- **Controller ↔ View:** Controller odovzdáva dáta View-u na zobrazenie.
- **Model ↔ View:** View dostáva dáta priamo z Modelu.

---

## 4. Aké sú kľúcové princípy JavaScriptu a ako umožňujú vytvárať dynamické webové stránky?

### Kľúcové princípy JavaScriptu:
1. **Interaktivita:** Umožňuje reagovať na akcie užívateľa (kliknutia, zadanie textu).
2. **Manipulácia s DOM:** Dynamické pridávanie, odstraňovanie alebo zmeny elementov.
3. **Asynchrónny chod:** Vďaka funkciám ako `setTimeout`, `fetch` a `async/await` umožňuje paralelné vykonávanie úloh.
4. **Podpora udalostí:** Možnosť nastaviť "event listener" na prvky stránky:
   ```javascript
   document.getElementById('button').addEventListener('click', function() {
       alert('Klikli ste na tlačidlo!');
   });
   ```

### Dynamické webové stránky:
- **Príklad:** Formulár, ktorý validuje vstup užívateľa pred odoslaním.
- **Funkcia:** Automatická aktualizácia obsahu (napr. chatovacie aplikácie, vyhľadávanie v reálnom čase).

---

## 5. Aké základné časti obsahuje React projekt a ako sú spojené súbory úsrredného /public/index.html?

### Základné časti React projektu:
1. **Komponenty:**
   - Samostatné časti aplikácie definované pomocou tried alebo funkcií.
   - Príklad:
     ```javascript
     function App() {
         return <h1>Vitajte v Reacte!</h1>;
     }
     ```
2. **JSX (JavaScript XML):**
   - Syntax pre kombinovanie HTML a JavaScriptu.
3. **State a Props:**
   - State: Lokálne uložené dáta komponentu.
   - Props: Dáta odovzdávané medzi komponentmi.
4. **Routing:**
   - Spravuje navigáciu medzi rôznymi častami aplikácie (napr. React Router).

### Spojenie s /public/index.html:
- Všetky React komponenty sa renderujú do **jediného elementu** v `index.html`:
  ```html
  <div id="root"></div>
  ```
- React aplikácia používa tento element ako „kořeň“ pre vykreslenie aplikácie.
- Príklad renderovania:
  ```javascript
  import React from 'react';
  import ReactDOM from 'react-dom';
  import App from './App';

  ReactDOM.render(<App />, document.getElementById('root'));
  ```

