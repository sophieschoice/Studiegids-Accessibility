---
layout: page
title: Alternatieve tekst
active: tutorials
---

Niet-tekstuele inhoud zoals pictogrammen, icon fonts, emoji's, afbeeldingen, audio, video en kaarten zijn niet toegankelijk zonder alternatieven. Daarom wordt voor dit soort inhoud door de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG) tekstuele alternatieven verplicht.

Alternatieve tekst heeft verschillende functies:

- Screenreaders kondigen alternatieve tekst aan in plaats van afbeeldingen, waardoor gebruikers met visuele of bepaalde cognitieve beperkingen de inhoud en functie van de afbeeldingen beter kunnen waarnemen.
- Als een afbeelding niet laadt of de gebruiker afbeeldingen heeft geblokkeerd, presenteert de browser de alternatieve tekst visueel in plaats van de afbeelding.
- Zoekmachines gebruiken de alternatieve tekst en houden er rekening mee bij hun beoordeling van het doel en de inhoud van de pagina.

<div class="opmerking">
<p>💡 <b>Opmerking</b>: Dit artikel is vooral toegespitst op afbeeldingen. Kaarten, grafieken, video, audio en pictogrammen worden in aparte artikelen behandeld:</p>

- <a href="complexeafbeeldingen.html">alternatieve tekst voor kaarten, grafieken en infographics</a>
- <a href="cssafbeeldingen.html">correct omgaan met pictogrammen, icon fonts en emoji's</a>
- <a href="ondertiteling_audiobeschrijving">audio en video toegankelijk maken</a>

</div> 

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Problemen

Hoewel technologie steeds beter wordt in het herkennen wat een afbeelding voorstelt, kunnen algoritmen alleen niet begrijpen wat een afbeelding betekent binnen de context van de pagina als geheel. Een esdoornblad kan Canada voorstellen, maar het kan ook gewoon het blad van een boom voorstellen. Schrijvers moeten alternatieve tekst bieden die de inhoud en functie van hun afbeeldingen weergeeft.

Op de volgende punten gaat het fout met alternatieve tekst:

- de afbeelding heeft geen alt-attribuut (elk afbeelding moet een alt-attribuut hebben).
- bij afbeeldingen die niet decoratief zijn, is het alt-attribuut niet ingevuld (alt-tekst).
- Decoratieve afbeeldingen krijgen alt-tekst.
- De alt-tekst die aanwezig is, is niet correct of niet beschrijvend genoeg (een bestandsnaam bijvoorbeeld).

Dit zijn inbreuken op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#niet-tekstuele-content">1.1.1 Niet-tekstuele content</a>.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Wanneer is een afbeelding decoratief of informatief?

Of er alternatieve tekst (alt-tekst) nodig is, hangt af van of een afbeelding informatief of decoratief is.

Een "decoratieve" afbeelding is een afbeelding die

- geen belangrijke inhoud bevat,
- gebruikt wordt voor lay-out of niet-informatieve doeleinden, en
- geen functie heeft (b.v. geen link is).
- Decoratieve afbeeldingen moeten een lege <code>alt=""</code> hebben.

Informatieve afbeeldingen zijn het tegenovergestelde:

- bevatten belangrijke inhoud, en zijn onmisbaar om de inhoud van de pagina goed te kunnen begrijpen.
- hebben daardoor vaak ook een functie.
- Informatieve afbeeldingen moeten alt-tekst hebben (een ingevuld <code>alt=""</code>).

Dit is grofweg hoe afbeeldingen ingedeeld kunnen worden. Gebruik de <a href="https://www.200ok.nl/tips/afbeeldingen/">Alt-keuzehulp van Jules Ernst</a> om te bepalen in welk scenario jouw afbeelding valt en wat je precies moet doen. 

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Afbeeldingen

### Presenteren van alternatieve tekst

Alternatieve tekst kan op meerdere manieren worden gepresenteerd: 

- In het alt-attribuut.
- Binnen de zichtbare tekst in de buurt van de afbeelding.
- Als de alt-tekst niet beknopt kan zijn, kan deze op een aparte pagina worden weergegeven. Deze moet dan wel gelinkt aan de afbeelding zijn of aan een link naast de afbeelding. 

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

### Schrijven van alt-tekst

Overweeg eerst de inhoud en functie. Een afbeelding heeft alleen een functie als het gelinkt is (of een <code>&lt;area&gt;</code> heeft binnen een <code>&lt;map&gt;</code>), of als het in een <code>&lt;button&gt;</code> staat. Het beoordelen en samenvatten van de inhoud van een afbeelding kan moeilijker zijn. Als de inhoud van de afbeelding wordt gepresenteerd in de omringende tekst, dan is <code>alt=""</code> misschien alles wat nodig is.

