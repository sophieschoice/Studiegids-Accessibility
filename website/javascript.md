---
layout: page
title: JavaScript en toegankelijkheid
active: tutorials
---

JavaScript stelt ontwikkelaars in staat om meer interactie, informatieverwerking en controle toe te voegen aan websites. JavaScript kan echter ook toegankelijkheidsproblemen veroorzaken. Deze problemen kunnen zijn:

1. Navigatie. Onvermogen of problemen bij het navigeren met behulp van een toetsenbord of ondersteunende technologie.
2. Controle door de gebruiker. Gebrek aan controle door de gebruiker over geautomatiseerde inhoudswijzigingen.
3. Verwarring/desoriëntatie. Wijziging of uitschakeling van de normale functionaliteit van de browser of het triggeren van gebeurtenissen of inhoud waarvan de gebruiker zich mogelijk niet bewust is.

Een webpagina met JavaScript is doorgaans volledig toegankelijk als de functionaliteit van het script onafhankelijk is van het apparaat (niet alleen een muis of alleen een toetsenbord vereist) en de informatie (inhoud) beschikbaar is voor ondersteunende technologieën. Er is geen eenvoudige oplossing die alle toegankelijkheidsproblemen in verband met JavaScript kan oplossen. De enige manier om JavaScript toegankelijk te maken is door elke pagina die gebruik maakt van scripting te evalueren en een unieke oplossing te bedenken voor elk gevonden toegankelijkheidsprobleem.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## JavaScript dat geen invloed heeft op toegankelijkheid

Het feit dat JavaScript op een pagina wordt gebruikt, wil nog niet zeggen dat de pagina ontoegankelijk is. In veel gevallen kan JavaScript worden gebruikt om de toegankelijkheid sterk te verbeteren en de gebruikerservaring te optimaliseren. Sommige aspecten van de naleving van de toegankelijkheidsvereisten zouden moeilijk zijn zonder JavaScript, vooral voor complexe webtoepassingen.

JavaScript wordt soms gebruikt om visuele interface-elementen te creëren die de toegankelijkheid niet beïnvloeden. Subtiele veranderingen in afbeeldingen bij muisbewegingen of andere wijzigingen die alleen van visuele aard zijn, hoeven bijvoorbeeld geen extra toegankelijkheidsfuncties te bevatten omdat de belangrijke inhoud niet door het script wordt beïnvloed.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## JavaScript-afhankelijkheid

Mensen met een handicap zullen gescripte inhoud ervaren, dus deze moet van nature toegankelijk worden gemaakt. Het is een misvatting dat mensen met een handicap geen JavaScript zouden hebben of gebruiken, dus is het aanvaardbaar om een ontoegankelijke scriptinterface te presenteren, zolang er maar een toegankelijke, niet-javaScript-versie beschikbaar is. Uit een enquête van WebAIM onder gebruikers van schermlezers bleek dat 99,3% van de respondenten JavaScript had ingeschakeld. De cijfers zijn nog hoger voor gebruikers met een slecht gezichtsvermogen of een motorische handicap.

De Richtlijnen voor Toegankelijkheid schrijven voor dat gescripte interfaces toegankelijk moeten zijn. WCAG 1.0 uit 1999 schreef voor dat pagina's functioneel en toegankelijk moesten zijn met uitgeschakelde scripting, maar WCAG 2 en alle andere moderne richtlijnen staan toe dat JavaScript wordt ingeschakeld. De gescripte inhoud of interacties moeten dan wel voldoen aan de richtlijnen.

Het is echter belangrijk te weten dat sommige gebruikers (ongeacht hun handicap) JavaScript uitschakelen of technologieën gebruiken die scripting niet volledig ondersteunen, zodat alternatieven voor JavaScript moeten worden aangeboden. Als een webpagina of -toepassing scripting vereist, denk dan aan de gevolgen voor gebruikers zonder JavaScript. Het is niet noodzakelijk dat alle functionaliteit werkt zonder scripting (hoewel dit optimaal zou zijn), maar er moet voorkomen worden dat er iets gepresenteerd wordt dat lijkt te werken, maar dat niet doet vanwege een gebrek aan JavaScript-ondersteuning.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Event handlers

Event handlers worden geactiveerd door een browser- of gebruikersgebeurtenis - bijvoorbeeld wanneer de pagina wordt geladen, wanneer de gebruiker op de muis klikt, of wanneer het 8 uur 's morgens is. Sommige event handlers zijn afhankelijk van het gebruik van een muis (of touch) of toetsenbord. Deze worden apparaat-afhankelijke event handlers genoemd. Andere event handlers zijn onafhankelijk van het apparaat en worden geactiveerd door zowel de muis/touch als het toetsenbord, of door andere middelen.

