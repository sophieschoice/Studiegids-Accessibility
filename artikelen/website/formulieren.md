---
layout: page
title: Toegankelijke formulieren
active: tutorials
---

Formulieren zijn niet meer weg te denken uit het moderne web: we geven onze adresgegevens op voor een bestelling of boeken een hotel. Ze zijn dus cruciaal voor het uitvoeren van bepaalde acties en het is daarom belangrijk dat formulieren toegankelijk zijn. In de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG) hebben daarom meerdere succescriteria betrekking op formulieren en formuliervalidatie. Onder andere wordt het volgende vereist:

* zorg ervoor dat formulieren logisch en gemakkelijk te gebruiken zijn
* zorg ervoor dat formulieren toetsenbord-toegankelijk zijn
* gebruik labels
* maak (fout)meldingen toegankelijk


## Mogelijke problemen

We bespreken even de problemen die voor kunnen komen met formulieren.

### Labels ontbreken of zijn niet geassocieerd

Een label beschrijft de functie van een formulierelement (tekstveld, selectievakje, keuzerondje, menu, enzovoort), en staat er meestal naast. Ziende gebruikers zien het verband, maar anderen niet. Het is daarom belangrijk dat er niet enkel een label aanwezig is, maar deze ook gekoppeld/geassocieerd is met het bijbehorende formulierelement. Dit zorgt ervoor dat een schermlezer het tekstlabel aankondigt wanneer de gebruiker naar het formulierelement navigeert.

{% highlight html %}
<label for="name">Naam:</label>
<input id="name" type="text" autocomplete="name">
{% endhighlight %}

Overeenkomende for- en id-waarden associëren het label met het bijbehorende formulierelement. Omdat id-attribuutwaarden op elke pagina uniek moeten zijn, kan een formulierbesturingselement maar één gekoppeld label hebben.

Je kunt de koppeling ook tot stand brengen door de labeltekst en de invoer binnen het element te plaatsen (en geen for en id te gebruiken).

{% highlight html %}
<label>Naam: <input type="text" autocomplete="name"></label>
{% endhighlight %}

Groepen besturingselementen, zoals checkboxen en keuzerondjes, hebben soms een label van een hoger niveau nodig (zoals "Verzendmethode" voor een groep verzendopties). Deze informatie kan aan de groep van formulierelementen worden gekoppeld met <code>&lgt;fieldset&gt;</code> en <code>&lt;legend&gt;</code>. De <code>&lgt;fieldset&gt;</code> definieert de groep en de <code>&lt;legend&gt;</code> bevat de beschrijving. Schermlezers kondigen de <code>&lt;legend&gt;</code> aan wanneer gebruikers naar de groep navigeren.

{% highlight html %}
<fieldset>
<legend>Selecteer jouw pizza:</legend>
<input id="ham" type="checkbox" name="toppings" value="ham">
<label for="ham">Ham</label><br>
<input id="pepperoni" type="checkbox" name="toppings" value="pepperoni">
<label for="pepperoni">Pepperoni</label><br>
<input id="margaritha" type="checkbox" name="toppings" value="margaritha">
<label for="margaritha">Margaritha</label><br>
<input id="hawai" type="checkbox" name="toppings" value="hawai">
<label for="hawai">Hawaï</label>
</fieldset>
{% endhighlight %}

De <code>&lgt;fieldset&gt;</code> bevat de groep van checkboxen, en de <code>&lt;legend&gt;</code> labelt de groep (hetzelfde principe geldt voor keuzerondjes). Screenreaders kunnen de <code>&lt;legend&gt;</code> herhalen voor elk vakje in de groep, dus de tekst moet kort en beschrijvend zijn.

Ook keuzelijsten hebben een een label nodig:

{% highlight html %}
<label for="favcity">Which is your favorite city?</label>
<select id="favcity" name="select">
<option value="1">Amsterdam</option>
<option value="2">Buenos Aires</option>
<option value="3">Delhi</option>
<option value="4">Hong Kong</option>
<option value="5">London</option>
<option value="6">Los Angeles</option>
<option value="7">Moscow</option>
<option value="8">Mumbai</option>
<option value="9">New York</option>
<option value="10">São Paulo</option>
<option value="11">Tokyo</option>
</select>
{% endhighlight %}

Opmerking
Vermijd het gebruik van meerkeuzemenu's. Niet alle browsers bieden intuïtieve toetsenbordnavigatie voor deze menu's. Veel gebruikers weten niet hoe ze <kbd>Control</kbd>/<kbd>Command</kbd> of <kbd>Shift</kbd> + klik moeten gebruiken om meerdere items te selecteren. Een groep aankruisvakjes biedt soortgelijke functionaliteit op een meer toegankelijke manier.

