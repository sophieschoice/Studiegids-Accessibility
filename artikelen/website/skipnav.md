---
layout: page
title: Skiplinks en andere manieren om blokken content over te slaan
active: tutorials
---

Op de meeste pagina's moeten gebruikers met een toetsenbord of screenreader door een lange lijst met navigatiekoppelingen en andere elementen navigeren voordat ze ooit bij de hoofdinhoud komen. Dit kan bijzonder moeilijk zijn voor gebruikers met bepaalde vormen van motorische beperkingen. Denk aan gebruikers zonder of met een beperkte armbeweging die op een webpagina navigeren door met hun hoofd op een schakelaar te tikken of die een stok in hun mond gebruiken om toetsen van het toetsenbord in te drukken. Als gebruikers een bepaalde handeling meerdere malen moeten uitvoeren voordat ze bij de hoofdinhoud komen, vormt dit een toegankelijkheidsbarrière.

Zienden die hun muis gebruiken, hebben natuurlijk geen moeite met dergelijke webpagina's. Zij kunnen vrijwel onmiddellijk de pagina scannen en zien waar de hoofdinhoud zich bevindt. Skiplinks zijn vooral nuttig om gebruikers van schermlezers en toetsenborden dezelfde mogelijkheid te geven om direct naar de hoofdinhoud te navigeren.

## Creëren van skiplinks

Het idee is eenvoudig: voorzie een link bovenaan de pagina die, wanneer geactiveerd, de gebruiker naar het begin van de hoofdinhoud brengt.

## Zichtbare links

De gemakkelijkste methode om een navigatie-link over te slaan is deze bovenaan of dichtbij de pagina te plaatsen in gewone tekst. Het belangrijkste is ervoor te zorgen dat de link een van de eerste items is die schermlezers horen en waarnaar toetsenbordgebruikers navigeren met het toetsenbord (meestal door op de Tab-toets te drukken). Anders beseffen gebruikers misschien niet dat er een link is om navigatie over te slaan en verspillen ze tijd met het navigeren door irrelevante links. De link moet ook duidelijk zijn om nuttig te zijn.

Voorbeeld

De link is het eerste item op de pagina. Het anker of doel voor de link (waar de link naartoe springt) is de hoofdinhoudsregio.
```
<body>
<a href="#maincontent">Skip to main content</a>
...
<main id="maincontent">
<h1>Heading</h1>
<p>This is the first paragraph</p>
```

Het doel wordt geïdentificeerd door de waarde in het `id`-attribuut die overeenkomt met de `href`-waarde (minus de "#") van de skip link. Als de overgeslagen link wordt geactiveerd, gaat de toetsenbordfocus naar het `<main>`-element. Navigatie en lezen vinden plaats vanaf deze locatie op de pagina.

## Tijdelijk verborgen snelkoppelingen