Om toegankelijkheid te garanderen, moet een apparaatonafhankelijke event handler worden gebruikt (een die zowel met de muis als met het toetsenbord werkt) of moeten zowel muis- als toetsenbordafhankelijke event handlers worden gebruikt.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### onmouseover en onmouseout
De `onmouseover` event handler (en gerelateerde `mouseover` en `mouseenter` events) wordt getriggerd wanneer de muiscursor over een item wordt geplaatst. Zoals de naam al aangeeft, vereist `onmouseover` het gebruik van een muis. Het is dus een apparaatafhankelijke event handler en kan toegankelijkheidsproblemen veroorzaken. `onmouseover` en zijn tegenhanger, `onmouseout` (en gerelateerde `mouseout` en `mouseleave` events), mogen worden gebruikt, zolang belangrijke inhoud of functionaliteit ook beschikbaar is zonder de muis te gebruiken. Als de muisinteractie puur cosmetisch is (zoals de toevoeging van een gloed of schaduw), zijn er waarschijnlijk geen toegankelijkheidsproblemen zolang de stijlverandering niet een of andere functie aangeeft (zoals aangeven dat een element klikbaar is).

Als de muisinteractie extra informatie of inhoud presenteert, zoals een tooltip, een navigatiemenu, enzovoort, dan zal deze inhoud niet toegankelijk zijn voor iedereen die geen muis gebruikt. Voor gebruikers van screenreaders (die zeer vaak een toetsenbord gebruiken voor navigatie) kan de extra inhoud direct op een toegankelijke manier worden aangeboden. Zoals via alternatieve tekst, via `aria-label`, `aria-describedby` of misschien via tekst buiten het scherm.  Voor ziende gebruikers die alleen een toetsenbord gebruiken, moet er echter een mechanisme zijn waarmee zij de nieuwe inhoud of functionaliteit kunnen openen en bekijken.

Soms wordt scripting gebruikt om complexe muisinteracties te presenteren, zoals een drop-down of fly-out menu. Hoewel deze technisch toetsenbord-toegankelijk kunnen worden gemaakt, kan soms een toegankelijke alternatieve aanpak vriendelijker zijn. In plaats van gebruikers te dwingen door een complex en lang navigatiemenu te navigeren, zou u er bijvoorbeeld voor kunnen zorgen dat de items in het submenu NIET direct toegankelijk zijn voor het toetsenbord (noch gelezen kunnen worden door een schermlezer). In plaats daarvan zouden standaardkoppelingen functionaliteit bieden voor het menu-item op het hoogste niveau (bijv. "Producten"). Deze links leiden de gebruiker naar secundaire pagina's met links naar aanvullende pagina's die via het complexe menu worden aangeboden (bv. een landingspagina "Producten" met links naar de diverse productcategorieën). Hoewel dit niet precies dezelfde interactie is die muisgebruikers kunnen kiezen, zijn dergelijke alternatieven vaak intuïtiever en vriendelijker.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### onfocus en onblur

Je kunt `onfocus` (of `focus` of `focusin` events) en `onblur` (of `blur` of `focusout` events) gebruiken wanneer het toetsenbord wordt gebruikt om naar en van een element te navigeren. Deze event handlers worden meestal gebruikt bij formulierinvoer, zoals tekstvelden, keuzerondjes en submit-knoppen, maar kunnen ook worden gebruikt bij links of misschien ARIA-widgets. `onfocus` wordt getriggerd wanneer de cursor op of binnen een specifiek formulierelement wordt geplaatst, of wanneer een gebruiker met het toetsenbord naar het element 'tabt'. `onblur` wordt getriggerd wanneer de cursor een formulierelement verlaat of de gebruiker ervan 'weg tabt'.

Beide event handlers zijn apparaatonafhankelijk, wat betekent dat ze kunnen worden uitgevoerd met de muis, een touchscreen, het toetsenbord of andere ondersteunende technologie. De acties die worden uitgevoerd als gevolg van deze event handlers moeten worden geanalyseerd om te bepalen of ze toegankelijkheidsproblemen veroorzaken, vooral als ze het standaardgedrag van de webbrowser wijzigen of interfereren met toetsenbordnavigatie binnen de webpagina. Voorbeelden van dergelijke problemen zijn het automatisch verschuiven van de focus naar andere delen van de pagina nadat `onfocus` en `onblur` zijn geactiveerd, het vastzetten van de gebruiker in een formulierbesturingselement, het dynamisch onthullen van formulierbesturingselementen onmiddellijk nadat een gebruiker een formulierinvoer heeft verlaten (vervagen), enz.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### onclick and ondblclick

