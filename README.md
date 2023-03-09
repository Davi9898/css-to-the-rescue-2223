<img src="images/voorkant.png" width=1000px>

# Vuurwerkshow in berglandschap
# Table of contents
1. [Inleiding](#inleiding)
2. [Week 1](#week1)
3. [Week 2](#week2)
5. [Week 3](#week3)
6. [Week 3,5](#week3,5)
7. [Week 4](#week4)
8. [Realisatiepunten](#realisatiepunten)
9. [Leerpunten](#leerpunten)

https://davi9898.github.io/css-to-the-rescue-2223/vuurwerkshow2

### Inleiding <a name="inleiding"></a>

Voor het vak CSS to the rescue ga ik een vuurwerkshow maken. De bedoeling is dat deze interactief is en door middel van klikken afgevuurd kan worden. Het vuurwerk moet op de voorgrond gebeuren. Het werk zal in 2D gemaakt worden. Op de achtergrond zal een berg landschap te zien. Om het gebied groter te maken dan één scherm, ga ik proberen om een optie toe te voegen waardoor je een viewport width naar links en rechts kan. Dit zou bijvoorbeeld door een button gebeuren of door te scrollen met je muis.

# Week 1 <a name="week1"></a>

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

## Week 2 <a name="week2"></a>

Deze week heb ik de lessen gemist omdat ik ziek was. Ondertussen ben ik thuis wel verder gaan werken aan mijn berglandschap

### Dag 1
Op dag één ben ik bezig gegaan om de schermen 100vw naar links en naar rechts te laten bewegen. Dit heb ik gedaan door een translateX(-200vw -> 100vw) toe te passen. Dit heeft me wel even geduurd voordat me dit lukte, ik liep de heletijd tegen problemen aan. Ook wilde ik graag dat de gebruiker landde op de home page. Hieronder kun je zien hoe ik dit heb aangepakt:
```
body:has(input[value="home"]:checked) main {
    transform: translateX(-100vw);
}

body:has(input[value="links"]:checked) main {
    transform: translateX(0);
}

body:has(input[value="rechts"]:checked) main {
    transform: translateX(-200vw);
}
```
Hier zie je de labels en de radio buttons hoe die zijn gestructureerd:
```
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
```

### Dag 2
Op dag 2 ben ik mij gaan richten op het volledig focusen van het maken van het berglandschap. Ik heb eerst gekeken hoe ik de bergen kon gaan maken. Ik had eerder wel eens driehoekbergen gemaakt en piramides bij een cursus van Sanne. Dit kon ik mooi gebruiken. Natuurlijk heb ik ook inspiratie gebruikt van het internet.

### Bergjes

De bergen heb ik gemaakt door gebruik te maken van de volgende code:
```
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
```

### Feedback
Sanne heeft aangegeven dat ik custom properties kan toepassen, dat dit mij zal helpen. 

## Week 3 <a name="week3"></a>

### Dag 1
Op dag 1 van Week 3 heeft Sanne s'ochtends een gastcollege gegeven. Deze heb ik helaas niet kunnen bijwonen omdat ik een afspraak had in de ochtend. Vervolgens ben ik verder gegaan met het plaatsen van de verchillende bergen in het landschap. Ik ben vervolgens een cursus gaan volgen over het gebruik van SVG paden. We hebben het voornamelijk gehad over de offset-path: path; functie die CSS heeft te bieden. Hoe je een SVG path kan maken in bijvoorbeeld Figma en vervolgens kan exporteren. Deze open je dan als een txt bestand en hier kan je het SVG path uithalen. Wat ik ook erg interessant vond is het toevoegen van een delay aan een transition. Dit heb ik zelf nog nooit gebruik en was mij er ook niet van bewust dat dit mogelijk was. 

Vervolgens ben ik voor elke berg de kleur gaan veranderen voor een variabel en deze in de :root gestopt. Hierdoor kan ik de kleuren van de bergen en de grond veranderen wanneer ik zou willen. Ook biedt dit een functionaliteit voor als ik bijvoorbeeld een dark mode wil toevoegen. Ik had dit beter eerder kunnen implementeren, dit heeft erg veel tijd gekost.

functionaliteiten die ik nog wil toevoegen:
- Light/Dark mode door middel van op de zon te klikken
- Berg laten wegvliegen door erop te klikken (easter egg)
- Vuurpijlen / Vuurdozen die exploderen.
- Responsive ( media queries om bergen te verwijderen wanneer scherm kleiner wordt)

### Dag 2
Op dag 2 zijn we begonnen met een gastcollege van Manuel Matuzovic. Manuel is schrijver van het blog 100days of More or less modern CSS, hij heeft ons allerlei epische properties laten zien die CSS met zich mee draagt. Vervolgens ben ik met Sanne gaan zitten om te kijken naar custom properties. Ik kreeg een privé sessie omdat niemand anders zich hiervoor had aangemeld. Hierin gingen we mijn huidge bergen transformeren met een border-width zodat we custom properties makkelijk konden gebruiken. Hier stak ik veel van op en kreeg ik door hoe ik deze functionaliteit kan toepassen. 

Vervolgens lukte het me niet om het ijstopje op de berg te plaatsen op de manier waarop we nu de bergen hadden ge hercreëerd. Sanne vond de manier waarop het ging sowieso al lelijk volgensmij dus had hij het geniale idee om nogmaals de bergen te transformeren naar een nieuw landschap. Dit keer met bergen met wel een sneeuwstukje er boven op. Hieronder valt te zien hoe we dit gedaan hebben.
```

/*************/
/* SETTINGS  */
/*************/
section:nth-of-type(1) ul {
	display:flex;
	align-items:end;
	justify-content:center;
	margin:0;
	padding:0;
	list-style:none;


	background-color:transparent;
}

section:nth-of-type(1) li {
	position:absolute;
	bottom:15vw; 
	width:var(--width, 10em);
	height:var(--height, 10em);
	
	left:var(--left, 0);
	z-index:var(--z-index, 0);
}

section:nth-of-type(1) li > div {
	position:absolute;
	inset:0;
}

section:nth-of-type(1) li > div:nth-of-type(1) {
	background-color:var(--clr-sun, lightgreen);

	clip-path: polygon(
		var(--point, 50%) 0%, 
		var(--shade, 50%) 100%, 
		0% 100%, 
		var(--point, 50%) 0%
	);

}

section:nth-of-type(1) li > div:nth-of-type(2) {
	background-color:var(--clr-shade, green);
	
	clip-path: polygon(
		var(--point, 50%) 0%, 
		var(--shade, 50%) 100%, 
		100% 100%, 
		var(--point, 50%) 0%
	);

}

/* snow */
section:nth-of-type(1) div div {
	position:absolute;
	width:100%;
	height:var(--snow, 40%);
}

section:nth-of-type(1) div div {
	clip-path: polygon(36% 100%, 26% 70%, 10% 100%, 0 67%, 0% 0%, 100% 0%, 100% 66%, 86% 89%, 79% 56%, 68% 100%, 59% 72%, 45% 68%);

}

section:nth-of-type(1) div:nth-of-type(1) div {
	background-color:var(--snw-sun, #fff);
}


section:nth-of-type(1) div:nth-of-type(2) div {
	background-color:var(--snw-shade, #ccd);
}


/*************/
/* DE BERGEN */
/*************/

section:nth-of-type(1) li:nth-of-type(1) {
	--height:20em;
	--width:28em;
	
	--shade:70%;
	--point:30%;
	
	--snow: 40%;
	
	--clr-sun:moccasin;
	--clr-shade:saddlebrown;
	
	--snw-sun: #ff9;
	--snw-shade: #cc6;

    --left: 20vw;
}
```
Hieronder kun je bij het list item de berg net zo maken zoals je zelf wilt door de custom property aan te passen. Wat de code robuuster maken en er voor zorgt dat er minder lines of code worden gebruikt. Dit heeft me enorm geholpen om de kwaliteit van zowel m'n code als m'n bergen vooruit te brengen. Ik moet nog wel veel doen zoals echt vuurwerk maken.

functionaliteiten die ik nog wil toevoegen:
- Berg laten wegvliegen door erop te klikken (easter egg)
- Vuurpijlen / Vuurdozen die wegvliegen (voetzoekers)
- Responsive ( media queries om bergen te verwijderen wanneer scherm kleiner wordt)

## Week 3,5  <a name="week3,5"></a>
### Dag 1
Deze dag ben ik de hele dag bezig geweest om de berglandschappen juist te krijgen, ik wilde voorheen drie verschillende berglandschappen maken. Dit zijn nu drie landschappen geworden met ongeveer dezelfde bergen. Alleen in dachlicht, zonsondergang en nacht. Ook heb ik verschillende veranderingen gemaakt. Met de huidige manier van bergen maken had ik toch wat complicaties met het responsive houden van de berg. Ik heb nu de height veranderd door een aspect ratio, ook schaalt de width ten opzichte van de parent nu in percentage. Hierdoor schalen de bergen mooi. Eigenlijk vind ik ze nu weer te klein wanneer je op een klein scherm zit. Hier kan ik misschien nog een draai aan geven.

functionaliteiten die ik nog wil toevoegen:
- Berg laten wegvliegen door erop te klikken (easter egg)
- Vuurpijlen / Vuurdozen die wegvliegen (voetzoekers)
- Responsive ( media queries om bergen te verwijderen wanneer scherm kleiner wordt)

### Dag 2
Deze dag ben ik bezig geweest het maken van media queries voor de bergen. Ik laat nu doormiddel van media queries bergen verdwijnen. Eigenlijk loopt het allemaal nog niet helemaal lekker maar door tijdgebrek ben ik genoodzaakt om verder te gaan.

```
@media only screen and (max-width: 800px) {
  section:nth-of-type(1) li:nth-of-type(1),
  section:nth-of-type(1) li:nth-of-type(3),
  section:nth-of-type(1) li:nth-of-type(8),
  section:nth-of-type(1) li:nth-of-type(11) {
    display: none;
  }
```
## Week 4 <a name="week4"></a>
### Dag 1
Deze eerste dag van de laatste week ben ik bezig gegaan met het maken van vuurwerk. Ik had bedacht om pijlen te maken die vervolgens de lucht in schieten als er op een button gedrukt wordt. 
Pijl: 
```
section:nth-of-type(1) > ul:nth-of-type(2) li div:nth-of-type(1) {
  position: absolute;
  width: 30px;
  height: var(--kopheight, 15px);
  background-color: var(--kopkleur, red);
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
  right: 0px;
  z-index: 10;
  transform: scaleX(0.5);
}

/* stok element */

section:nth-of-type(1) > ul:nth-of-type(2) li div:nth-of-type(2) {
  position: absolute;
  width: var(--stokwidth, 10px);
  height: var(--stokheight, 60px);
  background: repeating-linear-gradient(
    45deg,
    var(--stokgradientkleur1, #ffffff),
    var(--stokgradientkleur1, #ffffff) 10px,
    var(--stokgradientkleur2, #ff0000) 10px,
    var(--stokgradientkleur2, #ff0000) 20px
  );
  top: 14px;
  border-radius: 2px;
}
```
Deze worden dan individueel gepositioneerd en vervolgens door dat er aan het list item een transform hangt. Kunnen ze de lucht in geschoten worden.

### Dag 2
Op dag 2 heb ik de explosie toegevoegd. De bedoeling is dat de explosie in de verte zichtbaar wordt. De explosies komen nadat de laatste pijl is afgevuurd. Ik heb hier een bron voor gebruikt: https://codepen.io/MinzCode/pen/abmwmOG. Wanneer het label van de desbetreffende pagina aangeklikt wordt door de gebruiker. Dan gaan eerste de pijlen en vervolgens door een animation delay volgen de explosies.
```
body:has(section:nth-of-type(1) #animate1:checked)
  section:nth-of-type(1)
  > div:nth-of-type(3)
  > div::before,
body:has(section:nth-of-type(1) #animate1:checked)
  section:nth-of-type(1)
  > div:nth-of-type(4)
  > div::before,
body:has(section:nth-of-type(1) #animate1:checked)
  section:nth-of-type(1)
  > div:nth-of-type(5)
  > div::before,
body:has(section:nth-of-type(1) #animate1:checked)
  section:nth-of-type(1)
  > div:nth-of-type(6)
  > div::before,
body:has(section:nth-of-type(1) #animate1:checked)
  section:nth-of-type(1)
  > div:nth-of-type(7)
  > div::before,
body:has(section:nth-of-type(1) #animate1:checked)
  section:nth-of-type(1)
  > div:nth-of-type(8)
  > div::before {
  animation: explosion 2s ease-in-out 3;
  animation-delay: 3s;
}
```
Na het formatteren van mijn document is de vuurwerkshow afgerond

### Realisatiepunten <a name="realisatiepunten"></a>
Er zijn enkele punten die leuk waren geweest om te implementeren maar waar ik niet aan toe ben gekomen door tijdgebrek:
* Per dagdeel een verschillende show
* Bergen die wegvliegen (easter egg)

### Leerpunten <a name="leerpunten"></a>
* Selectors goed gebruiken
* ::before ::after
* :has()
* Custom properties
* Bergjes maken
* Semantisch HTML

