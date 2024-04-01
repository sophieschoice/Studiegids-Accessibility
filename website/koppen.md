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

Hoewel er geen limiet is, is het aanbevolen om koppen kort en krachtig te houden.

## Koppen ZOUDEN een duidelijk en nauwkeurig structureel overzicht moeten geven van de inhoudsdelen van een webpagina.

## Koppen ZOUDEN GEEN hiërarchische niveaus over moeten slaan.

## Het begin van de hoofdinhoud ZOU moeten beginnen met `<h1>`.

Gewoonlijk is het best practice om de hoofdinhoud van een webpagina te beginnen met een kop op niveau 1 (`<h1>`).

## De meeste webpagina's ZOUDEN slechts één `<h1>` moeten hebben.

Het is een goede best practice om slechts één kop niveau 1 te hebben, om duidelijk te maken waar het begin van de hoofdinhoud is.

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>