De `onclick` event handler (en `click` event) wordt getriggerd wanneer de muis wordt ingedrukt en losgelaten boven een pagina-element of wanneer de Enter-toets wordt ingedrukt terwijl een toetsenbord-navigeerbaar element focus heeft. In deze gevallen is `onclick` een apparaatonafhankelijke event handler.
Echter, de Enter-toets zal niet altijd `onclick` triggeren als het wordt gebruikt met niet-interactieve elementen zoals platte tekst, tabel cellen, of `<div>` elementen, zelfs als ze toetsenbord-navigeerbaar zijn gemaakt met behulp van `tabindex` of zijn gefocused met behulp van scripting. In deze gevallen zal het nodig zijn om het indrukken van de <kbd>Enter<kbd> en <kbd>Space<kbd> toets te detecteren terwijl de focus erop wordt gelegd. Door standaard HTML-besturingselementen te gebruiken, vermijd je vaak de noodzaak van scripting en potentiële toegankelijkheidsproblemen.

De `ondblclick` event handler (en `dblclick` event) wordt geassocieerd met de dubbele klik van een aanwijsapparaat (vaak een muis of trackpad) op een geselecteerd element. Op dezelfde manier zijn `mouseup` en `mousedown` events alleen beschikbaar via aanwijsapparaten. Doorgaans moeten deze worden vermeden.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### onchange en onselect

De `onchange` event handler (en `change` event) wordt geactiveerd wanneer de waarde van een formulierinvoer wordt gewijzigd, bijvoorbeeld wanneer een keuzerondje wordt geselecteerd, wanneer de tekst in een tekstvak of tekstgebied wordt gewijzigd, of wanneer het actieve item in een keuzemenu wordt gewijzigd. Hoewel deze gebeurtenissen onafhankelijk zijn van het apparaat en geactiveerd kunnen worden met de muis, het toetsenbord of een ander apparaat, moeten de acties die worden uitgevoerd als gevolg van deze gebeurtenissen worden geanalyseerd om te bepalen of ze toegankelijkheidsproblemen veroorzaken.
Een veelgebruikte toepassing van `onchange` is in keuzemenu's om navigatie te starten wanneer de actieve optie in het menu wordt gewijzigd. In sommige browsers kunnen deze menu's toetsenbord-toegankelijkheidsproblemen veroorzaken omdat de gebruiker niet met een toetsenbord door de lijst kan scrollen zonder een van de opties te selecteren (en zo de `change` event te triggeren). Het verwijderen van `onchange` en het voorzien van een submit knop die het huidig geselecteerde item activeert, biedt een meer toegankelijk en gebruikersvriendelijk alternatief.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Apparaatonafhankelijke event-handlers gebruiken

Verscheidene event handlers zijn onafhankelijk van het apparaat, waaronder `onfocus`, `onblur`, `onselect`, `onchange` en `onclick` (wanneer `onclick` wordt gebruikt met een toetsenbord-focusable element). Gebruik waar mogelijk apparaatonafhankelijke event handlers. Andere event handlers zijn apparaatafhankelijk, wat betekent dat ze volledig afhankelijk zijn van een bepaald type invoer. Bijvoorbeeld, `onmouseover`, `onmouseout`, en `ondblclick` zijn afhankelijk van het gebruik van een muis of trackpad. Er zijn ook enkele event handlers die afhankelijk zijn van het gebruik van het toetsenbord (`onkeydown`, `onkeyup`, enz.).
Meerdere van deze apparaatafhankelijke event handlers kunnen samen worden gebruikt om activering van JavaScript door de muis, aanraking en toetsenbord mogelijk te maken, maar dit moet worden getest in verschillende browsers en ondersteunende technologieën om er zeker van te zijn dat de toegankelijkheid op geen enkele manier wordt beperkt.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## JavaScript-gegenereerde inhoud

Inhoud die door JavaScript wordt gegenereerd of naar de pagina wordt geschreven (zoals gebruikelijk is bij AJAX en Single Page Applications) is over het algemeen toegankelijk voor ondersteunende technologieën, zoals screenreaders. DOM-veranderingen zijn doorgaans onmiddellijk beschikbaar. In sommige gevallen echter, als de dynamische inhoud voortdurend verandert of als deze verandert terwijl de gebruiker deze leest of erop heeft gefocussed, kan dit de navigatie of browserfunctionaliteit verstoren en toegankelijkheidsproblemen veroorzaken. Als bijvoorbeeld een element dat toetsenbordfocus heeft aanzienlijk wordt gewijzigd, verborgen of van de pagina wordt verwijderd, kan de toetsenbordfocus terugkeren naar het begin van de pagina.
Door ervoor te zorgen dat de inhoud wordt gegenereerd via een opdracht of interactie van de gebruiker (zoals het indrukken van een knop), in plaats van automatisch of willekeurig, kan ervoor worden gezorgd dat de inhoud niet verandert wanneer deze gefocust is of gelezen wordt. Als dynamische veranderingen nodig zijn, moet ervoor worden gezorgd dat de veranderingen niet interfereren. Een ARIA live region of alert kan (met grote voorzichtigheid) worden gebruikt om dynamische inhoud te laten lezen, zelfs als de focus er niet op wordt gelegd.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