Veel ontwerpers maken zich zorgen over de esthetische impact van zichtbare skiplinks. Ze kunnen denken dat deze links onaantrekkelijk of verwarrend zijn voor gebruikers die ze niet nodig hebben, dus kunnen ze besluiten ze onzichtbaar te maken. Een zeer kleine of verborgen link is niet in het voordeel van het publiek dat het meest behoefte heeft aan skiplinks - ziende toetsenbordgebruikers. Terwijl screenreaders veel mechanismen hebben om over de pagina te springen (bv. koppen en regio's/landmarkeringen), hebben andere toetsenbordgebruikers dat niet.

Om tegemoet te komen aan de bezorgdheid dat een zichtbare skiplink opdringerig kan zijn, maar toch een overslaan-link te maken die nuttig is voor ziende toetsenbordgebruikers, bevelen wij aan een link te maken die verborgen is tot de gebruiker er met een toetsenbord naartoe navigeert.

Om bruikbaar te zijn voor alle toetsenbordgebruikers, in het bijzonder gebruikers met een visuele handicap, moet de link

- standaard verborgen zijn
- toegankelijk zijn voor navigatie met het toetsenbord
- prominent zichtbaar worden wanneer erop wordt gefocust
- op de juiste manier de aandacht vestigen op de hoofdinhoud wanneer deze geactiveerd wordt

Waarschijnlijk de meest toegankelijke methode voor het visueel verbergen van een overgeslagen link is deze buiten het scherm te verbergen met CSS, en er dan voor te zorgen dat hij op het scherm wordt geplaatst wanneer hij toetsenbordfocus krijgt. Omdat de link nog steeds deel uitmaakt van de toegankelijke inhoud op de pagina, kunnen gebruikers van het toetsenbord en schermlezers er doorheen navigeren, en wordt de link zichtbaar wanneer hij wordt geopend.

Sommige technieken, zoals het verbergen van de koppeling overslaan met CSS display:none of het hidden-attribuut, verwijderen de koppeling uit de toetsenbordnavigatie, waardoor deze voor alle gebruikers ontoegankelijk wordt. De link dezelfde kleur geven als de achtergrond of volledig transparant maken, de link een grootte van 0 pixels geven of op een transparante afbeelding van één pixel plaatsen, kan ook toegankelijkheidsproblemen opleveren.

Belangrijk: lees het artikel over onzichtbare inhoud voor gebruikers van een schermlezer voor meer informatie over het gebruik van CSS om links die overgeslagen worden buiten het scherm te verbergen.

Een mogelijk probleem met deze aanpak is dat als de gebruiker heel snel navigeert met de Tab-toets, de link slechts een fractie van een seconde zichtbaar is op de pagina en over het hoofd kan worden gezien. Dit kan gedeeltelijk worden verholpen door ervoor te zorgen dat de link "skip", wanneer zichtbaar, visueel duidelijk opvalt bovenaan de pagina. Bovendien zou men scripting of CSS-overgangen kunnen gebruiken om de link te laten animeren, zodat hij langer zichtbaar blijft op het scherm.
Opmerking

Navigeer door de links aan het begin van deze pagina met de Tab-toets om een voorbeeld te zien van een verborgen skip-link die zichtbaar wordt bij toetsenbordfocus met behulp van CSS-overgangen om hem visueel opvallend te maken en minstens een moment op het scherm zichtbaar te houden.

## Meerdere links naar hoofdinhoud zijn meestal niet nodig

Wat als een pagina meerdere secties of meerdere niveaus van navigatielinks heeft? Moeten ontwikkelaars dan voor elk van deze secties een link maken om de navigatie over te slaan of om elk navigatieniveau over te slaan?

In de meeste gevallen is een enkele link voldoende. Voor pagina's met zeer weinig navigeerbare elementen die aan de hoofdinhoud voorafgaan, is een link om over te slaan misschien helemaal niet nodig. Anderzijds kan het op een zeer complexe pagina met verschillende herhaalde elementen nodig zijn extra links over te slaan. Onthoud dat het doel van links naar overgeslagen pagina's is om navigatie via het toetsenbord efficiënter te maken. Op welk moment moet u een "Sla de links over" link toevoegen?!

In-paginalinks elders op een pagina kunnen ook worden gebruikt om gebruikers in staat te stellen naar andere soorten pagina-inhoud te springen of daar overheen te springen. De "Inhoud van het artikel" bovenaan deze pagina bevat bijvoorbeeld in-pagina links om de navigatie naar belangrijke paginagedeelten te vergemakkelijken. Een "skip link" kan ook worden gebruikt om de gebruiker snel verwarrende of potentieel ontoegankelijke inhoud te laten omzeilen, zoals ASCII art, complexe tabellen, of complexe sociale media feeds.

## WCAG-conformiteit 

WCAG 2.4.1 (Blokken omzeilen - niveau A) stelt: "Er is een mechanisme beschikbaar om blokken inhoud die op meerdere webpagina's worden herhaald, te omzeilen." Dit vereist niet noodzakelijkerwijs dat er een "skip link" aanwezig is. Het beginnen van de hoofdinhoud met een `<h1>` of het gebruik van een `<main>`-gebied zou een voldoende "mechanisme" zijn.  Maar omdat geen van beide technieken erg nuttig is voor ziende toetsenbordgebruikers zonder schermlezer of gespecialiseerde software, wordt een link overslaan sterk aanbevolen voor optimale toegankelijkheid op pagina's met herhaalde navigatie.

### Koppen en regio's

Het implementeren van de juiste titelstructuren (met name het beginnen van de hoofdinhoud met een `<h1>`) en regio's (met name `<nav>` en `<main>) is een essentieel aspect van toetsenbord-toegankelijkheid. Helaas ondersteunen browsers dit soort navigatie nog niet van nature, zonder het gebruik van extensies of een schermlezer. Hoewel overgeslagen navigatiekoppelingen een nogal onhandige en opdringerige oplossing zijn voor een reëel probleem, zijn ze toch vaak nodig om zo goed mogelijk tegemoet te komen aan de behoeften van alle toetsenbordgebruikers.

Binnen webpagina's en -toepassingen kan focusbeheer nodig zijn om ervoor te zorgen dat de toetsenbordfocus wordt ingesteld op inhoudselementen wanneer deze worden gepresenteerd of geactiveerd. Wanneer bijvoorbeeld een pop-upvenster verschijnt, zal de focus waarschijnlijk moeten worden ingesteld met JavaScript.
Alternatieve leesvolgorde

Sommige websites gebruiken CSS om de paginalay-out zo te veranderen dat de hoofdinhoud wordt gepresenteerd vóór de navigatie in de onderliggende broncode (die de leesvolgorde voor schermlezers en de toetsenbordnavigatie bepaalt), maar visueel na de navigatie komt. Omdat gebruikers van schermlezers en toetsenborden de navigatie als eerste tegenkomen, kan deze methode een link om de navigatie over te slaan overbodig maken.

Wanneer de visuele volgorde niet overeenkomt met de navigatie- en leesvolgorde, kunnen gebruikers met een visuele toetsenbord- of schermlezer in de war raken wanneer hetgeen ze zien of waarnaar ze navigeren schijnbaar verspringt op de visuele pagina. Dit soort lay-outs wordt niet aanbevolen.
