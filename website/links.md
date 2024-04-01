---
layout: page
title: Links
active: tutorials
---

Hyperlinks zijn een van de meest elementaire elementen van HTML, zoals de naam al aangeeft (HTML staat voor HyperText Markup Language). Het toegankelijk maken van hyperlinks is dan ook een van de meest elementaire en belangrijkste aspecten van webtoegankelijkheid. 

Voor het grootste deel is dit een eenvoudig. Standaard hyperlinks werken met alle technologieën en platforms en gebruikers van alle bekwaamheden kunnen er toegang toe krijgen, hetzij rechtstreeks, hetzij met behulp van een of andere ondersteunende technologie. Maar zoals te verwachten valt, komt er bij de toegankelijkheid van hypertekstlinks meer kijken dan alleen het maken van een link. Sommige soorten links zijn toegankelijker dan andere, en sommige soorten links zijn volledig ontoegankelijk voor mensen met bepaalde soorten handicaps. 

Omdat links zo fundamenteel zijn voor de functionaliteit van webinhoud, vormen ontoegankelijke links een van de ernstigste belemmeringen voor algemene toegankelijkheid.

## Problemen

### Toegankelijkheid van links via het toetsenbord

Gebruikers moeten in staat zijn om naar elke link te navigeren en deze te selecteren met alleen het toetsenbord. In de meeste browsers kunnen gebruikers met de <kbd>Tab<kbd>-toets van link naar link springen, en met de <kbd>Enter<kbd>-toets een link selecteren. Als de enige manier om een link te openen met een muis is, is de link onbruikbaar voor mensen die geen muis kunnen gebruiken. Hoe is het überhaupt mogelijk om een link te maken die ontoegankelijk is via het toetsenbord? De meest gebruikelijke methode is door gebruik te maken van JavaScript event handlers die geen toetsenbord-toegang toestaan.

### Links die nergens naartoe gaan

Links moeten een niet-leeg href attribuut hebben om als echte links beschouwd te worden en om toegankelijk te zijn voor toetsenbordgebruikers.

Een van de grootste belemmeringen is het maken van links die nergens heen gaan. Ontwikkelaars gebruiken soms JavaScript om dynamische menu's te maken die naar beneden vallen wanneer de gebruiker met de muis over bepaalde links gaat. In sommige gevallen gaat de link zelf helemaal nergens heen, en dient hij alleen om de links in het dropdownmenu, die wel een echte bestemming hebben, zichtbaar te maken. Dergelijke links hebben vaak een pondteken als linkbestemming, wat betekent dat de linkbestemming dezelfde pagina is; klikken op de link levert niets op. Zowel toetsenbordgebruikers als muisgebruikers zullen helemaal niets ondervinden wanneer ze proberen de link te activeren.

Slecht voorbeeld

De link in dit voorbeeld gaat nergens heen. Het enige doel is om een JavaScript functie te activeren.
```<a href="#" onmouseover="dropdownmenu()">Products</a>```

Muisgebruikers kunnen ten minste klikken op de links in het vervolgkeuzemenu, maar toetsenbordgebruikers hebben geen toegang tot het vervolgkeuzemenu, dus de link is volledig nutteloos en alle linkbestemmingen in het vervolgkeuzemenu zijn volledig ontoegankelijk voor hen. Eén oplossing is om het drop-down menu te laten vallen en in plaats daarvan standaard hypertext links te gebruiken. Een andere oplossing is om een echte link-bestemming op te geven (b.v. href="products.htm") die dezelfde links zou bevatten die beschikbaar zijn via het uitklapmenu. 

### Onduidelijke of algemene linkteksten

1. De meeste screenreaders zeggen "link" voor elke link. Bijvoorbeeld, een "producten" link zou worden gelezen als "link producten" door JAWS.

Wat dit betekent: links hoeven dus geen "link" in de linktekst te bevatten, omdat alle gebruikers al weten dat de link een link is. Dit is meer een probleem met afbeeldingen die als link worden gebruikt. De alt-tekst voor een afbeelding hoeft niet te zeggen "link" of "link to". Anders zullen JAWS gebruikers horen "link graphic link to Products," wat overbodig is.

2. Tabben van link naar link is een manier om de inhoud van het web door te bladeren, vooral als gebruikers een bepaald deel van een website proberen te vinden.