Bovendien moet dynamische inhoud soms onmiddellijk toetsenbordfocus krijgen. Een dialoogvenster zal waarschijnlijk focus moeten krijgen (met `focus()`) nadat het verschijnt om ervoor te zorgen dat het onmiddellijk wordt genavigeerd of gelezen. Er kunnen aanvullende technieken nodig zijn om de toegankelijkheid van dergelijke dynamische elementen te garanderen - een modaal dialoogvenster kan bijvoorbeeld geprogrammeerd moeten worden om de toetsenbordfocus te behouden (in plaats van de focus naar andere delen van de pagina te laten gaan die visueel niet beschikbaar zijn).
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Widgets en complexe interacties

Waar mogelijk moet HTML worden gebruikt om webpaginafunctionaliteit te bieden. Wanneer HTML de gewenste functionaliteit niet ondersteunt, zoals voor pop-upvensters, complexe menu's, tabpanelen, accordeons, schuifregelaars, enz., kan JavaScript nodig zijn om complexe widgets en besturingselementen te maken. Deze kunnen vaak toegankelijk worden gemaakt, vooral door de ARIA Design Patterns and Widgets te volgen.
Er zijn veel problemen met zowel bruikbaarheid als toegankelijkheid die kunnen ontstaan bij niet-standaard widgets en interacties. De beslissing om ze te gebruiken moet met zorg worden genomen. Als ze gebruikt worden, is een grondige gebruikerstest van uw implementatie van vitaal belang.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Browservensters omleiden en vernieuwen

Wanneer de pagina die de browser toont plotseling verandert of vernieuwd wordt met scripting of `<meta>`-tags, kan de persoon die de pagina bekijkt gedesoriënteerd of verward raken, vooral als die persoon een ondersteunende technologie gebruikt. De Richtlijnen voor Toegankelijkheid vereisen dat gebruikers controle krijgen over tijdgevoelige inhoudsveranderingen. Verander of vernieuw het browservenster niet automatisch zonder de gebruiker eerst te waarschuwen dat de verandering zal plaatsvinden en hem/haar de mogelijkheid te geven de verandering uit te schakelen of uit te stellen, of nog beter, de gebruiker volledige controle te geven over de paginaverandering of -omleiding.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Verwerking op de server

In veel gevallen kan of moet de functionaliteit van JavaScript gedupliceerd worden door server-side scripting. JavaScript wordt bijvoorbeeld vaak gebruikt om formulierelementen te valideren voordat een formulier wordt verzonden. In plaats van of in aanvulling op het implementeren van dergelijke JavaScript-programmering en de bijbehorende toegankelijkheidstechnieken, zou je een server-side script kunnen gebruiken om de formulierelementen te valideren. Omdat scripts altijd door de eindgebruiker kunnen worden uitgeschakeld of gewijzigd, mag je er nooit op vertrouwen voor kritieke formuliervalidatie of andere functies. JavaScript wordt vaak gebruikt om dynamische informatie naar een webpagina te schrijven, zoals de huidige datum en/of tijd. Ook hier geldt dat het gebruik van een serverscript de noodzaak van extra toegankelijkheidsimplementatie wegneemt.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Progressive enhancement

Progressive enhancement is de techniek waarbij scripts worden gebruikt om de functionaliteit of het gedrag van inhoud en functionaliteit te verbeteren die zonder scripts al voldoende zijn. Een voorbeeld hiervan is het toevoegen van client-side formuliervalidatie en foutherstel aan een formulier dat al server-side validatie heeft. Het formulier functioneert nog steeds prima zonder scripting, maar de scripting verbetert geleidelijk het formulier om het bruikbaarder en toegankelijker te maken. Dit is een uitstekende benadering voor het ontwikkelen van toegankelijke gescripte interfaces- begin eerst met toegankelijke markup en kern HTML (en misschien server-side) functionaliteit, voeg dan toegankelijke scripting toe om het efficiënter, vriendelijker, en toegankelijker te maken.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie

JavaScript van nature toegankelijk maken is erg belangrijk. Zorg dat zaken bedienbaar zijn met het toetsenbord, focus krijgen, wijzig niet zomaar inhoud en voorkom verwarring of desoriëntatie door het triggeren van events of acties waar de gebruiker niet van op de hoogte is. Belangrijke tools hierbij zijn apparaatonafhankelijke event handlers en progressive enhancement. 
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van de paragraaf over focus indicators op <a href="https://webaim.org/techniques/javascript/">WebAim's pagina over JavaScript</a>.

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>