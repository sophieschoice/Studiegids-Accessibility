---
layout: page
title: Toegankelijk aanduiden/identificeren van taal
active: tutorials
---

Screenreaders kunnen verschillende talen "spreken" - zolang de taal van de inhoud maar geïdentificeerd is. Als de screenreader de gedefinieerde taal niet ondersteunt of niet kan spreken, kan de gebruiker geïnformeerd worden over de taal van de inhoud, zelfs als die inhoud niet goed gelezen kan worden.
Het definiëren van de documenttaal ondersteunt ook de geautomatiseerde vertaling van de inhoud met behulp van tools zoals Google Translate.

Om te voldoen aan niveau A van de Web Content Accessibility Guidelines (WCAG) moet de documenttaal programmatisch worden gedefinieerd. Om te voldoen aan niveau AA WCAG moet de taal van delen van een pagina in een andere taal dan de rest van de pagina ook worden geïdentificeerd. Dit vertelt de screenreader om naar die taal over te schakelen (als die mogelijkheid er is).

Het specificeren van de "taal van delen" van de pagina is alleen nodig voor anderstalige inhoud die niet algemeen begrepen wordt in de primaire taal van het document. "Los Angeles" en " piñata", bijvoorbeeld, zijn Spaanse woorden die door Engelse lezers worden begrepen, zodat het niet nodig zou zijn deze op een Engelse webpagina als Spaans aan te duiden.

Door de taal van de inhoud goed te definiëren, kan de browser ook de aanhalingstekens voor verschillende talen goed weergeven wanneer het `<q>`-element wordt gebruikt. Onderstaande voorbeelden zijn gedefinieerd als Duits en Frans. De browser heeft de gelokaliseerde aanhalingstekens gegenereerd die bij de taal horen.

Bovendien, als de taal is opgegeven kan de browser:
- de juiste tekens voor niet-Latijnse tekst geven
- gelokaliseerde invoer van datum en tijd (zoals MM/DD/JJJJ vs. DD/MM/JJJ of 24-uurs tijd vs. AM/PM tijd) gebruiken
- getallen met passende komma- of puntscheidingstekens tonen
- spellingscontrole in de juiste taal geven voor tekst in formulieren

## Het lang-attribuut

Het lang-attribuut wordt gebruikt om de taal van de webpagina aan te geven. Dit attribuut moet altijd aan de `<html>`-tag worden toegevoegd. Het krijgt een waarde die de natuurlijke taal van de pagina aangeeft. Door bijvoorbeeld `<html lang="en">` toe te voegen, wordt aangegeven dat de pagina in het Engels is.
Op dezelfde manier kan het lang-attribuut aan andere HTML-elementen op een pagina worden toegevoegd om hun natuurlijke taal aan te geven. `<p lang="ja">`, bijvoorbeeld, geeft aan dat de paragraaf in het Japans is geschreven.

Gebruik het lang-attribuut niet om de taal aan te geven van de inhoud waarnaar wordt gelinkt of waarnaar wordt genavigeerd. Als een link op een Engelse webpagina naar een Spaanse vertaling de tekst "Spanish" weergeeft, wordt het lang-attribuut niet gebruikt omdat "Spanish" een Engels woord is. Als de link in plaats daarvan de tekst "Español" weergeeft, dan moet lang="es" worden gedefinieerd op de link.

### De impact van een onjuiste waarde

Wanneer tekst in de ene taal wordt gelezen met de uitspraakregels van een andere taal, kan het resultaat de inhoud ontoegankelijk maken. Hieronder staat een passage van tekst in het Engels. De audio-opname is een screenreader die deze tekst uitspreekt alsof er `lang="cs"` (Tsjechisch) in staat.

### De juiste taalcodes kiezen

Meer dan 8.000 taalcodes, gedefinieerd door internationale specificaties, omvatten de verschillende talen, dialecten, regio's, enz. van de wereld. De Internet Assigned Numbers Authority (IANA) houdt een bijgehouden register bij van mogelijke en geldige waarden. Het W3C biedt een uitstekende gids voor het kiezen van een taalcode. Je kunt ook zoeken naar geldige waarden voor het lang-attribuut met deze language subtag lookup tool. Zorg ervoor dat u de onderstaande richtlijnen leest om er zeker van te zijn dat de gebruikte lang-waarde de grootste toegankelijkheidsondersteuning heeft.

## Hoofdtaal van het document instellen

De primaire taal is de belangrijkste taal van de webinhoud. Voor bijna alle primaire talen zijn codes van twee tekens beschikbaar. `lang="en"` is Engels, `lang="de"` is Duits, `lang="zh"` is Chinees, en `lang="ar"` is Arabisch, bijvoorbeeld.

Houd de waarde van het lang-attribuut zo kort als nodig is. Als de primaire taalcode van twee tekens volstaat om de inhoudstaal te identificeren, gebruik die dan.

Veel primaire talen hebben verschillende subtalen of dialecten. Engels heeft bijvoorbeeld verschillende varianten voor Groot-Brittannië, Australië en India. Het Chinees kent Mandarijn en Kantonees en talrijke andere dialecten, waarvan sommige niet onderling verstaanbaar zijn. Desondanks is het meestal voldoende om de primaire taal op een webpagina te vermelden.

Conclusie 
De taal aanduiden met het `lang` attribuut is meestal voldoende voor screenreader ondersteuning. Ondersteuning voor drie-karakter en uitgebreide, script, en regio subtags varieert afhankelijk van de gebruikte browser en screenreader, en de taalstemmen die ondersteund en geïnstalleerd zijn. When in doubt, test. Ondersteuning voor inline taalveranderingen, zoals voor een `<span>` of `<img>` element is ook gevarieerd. Wanneer mogelijk is het het beste om het lang attribuut te definiëren op een element op blokniveau, zoals een `<p>`, `<blockquote>`, of iets dergelijks.

Om de inhoud in de gedefinieerde taal te kunnen lezen, moet de screenreader die taal ondersteunen. Alle moderne screenreaders hebben ondersteuning voor een groot aantal talen. In bepaalde screenreaders moet de gebruiker handmatig taalstemmen of "taalpakketten" installeren of configureren.

Als een screenreader een lang-attribuut tegenkomt dat een taal specificeert waarvoor geen bijpassende taalstem is geïnstalleerd of wordt ondersteund, zal het meestal de taal van de inhoud identificeren. De screenreader kan bijvoorbeeld "Spaans" uitspreken voor inhoud met lang="es" als een Spaanse taalstem niet is ingeschakeld of geïnstalleerd.

Screenreaders zullen doorgaans proberen om inhoud te lezen die uitspreekbaar is, zelfs als de gedefinieerde taal niet wordt ondersteund. Poolse inhoud, bijvoorbeeld, is geschreven in Latijnse karakters, dus zal de screenreader het voorlezen met een Engelse standaardstem (hoewel het zal worden voorgelezen zonder de juiste uitspraak, verbuigingen, enz. - misschien klinkend als een beginnende Poolse les). Chinese karakters daarentegen zijn niet direct uit te spreken in het Engels, dus de screenreader zal ze niet voorlezen, hoewel hij "Chinees" kan aankondigen om de gebruiker te informeren dat er Chinese taalinhoud aanwezig is.