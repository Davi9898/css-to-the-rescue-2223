# Vuurwerkshow in berglandschap
https://davi9898.github.io/css-to-the-rescue-2223/vuurwerkshow
# Week 1


### Inleiding

Voor het vak CSS to the rescue ga ik een vuurwerkshow maken. De bedoeling is dat deze interactief is en door middel van klikken afgevuurd kan worden. Het vuurwerk moet op de voorgrond gebeuren. Het werk zal in 2D gemaakt worden. Op de achtergrond zal een berg landschap te zien. Om het gebied groter te maken dan één scherm, ga ik proberen om een optie toe te voegen waardoor je een viewport width naar links en rechts kan. Dit zou bijvoorbeeld door een button gebeuren of door te scrollen met je muis.

### Onderzoek 

Ik ben er snel achter gekomen deze week dat ik niet kan gaan scrollen om de pagina naar links en naar rechts te laten bewegen. Hiervoor ga ik radio buttons gebruiken en de :has() selector toepassen. De bergen ga ik maken doormiddel van driehoekjes en met schaduwen. 

functionaliteiten:
- Scherm van het midden naar links en rechts kunnen bewegen.
- Bergen 
- Light/Dark mode door middel van op de zon te klikken
- Berg laten wegvliegen door erop te klikken (easter egg)
- Vuurpijlen / Vuurdozen
- Nice colors.
- Responsive ( media queries om bergen te verwijderen wanneer scherm kleiner wordt) 

### Schetsen

<img src="images/schets_css1.jpg" width=500px>

Je ziet hier hoe de drie verschillende views ontworpen moeten worden. Ook zie je de klikbare pijlen die voor interactie zorgen.

# Week 2

Deze week heb ik de lessen gemist omdat ik ziek was. Ondertussen ben ik thuis wel verder gaan werken aan mijn berglandschap

### Bergjes

De bergen heb ik gemaakt door gebruik te maken van de volgende code:
<code>
section:nth-of-type(1) > div:first-of-type { /* container, hiermee kan ik de berg gemakkelijk bewegen */ 
    position: absolute;
    bottom: 30vh;
    left: -3vw;
}

section:nth-of-type(1) > div:first-of-type > div:first-of-type { /* De berg zelf kan ik hier groter en kleiner maken. */
    position: absolute;
    content: '';
    bottom: 0;
    left: 0px;
    border-top: 0px solid transparent;
    border-right: 130px solid transparent; 
    border-bottom: 150px solid #68F193; 
    border-left: 130px solid transparent; 
    z-index: 5;
  }

section:nth-of-type(1) > div:first-of-type > div:nth-of-type(2) { /* De schaduw van de berg kan ik hier aanpassen */
    position: absolute;
    content: '';
    bottom: 0;
    left: 130px;
    border-top: 0px solid transparent;
    border-right: 100px solid transparent; 
    border-bottom: 150px solid #40945C; 
    border-left: 0px solid transparent; 
    z-index: 5;
    transform-origin: top right;
    transform: skewX(18deg);
}
</code>

Het verplaatsen van het scherm heb ik gemaakt door middel van radio buttons:
<code>
    <li>
                    <label for="links">
                        <span>Links</span>
                        <input type="radio" id="links" name="nav" value="links" />
                    </label>
                </li>

                <li>
                    <label for="home">
                        <span>Home</span>
                        <input type="radio" id="home" name="nav" value="home" checked />
                    </label>
                </li>

                <li>
                    <label for="rechts">
                        <input type="radio" id="rechts" name="nav" value="rechts" />
                    </label>
</code>

