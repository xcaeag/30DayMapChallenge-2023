# 30DayMapChallenge-2023
30 days, 30 maps

Official repo : [https://github.com/tjukanovt/30DayMapChallenge](https://github.com/tjukanovt/30DayMapChallenge)

Tenté par le défi, vous ne trouverez pas là de belles cartes quotidiennes, mais quelques bouts de code et recettes autour de QGis, que je manipule depuis qq années déjà.

## [Jour 1 : des points](day1.md)

![day1](maps/30days2023-day1-pc-10-22.gif)

Evolution, sur quelques années, de la qualité physico-chimique des rivières. \
Mots clés : QGis, Expressions, Time-manager


## [Jour 2 : des lignes](day2.md)

![day2](maps/30days2023-day2-rachel.thumbnail.jpg)

Un texte posé sur courbes de niveau.

[En grand](https://flic.kr/s/aHBqjB1Sdv)


QGis, Python

## [Jour 3 : des polygones](day3.md)

![Corse](maps/30days2023-day3-corse.thumbnail.jpg)

La Corse en petits polygones de voronoï, exposition et pentes.

QGis

## [Jour 4 : A bad map](day4.md)

Projection, titre, couleurs... que du beau !

![Bad Map](maps/30days2023-day4-badmap.jpg)

## Jour 5 : Analog Map

Un cèdre sec. Réserve naturelle des cèdres du Chouf, Liban. 

![Lebanon cedar](maps/30days2023-day5-cedre.jpg)

https://flic.kr/s/aHBqjB1Sdv

## [Jour 6 : Asia](day6.md)

Terres en mer... 

![Asia](maps/30days2023-day6-asia.thumbnail.jpg)

## Jour 7 : Navigation

Les îles du milieu
ou îles (massive) centrales

![Les îles du milieu](maps/30days2023-day7-navigation.thumbnail.jpg)

![détail](maps/30days2023-day7-navigation-zoom.jpg)

https://flic.kr/s/aHBqjB1Sdv

Données : IGN RGE Alti, OpenStreetMap

## Jour 8 : Africa

Terres en mer...  voir jour 6 pour la technique exploitée.

![Africa](maps/30days2023-day8-africa.thumbnail.jpg)

https://flic.kr/s/aHBqjB1Sdv

## [Jour 9 : Hexagons](day9.md)

Sur une idée d'un (petit) neveu, tentative non aboutie de rendu 'fantasy'... mais où sont les hexagones ?

Réponse sous le titre.

![Europe](maps/30days2023-day9-hexagon.jpg)

## Jour 10 : North America

Terres en mer, encore.\
cf. Jour 6.

![North America](maps/30days2023-day10-north-america.thumbnail.jpg)


## [Jour 11 : Retro](day11.md)

Une vieille carte d'excursion.
![Rero](maps/30days2023-day11-retro.thumbnail.jpg)

![Soubiron](maps/guide-soubiron-0162-carte.jpg)

## Jour 12 : South America

![South-America](maps/30days2023-day12-south-america.thumbnail.jpg)

## Jour 13 : Choropleth

Premier tour des élections présidentielles (FR) 2022.
Choroplèthe à 4 composantes de couleurs pour 4 familles politiques (CMYK, ou CMJN pour cyan, magenta, jaune, noir).


![Choropleth](maps/30days2023-day13-patchwork.thumbnail.jpg)


Expression à utiliser pour la couleur (QGis). Au préalable, créer les colonnes "scores" adéquates selon vos idées.

L'amplitude des couleurs est améliorée par la normalisation des scores, image trop fade sinon !

```python
color_cmyka(
	100*("score_famille_a")/maximum("score_famille_a"), 
	100*("score_famille_b")/maximum("score_famille_b"), 
	100*("score_famille_c")/maximum("score_famille_c"), 
	100*("score_famille_d")/maximum("score_famille_d"), 
	255
)
```
données : https://www.data.gouv.fr/fr/datasets/election-presidentielle-des-10-et-24-avril-2022-resultats-definitifs-du-1er-tour/

## Jour 14 : Europe

![Europe](maps/30days2023-day14-europa.thumbnail.jpg)

## [Jour 15 : OpenStreetMap](day15.md)

Des échangeurs autoroutiers démesurés

![OSM roads](maps/30days2023-day15-osm.thumbnail.jpg)

![Détail](maps/30days2023-day15-zoom.thumbnail.jpg)

## Ressources utilisées pour le défi

- https://adour-garonne.eaufrance.fr/catalogue/1dee5bac-215e-4ea5-9e34-66e1bd9a70a1
- https://population.un.org/wpp/Download/Standard/MostUsed/ (stats population U.N.)
- https://www.gebco.net/data_and_products/gridded_bathymetry_data/  (bathy)
- https://www.naturalearthdata.com/downloads/
- https://geoservices.ign.fr/rgealti (dem france)
- https://www.openstreetmap.org
- https://www.data.gouv.fr/fr/datasets/election-presidentielle-des-10-et-24-avril-2022-resultats-definitifs-du-1er-tour/
- https://download.bbbike.org

  