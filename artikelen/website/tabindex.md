---
layout: page
title: Het tabindex-attribuut
active: tutorials
---

Met het <code>tabindex</code>-attribuut kan de lees- en tabvolgorde worden beïnvloed. Dit heeft impact op gebruikers die afhankelijk zijn van een toetsenbord en gebruikers van screenreaders, omdat deze de volgorde in de broncode gebruiken. Het kent drie waarden:

- <code>tabindex="1"</code> (of elk getal groter dan 1) definieert een expliciete tab- of navigatievolgorde.
- <code>tabindex="0"</code> staat elementen toe, behalve links en formulierelementen, om toetsenbordfocus te krijgen. Het verandert de tabvolgorde niet, maar plaatst het element in de logische navigatiestroom, alsof het een link/knop op de pagina is.
- <code>tabindex="-1"</code> staat toe dat elementen, behalve links en formulier-elementen, een "programmatische" focus krijgen, wat betekent dat de focus op het element kan worden gezet door middel van scripting.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Problemen

Door de kracht en invloed van het tabindex-attribuut kunnen er diverse problemen ontstaan als deze niet goed wordt toegepast:

- De visuele volgorde wijkt af van de volgorde in de broncode.
- Focus en bedienbaarheid van focusbare items blijft niet behouden.

Deze zaken zijn een inbreuk op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#focus-volgorde">2.4.3 Focus volgorde</a> in de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG).

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Oplossingen

Het <code>tabindex</code> attribuut met een <b>waarde van 1 of hoger</b> definieert expliciet een navigatievolgorde voor elementen die focus kunnen krijgen (meestal links en formulierelementen) binnen een pagina. Het kan ook worden gebruikt om te bepalen of elementen al dan niet focus moeten krijgen. <strong>Dit moet worden vermeden</strong>. Deze elementen zullen eerder toetsenbordfocus krijgen dan elementen zonder een <code>tabindex</code> (of <code>tabindex="0"</code>), wat resulteert in een volgorde die verschilt van de visuele volgorde. In plaats van <code>tabindex</code> te gebruiken, pas gewoon de volgorde in de broncode van de pagina aan om een logische navigatie- en leesvolgorde te bereiken.

Een waarde van 0 geeft aan dat het element in de standaard navigatievolgorde moet worden geplaatst. Hierdoor kunnen elementen die niet van nature focus ontvangen (zoals <code>&lt;div&gt;</code>, <code>&lt;span&gt;</code>, <code>&lt;p&gt;</code>, en <code>&lt;a&gt;</code> zonder <code>href</code>-attribuut), toetsenbordfocus krijgen. Links en formulierelementen zijn het beste voor bijna alle interactieve elementen, maar <code>tabindex=0</code> staat toe dat andere elementen focusbaar zijn en dus mogelijk interactie kunnen triggeren. Vaak zien we deze fout als developers denken op deze manier een <span lang="en">custom</span> component of widget toegankelijk voor toetsenbord te kunnen maken. Maar met <code>tabindex</code> maak je elementen <strong>niet bedienbaar</strong>. Het krijgt alleen focus. Zorg dat ARIA correct is toegepast en device onafhankelijke event handlers in JavaScript zijn gebruikt.


Een <code>tabindex="-1"</code> verwijdert interactieve elementen uit de standaard navigatievolgorde. <strong>In bijna alle gevallen is dit niet wenselijk!</strong> Indien toegevoegd aan iets dat nog niet interactief is, staat <code>tabindex="-1"</code> toe dat het element programmatische focus krijgt. Dit betekent dat focus erop gezet kan worden met focus() scripting. Dit kan nuttig zijn voor elementen waarnaar niet rechtstreeks genavigeerd moet worden met de <kbd>tab</kbd>-toets, maar die toch toetsenbordfocus moeten krijgen. Voorbeelden hiervan zijn een modal of overlay dat moet worden gefocust wanneer het wordt geopend, of een foutmelding bij het indienen van een formulier die onmiddellijk focus moet krijgen wanneer een ongeldig formulier wordt ingediend.

Een waarde van -1 kan ook nuttig zijn in complexe widgets en menu's die gebruik maken van pijltjestoetsen, of andere sneltoetsen. Het kan ervoor zorgen dat slechts één element binnen een widget, zoals het actieve tabblad binnen een groep tabbladen voor een tabpaneel, navigeerbaar is met de <kbd>tab</kbd>-toets, terwijl de focus nog steeds kan worden ingesteld op andere onderdelen binnen de widget.

<div class="opmerking">
<p>💡 <b>Opmerking</b>: Onthoud dat <code>tabindex="-1"</code> het element verwijdert uit de standaard navigatiestroom. Wijs het dus niet toe aan een element dat met het toetsenbord moet kunnen worden genavigeerd, zoals een link of knop waarop ziende gebruikers met de muis kunnen klikken.</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Testen

Controleer je code of dit attribuut voorkomt. 

## Conclusie

Gebruik het <code>tabindex</code>-attribuut liever niet. Gebruik het enkel in het geval van <span lang="en">custom</span> componenten of widgets. Maar zelfs in dat geval is het verstandig om na te denken of <span lang="en">native</span> HTML-elementen niet de voorkeur hebben boven <span lang="en">custom</span> componenten.

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

 <p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>