---
layout: page
title: Semantiek
active: tutorials
---

De grondleggers van HTML – deeltjesfysici die documenten uitwisselden – hadden geen interesse in mooie plaatjes. Ze wilden een World Wide Web maken van machinaal leesbare pagina's die in elk systeem en elke browser konden worden weergegeven, inclusief die welke tekst spraken voor visueel gehandicapte gebruikers. Het resultaat was een bibliotheek van documenten die alleen machines (of deeltjesfysici) zouden willen lezen.

Naarmate het Web groeide, leidde het gebrek aan visuele nadruk ertoe dat ontwerpers zich druk maakten om pagina's er op een bepaalde manier uit te laten zien, wat browserontwikkelaars weer onder druk zette om eigen visuele en opmaakkenmerken en extensies te maken die afweken van de HTML-standaarden.

CSS vulde het gat door ontwerpers in staat te stellen visuele presentatie te definiëren zonder de onderliggende semantiek en structuur aan te tasten, waar screenreaders en andere ondersteunende technologieën in de eerste plaats op vertrouwen.

## Landmarks

De meeste pagina's hebben een visuele structuur met een blok inhoud (typisch logo, navigatie, zoekfunctie, enz.) bovenaan, een hoofdgedeelte van de inhoud, een voettekst, en soms zijbalken met gerelateerde informatie. Landmarks zoals `<header>`, `<nav>`, `<main>`, `<aside>`, en `<footer>` definiëren programmatisch de essentiële semantische structuur van een pagina. Gebruikers van schermlezers kunnen gemakkelijk navigeren tussen deze belangrijke paginagebieden. Hetzelfde kan worden bereikt met equivalente ARIA-landmark rollen. De termen "region" en "landmark" worden vaak synoniem gebruikt.

Wij raden aan dat elke pagina één `<main>` element heeft (of `<div role="main">`). De meeste pagina's hebben ook maar één `<header>` en `<footer>`. `<header>`, `<main>`, en `<footer>` moeten directe children van `<body>` zijn om te worden getoond aan screenreaders. Ze kunnen niet in andere container-elementen worden genest. Alle pagina-inhoud moet in een regio staan.

De `<nav>`-regio moet gewoonlijk alleen worden toegepast op de primaire navigatie. Het is niet nuttig om elke link of lijst van links in een `<nav>`-element te verpakken. Aangezien gebruikers meestal verwachten dat `<footer>`-regio's links bevatten, is het ook niet nodig om `<nav>` binnen `<footer>` te gebruiken.

Op sites met veel inhoud kan het handig zijn om een tweede `<nav>` op binnenpagina's te gebruiken voor secundaire navigatie - bijvoorbeeld navigatie binnen een bepaalde inhoudscategorie of afdeling. In dat geval moet elk `<nav>`-element worden onderscheiden met een `aria-label`; bijvoorbeeld `<nav aria-label="Primary Navigation">`. Als de `<nav>` begint met een koptekst, kan `aria-labelledby` worden gebruikt om de `<nav>` te labelen met die koptekst.

`<section>` en `<article>` kunnen nuttig zijn om blokken inhoud te bevatten. Ze functioneren niet als regio's tenzij ze een `aria-label` krijgen, maar dit is zelden nuttig.

## Koppen

Een kop beschrijft de inhoud die erop volgt, net als een krantenkop. Als ze op een nieuwe pagina komen, gaan slechtziende gebruikers naar de koppen toe om snel te vinden wat ze willen op de pagina. Gebruikers van schermlezers en andere ondersteunende technologie kunnen ook van kop naar kop springen.

Koppen vormen een overzicht van de pagina, vergelijkbaar met het overzicht van een scriptie of een inhoudsopgave. De `<h1>` beschrijft de pagina in zijn geheel (en zou vergelijkbaar moeten zijn met de `<title>` van de pagina). Een pagina zou meestal maar één `<h1>` moeten hebben. De koppen `<h2>` tot en met `<h6>` vertegenwoordigen een toenemende mate van "inspringing" in onze conceptuele "outline". Als zodanig is het niet zinvol om titelniveaus over te slaan, zoals van `<h2>` naar `<h4>`, naar beneden op de pagina. Hier is een voorbeeld van inhoudshiërarchie met overeenkomstige koptekstniveaus: [voorbeeld maken]

### Koppen invoeren

Koppen moeten gebruik maken van heading-tags. Schermlezers en ondersteunende technologieën vertrouwen op heading elementen (`<h1>` - `<h6>`) om kopteksten te identificeren. Tekst die alleen groot, vet of benadrukt is, wordt niet geïnterpreteerd als een kop, tenzij de markup `<h1>` - `<h6>` wordt gebruikt. 

Gebruik koppen alleen als ze de volgende inhoud weergeven. Om tekst die geen koptekst is te benadrukken, gebruik je stijlen – geen koptags – om visuele resultaten te bereiken. 

## Lijsten

HTML-lijsten geven ook een hiërarchische inhoudsstructuur weer.

- Ongeordende lijsten (`<ul>`) zijn voor inhoud die geen volgorde of belang heeft. Lijstitems worden meestal voorafgegaan door een opsommingsteken, hoewel dit indien gewenst met CSS kan worden opgeheven.

- Geordende lijsten (`<ol>`) suggereren volgorde, ordening of rangschikking. Lijstitems worden meestal voorafgegaan door een cijfer, letter, Romeins cijfer, enz.

- Description lists (`<dl>`) zijn voor sleutel:waarde paren, zoals termen en definities in een woordenlijst of vragen en antwoorden in een FAQ. Termen (`<dt>`) zijn meestal vetgedrukt, terwijl beschrijvingen (`<dd>`) meestal normaal gewicht hebben en ingesprongen zijn.

Lijststructuren moeten worden gebruikt waar een logische lijst aanwezig is, en nergens anders. Maak niet alleen iets wat op een lijst lijkt door elke alinea te beginnen met een opsommingsteken. Pas ook geen lijststructuur toe op elementen die logisch gezien geen lijst vormen.