Alt-tekst moet typisch:

- accuraat en gelijkwaardig zijn in het weergeven van inhoud en functie van de afbeelding.
- beknopt zijn. Inhoud (indien aanwezig) en functie (indien aanwezig) moeten zo beknopt mogelijk worden weergegeven, zonder dat dit ten koste gaat van de nauwkeurigheid. Meestal zijn slechts enkele woorden nodig, hoewel zelden een korte zin of twee op zijn plaats kan zijn.
- niet overbodig zijn of dezelfde informatie geven als tekst in de buurt van de afbeelding.
- geen zinnen bevatten als "afbeelding van ..." of "afbeelding van ...", enz. Dit zou overbodig zijn aangezien screenreaders het woord "afbeelding" al aankondigen, samen met de alt-tekst. Als het feit dat een afbeelding een foto, schilderij,... etc. belangrijk is, kan het nuttig zijn dit in de alternatieve tekst op te nemen.

In veel gevallen kan je jezelf afvragen: "Als ik deze afbeelding niet zou kunnen gebruiken, wat zou ik er dan voor in de plaats zetten? Als het antwoord "niets" is, dan is <code>alt=""</code> waarschijnlijk voldoende. In sommige gevallen is het bepalen van alt-tekst subjectiever. Het testen van gebruikers - met en zonder schermlezer - kan je op ideeën brengen.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

<div class="opmerking">
<p>💡 <b>Opmerking</b>: om screenreaders te helpen met een natuurlijk spreekritme en intonatie, is het best practise om punten, komma's en hoofdletters (aan het begin van een zin) te gebruiken. Het is geen inbreuk op de richtlijnen als het niet gebruikt wordt, maar het maakt de ervaring voor gebruikers aangenamer.</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Afbeeldingsknoppen

Knoppen met afbeeldingen die alleen tekst bevatten, moeten worden vervangen door echte tekst. Eventueel naar wens opgemaakt met CSS. Als een afbeelding niet kan worden vermeden, heeft de afbeelding een alt-attribuut nodig dat de functie van de knop beschrijft. De alt-tekst moet beschrijven wat de knop zal doen als hij geactiveerd wordt, zoals "Zoeken", "Verzenden", "Registreren", "Plaats uw bestelling", enzovoort. 

Bijvoorbeeld, <code>&lt;input type="image" alt="Submit Search"&gt;</code> zou geschikt kunnen zijn voor een afbeeldingsknop op een zoekformulier.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Testen

Controleer je code op:

- aanwezigheid van het `alt`-attribuut
- dat bij informatieve afbeeldingen alt-tekst aanwezig is
- dat bij informatieve afbeeldingen de alt-tekst voldoende beschrijvend is
- dat bij decoratieve afbeeldingen een leeg `alt`-attribuut hebben

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie

Hoewel het een van de meest voorkomende problemen is met betrekking tot toegankelijkheid, zien we nog steeds uiteenlopende en onjuiste methoden voor het implementeren van alternatieve tekst op het web. Redacteuren moeten getraind worden in het herkennen wanneer alt-tekst nodig is en hoe je een goede alt-tekst schrijft.

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Credits

- Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/alttext/">WebAim's pagina over alternatieve tekst</a>.
- Dank aan Rian Rietveld en Marco Zehe om te wijzen op de voordelen van het gebruik van punten, komma's en hoofdletters in alt-teksten (hun <a href="https://twitter.com/RianRietveld/status/1495692483161989122">Twitter discussie over leestekens in alt-teksten</a>).

## Bronnen

- <a href="https://www.200ok.nl/tips/afbeeldingen/">Alt-keuzehulp van Jules Ernst</a>
- Thoughtbot en Eric Bailey - <a href="https://thoughtbot.com/blog/add-punctuation-to-your-alt-text">Add punctuation to your alt text</a>.
- Anysurfer - <a href="https://www.anysurfer.be/nl/documentatie/artikels/detail/tekstalternatieven">Welk tekstalternatief voor afbeeldingen</a>
- Anysurfer - <a href="https://www.anysurfer.be/nl/documentatie/artikels/detail/technieken-tekstalternatief-voor-afbeeldingen">Technieken om afbeeldingen een tekstalternatief te geven</a> 
- WebAim - <a href="https://webaim.org/techniques/alttext/">Alternative text</a>
- W3C - <a href="https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html">Understanding Success Criterion 1.1.1: Non-text Content</a>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>