---
layout: page
title: Accesskeys (sneltoetsen)
active: tutorials
---

Sneltoetsen kunnen nuttig zijn om toepassingen efficiënter te maken. Met het HTML-attribuut <code>accesskey</code> kunnen ontwikkelaars bepaalde sneltoetsen aan HTML elementen toewijzen. Omdat browsers en ondersteunende technologieën de <code>accesskey</code>-ondersteuning echter inconsistent, ineffectief of helemaal niet implementeren, moet het accesskey-attribuut meestal worden vermeden of met grote voorzichtigheid worden geïmplementeerd. Anders kan het een inbreuk zijn op de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG).

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Sneltoetsen als een algemeen concept

Het accesskey-attribuut kan worden toegevoegd aan interactieve HTML-elementen, zoals links en formulierelementen, zoals in dit voorbeeld:

<code>&lt;a href="https://www.marktplaats.nl/" accesskey="m" &gt;Marktplaats&lt;a&gt;</code>

Het `accesskey`-attribuut definieert een snelkoppeling naar de opgegeven bestemming. In bovenstaand voorbeeld zou de letter "m" de gebruiker naar de website van Marktplaats brengen.

Sneltoetsen kunnen nuttig zijn voor alle computergebruikers, omdat ze vaak snellere interacties mogelijk maken dan met muisklikken. Powerusers maken vaak gebruik van sneltoetsen. Onder mensen met handicaps, maken mensen die blind zijn of die motorische handicaps hebben ook vaak gebruik van sneltoetsen.

Sneltoetsen kennen we vooral van besturingssystemen en applicaties als Word of Outlook. Microsoft en Apple hebben sneltoetsen gestandaardiseerd om het gemakkelijker te maken snel toegang te krijgen tot menu's en functies, zonder een muis te hoeven gebruiken. Grafische interfaces geven vaak de standaard sneltoetsen voor veelgebruikte functies aan. 

Maar op het web is er momenteel echter geen standaard voor het definiëren of aangeven van sneltoetsen op een pagina.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Problemen

Ondanks goede bedoelingen en vanwege uiteenlopende en ontoereikende browserimplementaties, bieden Accesskeys vaak geen oplossing voor sneltoetsen op het web.

### Browser implementatie

Browser implementatie varieert sterk tussen merken en besturingssystemen, maar de basisideeën achter accesskey sneltoetsen zijn redelijk consistent. Gebruikers moeten de toetscombinaties voor het activeren van sneltoetsen leren, en moeten mogelijk nieuwe toetscombinaties leren om ze te activeren wanneer ze naar een andere browser of een ander besturingssysteem overschakelen.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Toetscombinaties

Verschillende browsers gebruiken verschillende toetscombinaties om sneltoetsen te activeren, zoals hieronder aangegeven:

- Browsers op Windows: <kbd>Shift</kbd> + <kbd>Alt</kbd> + [de sneltoets] (<kbd>Shift</kbd> is in sommige browsers optioneel).
- Browsers op Mac: <kbd>control</kbd> + <kbd>option</kbd> + [de sneltoets]

Daarnaast ondersteunen de meeste browsers geen dubbele sneltoetswaarden. Een pagina kan bijvoorbeeld geen twee sneltoetsen hebben met <code>accesskey="1"</code>. Indien aanwezig, ondersteunen de meeste browsers slechts één van de elementen. Sommige browsers doorlopen de elementen bij elke opeenvolgende activering van de sneltoets.
In HTML5 kan een element meerdere toegangstoetsen hebben, maar de ondersteuning daarvoor verschilt echter sterk per browser.

De implementatie varieert ook over wat het activeren van de juiste sneltoetscombinatie zal doen. Sommige zetten gewoon de focus op het element met de sneltoets (de gebruiker moet dan op Enter drukken om hem te activeren), terwijl andere hem onmiddellijk activeren. Dit varieert nog meer afhankelijk van het type element - links, knoppen, en formulierelementen kunnen zich allemaal anders gedragen.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Screenreaders en spraaksoftware

Accesskeys kunnen echter conflicteren met andere sneltoetsen en kunnen onbedoeld worden geactiveerd, vooral door gebruikers van spraakbesturingssoftware of screenreaders.

Omdat screenreaders voor veel van hun functionaliteit afhankelijk zijn van browsers, is de implementatie van de accesskey voor screenreaders grotendeels afhankelijk van de browser die wordt gebruikt. Sommige screenreaders geven de waarde van de sneltoets aan telkens als het element wordt aangetroffen. Dit kan onnodige ruis en herhaling veroorzaken als de gebruiker zich eenmaal op die sneltoets heeft georiënteerd. 

