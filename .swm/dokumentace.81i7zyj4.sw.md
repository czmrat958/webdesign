---
title: Dokumentace
---
# Dokumentace

## Obsah

1. Úvod
2. Požadavky na implementaci
3. Splnění požadavků na projekt

## Úvod

Tento dokument vás provede implementací herního zpravodajského webu. Web je navržen tak, aby poskytoval nejnovější zprávy, recenze a retro obsah související s hraním. Má responzivní design, aby byl přístupný na různých zařízeních. Budeme se zabývat: 1. Prezentací webu, 2. Požadavky na implementaci, 3. Splněním projektových požadavků

### Prezentace webu

Náš web QuestPoint je zpravodajskou stránkou pro hráče videoher. Web se zabývá nejnovějšími hrami, novinkami z her, a obsahuje články na daná témata. Ve článcích se autoři zabývají například i spekulacemi o tajných projektech, novými aktualizacemi již zveřejněných her, nebo naopak ohlášením nových herních projektů. Mimo to se autoři na stránkách zaměřují na uživatelské recenze specifických her, nebo také slaví prostřednictvím článků důležitá data pro hráče videoher, jako například 30 let od publikace počítačové hry Warcraft. Dále web obsahuje sekce s informacemi o redakci, zásadách ochrany, kariéře a nejhlavněji předplatném k newsletteru QuestPointu s možností odběru a platby. Web je plně responzivní a přizpůsobený všem platformám, a nabízí uživatelsky přístupné rozhraní, které je přístupné a konzistentní.

## Požadavky na implementaci

### Popis stránek

Webová stránka se skládá z několika klíčových sekcí:&nbsp;

- Nejnovější články
- Recenze
- Pohled do minulosti
- Předplatné
- Zásady ochrany
- Kariéra
- O nás
- Včetně stránky pro výsledky vyhledávání

Hlavní stránka sestává z několika hlavních sekcí:

- Záhlaví s logem a navigačním menu
- Sekce s hlavními články
- Sekce s recenzemi
- Sekce s retrospektivou
- Zápatí s navigací a odkazy na sociální sít

Každá sekce je jasně oddělena a obsahuje relevantní informace a obrázky.

#### Hlavní stránka - záhlaví

<SwmSnippet path="/Web/index.html" line="1">

---

Záhlaví je připevněné na vrchu stránky a obsahuje logo webové stránky, včetně burger menu pro mobilní navigaci.

```
<!DOCTYPE html>
<html lang="cs">
<head>
    <!-- Sekce metadata -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gaming News Page</title>
    <link rel="stylesheet" href="styles.css"> <!-- Odkaz na externí stylopis -->
</head>
<body>
<!-- Hlavička -->
<header>
        <div class="logo">
                <img src="images/logo.png" alt="Logo webu Questpoint">
        </div>
        <nav class="desktop-nav">
            <ul>
                <li><a href="#main-articles-heading">Nejnovější články</a></li>
                <li><a href="#reviews-heading">Recenze</a></li>
                <li><a href="#retro-heading">Pohled do minulosti</a></li>
                <li><a href="#">Předplatné</a></li>
                <li><a href="#">Zásady ochrany</a></li>
                <li><a href="#">Kariéra</a></li>
                <li><a href="#">O nás</a></li>
            </ul>
        </nav>
        <div class="desktop-search-bar">
            <input type="text" placeholder="Hledat...">
        </div>
        <div class="ham-menu">
```

---

</SwmSnippet>

<SwmSnippet path="/Web/index.html" line="37">

---

Zde máme HTML kód pro off-screen menu. Skládá se z vyhledávacího pole a seznamu odkazů. Odkazy se používají k navigaci do různých částí stránky.

```
<div class="off-screen-menu">
    <div class="mobile-search-bar">
      <input type="text" placeholder="Hledat...">
    </div>
    <ul>
      <li><a href="#main-articles-heading">Nejnovější články</a></li>
      <li><a href="#reviews-heading">Recenze</a></li>
      <li><a href="#retro-heading">Pohled do minulosti</a></li>
      <li><a href="#">Předplatné</a></li>
      <li><a href="#">Zásady ochrany</a></li>
      <li><a href="#">Kariéra</a></li>
      <li><a href="#">O nás</a></li>
      <li><a href="#">QuestPoint</a></li>
      <li><a href="#">Všechna práva vyhrazena</a></li>
    </ul>
</div>
```