Nog een voordeel van labels is dat de gebruiker op het label kan klikken om de focus op het formulier-element te zetten. Dit is handig op kleine schermen en voor sommige mensen met motorische handicaps, vooral wanneer kleine aankruisvakjes en keuzerondjes worden gebruikt.

Klikken op labels is ook een gemakkelijke manier om te controleren of het formulier correct is gelabeld. Als klikken op het label de focus op het formulierelement zet of het activeert, dan is dat label programmatisch geassocieerd.

ARIA-labels (aria-labelledby en aria-label) kunnen worden gebruikt wanneer het niet mogelijk is om <label> te gebruiken.

* het ontbreken van labels is een inbreuk op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#labels-of-instructies">3.3.2 Labels of instructies</a>. 
* als er een label aanwezig is, maar niet gekoppeld met het bijbehorende formulierelement, is dit een inbreuk op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#info-en-relaties">1.3.1 Info en relaties</a>.


### Toetsenbordbediening

Alle velden en opties in een formulier moeten bedienbaar zijn met toetsenbord. 

Een jump menu is a een <code>&lt;select&gt;</code> (of een custom component die zich zo gedraagt) die pagina veranderingen of navigatie triggert wanneer een gebruiker klikt op een optie met de muis.
Bij navigatie met een toetsenbord kan alleen al het bladeren door de opties met de pijltjestoetsen de verandering triggeren. Deze onverwachte navigatie kan toetsenbordgebruikers en gebruikers van screenreaders in verwarring brengen en desoriënteren. 

Dit is op te lossen door een knop naast de keuzelijst te zetten, waarmee een gebruiker zijn keuze mee kan bevestigen. 

### Automatisch aanvullen

Formuliervelden waarin bepaalde typen gebruikersspecifieke informatie worden verzameld, hebben de juiste attributen voor autocomplete nodig om het invoergedeelte te identificeren. Gebruikers hebben er baat bij wanneer veelgebruikte veldtypen (naam, adres, geboortedatum, etc.) op consistente wijze op het web worden weergegeven. De mogelijkheid om het doel van elk veld programmatisch te bepalen maakt het invullen van formulieren eenvoudiger, vooral voor mensen met cognitieve beperkingen. Hier kan het <code>autocomplete</code> attribuut voor worden gebruikt.

De MDN web docs hebben een [compleet overzicht van alle waarden voor het autocomplete attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/autocomplete) die je kan gebruiken:


### Verplichte velden

Verplichte velden worden gewoonlijk aangeduid met een asterisk, maar gebruikers begrijpen deze conventie niet altijd. Maar naast visueel moet dit ook wel programmatisch aangeduid worden, zodat screenreaders dit kunnen aankondigen. 

Als de aanduiding dat een veld vereist is buiten het invoerlabel wordt gepresenteerd, zal de toepassing van het attribuut <code>aria-required="true"</code> ervoor zorgen dat screenreaders (naast het label) aankondigen dat het veld verplicht is. Dit attribuut heeft geen visuele impact en verzorgt verder ook geen validatie van formulieren.

### Ongeldige velden

Ongeldige velden worden vaak visueel aangeduid (met kleurverandering of icoontjes). Maar programmatisch ontbreekt deze informatie vaak, waardoor screenreaders dit niet door kunnen geven aan hun gebruikers. 

Om programmatisch aan te geven aan een veld ongeldig is, kan het <code>aria-invalid="false"</code> attribuut gebruiken. Je kunt dit toepassen op verplichte velden die de gebruiker leeg heeft gelaten of op velden die op een andere manier niet gevalideerd zijn. De standaardwaarde van het attribuut is <code>false</code>, maar dient bij het valideren van het formulier met JavaScript naar <code>true</code> getoggeld worden als een veld ongeldige invoer bevat.

Voorbeeld: 

{% highlight html %}
<input id="name5" type="text" autocomplete="name" aria-invalid="true">
{% endhighlight %}

### Instructies ontbreken of worden niet voorgelezen

Uitleg en tips bij een formulier, of bij specifieke velden, is belangrijk. Als een datum op een bepaalde manier ingevuld moet worden, bijvoorbeeld.

Gebruikers van screenreaders navigeren met de Tab-toets. Hoewel labels worden aangekondigd wanneer formulierelementen toetsenbordfocus krijgen, wordt andere tekst tussen de formulierbesturingselementen meestal overgeslagen. Zorg ervoor dat alle instructies aan het begin van het formulier staan, of koppel ze aan specifieke velden met <code>aria-describedby</code>.

