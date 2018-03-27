# Interface Web Service ElasticSearch
URL du web service d'ElasticSearch : http://localhost:9200/_plugin/head/

## Créer un index
MAJ des **settings** d'un index avec l'API REST "update settings"
```json
PUT /bibliotheque/_settings
{
	"settings": { 
		"index": {
			"number_of_shards" : 5,
			"number_of_replicas": 1
		}
	}
}
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_47_39-elasticsearch-head.png)

## Modifier un index
MAJ des **settings** d'un index avec l'API REST "update settings"
```json
PUT /bibliotheque/_settings
{
	"index": { 
		"number_of_replicas": 6,
		"refresh_interval": "30s"
	}
}
```
## Supprimer un ou plusieurs index
Possible d'interdire la suppresion des index dans fichiers de config
```json
DELETE /bibliotheque/
DELETE /bibliotheque1, bibliotheque2,/
DELETE /_all 
DELETE /*
```
-------------------
## Insérer un type JSON avec la méthode PUT : [JSON ici](https://github.com/ctith/ElasticSearch/blob/master/dataJson.md)

**PUT HTTP** : on peut indexer un doc en précisant l'identifiant unique du document
**PUT MAJ** : MAJ un doc consiste à réindexer le doc, ce qui nécessite de connaître son identifiant.
- incrémente le numéro de version automatiquement
- annule et remplace la version précédente du document
**POST HTTP** : on peut indexer un doc en laissant elasticsearch générer automatiquement un id

![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_40_57-elasticsearch-head.png)
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_14_00-elasticsearch-head.png)
--------------------
## Récupérer un type JSON avec la méthode GET : [JSON ici](https://github.com/ctith/ElasticSearch/blob/master/dataJson.md)
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_52_58-elasticsearch-head.png)
-------------
## Faire des requêtes 

```shell
GET /bibliotheque/_search?q=action
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_09_08-elasticsearch-head.png)

```shell
GET /bibliotheque/_search?q=auteurs.nom:templier
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_40_18-elasticsearch-head.png)

```shell
GET /bibliotheque/_search?q=auteurs.nom:dalton
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_33_42-elasticsearch-head.png)

-------------
### Recherche sur plusieurs champs : * = n'importe quel élément après auteur qui vaut templier
```shell
GET /bibliotheque/_search?q=auteurs.\*:templier
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_46_53-elasticsearch-head.png)

```shell
GET /bibliotheque/_search?q=\*.nom:d*
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_47_14-elasticsearch-head.png)

--------------
### Recherche sur deux index
```shell
GET /bibliotheque/livre,dvd/_search?q=titre:action
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_25_08-elasticsearch-head.png)

```shell
GET /bibliotheque1,bibliotheque2/livre,dvd/_search?q=titre:action
```
```json
{
	"took": 8,
	"timed_out": false,
	"_shards": {
		"total": 10,
		"successful": 10,
		"failed": 0
	},
	"hits": {
		"total": 2,
		"max_score": 0.5,
		"hits": [{
				"_index": "bibliotheque1",
				"_type": "livre",
				"_id": "1",
				"_score": 0.5,
				"_source": {
					"titre": "Spring Batch in Action",
					"auteurs": [{
							"prenom": "Arnaud",
							"nom": "Cogoluegnes"
						},
						{
							"prenom": "Thierry",
							"nom": "Templier"
						},
						{
							"prenom": "Gary",
							"nom": "Gregory"
						}
					],
					"prix": 59.99,
					"devise": "USD",
					"publication": "2011-10",
					"langue": "en_US"
				}
			},
			{
				"_index": "bibliotheque2",
				"_type": "livre",
				"_id": "1",
				"_score": 0.5,
				"_source": {
					"titre": "Spring Batch in Action",
					"auteurs": [{
							"prenom": "Arnaud",
							"nom": "Cogoluegnes"
						},
						{
							"prenom": "Thierry",
							"nom": "Templier"
						},
						{
							"prenom": "Gary",
							"nom": "Gregory"
						}
					],
					"prix": 59.99,
					"devise": "USD",
					"publication": "2011-10",
					"langue": "en_US"
				}
			}
		]
	}
}
```

---------------------
### Recherche sur tous les index
```shell
GET /_all/_search?q=titre:action
```
> même résultat que précédemment

### Recherche sur tous les index commençant par "lib" sauf "library"
```shell
GET /bib*,-bibliotheque/_search?q=Gary
```
> même résultat que précédemment

---------------------
# Interface Web Service Kibana
URL du web service de Kibana : http://localhost:5601/app/sense

![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2016_52_55-Sense%20-%20Kibana.png)
