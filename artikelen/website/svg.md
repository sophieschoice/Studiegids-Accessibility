---
layout: page
title: Correcte SVG's
active: tutorials
---

We hebben gezien hoe het werkt met "gewone" afbeeldingen en alternatieve tekst. Maar wat als je met SVG-afbeeldingen werkt?

## Problemen

- SVG-bestanden worden niet correct aangeduid als een afbeelding.

Dit zijn inbreuken op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#niet-tekstuele-content">1.1.1 Niet-tekstuele content</a>.

<div class="opmerking">
<p>💡 <b>Opmerking</b>: Behalve het toevoegen van een tekstueel alternatief zijn er nog een aantal zaken waar je op moet letten. Je mag niet enkel op kleur steunen om informatie over te brengen. Lees daar meer over in <a>Niet steunen op enkel kleur: toegankelijk maken voor kleurenblinden</a>.</p>
</div>

## Wat met complexe SVG's?

Wat als je een kaart of grafiek opbouwt uit SVG-bestanden? Dat kan, en deze zijn ook wel toegankelijk te krijgen. In principe gelden daar alle regels die al eerder aan bod zijn gekomen in deze kennisdatabank. De belangrijkste zijn:

- Zorg voor een correcte focusvolgorde
- Zorg voor een focusindicator
- Interactieve elementen dienen toegankelijk te zijn met toetsenbord.
- Interactieve elementen dienen ook een naam, rol en waarde te hebben. 
- Niet-decoratieve zaken hebben alt-tekst nodig

## Conclusie

Om ervoor te zorgen dat SVG's worden herkend als afbeelding en dat complexe SVG's toegankelijk zijn, is extra werk nodig. Anders worden SVG's niet correct door screenreaders opgepikt, wat mogelijk tot verwarrende of ontbrekende informatie kan leiden. 

Zonder aandacht voor deze zaken, zal een groot deel van deze data niet toegankelijk zijn en onbruikbaar zijn voor een grote groep mensen en voldoet je project niet aan de succescriteria van de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG). 

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>


## Bronnen

- W3C - <a href="https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html">Understanding Success Criterion 1.1.1: Non-text Content</a>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>