---

</SwmSnippet>

<SwmSnippet path="Web/index.html" line="54">

---

Skript ./menu.js má za úkol jednoduché a hladké vyjíždění hamburger menu po jeho rozkliknutí v mobilních verzích stránky.

Následuje tělo stránky, tedy hlavní sekce s články, sekce s recenzemi a pohled do minulosti.

Hlavní sekce obsahuje nejnovější články s hlavním článkem zvýrazněným na vrchu, a vedlejšími články uvedenými níže\
Sekce recenzí ukazuje individuální recenze ke hrám s obrázky a textem, včetně informací o autorech a data. Sekce retrospekce zvýrazňuje články o klasických hrách a jejich vlivu na herní průmysl, historických milnících a komentářů.

```
<script src="./menu.js"></script>



<!-- Hlavní sekce s články -->
<main class="articles-wrapper" aria-labelledby="main-articles-heading">
        <h2 id="main-articles-heading" class="main-articles-heading">Nejnovější články</h2> <!-- Nadpis sekce nejnovějších článků -->
    <section class="articles-container">
        <!-- Hlavní článek -->
        <section class="main-article">
            <img src="images/main-image.png" alt="Obrázek ilustrující hru Mystic Lands Online"> <!-- Obrázek hlavního článku -->
            <div class="article-text">
                <h2>Spekuluje se o tajném projektu – Mystic Lands Online: Nové MMORPG?</h2> <!-- Nadpis hlavního článku -->
                <p>Kateřina Novotná 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
        <!-- Vedlejší články -->
        <section class="side-articles">
            <div class="side-article">
                <img src="images/side-image1.png" alt="Obrázek ze hry Realm of Eternity, zachycující nové AI společníky"> <!-- Obrázek vedlejšího článku -->
                <h3>Nový update pro populární RPG hru Realm of Eternity přináší revoluční AI společníky!</h3> <!-- Nadpis vedlejšího článku -->
                <p>Zuzana Veselá 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
            <div class="side-article">
                <img src="images/side-image2.png" alt="Obrázek ze hry Metro: Shadows of Moscow, zachycující temné podzemí"> <!-- Obrázek vedlejšího článku -->
                <h3>Metro: Shadows of Moscow – Návrat do hlubin podzemí v novém temném dílu?</h3> <!-- Nadpis vedlejšího článku -->
                <p>Petr Král 14.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
    </section>
</main>

<!-- Sekce recenzí -->
<section class="reviews" aria-labelledby="reviews-heading">
    <h2 id="reviews-heading">Recenze</h2> <!-- Nadpis sekce recenzí -->
    <!-- Jednotlivé recenze -->
    <div class="review">
        <img src="images/lifeisstrange.png" alt="Obrázek obalu hry Life is Strange"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Life is Strange</h3> <!-- Titulek recenze -->
            <p>Petr Král 8.10.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/eldenring.png" alt="Obrázek obalu hry Elden Ring"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Elden Ring</h3> <!-- Titulek recenze -->
            <p>Petr Král 6.5.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/farming simulator.png" alt="Obrázek obalu hry Farming Simulator 2025"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Farming Simulator 2025</h3> <!-- Titulek recenze -->
            <p>Zuzana Veselá 11.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/cs.jpeg" alt="Obrázek obalu hry Cities Skylines 2"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Cities Skylines 2 – Město vašich snů (a nočních můr)</h3> <!-- Titulek recenze -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
</section>

<!-- Retro sekce -->
<section class="retro" aria-labelledby="retro-heading">
    <h2 id="retro-heading">Pohled do minulosti</h2> <!-- Nadpis retro sekce -->
    <!-- Jednotlivé retro články -->
    <div class="retro-article">
        <img src="images/wolfenstein.png" alt="Obrázek z původní hry Wolfenstein, klasická akční hra"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>Wolfenstein: Průkopník herního průmyslu a legenda akčních her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 19.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/hl.png" alt="Obrázek z původní hry Half-Life, ukazující Gordona Freemana"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>20 let Half-Life: Jak Gordon Freeman navždy změnil svět her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/wow.png" alt="Obrázek ze hry Warcraft, ukazující legendární bitvu"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>30 let Warcraftu: Jak se zrodila legenda herního světa</h3> <!-- Titulek retro článku -->
            <p>Zuzana Veselá 12.12.2023</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
</section>
```

