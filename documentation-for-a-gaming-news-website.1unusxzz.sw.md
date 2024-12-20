---
title: Documentation for a gaming news website
---
# Obsah

1. Úvod
2. Prezentace webové stránky
3. Požadavky na implementaci
4. Popis stránky
5. Jak by se stránky měly chovat
6. Technologický design pro frontend + backend
7. Odpovědnost nasazení
8. Použití nástrojů AI
9. Splnění požadavků projektu

# Úvod

Tento dokument vás provede implementací herního zpravodajského webu. Web je navržen tak, aby poskytoval nejnovější zprávy, recenze a retro obsah související s hraním. Má responzivní design, aby byl přístupný na různých zařízeních. Budeme se zabývat:&nbsp;

1. Prezentací webu,
2. Požadavky na implementaci,
3. Splněním projektových požadavků

# Prezentace webu

Náš web QuestPoint je zpravodajskou stránkou pro hráče videoher. Web se zabývá nejnovějšími hrami, novinkami z her, a obsahuje články na daná témata. Ve článcích se autoři zabývají například i spekulacemi o tajných projektech, novými aktualizacemi již zveřejněných her, nebo naopak ohlášením nových herních projektů. Mimo to se autoři na stránkách zaměřují na uživatelské recenze specifických her, nebo také slaví prostřednictvím článků důležitá data pro hráče videoher, jako například 30 let od publikace počítačové hry Warcraft. Dále web obsahuje sekce s informacemi o redakci, zásadách ochrany, kariéře a nejhlavněji předplatném k newsletteru QuestPointu s možností odběru a platby. Web je plně responzivní a přizpůsobený všem platformám, a nabízí uživatelsky přístupné rozhraní, které je přístupné a konzistentní.

# Požadavky na implementaci

## Popis stránek

Webová stránka se skládá z několika klíčových sekcí:

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
- sekce s retrospektivou
- Zápatí s navigací a odkazy na sociální sítě

### Záhlaví

<SwmSnippet path="/QuestPoint/styles.css" line="36">

---

Záhlaví je připevněné na vrchu stránky a obsahuje logo webové stránky, včetně burger menu pro mobilní navigaci.

```
/* Hlavička: Stylizace hlavičky, aby byla pevná, zůstavala nahoře a obsahovala logo a menu */
header {
    background-color: var(--primary-color);
    color: var(--white-color);
    padding: 40px;
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
}
```

---

</SwmSnippet>

### Sekce Hlavní články

<SwmSnippet path="/QuestPoint/index.html" line="23">

---

Tato sekce obsahuje nejnovější články s hlavním článkem zvýrazněným na vrchu, a vedlejšími články uvedenými níže

```
<!-- Hlavní sekce s články -->
<main class="articles-wrapper" aria-labelledby="main-articles-heading">
    <div class="main-articles-heading-container">
        <h2 id="main-articles-heading" class="main-articles-heading">Nejnovější články</h2> <!-- Nadpis sekce nejnovějších článků -->
    </div>
    <section class="articles-container">
        <!-- Hlavní článek -->
        <section class="main-article">
            <img src="images/main-image.png" alt="Mystic Lands Online"> <!-- Obrázek hlavního článku -->
            <div class="article-text">
                <h2>Spekuluje se o tajném projektu – Mystic Lands Online: Nové MMORPG?</h2> <!-- Nadpis hlavního článku -->
                <p>Kateřina Novotná 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
        <!-- Vedlejší články -->
        <section class="side-articles">
            <div class="side-article">
                <img src="images/side-image1.png" alt="Realm of Eternity Update"> <!-- Obrázek vedlejšího článku -->
                <h3>Nový update pro populární RPG hru Realm of Eternity přináší revoluční AI společníky!</h3> <!-- Nadpis vedlejšího článku -->
                <p>Zuzana Veselá 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
            <div class="side-article">
                <img src="images/side-image2.png" alt="Shadows of Moscow"> <!-- Obrázek vedlejšího článku -->
                <h3>Metro: Shadows of Moscow – Návrat do hlubin podzemí v novém temném dílu?</h3> <!-- Nadpis vedlejšího článku -->
                <p>Petr Král 14.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
    </section>
</main>
```

