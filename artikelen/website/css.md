---
layout: page
title: Toegankelijke CSS
active: tutorials
---

<span lang="en">Cascading Style Sheets</span>, of CSS, maken het mogelijk om de weergave en stijl van HTML-elementen te wijzigen. CSS wordt "trapsgewijs" (het Nederlandse woord voor cascading) genoemd omdat er een hiërarchie of rangorde is voor hoe stijlen worden toegepast:

- de standaard stijlen van de browser
- een apart .css bestand
- CSS in de HTML-pagina zelf (meestal te vinden in de <code>&lt;head&gt;</code>, sectie van een pagina)
- CSS in de HTML-pagina, direct toegepast op een HTML element).

<div class="opmerking">
	<p>❗️<b>Belangrijk</b>: Om de toegankelijkheid te verbeteren, kunnen eindgebruikers de standaardstijlen in de browser wijzigen en kunnen ze aangepaste stijlen definiëren die alle andere stijlen in de "cascade" overschrijven. Pagina's moeten aanpasbaar en flexibel zijn voor stijlaanpassingen van eindgebruikers.</p>
	<p>Waarom zou een eindgebruiker zijn eigen stijlen definiëren? Een gebruiker met slecht zicht kan een veel grotere tekstgrootte definiëren. Een gebruiker met een kleurentekort of slechtziendheid kan paginakleuren overschrijven om bepaalde kleuren of een hoog contrast af te dwingen. Een gebruiker met cognitieve beperkingen of leermoeilijkheden kan de positionering wijzigen of afbeeldingen uitschakelen om een meer eenvoudige presentatie te verzekeren. Een gebruiker met dyslexie zou lettertypes en tekstafstanden kunnen veranderen voor een betere leesbaarheid.</p>
</div>

## Problemen
Omdat CSS voornamelijk over visuele presentatie gaat, heeft de meeste CSS geen invloed op wat een screenreader zal lezen. Maar toch kan CSS voor problemen zorgen:

- Sommige stijlen, zoals <code>display:none</code> en <code>visibility:hidden</code> zorgen ervoor dat inhoud wordt genegeerd door screenreaders. Afhankelijk van het soort inhoud kan dit een inbreuk zijn op een of meerdere succescriteria.
- Pseudo-content gedefinieerd met <code>::before</code> en <code>::after</code> wordt gelezen door schermlezers. Als er afbeeldingen of pictogrammen of icon fonts worden gebruikt, moet er een tekstueel alternatief zijn of dienen ze gemarkeerd te worden als decoratief. Anders is dit een inbreuk op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#niet-tekstuele-content">1.1.1 Niet-tekstuele content</a>.
- CSS wordt gebruikt om visuele informatie, betekenis en relaties weer te geven. Dit is een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#info-en-relaties">1.3.1 Info en relaties</a>  
- Eindgebruikers moeten in staat zijn de stijl van de website te overschrijven met zijn eigen stylesheet. Dit is anders een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#herschalen-van-tekst">1.4.4 Herschalen van tekst</a>, <a href="https://www.w3.org/Translations/WCAG21-nl/#reflow">1.4.10 Reflow</a> of <a href="https://www.w3.org/Translations/WCAG21-nl/#tekstafstand">1.4.12 Tekstafstand</a>. 
- De CSS geeft visueel de inhoud een andere volgorde dan de inhoud in de code heeft. Dit kan een inbreuk zijn op <a href="https://www.w3.org/Translations/WCAG21-nl/#betekenisvolle-volgorde">1.3.2 Betekenisvolle volgorde</a> of <a href="https://www.w3.org/Translations/WCAG21-nl/#focus-volgorde">2.4.3 Focus volgorde</a>

Deze valkuilen worden op deze pagina verder uitgelegd.

## Inhoud scheiden van presentatie

Een primair voordeel van CSS is dat auteurs inhoud kunnen scheiden van de presentatie. Inhoud betekent de tekst, koppen, lijsten, regio's, afbeeldingen en andere elementen gedefinieerd in HTML markup. Presentatie is de manier waarop inhoud wordt weergegeven, zoals gedefinieerd in het CSS-bestand. 

