---
layout: page
title: Contrast
active: tutorials
---

Contrast en kleurgebruik zijn van vitaal belang voor de toegankelijkheid. Gebruikers, waaronder gebruikers met een visuele handicap, moeten in staat zijn de inhoud van de pagina waar te nemen. Het gaat dan specifiek over slechtzienden en mensen die kleurenblind zijn. In de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG) zijn er dan ook een aantal succescriteria gericht op contrast:

- <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-minimum">1.4.3 Contrast (minimum)</a> (niveau AA)
- <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-versterkt">1.4.6 Contrast (versterkt)</a> (niveau AAA)
- <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-van-niet-tekstuele-content">1.4.11 Contrast van niet-tekstuele content</a> (niveau AA)

In dit artikel focussen we enkel op de succescriteria van niveau AA, het meestgebruikte niveau voor testen.

## Problemen

We noemen enkele veelvoorkomende problemen:

- Lage contrastverhoudingen in tekst kan dit onleesbaar maken voor gebruikers. Dit is een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-minimum">1.4.3 Contrast (minimum)</a>. 
- Vaak wordt vergeten dat randen van tabellen of knoppen ook aan contrastvereisten moeten voldoen. Dit is een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-van-niet-tekstuele-content">1.4.11 Contrast van niet-tekstuele content</a>.  
- De staat van elementen dienen ook aan een contrastvereiste te voldoen. Vaak is de focus indicator niet voldoende zichtbaar. Dit is een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-van-niet-tekstuele-content">1.4.11 Contrast van niet-tekstuele content</a>. 

## Vereisten voor contrastverhouding

In WCAG is contrast een maat voor het verschil in waargenomen "luminantie" of helderheid tussen twee kleuren (de term "kleurcontrast" wordt nooit gebruikt). Dit verschil in helderheid wordt uitgedrukt als een verhouding variërend van 1:1 (laag, bv. wit op wit) tot 21:1 (hoog, bv. zwart op wit). 

Om een referentiekader te geven, op een witte achtergrond:
- Zuiver rood (`#FF0000`) heeft een verhouding van 4:1.
- Puur groen (`#00FF00`) heeft een verhouding van 1.4:1.
- Puur blauw (`#000FF`) heeft een contrastverhouding van 8.6:1.

## Tekst

Succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-minimum">1.4.3 Contrast (minimum)</a> heeft betrekking op tekst en tekst in een afbeelding. Die stelt dat deze zaken een contrastverhouding van ten minste 4,5:1 hebben, behalve voor het volgende:

- Grote tekst: Hier geldt een contrastverhouding van ten minste 3:1;
- Incidenteel: Tekst of tekst in afbeeldingen die deel uitmaken van een inactieve gebruikersinterfacecomponent, die pure decoratie zijn, die voor niemand zichtbaar zijn, of die deel uitmaken van een afbeelding die significante andere visuele inhoud bevat, hebben geen contrastvereiste.
- Logo: Tekst die deel uitmaakt van een logo of merknaam heeft geen contrastvereiste.

Belangrijk: je kunt een contrastverhouding niet afronden tot 4.5:1. Bijvoorbeeld, `#777777` - een veelgebruikte grijstint met een contrastverhouding van 4,47:1 - voldoet niet aan deze eis.

### Grote tekst

Grote tekst is gemakkelijker te lezen, dus wordt de contrastvereiste verlaagd tot 3:1. WCAG definieert grote tekst als tekst van `18pt` en groter, of `14pt` en groter als de tekst vet is.

Noot: 
- In webpagina's zijn pixels veel gebruikelijker voor tekstgrootte dan punten. 18 punten komt overeen met 24 pixels en 14 punten met ongeveer 18,67 pixels.
- In CSS heeft vetgedrukte tekst meestal `font-weight:bold`, of `font-weight:700` of hoger.
- Voor tekst in afbeeldingen gelden dezelfde eisen, maar het kan moeilijk of onmogelijk zijn om de tekstgrootte of het fontgewicht in een afbeelding te meten.

### Incidenteel

WCAG 2.0 definieert vier soorten "incidentele" tekst die niet aan de contrastvereisten hoeft te voldoen.

