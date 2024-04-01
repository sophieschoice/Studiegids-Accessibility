---
layout: page
title: Toegankelijkheid voor toetsenbord
active: tutorials
---

<p>Dat je een website met het toetsenbord kan bedienen is een van de belangrijkste aspecten van webtoegankelijkheid. Veel gebruikers met een motorische handicaps zijn namelijk afhankelijk van een toetsenbord. Sommige mensen hebben moeite met fijne motoriek. Anderen kunnen hun handen niet of nauwelijks gebruiken (denk bijvoorbeeld aan RSI), of hebben helemaal geen handen. Naast traditionele toetsenborden kunnen sommige gebruikers aangepaste toetsenborden gebruiken of andere hardware die de functionaliteit van een toetsenbord nabootst. Blinde gebruikers gebruiken doorgaans ook een toetsenbord, om zo hun screenreader te bedienen en websites te navigeren. Bij problemen is er een inbreuk op de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG).</p>

<p>Gebruikers zonder handicap kunnen een toetsenbord gebruiken voor navigatie vanwege voorkeur of efficiëntie (👋 hoi powerusers en toetsenbordninja's!). Zij zullen mee profiteren als de toegankelijkheid voor en met het toetsenbord wordt verbeterd.</p>

<div class="toc_container">
    <p class="toc_title">Inhoud</p>
    <ol class="toc_list">
        <li><a href="#mogelijke-problemen">Mogelijke problemen</a></li>
            <ol class="toc_sublist">
                <li><a href="#focusindicatoren">Focusindicatoren</a></li>
                <li><a href="#navigatievolgorde-ook-wel-tabvolgorde">Navigatievolgorde (ook wel tabvolgorde)</a></li>
                <li><a href="#items-die-geen-toetsenbordfocus-mogen-krijgen">Items die geen toetsenbordfocus mogen krijgen</a></li>
                <li><a href="#ontoegankelijke-custom-widgets-of-componenten">Ontoegankelijke custom widgets of componenten</a></li>
                <li><a href="#teveel-elementen">Teveel elementen</a></li>
                <li><a href="#tabindex">Tabindex</a></li>
                <li><a href="#accesskeys">Accesskeys</a></li>
            </ol>
        <li><a href="#testen-met-toetsenbord">Testen met toetsenbord</a></li>
        <li><a href="#conclusie">Conclusie</a></li>
    </ol>
</div>


## Mogelijke problemen

<p>Er zijn vele manieren waarop een webpagina problemen kan opleveren voor gebruikers die voor navigatie afhankelijk zijn van een toetsenbord. Hieronder staan een paar van de meest voorkomende problemen die je tegen kan komen bij het testen van jouw project.</p>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Focusindicatoren

<p>Een toetsenbordgebruiker gebruikt gewoonlijk de <kbd>tab</kbd>-toets om door interactieve elementen op een webpagina te navigeren - links, knoppen, velden voor het invoeren van tekst, enz. Wanneer naar een item wordt getabbed, heeft het toetsenbord "focus" en kan het worden geactiveerd of gemanipuleerd met het toetsenbord. Een ziende toetsenbordgebruiker moet een visuele indicator krijgen van het element dat op dat moment toetsenbordfocus heeft.</p>
<p>Meer uitleg over <a href="focus.html">focus indicatoren en hoe problemen op te lossen</a>.</p>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Lees- en tabvolgorde (ook wel focusvolgorde)

<p>Als een toetsenbordgebruiker door de pagina navigeert, is de volgorde waarin items toetsenbordfocus krijgen belangrijk. De volgorde moet logisch en intuïtief zijn. Dit betekent over het algemeen dat deze de visuele stroom van de pagina volgt: van links naar rechts, van boven naar beneden. Voor de meeste pagina's betekent dit eerst de header, dan de hoofdnavigatie, dan items in de content (indien aanwezig) en ten slotte de footer. Deze volgorde (en ook de leesvolgorde voor schermlezers) wordt bepaald door de broncode van de webpagina.</p>
<p>Voor de beste resultaten:</p>
<ul>
    <li>Structureer broncode zo dat de lees- en tabvolgorde correct is.</li>
    <li>Gebruik vervolgens, indien nodig, CSS om de visuele presentatie van de elementen op de pagina te regelen.</li>
        <ul>
            <li>Let vooral goed op bij het gebruik van moderne CSS-technieken als grid of flex. Rachel Andrew legt uit hoe <a href="https://rachelandrew.co.uk/archives/2019/06/04/grid-content-re-ordering-and-accessibility/">flex en grid de tabvolgorde negatief kunnen beinvloeden</a>. CSS Tricks heeft ook geschreven <a href="https://css-tricks.com/grid-content-re-ordering-and-accessibility/">over herordenenen met grid</a> en ook MDN Docs heeft het over <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/CSS_Grid_Layout_and_Accessibility">grid en toegankelijkheid</a>.</li>
        </ul>
    <li>Gebruik geen <code>tabindex</code> waarden van 1 of hoger om de volgorde te veranderen.</li>
</ul>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Items die geen toetsenbordfocus mogen krijgen

<p>Links, knoppen en formulierelementen zijn van nature toegankelijk voor gebruikers van het toetsenbord, en moeten dus waar mogelijk worden gebruikt voor interactiviteit. Elementen die <strong>niet interactief</strong> zijn voor gebruikers van een muis of aanraakschermen mogen geen toetsenbordfocus krijgen (zoals door het gebruik van <code>tabindex</code>). Niet-interactieve elementen via het toetsenbord bedienbaar maken zal verwarring veroorzaken.</p>

<div class="opmerking">
<p>💡 <b>Opmerking</b>: Een link is alleen toegankelijk voor toetsenbordgebruikers of wordt aan screenreaders gepresenteerd als een link wanneer het een <code>href</code>-attribuut heeft dat <strong>niet leeg</strong> is. Een link zonder <code>href</code>-attribuut of zonder ingevuld <code>href</code>-attribuut mogen <strong>niet</strong> worden gebruikt voor links.</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Ontoegankelijke <span lang="en">custom widgets</span> of componenten

<p>Als een <span lang="en">native</span> HTML-element niet voldoende is, kan een op maat gemaakt widget of component nodig zijn. Dit wordt ook niet verboden door WCAG. Maar deze moeten nog steeds toegankelijk zijn voor gebruikers met een toetsenbord. Het kan nodig zijn om <code>tabindex</code> te gebruiken om ervoor te zorgen dat ze toetsenbordfocus kunnen krijgen. ARIA kan ook nodig zijn om ervoor te zorgen dat het component of de widget correct wordt gepresenteerd aan screenreaders. De <a href="https://www.w3.org/TR/wai-aria-practices-1.1/" hreflang="en">ARIA Authoring Practices</a> schetsen de noodzakelijke toetsenbordinteracties en ARIA-code die nodig zijn voor veel soorten zelfgemaakte componenten of widgets.</p>
<p>Om toegankelijk te worden gemaakt, moet het volgende gebeuren:</p>
<ul>
    <li>De interactie wordt op een intuïtieve en voorspelbare manier gepresenteerd.</li>
    <li>JavaScript event handlers werken met een toetsenbord en een muis.</li>
    <li>Er wordt gebruik gemaakt van toetsen die bij het component of de widget verwacht worden.</li>
</ul>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Teveel elementen

<p>Ziende gebruikers met een muis zijn in staat een webpagina visueel te scannen en direct op een item te klikken. Toetsenbordgebruikers moeten de <kbd>tab</kbd>-toets (of andere navigatietoetsen) indrukken om door de interactieve elementen te navigeren. Tabben door heel veel interactieve elementen totdat je bent waar je wil zijn, kan bijzonder veeleisend zijn voor gebruikers met motorische beperkingen. Hoe meer items doorgewerkt moeten worden voordat een gebruiker bijvoorbeeld de hoofdininhoud bereikt, hoe lastiger.</p>
<p>Lange lijsten met links of andere interactieve items kunnen overweldigend zijn voor gebruikers die alleen een toetsenbord gebruiken. De volgende <span lang="en">best practices</span> kunnen navigatie met het toetsenbord vergemakkelijken:</p>
<ul>
    <li>Zorg voor een skip link op de pagina om meteen naar de inhoud te kunnen gaan.</li>
    <li>Gebruik een goede kopstructuur.</li>
    <li>Gebruik landmarks.</li>
</ul>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Tabindex

<p>Het <code>tabindex</code>-attribuut heeft invloed op de toetsenbordfocus. Het heeft daardoor veel macht en je moet goed opletten dat je er geen problemen mee door creëert.</p>
<p>Lees meer over <a href="tabindex.html">tabindex en hoe je dat correct moet toepassen</a>.</p>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Accesskeys

<p>Accesskeys zijn sneltoetsen. Zeker sneltoetsen die uit 1 cijfer of letter bestaan, kunnen problematisch zijn.</p>
<p>Ik vertel je alles over het <a href="accesskeys.html">correct toepassen van accesskeys</a>.</p>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Testen met toetsenbord

<p>Je moet met een toetsenbord de volgende interactieve elementen kunnen bedienen:</p>
<ul>
    <li>links</li>
    <li>knoppen</li>
    <li>controls van formulieren (tekstvelden, keuzelijsten, radio buttons, checkboxen, …)</li>
    <li>dingen die getriggerd worden door <code>:hover</code> zoals tooltips</li>
    <li>widgets, bijv. een date picker</li>
</ul>

<p>Je kunt je eigen project testen door de muis aan de kant te schuiven en enkel het toetsenbord te gebruiken. Bekijk ook mijn <a href="toetsenbord_testen.html">lijst van de te gebruiken toetsen op je toetsenbord en waar je bij testen op moet letten</a>.</p>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie

<p>Het heeft een grote impact als een website of web applicatie niet bedienbaar is met het toetsenbord. Het testen en controleren van toegankelijkheid voor en met toetsenbord kost tijd, maar eventuele grote hindernissen kunnen dan wel weggenomen worden. Als het op dit gebied goed zit, is je project al voor een groot deel toegankelijk. Veel succes!</p>

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/keyboard/">WebAim's pagina over toegankelijkheid met toetsenbord</a>.

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>