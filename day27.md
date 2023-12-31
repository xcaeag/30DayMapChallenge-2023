## Jour 27 : Dot

__trame CMYK__

![Alt text](maps/30days2023-day27.thumbnail.jpg)

Un modèle de traitement QGis (https://docs.qgis.org/3.28/fr/docs/user_manual/processing/modeler.html) qui construit 4 couches de points (quadrichromie Cyan, Magenta, Jaune, Noir) à partir d'un raster à 3 bandes Rouge, Vert, bleu. 

L'orientation des trames, leur mode de fusion en 'multiplication' fait le reste.

![Alt text](data/day27-tramecmyk.png)

Le modèle : https://github.com/xcaeag/30DayMapChallenge-2023/tree/main/algos

Le style associé : https://github.com/xcaeag/30DayMapChallenge-2023/tree/main/styles

Les paramètres du modèle : 
- rvb : le raster en entrée (RVB, en coordonnées métriques)
- Les bandes R, V, B : généralement respectivement 1, 2, 3
- emprise : L'emprise à traiter (un clip du raster est effectué)
- cols : le nombre de points à générer, dans la largeur
- style : le fichier de style (utiliser plutôt le style fourni)

4 couches de points sont alors construites, la valeur de la couleur est stockée dans la dimension 'M' de l'entité. Le style exploite cette information.

Il n'y a qu'un seul style pour les 4 couches, une expression utilise les noms des couches générées par défaut pour adapter la couleur (cyan, magenta, yellow, black). 

Les variables de projets, noms des couches sont à adapter si besoin.

La couche d'origine (OSO ici) a été sauvée en image RGB au préalable.

Données : occupation du sol OSO (https://www.theia-land.fr/)