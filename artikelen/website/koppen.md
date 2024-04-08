---
layout: page
title: Koppen
active: tutorials
---

## Koppen

Een kop beschrijft de inhoud die erop volgt, net als een krantenkop. Als ze op een nieuwe pagina komen, gaan slechtziende gebruikers naar de koppen toe om snel te vinden wat ze willen op de pagina. Gebruikers van schermlezers en andere ondersteunende technologie kunnen ook van kop naar kop springen.

Koppen vormen een overzicht van de pagina, vergelijkbaar met het overzicht van een scriptie of een inhoudsopgave. De `<h1>` beschrijft de pagina in zijn geheel (en zou vergelijkbaar moeten zijn met de `<title>` van de pagina). Een pagina zou meestal maar één `<h1>` moeten hebben. De koppen `<h2>` tot en met `<h6>` vertegenwoordigen een toenemende mate van "inspringing" in onze conceptuele "outline". Als zodanig is het niet zinvol om titelniveaus over te slaan, zoals van `<h2>` naar `<h4>`, naar beneden op de pagina.

Koppen moeten gebruik maken van heading-tags. Schermlezers en ondersteunende technologieën vertrouwen op heading elementen (`<h1>` - `<h6>`) om kopteksten te identificeren. Tekst die alleen groot, vet of benadrukt is, wordt niet geïnterpreteerd als een kop, tenzij de markup `<h1>` - `<h6>` wordt gebruikt. 

Gebruik koppen alleen als ze de volgende inhoud weergeven. Om tekst die geen koptekst is te benadrukken, gebruik je stijlen – geen koptags – om visuele resultaten te bereiken. 

## Voorwaarden waar koppen aan moeten voldoen

## Tekst die eruit ziet als een kop en zich gedraagt als een kop MOET in de opmaak als een echte kop worden aangeduid.

Koppen zijn belangrijk voor de structuur van een pagina. Een paragraaf via CSS opmaken als grote, vette tekst ziet er visueel uit als een kop, maar wordt niet zo gepresenteerd door de screenreader. Pas als in de code tekst als kop is gemarkeerd, zal de screenreader de tekst als kop 'zien'.

Het tegenovergestelde is ook waar: tekst dat zich niet gedraagt als een kop en er ook zo niet uitziet, mag niet opgemaakt worden als kop. 

Dit is een inbreuk op succescriterium 1.3.1 Info en relaties. 

Noot: als je tekst groot wilt opmaken en het is geen kop, gebruik dan gewoon CSS om dat voor elkaar te krijgen. 

## Koppen MOETEN nauwkeurig en informatief zijn.

Koppen moeten voldoende beschrijvend zijn om gebruikers een goed idee te geven van de inhoud. Gebruikers van screenreaders kunnen namelijk een overzicht van koppen oproepen, om snel naar een bepaald gedeelte te kunnen navigeren. Bovendien helpen goede koppen gebruikers om de tekst te 'scannen'. 

Als dit niet het geval is, is dit een inbreuk op succescriterium 2.4.6 Koppen en labels. 

## Koppen zouden kort moeten zijn

Er is geen technische limiet voor de lengte van een kop, maar een kop moet een kort label zijn voor het gedeelte van de inhoud onder de kop, zodat gebruikers gemakkelijk door de koppen kunnen bladeren.

## Koppen ZOUDEN een duidelijk en nauwkeurig structureel overzicht moeten geven van de inhoudsdelen van een webpagina.

Creëer eerst de structuur en stijl daarna de koppen zoals jij dat wilt.
Denk altijd eerst aan de structuur, want screenreaders en andere ondersteunende technologieën letten op de structuur, niet op het uiterlijk. Als de standaardgrootte van de koppen te groot is voor het uiterlijk dat je voor ogen hebt, gebruik dan stijlen om de grootte te wijzigen in plaats van naar een lager kopniveau te springen.

## Koppen ZOUDEN GEEN hiërarchische niveaus over moeten slaan.

### Goed voorbeeld: Koppen in de juiste hiërarchische volgorde