Een van de grootste problemen met sneltoetsen is de mogelijkheid dat het de sneltoetsen van schermlezers overschrijft, die veel meer toetsenbordcommando's hebben dan standaardbrowsers. In geval van conflicten hebben de sneltoetsen van de schermlezer over het algemeen voorrang, wat betekent dat de sneltoetsen van de toegangstoetsen effectief zijn uitgeschakeld, ook al worden ze nog steeds herkend door de gebruiker. Het toegankelijkheidsvoordeel van sneltoetsen gaat dan verloren, maar de schermlezerfunctionaliteit blijft intact. Dit kan echter verwarrend zijn als de gebruiker juist een sneltoets wil activeren.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Taalproblemen

Er zijn geen toetscombinaties die zeker geen potentieel conflict opleveren met browsers, ondersteunende technologieën of besturingssystemen. Dit geldt vooral als ook buitenlandse talen meespelen. Een menu Bestand, bijvoorbeeld, heet niet altijd "Bestand" in andere talen dan het Engels. Als zodanig kan het gebeuren dat een sneltoets geen conflict veroorzaakt in een browser die is ingesteld op het gebruik van het Engels, maar wel in dezelfde browser wanneer deze is ingesteld op het gebruik van een andere taal.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Cijfers

Omdat elke letter al wordt geacht te zijn geassocieerd met een webfunctie, hebben sommigen gepleit voor het gebruik van cijfers - in plaats van letters - om de kans op conflicten met sneltoetsen te minimaliseren. Hoewel er minder potentiële conflicten zijn met cijfers, is het ontbreken van conflicten geenszins gegarandeerd. Er zijn geen standaardassociaties tussen cijfers en webpaginafunctionaliteit. Gebruikers kunnen in verwarring raken door het gebruik van cijfers in sneltoetsen.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Hoe weten gebruikers of sneltoetsen beschikbaar zijn?

In webpagina's of toepassingen is er geen standaardmanier om gebruikers te informeren welke sneltoetsen beschikbaar zijn. In tegenstelling tot de Windows-omgeving, waar de letter van de sneltoets in menu's wordt onderstreept, is er geen "vuistregel" voor websites om gebruikers te waarschuwen voor de aanwezigheid van een sneltoets.

Hoewel screenreaders gewoonlijk de sneltoetsen voor interactieve elementen identificeren wanneer ze worden aangetroffen, helpt dit slechtziende toetsenbordgebruikers niet. Ontwikkelaars die sneltoetsen willen gebruiken, moeten gebruikers ervan op de hoogte brengen dat de sneltoetsen beschikbaar zijn door de letter in een woord die de sneltoets activeert te onderstrepen, door de sneltoets of toetsencombinatie (die per browser en besturingssysteem verschilt) in de tekst te spellen, of door een lijst met sneltoetsen op de pagina of in de helpdocumentatie op te nemen. Geen van deze methoden biedt echter een consistente, direct beschikbare en intuïtieve methode om alle gebruikers te informeren.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Alternatieven voor accesskeys

JavaScript kan worden gebruikt om toetsaanslagen of toetscombinaties te detecteren om een sneltoets te activeren. Net als bij accesskeys kunnen ook deze potentiële conflicten opleveren, zijn ze mogelijk niet gemakkelijk te herkennen en kunnen ze resulteren in een verkeerde activering. Ondanks deze beperkingen kunnen dergelijke sneltoetsen bijzonder nuttig zijn in online toepassingen.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Testen

Controleer je code op het gebruik van het <code>accesskey</code>-attribuut.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie

Het attribuut wordt beter vermeden. Er kunnen sneltoetsen met één toets worden gebruikt om functies uit te voeren (zoals S om een zoekformulier te openen). Maar dan moeten de gebruikers de mogelijkheid krijgen om ze uit te schakelen of om ze om te zetten in een sneltoets met meerdere toetsen (bv. wijzigen in Shift + Alt + S voor zoeken). En een sneltoets kan alleen actief zijn als het betreffende element focus heeft.

Wordt er aan één van die drie voorwaarden niet voldaan, is het een inbreuk op criterium <a href="https://www.w3.org/Translations/WCAG21-nl/#enkel-teken-sneltoetsen">2.1.4 Enkel teken sneltoetsen</a>. 

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/keyboard/accesskey">WebAim's pagina over accesskeys</a>.

## Bronnen

- MDN web docs - <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/accesskey">Accesskey</a>
- WebAim - <a href="https://webaim.org/techniques/keyboard/accesskey">Accesskey</a>
- W3C - <a href="https://www.w3.org/WAI/WCAG21/Understanding/character-key-shortcuts.html">Understanding Success Criterion 2.1.4: Character Key Shortcuts</a>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>