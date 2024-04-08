---
layout: page
title: Focusindicators
active: tutorials
---

<p>Een toetsenbordgebruiker gebruikt gewoonlijk de <kbd>tab</kbd>-toets om door interactieve elementen (links, knoppen, velden voor het invoeren van tekst, enz.) op een webpagina te navigeren. Wanneer er naar een item wordt getabt, heeft het toetsenbordfocus en kan het item worden geactiveerd of bewerkt met het toetsenbord.</p>

<div class="toc_container">
    <p class="toc_title">Inhoud</p>
    <ol class="toc_list">
        <li><a href="#problemen">Problemen</a></li>
        <li><a href="#conclusie">Conclusie</a></li>
    </ol>
</div>

<p>Een ziende gebruiker moet volgens de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG) kunnen zien welk element op dat moment toetsenbordfocus heeft.</p>

<div class="opmerking">
<p>💡 <b>Opmerking</b>: focusindicatoren worden automatisch aangeboden door webbrowsers. Hoewel hun uiterlijk varieert afhankelijk van de browser, wordt het meestal weergegeven als een rand of markering (ook wel <span lang="en">outline</span> genoemd) rond het gefocuste element.</p> 
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Problemen

Problemen op dit gebied worden vooral veroorzaakt door twee zaken:

- de focusindicator is uitgeschakeld door <code>outline:0</code> of <code>outline:none</code> in de CSS-code. Dit is een inbreuk op criterium <a href="https://www.w3.org/Translations/WCAG21-nl/#focus-zichtbaar">2.4.7 Focus zichtbaar</a>.
- de indicator is aanwezig, maar heeft niet voldoende contrast (contrast met de achtergrond dient minstens een verhouding te hebben van 3:1). Dit is een inbreuk op criterium <a href="https://www.w3.org/Translations/WCAG21-nl/#contrast-van-niet-tekstuele-content">1.4.11 Contrast van niet-tekstuele content</a>.
- een element dat focus krijgt, verandert alleen van kleur en krijgt geen rand. Bijvoorbeeld een blauwe knop die bij focus groen wordt. Dit is een inbreuk op <a href="https://www.w3.org/Translations/WCAG21-nl/#gebruik-van-kleur">1.4.1 Gebruik van kleur</a>. 

<div class="opmerking">
<p>💡 <b>Opmerking</b>: in een update van WCAG die eraan komt (WCAG 2.2) komen er extra succescriteria bij die met focus te maken hebben. Verdiep je in wat je binnenkort over <a href="https://medium.com/eleven-ways/geef-je-bezoekers-focus-aac1baba2e48">focus in WCAG 2.2</a> kunt verwachten.</p> 
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie

Vermijd <code>outline:0</code> of <code>outline:none</code> of andere stijlen die de zichtbaarheid van focusindicatoren verwijderen of beperken.

Leunen op de standaard indicatoren die browsers bieden wordt niet geadviseerd. De kleur kan contrastproblemen veroorzaken bij gekleurde achtergronden. En als een standaard outline voldoende contrast biedt, kan dit na een update van de browser ineens weer anders zijn. Plus dat het heel lastig wordt om in <strong>alle</strong> browsers een voldoende te scoren op contrast, omdat per browser de kleur licht kan verschillen. Op welk besturingssysteem een browser wordt gebruikt, kan ook verschil maken. Het is dus beter om zelf een kleur te vast te leggen in CSS.

Ik raad aan om in de CSS de focusindicator vet te maken (minimaal 2 px dik) in een kleur die voldoende contrast biedt. Ook moet de indicator het element dat focus heeft helemaal omringen.

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>