Ook voor mensen die wel zien, zijn instructies belangrijk. Zorg daarom dat uitleg of tips bij een veld zowel visueel al programmatisch worden meegegeven. 

### Validatie

Formuliervalidatie zorgt ervoor dat webformulieren worden ingevuld en verzonden met alle noodzakelijke informatie in het juiste formaat. Foutherstel begeleidt een gebruiker bij het herstellen van ontbrekende of onjuist geformatteerde informatie als dit wordt ontdekt. 

Formuliervalidatie en foutherstel kunnen op verschillende manieren worden geïmplementeerd: 

* server-zijde: de formulierinformatie wordt ingediend en geanalyseerd door de webserver, en de nodige feedbackberichten worden naar een nieuw gegenereerde webpagina geschreven.
* clientzijde: de formuliervalidatie en het foutherstel worden uitgevoerd in de webclient of -browser met behulp van JavaScript en gegenereerd in de webpagina.

Voordelen van server-side validatie en foutherstel zijn onder meer:

* Het formulier kan worden ingevuld en verzonden zonder onderbreking van de validatie waarschuwingen, fouten of waarschuwingen.
* De gebruiker hoeft geen scripting ingeschakeld te hebben in zijn browser.
* Validatiemechanismen zijn moeilijker te omzeilen of te wijzigen, waardoor het veiliger is.

Voordelen van client-side validatie en foutherstel:

* Validatie kan in real time plaatsvinden, voordat de gebruiker de formuliergegevens naar de server stuurt.
* Voor de functionaliteit is geen server-side scripting nodig. Sommige gebruikers kunnen scripting in hun browser uitschakelen. 

Daarom zouden ontwikkelaars geen client-side scripting mogen vereisen om het webformulier nauwkeurig te kunnen invullen en verzenden. Bovendien kan elke client-side validatie of informatie gemakkelijk worden gewijzigd of uitgeschakeld in de browser. Voor de beste resultaten kunnen ontwikkelaars zowel server-side als client-side validatie en foutherstel gebruiken om zowel efficiëntie als veiligheid te bieden.

Formuliervalidatie zelf wordt meestal achter de schermen uitgevoerd en levert doorgaans geen toegankelijkheidsproblemen op, zolang de methode om het formuliervalidatiemechanisme aan te roepen maar toegankelijk is. Dit betekent dat het validatie- en verzendproces beschikbaar moet zijn bij gebruik van zowel de muis als het toetsenbord.

Het formulier moet ook naar de server worden verzonden als client-side scripting niet beschikbaar is. Formulieren die alleen afhankelijk zijn van scriptfuncties of event handlers moeten vermeden worden. Gebruik in plaats daarvan een echte URL-actiewaarde voor het formulier. Client-side validatie kan nog steeds worden aangeroepen, en het zou eerst worden verwerkt als scripting is ingeschakeld.

### Foutherstel

Als client-side of server-side validatie fouten in het formulier ontdekt, dan is er een 3-stappen proces om te zorgen voor bruikbaar en toegankelijk foutherstel:

* Waarschuw de gebruiker op een duidelijke en toegankelijke manier over de aanwezigheid van de fout.
* Geef de gebruiker gemakkelijk toegang tot de formulierelementen die gewijzigd moeten worden.
* Het formulier opnieuw indienen en valideren.

Er zijn drie manieren om aan deze eisen te voldoen. Elke aanpak heeft voor- en nadelen en kan optimaal zijn, afhankelijk van de inhoud, lay-out en complexiteit van het formulier.

1. Informeren en dan focus geven

De eerste stap is om de gebruiker te informeren dat er een fout is opgetreden. Deze foutmelding moet zichtbaar, informatief en direct toegankelijk zijn. Een manier om dit te bereiken is het gebruik van een JavaScript alert box - de browser geeft dan een zeer toegankelijke alert. Een ander alternatief is een modal dialog om de gebruiker op de hoogte te brengen van de fout, hoewel dialogs veel meer inspanningen vereisen om de toegankelijkheid te garanderen.

JavaScript-waarschuwing die vraagt om een waarde in te voeren voor het veld Voornaam.
Het voordeel van de aanpak "eerst waarschuwen, dan scherpstellen" is dat gebruikers onmiddellijk op de hoogte worden gebracht van fouten en het probleem vervolgens gemakkelijk direct kunnen oplossen. Het belangrijkste nadeel is dat slechts één fout per keer wordt aangegeven en aangepakt.

2. Geef fouten bovenaan weer

De foutmelding kan ook op de webpagina zelf worden geschreven. Wanneer client-side scripting beschikbaar is, kan de foutmelding naar de pagina worden geschreven voordat het formulier wordt verzonden. Met server-side scripting wordt de formulierpagina meestal opnieuw gegenereerd om het oorspronkelijke formulier met de juiste boodschap te bevatten.

