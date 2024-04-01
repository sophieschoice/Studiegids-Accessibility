---
layout: page
title: Toegankelijke frames
active: tutorials
---

Een frameset is een webpagina die een verzameling vormt van ten minste twee andere afzonderlijke webpagina's, die zijn gecombineerd in dezelfde visuele ruimte. Visuele gebruikers ervaren framesets gewoonlijk als een samenhangend geheel. Zij kunnen de inhoud van meerdere pagina's in één keer scannen.

Belangrijk: frames maken niet langer deel uit van HTML. Vanwege de beperkte ondersteuning en de moeilijkheid om ze toegankelijk en zeer bruikbaar te maken, moeten frames over het algemeen vermeden worden.

In dit artikel gaan we enkel in op iframes, aangezien dit vaak wordt gebruikt om bijvoorbeeld inhoud van social media op te nemen in je webpagina (denk aan video van YouTube).
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Inline Frame (iframe) toegankelijkheid

Inline frames maken het mogelijk om verschillende webdocumenten (en zelfs hele websites) op te nemen in een subvenster van een bovenliggende webpagina zonder het gedoe van het definiëren van een frameset document. Er zijn geen duidelijke toegankelijkheidsproblemen met inline frames. De inhoud van het inline frame wordt gelezen op het punt waar het wordt aangetroffen (op basis van de volgorde van de opmaak), alsof het inhoud van de bovenliggende pagina betreft.

Sommige screenreaders geven aan dat er iframes aanwezig zijn en kunnen zelfs de navigatie daarin ondersteunen, samen met standaardframes.

In tegenstelling tot frames is een beschrijvend `title`-attribuut niet vereist voor toegankelijkheid, maar als het inline frame inhoud presenteert als een geheel dat visueel onderscheidend is, zoals een advertentie of een videospeler, dan moet een titel worden meegegeven om dit onderscheid aan te geven.

{% highlight css %}
<iframe src="ad.htm" title="Advertentie">
{% endhighlight %}

Omdat veel gebruikers lettertypen en andere pagina-elementen vergroten om de zichtbaarheid en toegankelijkheid te vergroten, moet je het scrollen voor iframes (of frames, wat dat betreft) niet uitschakelen door scrolling="no" te gebruiken. De standaardwaarde voor scrollen (auto) is meestal de beste optie. Je moet ook, indien mogelijk, het iframe ontwerpen met relatieve afmetingen, zodat het iframe element zelf meeschaalt als de pagina en de inhoud ervan worden aangepast.

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/frames/">WebAim's pagina over frames en iframes/a>.

## Bronnen
<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>