1. Inactief: Een inactief element, zoals een uitgeschakelde knop, wordt visueel herkend aan de staat met een lager contrast.
2. Pure decoratie: Decoratieve tekst die niet bedoeld is om gelezen te worden. Een voorbeeld hiervan is een afbeelding van een boekenplank op de homepage van een bibliotheek. De titels van de boeken zijn niet bedoeld om door de gebruiker gelezen te worden.
3. Voor niemand zichtbaar: Tekst die bedoeld is om verborgen te blijven, zoals een onzichtbare skip-link, zou niet aan contrastvereisten hoeven te voldoen totdat hij zichtbaar wordt.
4. Deel van een afbeelding dat belangrijke andere visuele inhoud bevat: Tekst die geen belangrijk deel uitmaakt van de informatie in de afbeelding, zoals een naamplaatje op het shirt van een persoon op een foto van een feestje, hoeft niet aan contrastvereisten te voldoen.

Noot: als vuistregel geldt dat tekst die deel zou uitmaken van de alternatieve tekst van de afbeelding, waarschijnlijk aan de contrastvereisten moet voldoen, terwijl tekst die niet aan de alternatieve tekst zou worden toegevoegd, meestal als incidenteel kan worden beschouwd.

### Logo
Tekst die deel uitmaakt van een logo of merknaam heeft geen contrastvereiste.

### Belangrijk om te weten

Een paar belangrijke contrastoverwegingen worden niet genoemd in <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-minimum">1.4.3 Contrast (minimum)</a>.

Tekst met kleurverloop, semi-transparante kleuren, en achtergrondafbeeldingen moeten nog steeds aan de contrastvereisten voldoen, maar WCAG geeft geen richtlijnen voor het meten van het contrast. Best practice is dan het gebied te testen waar het contrast het laagst is.

## Niet-tekstcontrast
Er zijn ook richtlijnen voor zaken die geen tekst zijn:

- Gebruikersinterface-onderdelen: Visuele informatie die nodig is om gebruikersinterfacecomponenten en -toestanden te identificeren, behalve voor inactieve componenten of wanneer het uiterlijk van de component wordt bepaald door de gebruikersagent en niet wordt gewijzigd door de auteur;
- Grafische objecten: Delen van afbeeldingen die nodig zijn om de inhoud te begrijpen, behalve wanneer een bepaalde presentatie van afbeeldingen essentieel is voor de informatie die wordt overgebracht.

### Gebruikersinterface-elementen
Er zijn twee soorten niet-tekstelementen die volgens <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-van-niet-tekstuele-content">1.4.11 Contrast van niet-tekstuele content</a> een contrastverhouding van 3:1 moeten hebben. De eerste zijn "User Interface Components", dat zijn bedieningselementen voor verschillende functies.

#### Kleurveranderingen bij hover, focus, enz.
Tekst verandert soms van kleur door een gebruikersinteractie met een muis of toetsenbord. CSS kan worden gebruikt om `hover`, `focus` of `active` statussen voor interactieve elementen te definiëren. Er is geen sprake van speciale aandacht voor deze veranderingen in tekstkleur, dus tekst in al deze toestanden moet aan dezelfde contrastvereisten voldoen (en moet onafhankelijk van elkaar worden geëvalueerd). Dat betekent een contrastverhouding van 3:1.

Noot: als er geen zichtbare focus indicator aanwezig is, is er sprake van een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#focus-zichtbaar">2.4.7 Focus zichtbaar</a>

### Grafische objecten
Het tweede type niet-tekstelementen dat in dit succescriterium aan bod komt zijn "grafische objecten". Er zijn een paar belangrijke termen binnen deze definitie.

#### "Vereist om de inhoud te begrijpen"

Om iets te definiëren als een grafisch object dat een 3:1 contrast nodig heeft, moet het "nodig zijn om de inhoud te begrijpen". Voorbeeld: een Twitter-pictogram dat een link is, zou 3:1 contrast nodig hebben. Maar als de link ook het woord "Twitter" bevat (met ten minste een contrastverhouding van 4,5:1), dan is het pictogram niet langer nodig om de inhoud te begrijpen en heeft het dus geen contrastvereiste.

#### "...behalve wanneer een bepaalde presentatie essentieel is"

Bepaalde soorten afbeeldingen moeten wellicht met een lager contrast worden gepresenteerd, zodat ze hun betekenis of doel niet verliezen. Een heatmap moet laag-contrast kleuren gebruiken zodat de onderliggende pagina nog steeds zichtbaar is. Real-life beeldmateriaal, zoals foto's en screenshots, vallen ook in deze categorie. Logo's ook.

