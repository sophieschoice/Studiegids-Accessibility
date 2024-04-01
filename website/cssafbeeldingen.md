---
layout: page
title: Pictogrammen, icon fonts en afbeeldingen ingeladen via CSS
active: tutorials
---

Afbeeldingen ingeladen via CSS moeten worden gebruikt voor decoratieve afbeeldingen die geen alternatieve tekst nodig hebben. Afbeeldingen die inhoud overbrengen moeten over het algemeen niet in CSS worden gedefinieerd. Zij zouden in de pagina-inhoud moeten staan. Het is niet mogelijk om direct alternatieve tekst toe te voegen aan CSS of andere achtergrondafbeeldingen, dus wanneer achtergrondafbeeldingen wel inhoud bevatten, moet die inhoud toegankelijk worden gemaakt binnen de opmaak van de pagina. 

## Problemen

Enkele voorbeelden die problematisch zijn:

- Informatieve achtergrondafbeeldingen die belangrijke informatie geven.
- Knoppen die een icon font gebruiken om een pictogram weer te geven, en die enkel dat pictogram weergeven.
- Externe links die via CSS een pictogram aan het eind krijgen.

Dit zijn inbreuken op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#niet-tekstuele-content">1.1.1 Niet-tekstuele content</a>.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Afbeeldingen inladen via CSS

Hier kunnen we kort zijn en de boodschap uit de inleiding herhalen: doe het niet. Of enkel als je zeker weet dat de afbeelding decoratief is. Want via CSS is het niet mogelijk om alt-tekst mee te geven. 

Maar in gevallen van pictogrammen of icon fonts kan je vaak niet buiten CSS om. Gelukkig zijn er wel trucs om die dan toegankelijk te maken. 

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Pictogrammen en icon fonts

Pictogrammen en icon fonts worden vaak gebruikt in knoppen of controls, om de achterliggende actie visueel duidelijker te maken. Denk bijvoorbeeld aan een knop met een rode kruis om iets te verwijderen, een knop met een figuurtje om een profiel-pagina aan te duiden of een knop met een envelop om naar je privé-berichten te gaan. 

Als deze knoppen verder geen tekst bevatten, zijn deze pictogrammen informatief en hebben ze alternatieve tekst nodig. Het is ook een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#labels-of-instructies">3.3.2 Labels en instructies</a>, omdat knoppen een label moeten hebben. 

Bij icon fonts speelt ook nog mee dat er een karakter wordt ingeladen dat voorgelezen kan worden door screenreaders, maar een hele andere betekenis heeft dan waarvoor het wordt gebruikt. Dit kan heel verwarrend zijn. 

Pictogrammen en icon fonts kunnen het beste als volgt aangepakt worden: 

{% highlight html %}
<a class="link" href="url/hier">
	<span class="sr-only">Onze geweldige website</span>
</a>

{% endhighlight %}

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Testen

Dit dien je handmatig te controleren. 

## Conclusie

Bij afbeeldingen die via CSS ingeladen worden is het belangrijk dat je dat enkel doet voor afbeeldingen die decoratief zijn, anders dienen ze alternatieve tekst te hebben. Gelukkig zijn er wel trucs voor de gevallen waarin je alternatieve tekst nodig hebt. Dat helpt om ze toegankelijk te maken voor gebruikers.
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>