---

</SwmSnippet>

### Sekce Recenze

<SwmSnippet path="/QuestPoint/index.html" line="53">

---

Sekce recenzí ukazuje individuální recenze ke hrám s obrázky a textem, včetně informací o autorech a data.

```
<!-- Sekce recenzí -->
<section class="reviews" aria-labelledby="reviews-heading">
    <h2 id="reviews-heading">Recenze</h2> <!-- Nadpis sekce recenzí -->
    <!-- Jednotlivé recenze -->
    <div class="review">
        <img src="images/lifeisstrange.png" alt="Life is Strange"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Life is Strange</h3> <!-- Titulek recenze -->
            <p>Petr Král 8.10.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/eldenring.png" alt="Elden Ring"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Elden Ring</h3> <!-- Titulek recenze -->
            <p>Petr Král 6.5.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/farming simulator.png" alt="Farming Simulator 2025"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Farming Simulator 2025</h3> <!-- Titulek recenze -->
            <p>Zuzana Veselá 11.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/cs.jpeg" alt="Cities Skylines 2"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Cities Skylines 2 – Město vašich snů (a nočních můr)</h3> <!-- Titulek recenze -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
```

---

</SwmSnippet>

### Sekce Pohled do minulosti

<SwmSnippet path="/QuestPoint/index.html" line="87">

---

Sekce retrospekce zvýrazňuje články o klasických hrách a jejich vlivu na herní průmysl, historických milnících a komentářů.

```
<!-- Retro sekce -->
<section class="retro" aria-labelledby="retro-heading">
    <h2 id="retro-heading">Pohled do minulosti</h2> <!-- Nadpis retro sekce -->
    <!-- Jednotlivé retro články -->
    <div class="retro-article">
        <img src="images/wolfenstein.png" alt="Wolfenstein"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>Wolfenstein: Průkopník herního průmyslu a legenda akčních her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 19.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/hl.png" alt="Half-Life"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>20 let Half-Life: Jak Gordon Freeman navždy změnil svět her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/wow.png" alt="Warcraft"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>30 let Warcraftu: Jak se zrodila legenda herního světa</h3> <!-- Titulek retro článku -->
            <p>Zuzana Veselá 12.12.2023</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
</section>
```

---

</SwmSnippet>

### Zápatí

<SwmSnippet path="/QuestPoint/index.html" line="114">

---

Zápatí obsauje navigační odkazy a odkazy na sociální sítě v ikonách.

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
            <a href="#" aria-label="YouTube"><img src="images/yt.png" alt="YouTube" aria-hidden="true"></a>
            <a href="#" aria-label="X"><img src="images/x.png" alt="X" aria-hidden="true"></a>
            <a href="#" aria-label="Instagram"><img src="images/ig.png" alt="Instagram" aria-hidden="true"></a>
            <a href="#" aria-label="Facebook"><img src="images/fb.png" alt="Facebook" aria-hidden="true"></a>
        </div>
    </div>
    <p>Studentský projekt</p> <!-- Poznámka v patice -->