---

</SwmSnippet>

<SwmSnippet path="/Web/index.html" line="147">

---

Zde máme patičku webové stránky. Obsahuje navigační odkazy na 'O nás', 'Zásady ochrany', 'Kariéra' a 'Předplatné'. Zobrazuje také ikony sociálních médií pro YouTube, X, Instagram a Facebook. Na dně je poznámka, že se jedná o studentský projekt.

```
<!-- Patička -->
<footer>
    <div class="footer-nav" role="navigation" aria-label="Footer Navigation">
        <a href="#">O nás</a> <!-- Odkaz v patice -->
        <a href="#">Zásady ochrany</a> <!-- Odkaz v patice -->
        <a href="#">Kariéra</a> <!-- Odkaz v patice -->
        <a href="#">Předplatné</a> <!-- Odkaz v patice -->
    </div>
    <div class="footer-socials">
        <p>Všechna práva vyhrazena</p> <!-- Oznámení o autorských právech -->
        <div class="social-icons" role="navigation" aria-label="Social Media Links">
            <!-- Ikony sociálních sítí -->
            <a href="#" aria-label="YouTube"><img src="images/yt.png" alt="Ikona YouTube" aria-hidden="true"></a>
            <a href="#" aria-label="X"><img src="images/x.png" alt="Ikona X" aria-hidden="true"></a>
            <a href="#" aria-label="Instagram"><img src="images/ig.png" alt="Ikona Instagram" aria-hidden="true"></a>
            <a href="#" aria-label="Facebook"><img src="images/fb.png" alt="Ikona Facebook" aria-hidden="true"></a>
        </div>
    </div>
    <p>Studentský projekt</p> <!-- Poznámka v patice -->
</footer>
</body>
</html>
```

---

</SwmSnippet>

### Jak se mají stránky chovat

Stránky jsou navrženy tak, aby byly uživatelsky přívětivé a snadno navigovatelné. Hlavní navigace je umístěna v hlavičce a obsahuje odkazy na všechny hlavní sekce webu. Pro mobilní zařízení je k dispozici <SwmToken path="/Web/menu.js" pos="3:12:14" line-data="const offScreenMenu = document.querySelector(&quot;.off-screen-menu&quot;);">`off-screen`</SwmToken> menu, které se aktivuje kliknutím na hamburger menu.

&nbsp;

### Návrh technologií pro frontend + backend

Všechny elementy jsou stylizované a definované tak, aby byl zajištěn jednotný vzhled pro všechny zařízení i prohlížeče. Články jsou umístěné do Flexbox kontejnerů, aby bylo možné je dát k sobe nebo pod sebe tak, jak se editorům zalíbí.

Frontend je postaven na HTML, CSS a JavaScriptu. CSS je použito pro stylizaci a responzivitu, zatímco JavaScript je použit pro interaktivní prvky, jako je hamburger menu. Pomocí CSS je proveden základní reset stylů pro všechny elementy, aby se odstranily předdefinované hodnoty odlišných prohlížečů. Je zajištěno, aby hamburger menu bylo interaktivním prvkem a vyjíždělo při kliknutí na něj.

Responzivita je hlavním prvkem, na který je naše stránka hrdá, a je vytvořena stylem "mobile first". Stránka je schopna se přizpůsobit většině zařízení tak, aby čtenář měl hladkou a příjemnou návštěvu našeho zpravodajského webu. Interaktivita se čtenářem je zajištěna také zvětšením prvků, na kterých je najeto kurzorem myši.

&nbsp;

&nbsp;

<SwmSnippet path="/Web/styles.css" line="127">

---

Stylizace hamburger menu