Dus door ervoor te zorgen dat de inhoud in HTML staat en de presentatie in CSS, zouden, als iemand CSS uitschakelt of overschrijft, de inhoud en semantiek nog steeds volledig toegankelijk moeten zijn.

## De visuele opmaak regelen

In CSS bieden zaken als <code>float</code>, <code>display</code> (vooral met <code>display: grid</code>), enz. grote controle over de positionering van elementen binnen een pagina, ongeacht de volgorde van die elementen in de HTML-code. De volgorde van de onderliggende broncode bepaalt de leesvolgorde van de screenreader en de volgorde van de navigatie op het toetsenbord. Dit moet overeenstemmen met de visuele lay-out. Beide moeten logisch en intuïtief zijn, en moeten over het algemeen op één lijn liggen.

<div class="opmerking">
	<p>💡 <b>Opmerking</b>: WCAG vereist dat de leesvolgorde en de navigatievolgorde van elementen overeenkomen met de visuele betekenis en volgorde. Iemand die de inhoud van een pagina verkent met behulp van een screenreader of toetsenbord, moet de inhoud doorgaans in dezelfde volgorde tegenkomen als iemand die de inhoud visueel leest (doorgaans van links naar rechts, van boven naar beneden).</p>
</div>

## Inhoud verbergen met CSS

De regel is dat in bijna alle gevallen content die visueel op een pagina wordt gepresenteerd, toegankelijk moet zijn voor gebruikers van screenreaders. Andersom geldt ook: inhoud die visueel verborgen is met CSS zou niet toegankelijk moeten zijn voor gebruikers van screenreaders. 

Echter wordt vaak <code>display:none</code> en <code>visibility:hidden</code> gebruikt om zaken visueel te verbergen. Als het ook voor screenreaders verborgen moet zijn, is dat niet erg. Maar als de informatie nog wel beschikbaar moet zijn voor screenreaders, worden deze zaken beter niet in de CSS gebruikt. 

In het geval dat iets visueel verborgen mag worden, maar niet verborgen voor screenreaders, gebruik je beter de CSS cliptechniek:

{% highlight css %}

.sr-only
{clip: rect(1px, 1px, 1px, 1px);
clip-path: inset(50%);
hoogte: 1px;
breedte: 1px;
marge: -1px;
overflow: verborgen;
padding: 0;
position: absolute;}

{% endhighlight %}

Deze vrij moderne techniek verbergt of knipt inhoud die niet in een zichtbaar gebied van 1 pixel past. Net als buiten-het-scherm inhoud, zal het visueel verborgen zijn, maar nog steeds leesbaar door moderne screenreaders.

## Inhoud en betekenis weergeven met CSS

In tegenstelling tot het verbergen van inhoud met CSS, wordt inhoud of betekenis soms uitsluitend gepresenteerd met CSS. Dit kan zijn om het volgende te doen:

- achtergrondafbeeldingen te definiëren die inhoud presenteren of betekenis hebben
- de lay-out of visuele presentatie is op een manier die de betekenis beïnvloedt
- er wordt op enkel kleur geleund om betekenis over te brengen

Deze technieken moeten over het algemeen vermeden worden. Echter, in situaties waar CSS wordt gebruikt om informatie, inhoud of betekenis te presenteren die anders niet toegankelijk is, moet een toegankelijk alternatief worden geboden.

CSS achtergrondafbeeldingen kunnen bijvoorbeeld niet direct van alternatieve tekst worden voorzien (hoewel een CSS alt eigenschap momenteel in ontwikkeling is). Als een afbeelding inhoud overbrengt, moet deze optimaal in de inhoud worden geplaatst door gebruik te maken van het img element met een geschikte alt attribuut waarde. Als dit niet mogelijk is, kan verborgen tekst of tekst buiten het scherm (of misschien ARIA) worden gebruikt om de inhoud van de afbeelding over te brengen aan gebruikers die deze niet kunnen zien.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie
Pseudo-content en het verbergen van inhoud zijn enkele zaken waar CSS op het gebied van toegankelijkheid problemen kan veroorzaken. Gebruik daarom altijd native HTML markup om de nodige semantische inhoud en betekenis te geven en gebruik dan CSS om de standaard stijlen te verbeteren en te veranderen.


<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/css/">WebAim's pagina over toegankelijke CSS</a>.

## Bronnen


<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>