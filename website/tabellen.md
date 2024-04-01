---
layout: page
title: Toegankelijke tabellen
active: tutorials
---

Tabellen worden veel gebruikt op het web. En er kunnen makkelijk inbreuken op de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG). Het meest voorkomende probleem is:

* er zijn geen koppen voor kolommen en/of rijen gedefinieerd.
* er worden tabellen gebruiikt voor layout/opmaak.

<div class="opmerking">
<p>💡 <b>Opmerking</b>: tabellen gebruiken om de lay-out te maken van een website, is in principe geen inbreuk op WCAG. Maar het is best practice om lay-out via CSS te maken en er geen tabellen meer voor te gebruiken. Lay-out tabellen zijn wel een inbreuk als de `<th>`, `<summary>` en `<caption>` elementen worden gebruikt en de attributen headers en scope. </p>
</div>

Het veiligste is om tabellen enkel te gebruiken om gegevens/data weer te geven. 

## Correct aanduiden gegevenstabellen

Gegevenstabellen zijn bedoeld om informatie in tabelvorm te presenteren in een raster, of matrix, en om kolommen of rijen te hebben die de betekenis van de informatie in het raster weergeven. Ziende gebruikers kunnen een tabel visueel scannen. Zij kunnen snel zien welke gegevens in welke rij en/of kolom thuishoren. Iemand die de tabel niet kan zien, kan deze visuele associaties niet maken, dus moet de juiste markup worden gebruikt om een programmatische associatie te maken tussen elementen in de tabel. Wanneer de HTML-markup correct is, kunnen gebruikers van screenreaders cel per cel door de gegevenstabellen navigeren en worden de kolom- en rijkoppen uitgesproken.

### Gebruik het <caption> element

Gegevenstabellen hebben vaak een korte beschrijvende tekst voor of na de tabel die de inhoud van die tabel aangeeft. Deze tekst moet aan de tabel worden gekoppeld met behulp van het `<caption>` element. Het `<caption>` element moet het eerste zijn na het `<table>` element.

```
<table>
<caption>Shelly's Dochters</caption>
</table>
```

Hoewel het niet noodzakelijk is dat elke tabel een bijschrift heeft, is het over het algemeen erg nuttig. Indien aanwezig, moet het aan de tabel worden gekoppeld met behulp van het `<caption>` element.

### Identificeer rij- en kolomkoppen

Een belangrijke stap voor het maken van een toegankelijke gegevenstabel is het aanduiden van rij- en/of kolomkoppen. In de opmaak wordt het `<td>` element gebruikt voor tabel data cellen en het `<th>` element wordt gebruikt voor tabel header cellen. Tabelkoppen mogen nooit leeg zijn. Dit is vooral van belang voor de linkerbovenhoek van sommige tabellen

Het scope attribuut geeft aan of een tabelkop een kolomkop of een rijkop is. Hier is de opmaak voor de tabel, met gebruik van het scope attribuut:

```
<table>
<caption>Shelly's Dochters</caption>
<tr>
<th scope="col">Naam</th>
<th scope="col">Leeftijd</th>
<th scope="col">Verjaardag</th>
</tr>
<tr>
<th scope="row">Jackie</th>
<td>5</td>
<td>5 april</td>
</tr>
<tr>
<th scope="row">Beth</th>
<td>8</td>
<td>14 januari</td>
</tr>
</tabel>
``` 
Het `scope="col"` attribuut geeft aan dat het een koptekst is voor die kolom. Met `scope="row"`geef je een koptekst aan voor die rij. Alle `<th>`-elementen moeten over het algemeen altijd een scope-attribuut hebben. Hoewel screenreaders aan de hand van de tabelopmaak kunnen raden of een koptekst een kolom- of een rijkoptekst is, zorgt het gebruik van het scope-attribuut dat een tabel correct geinterpreteerd wordt.