Elk rubriekniveau, <h1>-<h6>, geeft de relatie aan tussen een deel van de inhoud en de andere delen. De inhoud onder een rubriek heeft een logisch verband met een rubriek erboven. Op dezelfde manier zou de inhoud binnen een <h2> inhoudsblok een logisch verband hebben met de <h1> die eraan voorafgaat. Op deze manier kan de koppenstructuur van een document worden gebruikt als een methode om de inhoud van het document hiërarchisch te ordenen, net als een schets.


## Het begin van de hoofdinhoud ZOU moeten beginnen met `<h1>`.

Gewoonlijk is het de beste gewoonte om de hoofdinhoud van een webpagina te beginnen met een kop op niveau 1 (`<h1>`), zonder andere koppen vóór deze kop op hoog niveau. De subsecties van de pagina moeten elk worden gemarkeerd als koppen van niveau 2 (`<h2>`). Als er subsecties zijn binnen de niveau 2-secties, moeten deze worden gemarkeerd als niveau 3 (`<h3>`) enzovoort. Alles wat voor de hoofdinhoud van de pagina komt, moet waarschijnlijk helemaal niet gemarkeerd worden met koppen, hoewel dit geen onwrikbare regel is. Een van de belangrijkste redenen dat de `<h1>` aan het begin van de hoofdinhoud moet staan, is omdat gebruikers van schermlezers sneltoetsen kunnen gebruiken om direct naar de eerste `<h1>` te navigeren, waardoor ze in principe direct naar de hoofdinhoud van de webpagina kunnen springen. Als er geen `<h1>` is, of als de `<h1>` ergens anders staat dan aan het begin van de hoofdinhoud, moeten schermlezergebruikers naar meer informatie luisteren.
moeten gebruikers van schermlezers meer van de webpagina beluisteren om de structuur te begrijpen, waardoor kostbare tijd verloren gaat.

Zoals bij alle aanbevelingen voor best practices, zijn er uitzonderingen waarbij het niet zinvol is om de inhoud te beginnen met `<h1>`, of wanneer het beter is om andere koppen voor het begin van de hoofdinhoud te plaatsen.
hoofdinhoud, maar de uitzonderingen zijn niet van toepassing op de overgrote meerderheid van webpagina's.

## De meeste webpagina's ZOUDEN slechts één `<h1>` moeten hebben.

Op enkele uitzonderingen na zouden de meeste webpagina's slechts één kop niveau 1 moeten hebben, om duidelijk te maken waar het begin van de hoofdinhoud is.

Een veel voorkomende uitzondering op deze best practice is wanneer een pagina een modal of overlay heeft. De modal/overlay is een element dat boven op de hoofdpagina wordt weergegeven, en het kopniveau van de modale titel wordt vaak gemarkeerd als een `<h1>`. Dit zou gebruikers echter niet in verwarring moeten brengen, omdat het modal en de titel niet beschikbaar zouden moeten zijn terwijl een gebruiker interactie heeft met de hoofdpagina, en de hoofdpagina zou niet beschikbaar moeten zijn terwijl een gebruiker interactie heeft met het modal/overlay.

Een andere mogelijke uitzondering zijn indexpagina's van verschillende blogartikelen gecombineerd op dezelfde pagina, waarbij elk blogartikel op de pagina begint met `<h1>`. Zelfs dit voorbeeld hoeft echter geen uitzondering op de regel te zijn. De bovenste kop niveau 1 zou de titel van de blog kunnen zijn (bijv. "Paul's cameratips"), en elk blogartikel op de indexpagina zou kunnen beginnen met `<h2>`. Maar als de individuele blogartikelen ook op hun eigen pagina's verschijnen, moeten die pagina's beginnen met `<h1>` en niet met `<h2>`, dus realistisch gezien kan het praktischer zijn om `<h1>` te gebruiken op zowel de individuele blogartikelpagina als op de gecombineerde indexpagina met meerdere artikelen. Het is gemakkelijker om de markup op die manier te onderhouden, ook al is het niet ideaal voor de toegankelijkheid.