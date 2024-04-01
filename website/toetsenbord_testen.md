---
layout: page
title: Testen van toegankelijkheid voor en met toetsenbord
active: tutorials
---
<p>Testen met een toetsenbord is een essentieel onderdeel van het testen van de toegankelijkheid van je website. Maar waar moet je op letten? Welke toetsen op je toetsenbord moet je gebruiken om te testen? Op deze pagina leg ik het allemaal uit.</p>

<div class="toc_container">
    <p class="toc_title">Inhoud</p>
    <ol class="toc_list">
        <li><a href="#waar-je-op-moet-letten">Waar je op moet letten</a></li>
        <li><a href="#de-toetsen-die-je-dient-te-gebruiken">De toetsen die je dient te gebruiken</a></li>
        <li><a href="#conclusie">Conclusie</a></li>
    </ol>
</div>

## Waar je op moet letten

  <ul>
    <li>Elk interactief element kan worden bereikt.</li>
      <ul>
        <li>links</li>
        <li>knoppen</li>
        <li>controls van formulieren (invoervelden, keuzelijsten, radio buttons, checkboxen)</li>
        <li>dingen die getriggerd worden door <code>:hover</code> zoals tooltips</li>
        <li>widgets en <span lang="en">custom</span> componenten, bijv. een date picker</li>
      </ul>
    <li>Elk interactief element krijgt een focusindicator.</li>
    <li>Navigatievolgorde moet logisch en intuïtief zijn.</li>
    <li>Bij modals en overlays:</li>
      <ul>
        <li>Deze moeten de volledige toetsenbordfocus hebben en behouden. Dat wil zeggen dat enkel de interactieve elementen in het venster bedienbaar zijn en focus krijgen. Als het venster wordt gesloten, dan pas is de achterliggende website weer bedienbaar met het toetsenbord.</li>
        <li>Wanneer het venster sluit, moet de focus meestal teruggaan naar het element dat het venster opende.</li>
      </ul>
    <li>Bij <span lang="en">custom</span> componenten en widgets worden de <a href="https://www.w3.org/TR/wai-aria-practices-1.1/" hreflang="en">ARIA Authoring Practices</a> gerespecteerd. En dan vooral de aanwijzingen die over bediening met toetsenbord gaan.</li>
    <li>Controleer de broncode op het gebruik van <code>tabindex</code>.</li>
    <li>Controleer dat event handlers in JavaScript device-onafhankelijk zijn.</li>
  </ul>

<div class="opmerking">
<p>💡 <b>Opmerking</b>: Een link is alleen toegankelijk voor toetsenbordgebruikers of wordt aan screenreaders gepresenteerd als een link wanneer het een <code>href</code>-attribuut heeft dat <strong>niet leeg</strong> is. Een link zonder <code>href</code>-attribuut of zonder ingevuld <code>href</code>-attribuut mogen <strong>niet</strong> worden gebruikt voor links.</p>
</div>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## De toetsen die je dient te gebruiken

<p>De volgende tabel bevat veel van de meest voorkomende online interacties en de toetsen die daar gebruikt voor dienen te worden.</p>

<table>
  <caption class="sr-only">Overzicht van toetsen die je dient te gebruiken bij het testen</caption>
  <thead>
    <tr>
      <th>Element of component</th>
      <th>Te gebruiken toets(en)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Navigeren naar interactieve elementen</td>
      <td>
        <ul>
          <li><kbd>Tab</kbd></li>
          <li><kbd>Shift</kbd> + <kbd>Tab</kbd> (achterwaarts navigeren)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Link</td>
      <td><kbd>Enter</kbd> om de link te openen.</td>
    </tr>
    <tr>
      <td>Knop</td>
      <td><kbd>Enter</kbd> of <kbd>Spatiebalk</kbd> om de knop te activeren.</td>
    </tr>
    <tr>
      <td>Selectievakjes (checkboxen)</td>
      <td><kbd>Spatiebalk</kbd> om een vakje wel of niet aan te kruisen.</td>
    </tr>
    <tr>
      <td>Keuzerondjes (radio buttons)</td>
      <td>
        <ul>
          <li>Met de pijltjestoetsen een optie selecteren.</li>
          <li><kbd>Tab</kbd> om naar het volgende element.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Keuzelijst (dropdown)</td>
      <td>
        <ul>
          <li>De <kbd>Spatiebalk</kbd> om de lijst in of uit te klappen.</li>
          <li>Pijltjestoetsen om in de lijst te navigeren.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Automatisch aanvullen (autocomplete)</td>
      <td>
        <ul>
          <li>Typen om te beginnen met filteren.</li>
          <li>Pijltjes om naar een optie te navigeren.</li>
          <li><kbd>Enter</kbd> om een optie te selecteren.</li>
        </ul>
      </td>    
    </tr>
    <tr>
      <td>Dialogs, modals en overlays</td>
      <td><kbd>Esc</kbd> om te sluiten.</td>
    </tr>
  </tbody>
</table>

<p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>

## Conclusie

<p>Je moet met een toetsenbord de volgende interactieve elementen kunnen bedienen:</p>
<ul>
    <li>links</li>
    <li>knoppen</li>
    <li>controls van formulieren (tekstvelden, keuzelijsten, radio buttons, checkboxen, …)</li>
    <li>dingen die getriggerd worden door <code>:hover</code> zoals tooltips</li>
    <li>widgets, bijv. een date picker</li>
</ul>

<p>Als je een element <strong>niet</strong> kan bedienen, is dit een inbreuk op succescriterium <a href="https://www.w3.org/Translations/WCAG21-nl/#toetsenbord">2.1.1 Toetsenbord</a> in de <a href="https://www.w3.org/Translations/WCAG21-nl/">Richtlijnen voor Toegankelijkheid van Webcontent</a> (WCAG).</p>

<div class="opmerking">
<p>👉️ Opmerkingen? Vragen? Iets onduidelijk of onvolledig? Of vond je het helemaal geweldig? Stuur me een <a href="mailto:sophie@sophieschoice.net">mailtje met je feedback</a>!</p>
</div>


 <p class="toplink">
  <a href="#top" title="Terug naar boven">&uarr; Terug naar boven</a>
</p>