Het scope attribuut is zelfs van toepassing bij complexe tabellen die `rowspan` gebruiken. 

<div class="opmerking">
<p>💡 <b>Opmerking</b>: hoewel het al jaren standaard opmaak voor tabellen is, ondersteunen sommige schermlezers nog steeds complexe tabellen niet volledig. Probeer waar mogelijk de tabel 'plat' te maken en koppen die meerdere rijen of kolommen overspannen te vermijden.</p>
</div>

## De attributen headers en id

Een andere manier om cellen en koppen te associëren is het gebruik van de attributen `headers` en `id`. Deze methode wordt over het algemeen NIET aanbevolen omdat `scope` meestal voldoende is voor de meeste tabellen, zelfs als de tabel complex is met koppen die meerdere kolommen of rijen overspannen..

Met deze aanpak krijgt elke `<th>` een unieke id-attribuutwaarde. Vervolgens krijgt elke `<td>`-cel in de tabel een headers-attribuut met waarden die overeenkomen met elke `<th>`-id-waarde waaraan de cel is gekoppeld. De waarden worden gescheiden door spaties en moeten worden vermeld in de volgorde waarin een schermlezer ze zou moeten lezen. Bij gebruik van headers/id in het voorbeeld hierboven, zou de cel voor Jackie's leeftijd kunnen worden gemarkeerd als ```<td headers="geboorte jackie leeftijd">5</td>```).

Nogmaals, het moet benadrukt worden dat deze methode ingewikkelder is, veel meer markup gebruikt (en potentieel om gebroken te worden), en zelden nodig is. Gebruik in plaats daarvan `scope`.

## Gebruik proportionele grootte, eerder dan absolute grootte

De regel die geldt voor lay-out tabellen, geldt ook voor gegevenstabellen. Laat waar mogelijk het browservenster de breedte van de tabel bepalen, om het horizontaal scrollen van slechtzienden te beperken. Als celbreedtes moeten worden gedefinieerd, gebruik dan relatieve waarden, zoals percentages, in plaats van pixelwaarden. Gedefinieerde celhoogtes moeten over het algemeen vermeden worden, zodat de cel naar beneden kan uitzetten om de inhoud aan te passen - iets wat vooral nuttig is voor gebruikers met slecht zicht die tekstinhoud kunnen vergroten.

## Andere opmaak

Het attribuut `summary` kan worden gebruikt om een samenvatting te geven van de structuur van een gegevenstabel (niet van de inhoud). Ondersteuning varieert, maar in het algemeen is het screenreader-specifiek (het is niet toegankelijk voor iemand anders) en wordt het niet goed ondersteund. Bovendien maakt het attribuut geen deel uit van de HTML5-specificatie. In het algemeen, als een tabel zo complex is dat er een uitleg nodig is over hoe hij is opgebouwd, is het waarschijnlijk niet erg toegankelijk en moet het worden vereenvoudigd. Om deze redenen raden wij het gebruik van `summary` af. Als het wordt gebruikt, mag het nooit worden gebruikt voor opmaaktabellen.

De `thead` en `tfoot` elementen definiëren header en footer rijen voor tabellen. Ze bieden geen toegankelijkheidsfunctionaliteit en zijn over het algemeen alleen van nut wanneer een lange tabel wordt afgedrukt - de kop- en/of voetrijen zullen zich herhalen bovenaan of onderaan elke afgedrukte pagina. Op dezelfde manier definieert het `tbody` element de content van een gegevenstabel (dus alles wat geen `thead` of `tfoot` is). Ook dit element biedt geen extra toegankelijkheidsvoordelen, maar het kan geen kwaad het te gebruiken voor tabelstyling of andere redenen.

## Conclusie

Zorg ervoor dat tabellen zo eenvoudig mogelijk zijn, gebruik kolom- of rijkoppen en koppel deze op een correcte manier met het `scope` attribuut. 

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/tables/">WebAim's pagina over tabellen</a>.

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>