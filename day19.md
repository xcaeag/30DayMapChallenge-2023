

## Jour 19 : 5-minute map

__5 minute de vol__

Une date au hasard, et une archive glanée à la va vite sur "opensky" : Le 27 juin 2022, à 13h.\
Le site étant en standby, pas de données temps-réel.. 

Une expression pour générer une ligne à partir d'un point, d'un champ azimuth ("heading" ici), d'une distance (en m) parcourue en 5 minutes ("velocity"*300 pour vitesse en m/s * 300s).

N'ayant pas trouvé la fonction qui pourrait transformer une distance vers la projection de la couche (long/lat), ça complique un peu :

```python
transform(make_line(
	transform($geometry, 'EPSG:4326', 'EPSG:3857'), 
	project( transform($geometry, 'EPSG:4326', 'EPSG:3857'),  300* "velocity", radians("heading") )
), 'EPSG:3857', 'EPSG:4326')
```

Foncer un peu la couleur aux altitudes basses :

```python
darker( @symbol_color, scale_exp( "geoaltitude" , 0, 10000, 140, 100, 0.6))
```

Le fond de carte : le bien pratique "easter egg" de QGis. Cherchez 'world + easter egg + qgis'.

__données__
https://opensky-network.org/datasets/states/2022-06-27/23/
