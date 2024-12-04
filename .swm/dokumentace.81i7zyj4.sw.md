---
title: Dokumentace
---
# Dokumentace

## Obsah

1. Úvod
2. Požadavky na implementaci
3. Splnění požadavků na projekt

## Úvod

Náš web QuestPoint je zpravodajskou stránkou pro hráče videoher. Web se zabývá nejnovějšími hrami, novinkami z her, a obsahuje články na daná témata. Ve článcích se autoři zabývají například i spekulacemi o tajných projektech, novými aktualizacemi již zveřejněných her, nebo naopak ohlášením nových herních projektů. Mimo to se autoři na stránkách zaměřují na uživatelské recenze specifických her, nebo také slaví prostřednictvím článků důležitá data pro hráče videoher, jako například 30 let od publikace počítačové hry Warcraft. Dále web obsahuje sekce s informacemi o redakci, zásadách ochrany, kariéře a nejhlavněji předplatném k newsletteru QuestPointu s možností odběru a platby. Web je plně responzivní a přizpůsobený všem platformám.

## Požadavky na implementaci

### Popis stránek

#### Hlavní stránka

<SwmSnippet path="/Web/index.html" line="1">

---

Hlavní stránka obsahuje několik sekcí: nejnovější články, recenze, a retro články. Každá sekce je jasně oddělena a obsahuje relevantní informace a obrázky.

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

<SwmSnippet path="/Web/index.html" line="54">

---

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
```

---

</SwmSnippet>

<SwmSnippet path="/Web/index.html" line="120">

---

```
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

<SwmSnippet path="/Web/index.html" line="31">

---

Stránky jsou navrženy tak, aby byly uživatelsky přívětivé a snadno navigovatelné. Hlavní navigace je umístěna v hlavičce a obsahuje odkazy na všechny hlavní sekce webu. Pro mobilní zařízení je k dispozici <SwmToken path="/Web/menu.js" pos="3:12:14" line-data="const offScreenMenu = document.querySelector(&quot;.off-screen-menu&quot;);">`off-screen`</SwmToken> menu, které se aktivuje kliknutím na hamburger menu.

```
            <span></span>
            <span></span>
            <span></span>
        </div>
</header>
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="127">

---

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

### Návrh technologií pro frontend + backend

<SwmSnippet path="/Web/styles.css" line="1">

---

Frontend je postaven na HTML, CSS a JavaScriptu. CSS je použito pro stylizaci a responzivitu, zatímco JavaScript je použit pro interaktivní prvky, jako je hamburger menu.

```
/* Základní reset: Resetuje styly pro všechny elementy, aby se odstranily předdefinované hodnoty odlišných prohlížčů */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style: none;
    text-decoration: none;
    scroll-behavior: smooth;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="12">

---

