# Groen in Beeld
Geeft op peildatum een overzicht van hoeveel groen er in de gemeente Rotterdam gepland is voor realisatie in of voor 2022.

## toelichting
Per peildatum wordt bepaald welke IP's op dat moment actueel zijn en waarvan de realisatiedatum vóór op in 2022 gepland is. Van deze plannen wordt voor de gehele gemeente en per gebied het totaal aan extra groen bepaald.

## bronnen
* Overzicht van contouren van uitgezonden inrichtingsplannen

  `K:\GEODATA\Kennisloods\Data\IP_uitzendingen_overzicht\IP_overzicht.gdb`
* Overzicht van groenoppervlaktes per uitgezonden IP

  `K:\GEODATA\Kennisloods\Data\GroenInBeeld\IP_Groen.csv`

Beide bronnen zijn afkomstig van het [overzicht van inrichtingsplannen](https://github.com/kennisloods/inrichtingsplannen-op-de-kaart).

## bewerking

1. Inlezen IP's die op de peildatum bijdragen aan de vergroeningsopgave
2. Per IP inlezen van het huidige oppervlakte groen en het te realiseren oppervlakte aan groen
3. Voor de gehele gemeente en per gebied sommeren van de oppervlaktes en berekenen van de toename.

Ad 1).
Een IP doet mee als:

* het contour bekend is (zie <https://github.com/kennisloods/inrichtingsplannen-op-de-kaart>)
* de uitzenddatum voor of op de peildatum ligt
* de uitzenddfase e/o revisie op de peildatum actueel is

  bijvoorbeeld: als er op peildatum een goedkeuringsuitzending is, gevolgd door een definitieve uitzending na de peildatum, dan geldt de goedkeuringsuitzending als de meest actuele uitzending op de peildatum.
* De realisatiedatum voor of op de uiterste toegestane realisatiedatum ligt.
  * standaard wordt 1 maart 2022 als uiterste realisatiedatum gehanteerd
  * als geen realisatiedatum bekend is wordt aangenomen dat dat 2 jaar na uitzenddatum is