## Testen van contrastverhoudingen

In dit gedeelte worden hulpmiddelen en technieken beschreven die kunnen worden gebruikt om contrast en kleurgebruik te testen.

### Tools

Contrast kan gecontroleerd worden met diverse tools:

* <a href="https://webdesign.tutsplus.com/articles/how-to-use-the-contrast-checker-in-chrome-devtools--cms-31504">Chrome Developer Tools</a>
* <a href="https://webaim.org/resources/contrastchecker">WebAIM Contrast Checker</a>
* <a href="https://wave.webaim.org">WAVE</a>
* <a href="https://www.tpgi.com/color-contrast-checker/">Colour Contrast Analyser</a>
* <a href="https://www.colorzilla.com/chrome/">ColorZilla</a>
* <a href="https://www.deque.com/axe/devtools/">axe DevTools</a>
* <a href="https://www.tpgi.com/arc-platform/arc-toolkit/">ARC Toolkit</a>

#### WebAIM Link Contrast Checker

Als een link alleen herkenbaar is aan een kleurverschil (wat meestal betekent dat de link niet onderlijnt is), vereist WCAG een contrastverhouding van 3:1 tussen de linktekst en de omringende bodytekst. Dit komt bovenop het 4,5:1 contrast van de linktekst ten opzichte van de achtergrond, en de bodytekst ten opzichte van de achtergrond. Met de <a href="https://webaim.org/resources/linkcontrastchecker/">WebAIM Link Contrast Checker</a> kan dit in een keer getest worden. De tool zal dan laten zien of deze kleuren wel of niet voldoen aan elk van deze drie contrastvereisten.

Noot: voor inclusief design is het sowieso aan te raden om links altijd te onderlijnen in de bodytekst.

## Conclusie

Er is niet één "beste" hulpmiddel voor contrasttesten. De hulpmiddelen die je gebruikt, hangen af van de inhoud die wordt geëvalueerd en van persoonlijke voorkeuren. Bovendien is er niet één testproces dat het beste is voor alle inhoud. Maar de meeste contrastbeoordelingen omvatten ten minste deze drie "stappen" (hoewel de volgorde kan variëren):
- Een voorafgaande scan voor potentiële problemen zoals:
	- Afhankelijkheid van kleur (vaak bij links en formulieren)
	- Laag contrast tekst
	- Tekst in afbeeldingen
	- Grafische objecten of gebruikersinterfacecomponenten, zoals gedefinieerd in WCAG 2.1
	- Toestanden van muisover en toetsenbordfocus
- Indien mogelijk, een geautomatiseerde scan met <a href="https://wave.webaim.org">WAVE</a>, <a href="https://www.deque.com/axe/devtools/">axe DevTools of <a href="https://www.tpgi.com/arc-platform/arc-toolkit/">ARC Toolkit</a>
- Een handmatige test van andere potentiële problemen met behulp van contrastcheckers als <a href="https://www.colorzilla.com/chrome/">ColorZilla</a>, <a href="https://webdesign.tutsplus.com/articles/how-to-use-the-contrast-checker-in-chrome-devtools--cms-31504">Chrome Developer Tools</a>, <a href="https://www.tpgi.com/color-contrast-checker/">Colour Contrast Analyser</a> of een combinatie hiervan.

Het testen van contrast en kleurgebruik kan veel tijd en moeite kosten, maar dit proces zal met de tijd natuurlijker worden. De hulpmiddelen en methoden van zullen waarschijnlijk veranderen naarmate je meer ervaring krijgt en kunnen verder gaan dan wat in dit artikel wordt beschreven, maar door de principes en stappen in dit artikel toe te passen, leg je een solide basis voor wat WCAG 2 vereist en hoe je hierop kunt testen.

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

## Credits
- Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/articles/contrast/">WebAim's pagina over contrast</a>.

## Bronnen
- Anysurfer - <a href="https://www.anysurfer.be/nl/documentatie/artikels/detail/voldoende-kleurcontrast">Voldoende contrast</a> 
- WebAim - <a href="https://webaim.org/articles/contrast/">Contrast and accessibility</a>
- Belgian Web Accessiiblity (BOSA) - <a href="https://accessibility.belgium.be/nl/artikels/vormgeving/gebruik-voldoende-contrast">Gebruik voldoende contrast</a>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>