Implicatie 1: Links moeten zinvol zijn buiten de context. Zinnen als "klik hier", "meer", "klik voor details" enzovoort zijn dubbelzinnig wanneer ze uit hun context worden gehaald. Tegelijkertijd zou het overkill zijn om ervoor te zorgen dat elk detail over een link-bestemming kan worden onderscheiden door te luisteren naar de context van de link. Gebruikers zouden niet willen horen "Pagina met producten waarop een lijst van al onze producten wordt gepresenteerd, inclusief softwareproducten en opleidingsproducten, met een lijst van prijzen en beschikbaarheid per regio (deze pagina gebruikt hetzelfde navigatiesjabloon als de pagina waarop u zich nu bevindt)". Misschien zou een beter alternatief een link zijn die gewoon "Producten" zegt.

Implicatie 2: Plaats de onderscheidende informatie van links aan het begin van een link. Zet niet eerst extra informatie, Bijvoorbeeld niet "Link opent in een nieuw venster: Producten." Zeg in plaats daarvan "Producten (opent in een nieuw venster)" (of iets van die strekking). Dit is vooral belangrijk in dit voorbeeld als meerdere links in een nieuw venster openen. Als de verklarende informatie eerst komt in plaats van de hoofdinformatie, moeten gebruikers van schermlezers de zin "link opent in een nieuw venster" steeds opnieuw aanhoren. Ze zullen moeilijker onderscheid kunnen maken tussen de verschillende links, of er in ieder geval langer over doen.

3. Gebruikers van schermlezers kunnen met een sneltoets de lijst van alle op de pagina aanwezige links bekijken. Dit is vooral nuttig als zij naar een bepaalde link zoeken.

Implicatie: Gebruik linkwoorden en -zinnen die ondubbelzinnig zijn en die intuïtief kunnen worden georganiseerd, ongeacht de volgorde (de schermlezer kan ze sorteren in volgorde van voorkomen of alfabetisch). Bijvoorbeeld, de zin "neem contact met ons op" is een veel voorkomende zin waar gebruikers toegang toe willen hebben. Als de link zegt "u kunt contact met ons opnemen", "hoe neemt u contact met ons op" of een andere zin die minder intuïtief is, kunnen gebruikers de link moeilijker vinden.

Links zijn nuttiger als ze zinvol zijn buiten de context. Auteurs moeten niet-informatieve linkzinnen vermijden zoals:

- klik hier
- hier
- meer
- lees meer
- link naar [een of andere linkbestemming]
- info

In feite is de zin "klik hier" onnodig, zelfs als hij voorafgaat aan een zinvollere zin. Bijvoorbeeld, een link die zegt "klik hier voor het weer van vandaag" kan worden ingekort tot "het weer van vandaag". In sommige gevallen kan het zinvol zijn om een linkzin vooraf te laten gaan door "meer" of "lees meer over" (bijvoorbeeld "meer over de opwarming van de aarde"), maar als deze extra woorden vermeden kunnen worden, is het waarschijnlijk het beste om ze te vermijden (bijvoorbeeld "opwarming van de aarde" kan dezelfde betekenis overbrengen als "meer over de opwarming van de aarde," afhankelijk van de context).

### Lange links

Er is geen maximum toegestane lengte van de linktekst. Om praktische redenen moet de link lang genoeg zijn om het doel van de link over te brengen en niet langer. Auteurs van inhoud hebben de vrijheid om betekenis te geven aan hun inhoud op een manier die voor hen zinvol is. Als algemene regel geldt echter dat links zo beknopt mogelijk moeten zijn zonder dat dit ten koste gaat van de betekenis.

Sommige auteurs maken links van hele zinnen, paragrafen, of zelfs meerdere paragrafen. Deze lange links zijn vrijwel zeker onnodig, en zijn gebruikersonvriendelijk voor gebruikers van schermlezers. Vergeet niet dat blinde gebruikers niet visueel door lange links kunnen bladeren. Ze moeten naar de hele tekst luisteren. Sommigen raken gefrustreerd van lange linkteksten en gaan ongeduldig door naar de volgende link als ze na de eerste paar woorden het doel van de link niet begrijpen. Hoewel auteurs dit gedrag niet kunnen controleren, kunnen ze wel enkele bronnen van frustratie controleren. Korte, beknopte links zullen gebruikers van schermlezers minder frustreren dan lange, onnauwkeurige links.
Korte links

### Kleine links 

