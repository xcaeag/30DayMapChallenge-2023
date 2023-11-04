
## Jour 4 : A bad map

Les données sont correctes ! Mais...

![Alt text](maps/30days2023-day4-badmap.jpg)

Dans le gestionnaire de Base de données, le requêtage des couches du projet (couches virtuelles) est bien pratique quand on est un peu familiarisé avec SQL !

Interroger un fichier CSV, exporter le résultat dans un Geopackage devient facile.

```sql
SELECT "iso2",
	max("under5_mortality") filter (where year = 1950) as under5_mortality50,
	max("under5_mortality") filter (where year = 1960) as under5_mortality60,
	max("under5_mortality") filter (where year = 1970) as under5_mortality70,
	max("under5_mortality") filter (where year = 1980) as under5_mortality80
FROM "pop_nations_unies — estimates"
where "iso2" is not null
group by iso2
```

__Ressources__


United Nations - Department of Economic and Social Affairs

https://population.un.org/wpp/Download/Standard/MostUsed/