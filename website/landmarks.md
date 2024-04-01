---
layout: page
title: Semantiek
active: tutorials
---

De meeste pagina's hebben een visuele structuur met een blok inhoud (typisch logo, navigatie, zoekfunctie, enz.) bovenaan, een hoofdgedeelte van de inhoud, een voettekst, en soms zijbalken met gerelateerde informatie. Landmarks zoals `<header>`, `<nav>`, `<main>`, `<aside>`, en `<footer>` definiëren programmatisch de essentiële semantische structuur van een pagina. Gebruikers van schermlezers kunnen gemakkelijk navigeren tussen deze belangrijke paginagebieden. Hetzelfde kan worden bereikt met equivalente ARIA-landmark rollen. De termen "region" en "landmark" worden vaak synoniem gebruikt.

Wij raden aan dat elke pagina één `<main>` element heeft (of `<div role="main">`). De meeste pagina's hebben ook maar één `<header>` en `<footer>`. `<header>`, `<main>`, en `<footer>` moeten directe children van `<body>` zijn om te worden getoond aan screenreaders. Ze kunnen niet in andere container-elementen worden genest. Alle pagina-inhoud moet in een regio staan.

De `<nav>`-regio moet gewoonlijk alleen worden toegepast op de primaire navigatie. Het is niet nuttig om elke link of lijst van links in een `<nav>`-element te verpakken. Aangezien gebruikers meestal verwachten dat `<footer>`-regio's links bevatten, is het ook niet nodig om `<nav>` binnen `<footer>` te gebruiken.

Op sites met veel inhoud kan het handig zijn om een tweede `<nav>` op binnenpagina's te gebruiken voor secundaire navigatie - bijvoorbeeld navigatie binnen een bepaalde inhoudscategorie of afdeling. In dat geval moet elk `<nav>`-element worden onderscheiden met een `aria-label`; bijvoorbeeld `<nav aria-label="Primary Navigation">`. Als de `<nav>` begint met een koptekst, kan `aria-labelledby` worden gebruikt om de `<nav>` te labelen met die koptekst.

`<section>` en `<article>` kunnen nuttig zijn om blokken inhoud te bevatten. Ze functioneren niet als regio's tenzij ze een `aria-label` krijgen, maar dit is zelden nuttig.

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/javascript/">WebAim's pagina over semantiek</a>.

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>