```
/* Ham menu: Stylizace hamburger menu */
.ham-menu {
    height: 50px;
    width: 40px;
    margin-left: auto;
    position: relative;

}
.ham-menu span {
    height: 5px;
    width: 100%;
    background-color: var(--white-color);
    border-radius: 25px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    transition: 0.3s ease;
}
.ham-menu span:nth-child(1) {
    top: 25%;
}
.ham-menu span:nth-child(3) {
    top: 75%;
}
.ham-menu.active span {
    background-color: white;
}
.ham-menu.active span:nth-child(1) {
    top: 50%;
    transform: translate(-50%, -50%) rotate(45deg);
}
.ham-menu.active span:nth-child(2) {
    opacity: 0;
}
.ham-menu.active span:nth-child(3) {
    top: 50%;
    transform: translate(-50%, -50%) rotate(-45deg);
}

/* Nadpis hlavních článků */
.main-articles-heading {
    font-size: 28px;
    font-weight: bold;
    margin: 0;
    width: 100%;
    padding: 30px;
    text-align: center;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/menu.js" line="1">

---

Interaktivita hamburger menu

```
const hamMenu = document.querySelector(".ham-menu");

const offScreenMenu = document.querySelector(".off-screen-menu");

hamMenu.addEventListener("click", () => {
  hamMenu.classList.toggle("active");
  offScreenMenu.classList.toggle("active");
});
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="177">

---

Flexbox