De "Errors on top" aanpak toont de foutmelding boven het formulier. Bij presentatie moet de focus op deze foutmelding worden gezet, zodat gebruikers van schermlezers en toetsenborden de foutmelding onmiddellijk kunnen openen zonder deze te hoeven zoeken tussen de rest van de pagina-inhoud. De focus kan op het bericht worden gezet met client-side scripting met behulp van JavaScript focus(), of de server-gegenereerde pagina kan een ankernaam in de URL opnemen (bijv. http://myserver.com/form.php#errormessage) die de focus direct op het foutberichtelement zal zetten als het de bijbehorende id-attribuutwaarde krijgt (bijv. ```<p id="errormessage">```).
In de foutmelding moet duidelijk worden beschreven welke fouten zich voordoen en hoe deze moeten worden opgelost. Bijvoorbeeld: "Cursusnummer is niet geldig" is niet zo nuttig als "Cursusnummer moet een getal van 3 cijfers zijn". Het kan nuttig zijn de gebruiker te laten weten hoeveel fouten er zijn ontdekt.
Zodra de gebruiker de foutmelding te zien krijgt, moet een mechanisme worden geboden om snel toegang te krijgen tot de formulierinvoer(en) die moet(en) worden gecorrigeerd. In de foutmelding kan een link worden opgenomen om de aandacht op het juiste formulierelement te vestigen.
Voorbeeld van een foutmelding met directe links naar de te herstellen formulierelementen.
Het voordeel van de "Errors on top" aanpak is dat alle fouten samen worden gepresenteerd. Het nadeel is dat als er veel fouten zijn, het moeilijk kan zijn voor de gebruiker om ze allemaal te onthouden, te vinden en aan te pakken.

3. Inline fouten

Een andere aanpak is om de foutmeldingen binnen het formulier weer te geven in de context van het formulierelement dat aandacht nodig heeft. Deze aanpak vereist visueel onderscheidende foutmeldingen, zodat de visuele aandacht er onmiddellijk op wordt gevestigd. De foutmeldingen moeten gekoppeld worden aan hun respectievelijke besturingselementen (via labeling of aria-describedby). Het is meestal het beste om de focus te leggen op het eerste besturingselement dat aandacht nodig heeft.
Het voordeel van de "Inline errors" aanpak is dat de fouten verschijnen in context met hun respectievelijke controles. Het nadeel is dat de gebruiker visueel moet scannen of navigeren door het formulier om de ongeldige controles en hun respectievelijke foutmeldingen te ontdekken. Dit kan enige tijd duren.
Een combinatie van "fouten bovenop" en "Inline fouten" technieken kan vaak optimaal zijn, omdat het profiteert van de voordelen van beide benaderingen terwijl het de nadelen minimaliseert.
aria-invalid
Ongeacht het mechanisme dat gebruikt wordt om formulierfouten te herkennen en te herstellen, moet aria-invalid="true" over het algemeen ingesteld worden op elk ongeldig formulierelement. Dit attribuut zorgt ervoor dat screenreaders het besturingselement als "ongeldig" herkennen of als iets dat aandacht nodig heeft.


## Samenvatting

In alle gevallen kan een zorgvuldige gebruikerstest meestal moeilijkheden of problemen aan het licht brengen in de bruikbaarheid van formulieren, de validatie en de mechanismen voor foutherstel. Hoewel er veel methoden zijn om de bruikbaarheid en validatie van formulieren en een toegankelijk, gebruikersvriendelijk foutherstel te garanderen, moeten de volgende algemene principes worden toegepast:

* Bouw formulieren die gemakkelijk te gebruiken en intuïtief zijn, met alle nodige instructies, aanwijzingen en prompts.
* Zorg ervoor dat de formulieren toegankelijk zijn via het toetsenbord.
* Koppel formulier `<label>`-elementen aan formulierelementen.
* Gebruik fieldsets en legenda's om groepen selectievakjes en keuzerondjes aan elkaar te koppelen.
* Voeg noodzakelijke instructies toe aan formulier `<label>`-elementen (bijv. verplichte of speciaal opgemaakte besturingselementen)
* Steun niet alleen op JavaScript voor formulierindiening, validatie en foutherstel.
* Informeer de gebruiker op een duidelijke en toegankelijke manier over eventuele validatiefouten met informatieve feedbackberichten.
* Geef de gebruiker gemakkelijk toegang tot de formulierelementen die moeten worden gewijzigd.
* Sta herindiening en hervalidatie van formulierinformatie toe.