```
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

<SwmSnippet path="/Web/styles.css" line="32">

---

```
/* Tělo dokumentu: Nastavení základního stylu pro tělo webu */
body {
    max-width: 1500px;
    margin: 0 auto;
    padding-top: 100px;
    font-family: Arial, sans-serif;
    background-color: var(--background-color);
    color: var(--text-color);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="42">

---

```
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

<SwmSnippet path="/Web/styles.css" line="56">

---

```
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

<SwmSnippet path="/Web/styles.css" line="66">

---

```
.desktop-nav {
    display: none; 
}

.desktop-search-bar {
    display: none; 
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="74">

---

```
/* Off-screen-menu: Stylizace off-screen menu */
.off-screen-menu {
    background-color: var(--primary-color);
    height: 100vh;
    width: 100%;
    max-width: 450px;
    position: fixed;
    top: 0;
    right: -450px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    font-size: 2rem;
    transition: 0.3s ease;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="91">

---

```
a {
    color: var(--white-color);
}
a:visited {
    color: var(--white-color);
}
a:hover {
    color: var(--accent-color);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="101">

---

```
.off-screen-menu ul li:nth-last-child(2) a, .off-screen-menu ul li:last-child a {
    font-size: 12px;
}

.off-screen-menu.active {
    right: 0;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="109">

---

```
.mobile-search-bar {
    width: 90%;
    margin-bottom: 20px;
    display: flex;
    position: relative;
    margin: 0 auto;

}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="118">

---

```
.mobile-search-bar input[type="text"] {
    width: 100%;
    padding: 10px;
    border-radius: var(--border-radius);
    border: none;
    outline: none;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="127">

---

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

<SwmSnippet path="/Web/styles.css" line="177">

---

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

<SwmSnippet path="/Web/styles.css" line="185">

---

```
/* Hlavní článek: Stylizace jednotlivých hlavních článků */
.main-article {
    background-color: var(--white-color);
    padding: var(--padding-standard);
    border-radius: var(--border-radius);
    box-shadow: var(--box-shadow);
    width: 100%;
    transition: transform var(--transition-duration), box-shadow var(--transition-duration);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="195">

---

```
.main-article:hover {
    transform: scale(var(--hover-scale));
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}

.main-article:focus {
    outline: var(--focus-outline);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="204">

---

```
/* Obrázek v hlavním článku */
.main-article img {
    width: 100%;
    border-radius: 5px;
    margin-bottom: 5px;
}

/* Text v hlavním článku */
.article-text {
    margin-top: 5px;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="216">

---

```
/* Kontejner pro vedlejší články: Flexbox pro umístění vedlejších článků pod sebou */
.side-articles {
    display: flex;
    flex-direction: column;
    gap: 20px;
    width: 100%;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="224">

---

```
/* Vedlejší článek: Stylizace jednotlivých vedlejších článků */
.side-article {
    background-color: var(--white-color);
    padding: var(--padding-standard);
    border-radius: var(--border-radius);
    box-shadow: var(--box-shadow);
    display: flex;
    flex-direction: column;
    min-height: 160px;
    transition: transform var(--transition-duration), box-shadow var(--transition-duration);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="236">

---

```
.side-article:hover {
    transform: scale(var(--hover-scale));
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}

.side-article:focus {
    outline: var(--focus-outline);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="245">

---

```
/* Obrázek ve vedlejším článku */
.side-article img {
    width: 100%;
    border-radius: 5px;
    margin-bottom: 5px;
    height: 150px;
    object-fit: cover;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="254">

---

```
/* Sekce recenzí: Stylizace sekce pro recenze */
.reviews {
    background-color: var(--secondary-color);
    padding: 20px;
    border-radius: 30px;
    margin: 20px;
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="265">

---

```
/* Nadpis recenzí */
.reviews h2 {
    grid-column: 1 / -1;
    margin-bottom: 20px;
    text-align: center;
    font-size: var(--font-size-medium);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="273">

---

```
/* Jednotlivá recenze: Stylizace jednotlivých recenzí */
.review {
    display: flex;
    flex-direction: column;
    gap: 15px;
    align-items: flex-start;
    background-color: var(--light-blue-color);
    padding: var(--padding-standard);
    border-radius: 5px;
    box-shadow: var(--box-shadow);
    transition: transform var(--transition-duration), box-shadow var(--transition-duration);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="286">

---

```
.review:hover {
    transform: scale(var(--hover-scale));
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}

.review:focus {
    outline: var(--focus-outline);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="295">

---

```
/* Obrázek recenze */
.review img {
    width: 80px;
    height: 80px;
    border-radius: 5px;
}

/* Text recenze */
.review-text {
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: left;
    font-size: var(--font-size-small);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="311">

---

```
/* Retro sekce: Stylizace sekce s retro obsahem */
.retro {
    background-color: var(--accent-color);
    padding: 20px;
    border-radius: 30px;
    margin: 20px;
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
    text-align: center;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="323">

---

```
/* Nadpis retro sekce */
.retro h2 {
    grid-column: 1 / -1;
    margin-bottom: 20px;
    text-align: center;
    font-size: var(--font-size-medium);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="331">

---

```
/* Retro článek: Stylizace jednotlivých retro článků */
.retro-article {
    display: flex;
    flex-direction: column;
    gap: 10px;
    background-color: var(--light-blue-color);
    padding: var(--padding-standard);
    border-radius: 5px;
    box-shadow: var(--box-shadow);
    text-align: center;
    transition: transform var(--transition-duration), box-shadow var(--transition-duration);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="344">

---

```
.retro-article:hover {
    transform: scale(var(--hover-scale));
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}

.retro-article:focus {
    outline: var(--focus-outline);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="353">

---

```
/* Obrázek v retro článku */
.retro-article img {
    width: 100%;
    height: auto;
    border-radius: 8px;
}

/* Text v retro článku */
.retro-text {
    background-color: var(--light-blue-color);
    padding: 10px;
    border-radius: 8px;
    margin-top: auto;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="368">

---

```
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

<SwmSnippet path="/Web/styles.css" line="381">

---

```
/* Navigace v zápatí: Grid pro odkazy v zápatí */
.footer-nav {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
    max-width: 500px;
    margin-bottom: 15px;
    text-align: center;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="391">

---

```
/* Odkazy v zápatí */
.footer-nav a {
    color: var(--text-color);
    text-decoration: none;
    font-weight: bold;
    transition: color var(--transition-duration);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="399">

---

```
.footer-nav a:hover,
.footer-nav a:focus {
    color: var(--primary-color);
    outline: var(--focus-outline);
}

/* Sociální odkazy v zápatí */
.footer-socials {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="413">

---

```
.footer-socials p {
    margin: 0;
    font-size: 0.9rem;
    color: var(--text-color);
}

/* Ikonky sociálních sítí */
.social-icons {
    display: flex;
    justify-content: center;
    gap: 15px;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="426">

---

```
.social-icons a img {
    width: 30px;
    height: 30px;
}

/* Text v zápatí */
footer p:last-child {
    margin-top: 15px;
    font-size: 0.8rem;
    color: var(--text-color);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="438">

---

```
/* Sociální ikonky: Flexbox pro zarovnání ikonek */
.social-icons {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 20px;
    align-items: center;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="447">

---

```
/* Stylizace jednotlivých odkazů sociálních sítí */
.social-icons a {
    width: 30px;
    height: 30px;
    display: block;
    transition: transform var(--transition-duration);
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="455">

---

```
.social-icons a:hover,
.social-icons a:focus {
    transform: scale(var(--hover-scale));
    outline: var(--focus-outline);
}

.social-icons a img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="467">

---

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

<SwmSnippet path="/Web/styles.css" line="478">

---

```
    .main-article,
    .main-article, .side-article {
        width: 100%;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="483">

---

```
    .reviews {
        grid-template-columns: 1fr 1fr;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="487">

---

```
    .retro {
        grid-template-columns: 1fr 1fr 1fr;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="491">

---

```
    .review img {
        width: 60px;
        height: 60px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="496">

---

```
    .footer-nav {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="501">

---

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

<SwmSnippet path="/Web/styles.css" line="512">

---

```
    .logo img {
        position: relative;
        left: 0;
        top: 0;
        transform: none;
        border-radius: 25px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="520">

---

```
    .desktop-nav {
        display: flex;
        gap: 20px; 
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="525">

---

```
    .desktop-nav ul {
        display: flex;
        list-style: none;
        gap: 20px; 
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="531">

---

```
    .desktop-nav a {
        color: var(--white-color);
        text-decoration: none;
        font-size: var(--font-size-medium);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="537">

---

```
    .desktop-nav a:hover {
        color: var(--accent-color);
    }
    .desktop-search-bar {
        display: flex;
        margin-left: auto;
        position: relative;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="546">

---

```
    .desktop-search-bar input[type="text"] {
        width: 100%;
        padding: 10px;
        border-radius: var(--border-radius);
        border: none;
        outline: none;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="554">

---

```
    .main-articles-heading {
        font-size: 36px;
        padding-top: 60px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="559">

---

```
    .articles-wrapper {
        margin: 0 auto;
        padding: 0 15px;
        max-width: 100%;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="565">

---

```
    .articles-container {
        display: grid;
        grid-template-columns: 2fr 1fr;
        gap: 30px;
        align-items: stretch;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="572">

---

```
    .main-article {
        font-size: 22px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="576">

---

```
    .side-articles {
        display: grid;
        grid-template-rows: 1fr 1fr;
        gap: 30px;
        align-items: stretch;
        height: 100%;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="584">

---

```
    .side-article {
        display: flex;
        width: 100%;
        background-color: #fff;
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        font-size: 18px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="593">

---

```
    .side-article img {
        width: 100%;
        height: auto;
        border-radius: var(--border-radius);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="599">

---

```
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

<SwmSnippet path="/Web/styles.css" line="607">

---

```
    .reviews h2 {
        font-size: 28px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="611">

---

```
    .review-text {
        font-size: 22px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="615">

---

```
    .review {
        padding: 20px;
        background-color: #E4F2FF;
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        font-size: 18px;
        line-height: 1.5;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="624">

---

```
    .review img {
        width: 100px;
        height: 100px;
        border-radius: 5px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="630">

---

```
    /* Retro sekce */
    .retro {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 30px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="637">

---

```
    .retro h2 {
        font-size: 28px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="641">

---

```
    .retro-article {
        padding: 20px;
        background-color: #E4F2FF;
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        line-height: 1.5;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="649">

---

```
    footer {
        padding: 40px;
        font-size: 18px;
        line-height: 1.6;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="655">

---

```
    .footer-nav {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/menu.js" line="1">

---

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

### Zdůvodnění

Použití HTML, CSS a JavaScriptu zajišťuje širokou kompatibilitu a snadnou údržbu. Responzivní design zajišťuje, že web je přístupný na všech zařízeních.

### Nasazení – hosting, technologie, údržba, analytika, marketing

Web je hostován na platformě, která podporuje HTML, CSS a JavaScript. Údržba zahrnuje pravidelné aktualizace obsahu a kontrolu funkčnosti. Analytika je implementována pomocí nástrojů jako Google Analytics pro sledování návštěvnosti a chování uživatelů.

### Využití AI nástrojů

AI nástroje nebyly v tomto projektu využity.

## Splnění požadavků na projekt

### Seznam požadavků

1. Responzivní design
2. Navigace
3. Obsahové sekce
4. Interaktivní prvky

### Popis, jak bylo splněno

#### Responzivní design

<SwmSnippet path="/Web/styles.css" line="467">

---

Web je plně responzivní díky použití CSS media queries.

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

<SwmSnippet path="/Web/styles.css" line="478">

---

```
    .main-article,
    .main-article, .side-article {
        width: 100%;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="483">

---

```
    .reviews {
        grid-template-columns: 1fr 1fr;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="487">

---

```
    .retro {
        grid-template-columns: 1fr 1fr 1fr;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="491">

---

```
    .review img {
        width: 60px;
        height: 60px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="496">

---

```
    .footer-nav {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
}
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="501">

---

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

<SwmSnippet path="/Web/styles.css" line="512">

---

```
    .logo img {
        position: relative;
        left: 0;
        top: 0;
        transform: none;
        border-radius: 25px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="520">

---

```
    .desktop-nav {
        display: flex;
        gap: 20px; 
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="525">

---

```
    .desktop-nav ul {
        display: flex;
        list-style: none;
        gap: 20px; 
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="531">

---

```
    .desktop-nav a {
        color: var(--white-color);
        text-decoration: none;
        font-size: var(--font-size-medium);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="537">

---

```
    .desktop-nav a:hover {
        color: var(--accent-color);
    }
    .desktop-search-bar {
        display: flex;
        margin-left: auto;
        position: relative;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="546">

---

```
    .desktop-search-bar input[type="text"] {
        width: 100%;
        padding: 10px;
        border-radius: var(--border-radius);
        border: none;
        outline: none;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="554">

---

```
    .main-articles-heading {
        font-size: 36px;
        padding-top: 60px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="559">

---

```
    .articles-wrapper {
        margin: 0 auto;
        padding: 0 15px;
        max-width: 100%;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="565">

---

```
    .articles-container {
        display: grid;
        grid-template-columns: 2fr 1fr;
        gap: 30px;
        align-items: stretch;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="572">

---

```
    .main-article {
        font-size: 22px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="576">

---

```
    .side-articles {
        display: grid;
        grid-template-rows: 1fr 1fr;
        gap: 30px;
        align-items: stretch;
        height: 100%;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="584">

---

```
    .side-article {
        display: flex;
        width: 100%;
        background-color: #fff;
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        font-size: 18px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="593">

---

```
    .side-article img {
        width: 100%;
        height: auto;
        border-radius: var(--border-radius);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="599">

---

```
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

<SwmSnippet path="/Web/styles.css" line="607">

---

```
    .reviews h2 {
        font-size: 28px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="611">

---

```
    .review-text {
        font-size: 22px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="615">

---

```
    .review {
        padding: 20px;
        background-color: #E4F2FF;
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        font-size: 18px;
        line-height: 1.5;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="624">

---

```
    .review img {
        width: 100px;
        height: 100px;
        border-radius: 5px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="630">

---

```
    /* Retro sekce */
    .retro {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 30px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="637">

---

```
    .retro h2 {
        font-size: 28px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="641">

---

```
    .retro-article {
        padding: 20px;
        background-color: #E4F2FF;
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        line-height: 1.5;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="649">

---

```
    footer {
        padding: 40px;
        font-size: 18px;
        line-height: 1.6;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/Web/styles.css" line="655">

---

```
    .footer-nav {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
}
```

---

</SwmSnippet>

#### Navigace

<SwmSnippet path="/Web/index.html" line="1">

---

Navigace je implementována v hlavičce a <SwmToken path="/Web/menu.js" pos="3:12:14" line-data="const offScreenMenu = document.querySelector(&quot;.off-screen-menu&quot;);">`off-screen`</SwmToken> menu pro mobilní zařízení.

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

<SwmSnippet path="/Web/styles.css" line="127">

---

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

#### Obsahové sekce

<SwmSnippet path="/Web/index.html" line="1">

---

Web obsahuje sekce pro nejnovější články, recenze a retro články.

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

<SwmSnippet path="/Web/index.html" line="54">

---

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
```

---

</SwmSnippet>

<SwmSnippet path="/Web/index.html" line="120">

---

```
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

#### Interaktivní prvky

<SwmSnippet path="/Web/styles.css" line="127">

---

Interaktivní prvky zahrnují hamburger menu pro mobilní zařízení.

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

Tímto je dokumentace kompletní a pokrývá všechny požadavky na projekt.

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBd2ViZGVzaWduJTNBJTNBY3ptcmF0OTU4" repo-name="webdesign"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