Er is ook geen minimum toegestane lengte van de linktekst, zolang de link maar niet leeg is (zie hieronder). In de meeste gevallen moeten links bestaan uit woorden of zinnen. In sommige gevallen kan het echter zinvol zijn een enkel karakter, letter van het alfabet of cijfer te linken. Bijvoorbeeld, in een alfabetische index kan elke letter van het alfabet afzonderlijk als link worden gebruikt.

Het gevaar bij het gebruik van afzonderlijke tekens als links - of bij het gebruik van om het even welke kleine link (zoals een afbeelding van 10 pixel bij 10 pixel) - is dat sommige gebruikers moeilijkheden zullen hebben om op zo'n klein oppervlak te klikken. Iemand met hersenverlamming kan bijvoorbeeld wel de handen gebruiken om een muis te bedienen, maar kan moeite hebben met de precieze bewegingen en spiercontrole die nodig zijn om op een kleine link te klikken. Auteurs kunnen deze problemen beperken door kleine links groter te maken, het lettertype van links met één teken te vergroten, of het doelgebied groter te maken door witruimte (zoals CSS padding) op te nemen in kleine links. Bovendien moeten kleine aangrenzende links voldoende witruimte hebben (zoals CSS-marges voor links) om te voorkomen dat gebruikers per ongeluk op de verkeerde link klikken.

### Lege links

Links mogen nooit leeg zijn. Ze moeten altijd tekst of afbeeldingen met alternatieve tekst bevatten. Naar een lege link kan worden genavigeerd, maar hij bevat geen inhoud. Dit kan zeer verwarrend zijn voor gebruikers van toetsenborden en schermlezers.

### URL's als links

Webadressen, of URL's, brengen twee soorten uitdagingen met zich mee:

- Leesbaarheid
- Lengte

