---
layout: page
title: Typografische opmaak
active: tutorials
---

## Uitlijning

Standaard lijnen browsers tekst links uit. Tekst kan ook rechts worden uitgelijnd, gecentreerd, of uitgevuld (uitgelijnd op zowel de linker- als de rechtermarge). Links uitgelijnde tekst is bijna altijd het gemakkelijkst te lezen, behalve in sommige Aziatische talen en talen uit het Midden-Oosten, die traditioneel verticaal van boven naar beneden of horizontaal van rechts naar links worden gelezen.

Lange blokken gecentreerde tekst hebben tot gevolg dat elke nieuwe regel op een iets andere plaats begint. Dit kan leiden tot overhead bij het lezen.

Volledig uitgelijnde tekst dwingt elke regel tot zowel de linker- als de rechterkantlijn door de woord- en letterafstand aan te passen. Hoewel de resulterende presentatie er op het eerste gezicht netter uitziet, verminderen deze verschillen in spatiëring de leesbaarheid. Volledig uitgelijnde tekst kan ook leiden tot storende "witte rivieren" - patronen van onbedoelde witruimte die het oog afleiden van de van de tekst.

Sommige omstandigheden, zoals gecentreerde koppen of een rechts uitgelijnde datum op een document, kunnen gepast zijn, maar deze moeten als uitzonderingen worden behandeld.

## Marges, spatiëring en witruimte

Documenten met lege ruimte, of "witruimte", rond blokken tekst zijn over het algemeen gemakkelijker te lezen en te scannen. De ruimte helpt de lezer zich te concentreren op de tekst en zorgt voor een schonere lay-out. Wanneer tekst echter dicht bij de rand van het weergavegebied komt, kan het document rommeliger aanvoelen, kunnen de tekstregels langer zijn en kunnen sommige lezers met leesproblemen het moeilijker vinden om het document te lezen.

Bij het ontwerpen voor kleine schermen kan de hoeveelheid witruimte binnen de marges worden beperkt om een optimale regellengte te garanderen.

### Witruimte om paragrafen te onderscheiden

Alinea's en andere blokken tekst moeten gemakkelijk van elkaar te onderscheiden zijn. Browsers voegen standaard verticale ruimte tussen alinea's in. Een alternatieve methode om alinea's van elkaar te scheiden is de extra ruimte boven en onder de alinea's weg te laten, en in plaats daarvan de eerste regel van elke alinea in te laten springen. Gedrukte materialen zoals boeken en tijdschriften volgen meestal deze conventie. Omdat bij online-inhoud de neiging bestaat om te scrollen, maakt alinea-afstand het gemakkelijker om alinea's van elkaar te onderscheiden.

## Regellengte

Lange tekstregels (veel tekens per regel) vergen inspanning van de gebruiker om terug te gaan naar het begin van de volgende regel. Bij een zeer korte regellengte wordt veel tijd besteed aan het terugvinden van het begin van de volgende regel.

De regellengte wordt beïnvloed door het lettertype, de tekstgrootte en de woord/letterafstand, alsmede door de schermgrootte en -instellingen van de eindgebruiker. Hoewel er geen universeel optimaal aantal tekens per regel is, zal in het algemeen minder dan ongeveer 50 of meer dan ongeveer 120 tekens per regel waarschijnlijk tot moeilijkheden leiden.

Er zijn uitzonderingen.
Soms zijn korte regels nodig.
Zoals in een haiku.

Responsive web design, minimum en maximum breedtes, variabele breedtes gebaseerd op de viewport grootte, enz. kunnen worden toegepast om ervoor te zorgen dat regellengtes geschikt zijn.

## Tekstopmaak 

### Onderstrepen
De conventie van onderstreepte links bestaat al zo lang als het World Wide Web. Onderstreepte tekst gebruiken voor andere doeleinden op het web zal waarschijnlijk sommige gebruikers in verwarring brengen, die zullen proberen op de onderstreepte termen te klikken. Op dezelfde manier zullen links die niet onderstreept zijn misschien niet zo duidelijk zijn.

### Verwijderen <del>, invoegen <ins>, en doorhalen <s>
Verwijderde tekst kan worden aangegeven met het <del>-element, waardoor de tekst wordt doorgehaald. Tekst die in een document wordt ingevoegd, kan worden aangeduid met het <ins>-element. Het <s>-element kan worden gebruikt om tekst die niet langer relevant of juist is, door te halen.

Doorhalingen, tussenvoegsels en doorhalingen worden soms gebruikt in juridische documenten om veranderingen van de ene versie naar de andere aan te geven. Helaas geven screenreaders niet altijd aan wanneer deze elementen worden gebruikt, zodat het moeilijk kan zijn om te zien of de auteur passages als doorgestreept heeft gemarkeerd. De makers van screenreadersoftware hadden dit probleem al lang geleden moeten oplossen, maar hebben dat niet gedaan. Deze beperkingen kunnen worden aangepakt door tekst aan de pagina toe te voegen (misschien met CSS `::before` en `::after`) om het begin en einde van tussenvoegsels en doorhalingen aan te geven.
CSS line-through creëert een visueel doorgehaald effect, maar dit wordt nooit overgebracht aan gebruikers van schermlezers.

### Knipperende en scrollende tekst
Gebruikers met aandachtsstoornissen of cognitieve handicaps kunnen gemakkelijk worden afgeleid door knipperende of scrollende tekst. Als scrollende tekst links bevat, zijn mensen met een beperkte fijne motoriek mogelijk niet in staat om op de bewegende links te klikken. Hoewel noch knipperende tekst noch marquee-tekst waarschijnlijk een aanval zal veroorzaken, vinden veel gebruikers deze effecten vervelend, wat reden genoeg is om ze niet te gebruiken.

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/textlayout/">WebAim's pagina over typografische lay-out</a>.

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>