```
/* Kontejner pro články: Flexbox pro umístění článků pod sebou */
.articles-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: center;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="467">

---

Responzivita pro tablety

```
/* Responzivita: Styl pro tablety od 768px do 1024px */
@media (min-width: 768px) and (max-width: 1024px) {
 
    .main-articles-heading {
        font-size: 24px;
    }

    .articles-wrapper {
        padding: 0 40px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="501">

---

Responzivita pro větší obrazovky

```
/* Responzivita: Styl pro obrazovky od 1025px */
@media (min-width: 1025px){

    .ham-menu {
        display: none;
    }

    .off-screen-menu {
        display: none;
    }
```

---

</SwmSnippet>

#### &nbsp;&nbsp;&nbsp;&nbsp;Zdůvodnění

Použití HTML, CSS a JavaScriptu zajišťuje širokou kompatibilitu a snadnou údržbu. Responzivní design zajišťuje, že web je přístupný na všech zařízeních. Vyjíždějící hamburger menu nabízí interaktivitu a zároveň větší prostor pro texty a design stránky, pokud je skryté.

### Nasazení – hosting, technologie, údržba, analytika, marketing

Web by měl být hostován na platformě, která podporuje HTML, CSS a JavaScript. Údržba zahrnuje pravidelné aktualizace obsahu a kontrolu funkčnosti, včetně kontroly funkčnosti a bezpečnosti plateb za předplatné. Analytika je implementována pomocí nástrojů jako Google Analytics pro sledování návštěvnosti a chování uživatelů.

### Využití AI nástrojů

**Jaké nástroje byly využity?**\
Při tvorbě webové stránky jsme pracovali s nástrojem ChatGPT 4o with Canvas. Tento systém nám umožnil zvládnout nejen technickou část, jako je kódování, ale také obsahovou a vizuální stránku projektu.

\
**Jak jsme nástroj použili?**

1. **Generování kódu**

ChatGPT 4o with Canvas nám pomohl vytvořit základní strukturu HTML a CSS. Tento „hrubý návrh“ jsme poté upravili a přizpůsobili konkrétním potřebám webu.&nbsp;

2. **Tvorba textového obsahu**

Generování smyšlených textů pro naši webovou stránku bylo další důležitou částí. Pomocí nástroje jsme získali rychle hotové návrhy textů pro naše stránky.&nbsp;

3. **Vytváření vizuálů**

Pro grafickou stránku projektu jsme využili schopnosti nástroje generovat obrázky podle našich zadání. Ilustrace a vizuální prvky byly tvořeny na míru tak, aby ladily s celkovým vzhledem a účelem webu.

\
**Přínosy a výzvy při používání**\
&nbsp;Použití ChatGPT 4o with Canvas nám výrazně usnadnilo práci a zrychlilo proces tvorby. Jednou z největších výhod byla jeho univerzálnost – mohli jsme v něm řešit kódování, texty i grafiku, což nám umožnilo soustředit se na celkovou koncepci projektu místo řešení jednotlivých částí samostatně.\
&nbsp;Nicméně i zde jsme narazili na určité výzvy. Přesné formulování zadání bylo klíčové, zejména u generování obrázků a některých částí kódu. Chybný nebo nejasný popis mohl vést k výsledkům, které neodpovídaly našim představám, což vyžadovalo opakované úpravy.\
&nbsp;Celkově byl ale přínos nástroje ChatGPT 4o with Canvas značný. Pomohl nám vytvořit komplexní projekt v kratším čase a s menší námahou, než bychom toho dosáhli bez jeho pomoci. Tato zkušenost ukázala, že generativní umělá inteligence může být cenným pomocníkem i v kreativních a technických projektech.

## Splnění požadavků na projekt

### Seznam požadavků

1. Použití CSS proměnných
2. Grid layout
3. Flexbox

&nbsp;

1. Hlavní stránka
2. Responzivní design
3. Jasná sekce obsahu
4. Konzistentní stylování

### Popis, jak bylo splněno

#### Hlavní stránka

Hlavní stránka obsahuje záhlaví, zápatí, sekci s hlavními i vedlejšími články, recenze a retrospektivu. Stránka je plně reponzivní, interaktivní a pro mobilní zařízení obsahuje vyjížděcí hamburger menu.

#### Responzivní design

Web je plně responzivní díky použití CSS media queries stylem mobile first pro různé velikosti obrazovky a různá zařízení.

<SwmSnippet path="/Web/styles.css" line="467">

---

&nbsp;

```
/* Responzivita: Styl pro tablety od 768px do 1024px */
@media (min-width: 768px) and (max-width: 1024px) {
 
    .main-articles-heading {
        font-size: 24px;
    }

    .articles-wrapper {
        padding: 0 40px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="501">

---

&nbsp;

```
/* Responzivita: Styl pro obrazovky od 1025px */
@media (min-width: 1025px){

    .ham-menu {
        display: none;
    }

    .off-screen-menu {
        display: none;
    }
```

---

</SwmSnippet>

#### Jasná sekce obsahu a navigace

<SwmSnippet path="/Web/index.html" line="1">

---

Navigace je implementována v hlavičce pro desktop a <SwmToken path="/Web/menu.js" pos="3:12:14" line-data="const offScreenMenu = document.querySelector(&quot;.off-screen-menu&quot;);">`off-screen`</SwmToken> menu pro mobilní zařízení. Díky těmto menu je jednoduchá navigace po webové stránce a i hledání v ní.

```
<!DOCTYPE html>
<html lang="cs">
<head>
    <!-- Sekce metadata -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gaming News Page</title>
    <link rel="stylesheet" href="styles.css"> <!-- Odkaz na externí stylopis -->
</head>
<body>
<!-- Hlavička -->
<header>
        <div class="logo">
                <img src="images/logo.png" alt="Logo webu Questpoint">
        </div>
        <nav class="desktop-nav">
            <ul>
                <li><a href="#main-articles-heading">Nejnovější články</a></li>
                <li><a href="#reviews-heading">Recenze</a></li>
                <li><a href="#retro-heading">Pohled do minulosti</a></li>
                <li><a href="#">Předplatné</a></li>
                <li><a href="#">Zásady ochrany</a></li>
                <li><a href="#">Kariéra</a></li>
                <li><a href="#">O nás</a></li>
            </ul>
        </nav>
        <div class="desktop-search-bar">
            <input type="text" placeholder="Hledat...">
        </div>
        <div class="ham-menu">
            <span></span>
            <span></span>
            <span></span>
        </div>
</header>
```

---

</SwmSnippet>

<SwmSnippet path="/Web/index.html" line="37">

---

Mobilní hamburger menu pro navigaci

```
<div class="off-screen-menu">
    <div class="mobile-search-bar">
      <input type="text" placeholder="Hledat...">
    </div>
    <ul>
      <li><a href="#main-articles-heading">Nejnovější články</a></li>
      <li><a href="#reviews-heading">Recenze</a></li>
      <li><a href="#retro-heading">Pohled do minulosti</a></li>
      <li><a href="#">Předplatné</a></li>
      <li><a href="#">Zásady ochrany</a></li>
      <li><a href="#">Kariéra</a></li>
      <li><a href="#">O nás</a></li>
      <li><a href="#">QuestPoint</a></li>
      <li><a href="#">Všechna práva vyhrazena</a></li>
    </ul>
</div>
```

---

</SwmSnippet>

#### Konzistentní stylování

CSS proměnné se používají k udržování konzistentního barevného schématu a typografie na celém webu. Následuje pouze úryvek kódu CSS provádějící základní reset stylů a definici CSS proměnných. Tímto a zbylým kódem v souboru styles.css je dosaženo toho, aby stylování po celé webové stránce bylo jednotné a hlavně příjemné pro oči.

<SwmSnippet path="/Web/styles.css" line="1">

---

V úryvku jsou použitý proměnné jako margin, color, font-size, které jsou vyžadovány v požadavcích k projektu.

```css
/* Základní reset: Resetuje styly pro všechny elementy, aby se odstranily předdefinované hodnoty odlišných prohlížčů */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style: none;
    text-decoration: none;
    scroll-behavior: smooth;
}


/* Definice CSS proměnných */
:root {
    --primary-color: #222;
    --secondary-color: #b3d1ff;
    --accent-color: #5985C9;
    --background-color: #f0f0f0;
    --text-color: #333;
    --white-color: #fff;
    --light-blue-color: #E4F2FF;
    --font-size-large: 24px;
    --font-size-medium: 20px;
    --font-size-small: 14px;
    --padding-standard: 15px;
    --border-radius: 10px;
    --box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    --transition-duration: 0.3s;
    --hover-scale: 1.05;
    --focus-outline: 3px solid #5985C9;
}
```

---

</SwmSnippet>

&nbsp;

<SwmSnippet path="/Web/index.html" line="9">

---

&nbsp;

```html
</head>
<body>
<!-- Hlavička -->
<header>
        <div class="logo">
                <img src="images/logo.png" alt="Logo webu Questpoint">
        </div>
        <nav class="desktop-nav">
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="42">

---

&nbsp;

```css
/* Hlavička */
header {
    background-color: var(--primary-color);
    display: flex;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    padding: 1rem;
    width: 100%;
    z-index: 1000;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="368">

---

&nbsp;

```css
/* Zápatí: Stylizace zápatí webu */
footer {
    background-color: var(--secondary-color);
    width: 100vw;
    margin-left: calc(50% - 50vw);
    padding: 25px;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="599">

---

&nbsp;

```css
    /* Recenze */
    .reviews {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-auto-rows: auto;
        gap: 30px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="630">

---

&nbsp;

```css
    /* Retro sekce */
    .retro {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 30px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="649">

---

&nbsp;

```css
    footer {
        padding: 40px;
        font-size: 18px;
        line-height: 1.6;
    }

    .footer-nav {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="56">

---

&nbsp;

```css
/* Obrázek loga: Nastavení velikosti pro obrázek loga */
.logo img {
    width: 100px;
    border-radius: 25px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="413">

---

&nbsp;

```css
.footer-socials p {
    margin: 0;
    font-size: 0.9rem;
    color: var(--text-color);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/index.html" line="58">

---

&nbsp;

```html
<!-- Hlavní sekce s články -->
<main class="articles-wrapper" aria-labelledby="main-articles-heading">
        <h2 id="main-articles-heading" class="main-articles-heading">Nejnovější články</h2> <!-- Nadpis sekce nejnovějších článků -->
```

---

</SwmSnippet>

<SwmSnippet path="/Web/index.html" line="61">

---

&nbsp;

```html
    <section class="articles-container">
        <!-- Hlavní článek -->
        <section class="main-article">
            <img src="images/main-image.png" alt="Obrázek ilustrující hru Mystic Lands Online"> <!-- Obrázek hlavního článku -->
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="176">

---

&nbsp;

```css

/* Kontejner pro články: Flexbox pro umístění článků pod sebou */
.articles-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: center;
}
```

---

</SwmSnippet>

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBd2ViZGVzaWduJTNBJTNBY3ptcmF0OTU4" repo-name="webdesign"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