URL's zijn niet altijd menselijk leesbaar of schermlezer-vriendelijk. Veel URL's bevatten combinaties van cijfers, letters, ampersands, streepjes, underscores en andere tekens die zinvol zijn voor scripts en databases, maar die weinig of geen zin hebben voor de gemiddelde persoon. In de meeste gevallen is het beter om een menselijk leesbare tekst te gebruiken in plaats van de URL. De menselijk leesbare link Constructing Accessible Web Sites is gebruikersvriendelijker dan de link naar het boek met dezelfde titel op Amazon.com, die bestaat uit een link van 108 tekens vol getallen, schuine strepen en tekst die niet erg menselijk leesbaar is. (http://www.amazon.com/exec/obidos/ASIN/1590591488/qid=1116957951/sr=2-1/ref=pd_bbs_b_2_1/103-5755258-8204633)

Betekent dit dat URL's nooit als links mogen worden gebruikt? Nee. Als de URL relatief kort is (zoals de homepage van een site), mag de URL als linktekst worden gebruikt. Het is belangrijk om rekening te houden met gebruikers van schermlezers die de langere, minder begrijpelijke URL's moeten aanhoren.

### Alternatieve tekst voor afbeeldingen die als link worden gebruikt

Wanneer afbeeldingen als links worden gebruikt, vervult de alternatieve tekst de functie van linktekst. Net als bij gelinkte tekst hoeft de alt-tekst van gelinkte afbeeldingen gebruikers niet te informeren dat de link een link is, aangezien dit al wordt weergegeven. De alternatieve tekst moet de inhoud van de afbeelding en de functie van de link duidelijk maken. In de meeste gevallen zijn de inhoud van de afbeelding en de functie van de link dezelfde, zodat deze tekst zeer beknopt kan zijn (bv. alt="Producten"). In sommige gevallen kan het meer tekst vereisen (bv. alt="Grafiek met 10% verkoopstijging over de laatste tien jaar met link naar meer verkoopgegevens").


Belangrijk: afbeeldingen die het enige onderdeel van een link zijn, MOETEN alternatieve tekst hebben. Als een gelinkte afbeelding geen alternatieve tekst heeft, kan een schermlezer de bestandsnaam van de afbeelding of de URL waarnaar gelinkt wordt, lezen.

### Uiterlijk van links

Links moeten eruit zien als links, en niets anders. Gebruikers kunnen gefrustreerd raken als ze proberen te klikken op tekstfragmenten of afbeeldingen die eruit zien als links maar het niet zijn. Ze zullen ook gefrustreerd raken als ze hun muis over de hele pagina moeten bewegen om links te ontdekken die er niet als links uitzien.

Browsers onderstrepen hyperlinks standaard. Het is mogelijk om de onderstreping te verwijderen met behulp van Cascading Style Sheets (CSS), maar dit is meestal een slecht idee. Gebruikers zijn gewend links onderstreept te zien. In bodyteksten kunnen ze al dan niet zien welke tekst gelinkt is als de onderstreepte conventie niet wordt gebruikt.

Hoewel gebruikers gewend zijn om links in de hoofdinhoud onderstreept te zien, zijn ze ook gewend om tabbladen en belangrijke navigatiefuncties te zien (vaak gemaakt als afbeeldingen in plaats van tekst) zonder onderstreping. In deze gevallen moeten de gelinkte items zo worden ontworpen dat het duidelijk is dat de gebruiker erop kan klikken om een actie uit te voeren.
Opmerking

WCAG 2.1 stelt twee extra eisen aan bodytext-links die niet standaard onderstreept zijn:

- De linktekst moet een contrastverhouding van 3:1 hebben ten opzichte van de omringende niet-linktekst.
- De link moet een "niet-kleurenindicator" (meestal de introductie van de onderstreping) tonen bij zowel muisoverslag als toetsenbordfocus.

Deze twee vereisten helpen ervoor te zorgen dat alle gebruikers links kunnen onderscheiden van niet-link tekst, zelfs als ze slechtziend zijn, een kleurentekort hebben, of de kleuren van de pagina hebben overschreven.

### Hover- en focuseffecten

Veel sites hebben visuele muisoverdeffecten voor links geïmplementeerd, zoals het toevoegen van achtergrondgloed, slagschaduwen, kleurveranderingen of onderstreping. Deze effecten helpen gebruikers te weten dat er op het item kan worden geklikt en dat de muisfocus op een bepaalde link ligt.

Om deze effecten apparaatonafhankelijk te maken, moet ervoor worden gezorgd dat ze zowel met de muis als met het toetsenbord kunnen worden geactiveerd. In CSS betekent dit dat zowel de :hover- als de :focus-pseudoklasse moeten worden gebruikt.

Belangrijk: Bijna altijd wanneer a:hover (of andere hover-effecten) in CSS worden gedefinieerd, moet dit worden gewijzigd in a:hover, a:focus om ervoor te zorgen dat dezelfde visuele presentatie beschikbaar is wanneer toetsenbordgebruikers naar de link navigeren of 'tabben'.


### Links naar ankers op dezelfde pagina

Links worden vaak gebruikt om naar een andere plaats op de huidige pagina te springen. De links naar de inhoud van het artikel hierboven zijn daar een voorbeeld van. Paginalinks kunnen een grote toegankelijkheidsfunctionaliteit bieden, vooral met "Skip"-links om de paginanavigatie te omzeilen of links om over lange lijsten met links of andere complexe of potentieel verwarrende informatie heen te springen.

Schermlezers herkennen in het algemeen in-paginalinks door er "in page link" bij te lezen. Slechtziende gebruikers zijn zich er echter mogelijk niet van bewust dat een link naar een andere locatie binnen dezelfde pagina springt. De gebruiker kan in de war raken wanneer de browserpagina niet verandert. Paginalinks moeten in het algemeen zo worden gepresenteerd dat het visueel en/of contextueel duidelijk is dat het om een paginalink gaat.

### Links naar niet-HTML-bronnen

Gebruikers moeten in het algemeen worden gewaarschuwd voor links die leiden naar niet-HTML-bronnen, zoals PDF-bestanden, Word-bestanden, PowerPoint-bestanden, enzovoort. Er is echter discussie over de vraag of de auteur van de inhoud of de browser degene moet zijn die de gebruiker waarschuwt. Het probleem is dat geen van de browsers of screenreaders de gebruiker momenteel waarschuwt, dus het debat is meer theoretisch dan praktisch.

Een link naar een PowerPoint-diavoorstelling zou bijvoorbeeld kunnen luiden: "Verkoopprognoses derde kwartaal (PowerPoint)" of iets dergelijks, en een link naar een PDF-bestand zou kunnen luiden: "Belastingformulier 1040 (PDF)" of iets dergelijks.

Belangrijk

Bij het identificeren van het bestandstype van de link, moet deze extra inhoud binnen de link worden gepresenteerd, in plaats van er net achter, zodat de informatie samen met de link wordt gepresenteerd als een screenreader-gebruiker navigeert via links of een lijst met links leest.

Gebruik liever
```<a href="1040.pdf">Tax form 1041 (PDF)</a>```
in plaats van
```<a href="1040.pdf">Tax form 1041</a> (PDF)```

### Links naar nieuwe vensters, pop-ups, andere frames of externe websites

Er is veel discussie over de verdiensten van links die openen in nieuwe vensters, pop-up vensters, of andere frames. Sommigen zouden ze volledig willen verbieden. Anderen geven toe dat ze soms geschikt kunnen zijn, maar bijna iedereen is het erover eens dat gebruikers gewaarschuwd moeten worden wanneer de link niet in het huidige venster of frame opent. Het toegankelijkheidsprobleem is dat sommige gebruikers in de war kunnen raken van de nieuwe vensters of tabbladen. Nieuwere screenreaders waarschuwen de gebruiker wanneer een link een nieuw venster opent, maar pas nadat de gebruiker op de link heeft geklikt. Older screen readers do not alert the user at all.  Gebruikers die kunnen zien, zien dat het nieuwe venster wordt geopend, maar gebruikers met cognitieve beperkingen kunnen moeite hebben om te interpreteren wat er zojuist is gebeurd. Als ze dan op de knop Terug in de browser proberen te klikken, gebeurt er niets, omdat er geen vorige link is om naar terug te gaan in een nieuw venster of tabblad.

Net als bij links naar niet-HTML-bestanden zouden browsers de gebruikers kunnen waarschuwen, maar de huidige browsers kunnen dit niet. Het is aan de auteurs om de gebruikers te waarschuwen. Auteurs kunnen deze informatie aan links toevoegen door deze tussen haakjes aan het eind van de link te plaatsen, bijvoorbeeld met de tekst "Biografische schets (opent nieuw venster)". Sommige sites gebruiken pictogrammen om dezelfde boodschap over te brengen. Hieronder staan enkele van de iconen die door verschillende websites worden gebruikt.

Soms worden deze icoontjes gebruikt om aan te geven dat een link naar een externe site verwijst, in plaats van dat een nieuw venster wordt geopend, dus er kan enige verwarring ontstaan. Net zoals bij de bestandstypes hierboven, moeten deze icoontjes (met passende alternatieve tekst) binnen de link staan en niet er net achter.

Opmerking: soms worden achtergrondafbeeldingen (vaak in de vorm van CSS sprites) gebruikt om deze pictogrammen te presenteren. Omdat achtergrondafbeeldingen geen tekst bevatten en niet van alternatieve tekst kunnen worden voorzien, moet extra moeite worden gedaan om ervoor te zorgen dat gebruikers met een schermlezer dezelfde inhoud te zien krijgen als ziende gebruikers in de achtergrondafbeelding zien.

Zie ons artikel over alternatieve tekst voor meer details.

### Aangrenzende links

Bij het gebruik van een schermlezer, kan het soms een beetje moeilijk zijn om te zien wanneer een link eindigt en waar een aangrenzende link begint.  JAWS zegt "link" voor elke link, wat dit probleem minimaliseert, maar het kan een beetje moeilijker zijn met andere schermlezers. Een oplossing is om een niet-link teken tussen elke link te zetten.De verticale balk ( | ) wordt vaak voor dit doel gebruikt. Een andere oplossing is om de links in een geordende of genummerde lijst te zetten. Schermlezers hebben de neiging te pauzeren tussen items in de lijst, zodat de gebruiker hoorbaar onderscheid kan maken tussen afzonderlijke links.

### Lange lijsten met links 

Lange lijsten met links kunnen onhandig zijn om naar te luisteren als de persoon meer geïnteresseerd is in verhalende inhoud dan in navigerende inhoud. Een methode om dit potentiële probleem te omzeilen is door bovenaan een "skip" link te plaatsen waarmee gebruikers de lijst met links kunnen overslaan. Dit is in wezen hetzelfde concept als "navigatie overslaan"-links. Op pagina's waar de belangrijkste inhoud navigatie-inhoud is (zoals een inhoudsopgave), is een dergelijke oplossing waarschijnlijk onnodig.

In veel gevallen zullen gebruikers minder moeite hebben met het begrijpen van lange lijsten met links als de lijsten worden opgedeeld in kleinere stukken met beschrijvende kopjes. De kleinere stukken vormen een minder grote cognitieve belasting voor alle gebruikers, wat vooral gunstig kan zijn voor gebruikers met cognitieve beperkingen.

## Credits

Deze pagina is grotendeels gebaseerd op een vertaling van <a href="https://webaim.org/techniques/hypertext/">WebAim's pagina over links</a>.

## Bronnen

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>