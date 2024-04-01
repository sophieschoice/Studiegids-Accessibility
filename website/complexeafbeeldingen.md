---
layout: page
title: Complexe afbeeldingen
active: tutorials
---

We hebben gezien hoe het werkt met "gewone" afbeeldingen en alternatieve tekst. Maar hoe werkt het als je kaarten of grafieken hebt. Of infographics? Hoe werkt het dan met alt-tekst? In dit artikel wordt het allemaal uitgelegd hoe het werkt voor afbeeldingen met visuele data: complexe afbeeldingen dus.

## Problemen

- Vaak krijgen dit soort complexe afbeeldingen helemaal geen alternatief. Ze zijn haast nooit decoratief en hebben dus alt-tekst nodig.
- De alt-tekst - indien aanwezig - is niet correct en beschrijft niet alle visuele data.
- Het alt-attribuut is niet aanwezig (verplicht voor alle afbeeldingen).
- Vaak is er erg veel visuele data aanwezig, te veel om in een alt-tekst te beschrijven.
- SVG-bestanden worden niet correct aangeduid als een afbeelding.

Dit zijn inbreuken op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#niet-tekstuele-content">1.1.1 Niet-tekstuele content</a>.

<div class="opmerking">
<p>💡 <b>Opmerking</b>: Behalve het toevoegen van een tekstueel alternatief zijn er nog een aantal zaken waar je op moet letten. Je mag niet enkel op kleur steunen om informatie over te brengen. Lees daar meer over in <a>Niet steunen op enkel kleur: toegankelijk maken voor kleurenblinden</a>.</p>
</div>

## Kaarten 

Hoe maak je wegenkaarten met een aangeduide route en weerkaarten toegankelijk? Of archeologische kaarten? De enige manier is om in tekst een alternatief te geven. Geef een routebeschrijving. Geef aan wat de weersverwachtingen voor de provincies zijn. Kortom: leg exact uit wat er op de kaart te zien is. Dat noemen we een <strong>uitgebreide beschrijving</strong>. 

Dat kan in een paragraaf onder de kaart of op een aparte pagina. Het is wel belangrijk de uitgebreide beschrijving te koppelen aan een afbeelding. Dat kan door de paragraaf een ID te geven en die te koppelen via <code>aria-describedby</code> aan de afbeelding. In de alt-tekst omschrijf je kort en bondig wat te zien en meldt je dat een uitgebreidere beschrijving onder de afbeelding volgt.

Er kan ook een link onder de kaart geplaatst worden en in de alt-tekst verwijzen dat er een link naar een uitgebreide beschrijving onder de afbeelding volgt. 
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Grafieken

Grafieken bevatten veel informatie. Vaak gaat het ook om relaties die je af kunt leiden. Een land en het aantal inwoners bijvoorbeeld. Of een politieke partij en het aantal stemmen. De beste manier om dit via tekst over te brengen is een datatabel. Een correct opgemaakte datatabel is toegankelijk en screenreaders kunnen de relaties tussen de kolommen en de cellen dan zonder problemen correct overbrengen. 

Naast een datatabel is het een goede gewoonte om de data ook via een spreadsheet of CSV-formaat aan te bieden. Dit geeft mensen de kans de data in een tool van hun eigen voorkeur in te laden en zo de data te bekijken of voor te laten lezen. 

Een andere mogelijkheid naast een datatabel, maar wat complexer, is proberen de grafiek uit SVG's op te bouwen en de SVG's toegankelijk te maken. Lees de tutorial over lijngrafieken van CSS Tricks om te leren hoe je dat doet.


<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie

Complexe afbeeldingen hebben een alternatief nodig dat toegankelijk is: een uitgebreide beschrijving. Redacteuren moeten getraind worden in het herkennen wanneer uitgebreide beschrijvingen nodig zijn. 

Zonder aandacht voor deze zaken, zal een groot deel van deze data niet toegankelijk zijn en onbruikbaar zijn voor een grote groep mensen en voldoet je project niet aan de succescriteria van de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG). 

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/alttext/">WebAim's pagina over alternatieve tekst</a>.

## Bronnen

- <a href="https://www.200ok.nl/tips/afbeeldingen/">Alt-keuzehulp van Jules Ernst</a>
- Anysurfer - <a href="https://www.anysurfer.be/nl/documentatie/artikels/detail/tekstalternatieven">Welk tekstalternatief voor afbeeldingen</a>
- Anysurfer - <a href="https://www.anysurfer.be/nl/documentatie/artikels/detail/technieken-tekstalternatief-voor-afbeeldingen">Technieken om afbeeldingen een tekstalternatief te geven</a> 
- WebAim - <a href="https://webaim.org/techniques/alttext/">Alternative text</a>
- W3C - <a href="https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html">Understanding Success Criterion 1.1.1: Non-text Content</a>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>