</footer>
</body>
</html>
```

---

</SwmSnippet>

## Chování stránek

Webová stránka je navržena tak, aby byla responzivní a vypadala správně na různých velikostech obrazovky. Rozložení se přizpůsobuje šířce zařízení a poskytuje optimální zobrazení.

&nbsp;

### Responzivní design pro tablety

<SwmSnippet path="/QuestPoint/styles.css" line="390">

---

```
/* Responzivita: Styl pro tablety od 768px do 1024px */
@media (min-width: 768px) and (max-width: 1024px) {
    header {
        padding: 30px;
    }

    .logo img {
        width: 80px;
    }
```

---

</SwmSnippet>

### Responzivní design pro větší obrazovky

<SwmSnippet path="/QuestPoint/styles.css" line="431">

---

```
/* Responzivita: Styl pro obrazovky od 1025px do 1440px */
@media (min-width: 1025px) and (max-width: 1440px) {
    header {
        padding: 40px 80px;
    }

    .logo img {
        width: 130px;
    }
```

---

</SwmSnippet>

## Technologický design pro frontend + backend

Frontend je postaven pomocí HTML a CSS, s důrazem na responzivní design. Backend není v tomto dokumentu pokryt, protože projekt se zaměřuje na implementaci frontendu.

## Odpovědnost

Návrhové volby zajistí konzistentní a uživatelsky přívětivý zážitek na všech zařízeních. Použití CSS proměnných umožňuje snadné vytváření motivů a údržbu.

## Nasazení

Webová stránka může být hostována na libovolné službě pro hostování statických stránek. Pravidelná údržba by měla zahrnovat aktualizaci obsahu a zajištění kompatibility s novými zařízeními a prohlížeči. Analytické nástroje lze integrovat pro sledování zapojení uživatelů.

## Použití nástrojů AI

V této implementaci nebyly explicitně použity AI nástroje. Nicméně, nástroje jako služby pro optimalizaci obrázků by mohly být zváženy pro budoucí vylepšení.

# Splnění požadavků projektu

## Seznam požadavků

1. Responzivní design
2. Jasná sekce obsahu
3. Konzístentní stylování
4. Přístupnostní funkce

## Popis splnění

### Responzivní design

<SwmSnippet path="/QuestPoint/styles.css" line="390">

---

Webová stránka používá media queries k přizpůsobení rozvržení na základě velikosti obrazovky.

```
/* Responzivita: Styl pro tablety od 768px do 1024px */
@media (min-width: 768px) and (max-width: 1024px) {
    header {
        padding: 30px;
    }

    .logo img {
        width: 80px;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/styles.css" line="431">

---

```
/* Responzivita: Styl pro obrazovky od 1025px do 1440px */
@media (min-width: 1025px) and (max-width: 1440px) {
    header {
        padding: 40px 80px;
    }

    .logo img {
        width: 130px;
    }
```

---

</SwmSnippet>

### Jasná sekce obsahu

<SwmSnippet path="/QuestPoint/index.html" line="23">

---

Webová stránka je rozdělena do jednotlivých sekcí: záhlaví, hlavní články, recenze, retro obsah a zápatí.

```
<!-- Hlavní sekce s články -->
<main class="articles-wrapper" aria-labelledby="main-articles-heading">
    <div class="main-articles-heading-container">
        <h2 id="main-articles-heading" class="main-articles-heading">Nejnovější články</h2> <!-- Nadpis sekce nejnovějších článků -->
    </div>
    <section class="articles-container">
        <!-- Hlavní článek -->
        <section class="main-article">
            <img src="images/main-image.png" alt="Mystic Lands Online"> <!-- Obrázek hlavního článku -->
            <div class="article-text">
                <h2>Spekuluje se o tajném projektu – Mystic Lands Online: Nové MMORPG?</h2> <!-- Nadpis hlavního článku -->
                <p>Kateřina Novotná 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
        <!-- Vedlejší články -->
        <section class="side-articles">
            <div class="side-article">
                <img src="images/side-image1.png" alt="Realm of Eternity Update"> <!-- Obrázek vedlejšího článku -->
                <h3>Nový update pro populární RPG hru Realm of Eternity přináší revoluční AI společníky!</h3> <!-- Nadpis vedlejšího článku -->
                <p>Zuzana Veselá 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
            <div class="side-article">
                <img src="images/side-image2.png" alt="Shadows of Moscow"> <!-- Obrázek vedlejšího článku -->
                <h3>Metro: Shadows of Moscow – Návrat do hlubin podzemí v novém temném dílu?</h3> <!-- Nadpis vedlejšího článku -->
                <p>Petr Král 14.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
    </section>
</main>
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/index.html" line="53">

---

```
<!-- Sekce recenzí -->
<section class="reviews" aria-labelledby="reviews-heading">
    <h2 id="reviews-heading">Recenze</h2> <!-- Nadpis sekce recenzí -->
    <!-- Jednotlivé recenze -->
    <div class="review">
        <img src="images/lifeisstrange.png" alt="Life is Strange"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Life is Strange</h3> <!-- Titulek recenze -->
            <p>Petr Král 8.10.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/eldenring.png" alt="Elden Ring"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Elden Ring</h3> <!-- Titulek recenze -->
            <p>Petr Král 6.5.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/farming simulator.png" alt="Farming Simulator 2025"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Farming Simulator 2025</h3> <!-- Titulek recenze -->
            <p>Zuzana Veselá 11.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/cs.jpeg" alt="Cities Skylines 2"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Cities Skylines 2 – Město vašich snů (a nočních můr)</h3> <!-- Titulek recenze -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/index.html" line="87">

---

```
<!-- Retro sekce -->
<section class="retro" aria-labelledby="retro-heading">
    <h2 id="retro-heading">Pohled do minulosti</h2> <!-- Nadpis retro sekce -->
    <!-- Jednotlivé retro články -->
    <div class="retro-article">
        <img src="images/wolfenstein.png" alt="Wolfenstein"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>Wolfenstein: Průkopník herního průmyslu a legenda akčních her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 19.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/hl.png" alt="Half-Life"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>20 let Half-Life: Jak Gordon Freeman navždy změnil svět her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/wow.png" alt="Warcraft"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>30 let Warcraftu: Jak se zrodila legenda herního světa</h3> <!-- Titulek retro článku -->
            <p>Zuzana Veselá 12.12.2023</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
</section>
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/index.html" line="114">

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
            <a href="#" aria-label="YouTube"><img src="images/yt.png" alt="YouTube" aria-hidden="true"></a>
            <a href="#" aria-label="X"><img src="images/x.png" alt="X" aria-hidden="true"></a>
            <a href="#" aria-label="Instagram"><img src="images/ig.png" alt="Instagram" aria-hidden="true"></a>
            <a href="#" aria-label="Facebook"><img src="images/fb.png" alt="Facebook" aria-hidden="true"></a>
        </div>
    </div>
    <p>Studentský projekt</p> <!-- Poznámka v patice -->
</footer>
</body>
</html>
```

---

</SwmSnippet>

### Konzistentní stylovaní

<SwmSnippet path="/QuestPoint/styles.css" line="1">

---

CSS proměnné se používají k udržování konzistentního barevného schématu a typografie na celém webu.

```
/* Základní reset: Resetuje styly pro všechny elementy, aby se odstranily předdefinované hodnoty odlišných prohlížčů */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
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

### Přístupnostní funkce

<SwmSnippet path="/QuestPoint/index.html" line="1">

---

ARIA štítky a role i alternativní popisky se používají k zlepšení přístupnosti.

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
    <div class="logo-container">
        <div class="logo">
            <img src="images/logo.png" alt="Questpoint Logo"> <!-- Logo webu -->
        </div>
    </div>
    <div class="burger-menu" role="button" aria-label="Toggle navigation">
        <img src="images/burgermenu.png" alt="Menu" aria-hidden="true"> <!-- Burger menu pro mobilní navigaci -->
    </div>
</header>
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/index.html" line="23">

---

```
<!-- Hlavní sekce s články -->
<main class="articles-wrapper" aria-labelledby="main-articles-heading">
    <div class="main-articles-heading-container">
        <h2 id="main-articles-heading" class="main-articles-heading">Nejnovější články</h2> <!-- Nadpis sekce nejnovějších článků -->
    </div>
    <section class="articles-container">
        <!-- Hlavní článek -->
        <section class="main-article">
            <img src="images/main-image.png" alt="Mystic Lands Online"> <!-- Obrázek hlavního článku -->
            <div class="article-text">
                <h2>Spekuluje se o tajném projektu – Mystic Lands Online: Nové MMORPG?</h2> <!-- Nadpis hlavního článku -->
                <p>Kateřina Novotná 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
        <!-- Vedlejší články -->
        <section class="side-articles">
            <div class="side-article">
                <img src="images/side-image1.png" alt="Realm of Eternity Update"> <!-- Obrázek vedlejšího článku -->
                <h3>Nový update pro populární RPG hru Realm of Eternity přináší revoluční AI společníky!</h3> <!-- Nadpis vedlejšího článku -->
                <p>Zuzana Veselá 15.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
            <div class="side-article">
                <img src="images/side-image2.png" alt="Shadows of Moscow"> <!-- Obrázek vedlejšího článku -->
                <h3>Metro: Shadows of Moscow – Návrat do hlubin podzemí v novém temném dílu?</h3> <!-- Nadpis vedlejšího článku -->
                <p>Petr Král 14.11.2024</p> <!-- Informace o autorovi a datu -->
            </div>
        </section>
    </section>
</main>
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/index.html" line="53">

---

```
<!-- Sekce recenzí -->
<section class="reviews" aria-labelledby="reviews-heading">
    <h2 id="reviews-heading">Recenze</h2> <!-- Nadpis sekce recenzí -->
    <!-- Jednotlivé recenze -->
    <div class="review">
        <img src="images/lifeisstrange.png" alt="Life is Strange"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Life is Strange</h3> <!-- Titulek recenze -->
            <p>Petr Král 8.10.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/eldenring.png" alt="Elden Ring"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Elden Ring</h3> <!-- Titulek recenze -->
            <p>Petr Král 6.5.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/farming simulator.png" alt="Farming Simulator 2025"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Farming Simulator 2025</h3> <!-- Titulek recenze -->
            <p>Zuzana Veselá 11.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="review">
        <img src="images/cs.jpeg" alt="Cities Skylines 2"> <!-- Obrázek recenze -->
        <div class="review-text">
            <h3>Cities Skylines 2 – Město vašich snů (a nočních můr)</h3> <!-- Titulek recenze -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/index.html" line="87">

---

```
<!-- Retro sekce -->
<section class="retro" aria-labelledby="retro-heading">
    <h2 id="retro-heading">Pohled do minulosti</h2> <!-- Nadpis retro sekce -->
    <!-- Jednotlivé retro články -->
    <div class="retro-article">
        <img src="images/wolfenstein.png" alt="Wolfenstein"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>Wolfenstein: Průkopník herního průmyslu a legenda akčních her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 19.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/hl.png" alt="Half-Life"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>20 let Half-Life: Jak Gordon Freeman navždy změnil svět her</h3> <!-- Titulek retro článku -->
            <p>Kateřina Novotná 14.11.2024</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
    <div class="retro-article">
        <img src="images/wow.png" alt="Warcraft"> <!-- Obrázek retro článku -->
        <div class="retro-text">
            <h3>30 let Warcraftu: Jak se zrodila legenda herního světa</h3> <!-- Titulek retro článku -->
            <p>Zuzana Veselá 12.12.2023</p> <!-- Informace o autorovi a datu -->
        </div>
    </div>
</section>
```

---

</SwmSnippet>

<SwmSnippet path="/QuestPoint/index.html" line="114">

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
            <a href="#" aria-label="YouTube"><img src="images/yt.png" alt="YouTube" aria-hidden="true"></a>
            <a href="#" aria-label="X"><img src="images/x.png" alt="X" aria-hidden="true"></a>
            <a href="#" aria-label="Instagram"><img src="images/ig.png" alt="Instagram" aria-hidden="true"></a>
            <a href="#" aria-label="Facebook"><img src="images/fb.png" alt="Facebook" aria-hidden="true"></a>
        </div>
    </div>
    <p>Studentský projekt</p> <!-- Poznámka v patice -->
</footer>
</body>
</html>
```

---

</SwmSnippet>

# Kódový vzorek/řádkový odkaz/snímek obrazovky

Pro podrobný pohled na implementaci se odkazujte na kompletní soubory CSS a HTML poskytnuté výše ve výňatcích.

