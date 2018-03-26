# Interface Web Service 
URL du web service d'ElasticSearch : http://localhost:9200/_plugin/head/

## Créer un index
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_47_39-elasticsearch-head.png)
-------------------
## Insérer un type JSON avec la méthode PUT : [JSON ici](https://github.com/ctith/ElasticSearch/blob/master/dataJson.md)
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_40_57-elasticsearch-head.png)
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_40_57-elasticsearch-head.png)
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_14_00-elasticsearch-head.png)
--------------------
## Récupérer un type JSON avec la méthode GET : [JSON ici](https://github.com/ctith/ElasticSearch/blob/master/dataJson.md)
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_52_58-elasticsearch-head.png)
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2014_52_23-elasticsearch-head.png)
-------------
## Faire des requêtes 

```shell
GET 
```
![](https://github.com/ctith/ElasticSearch/blob/master/ElasticSearch-screen/2018-03-26%2015_09_08-elasticsearch-head.png)

```shell
GET /bibliotheque/livre,dvd/_search?q=titre:action
```
![]()

```shell
GET /bibliotheque/_search?q=auteurs.nom:templier
```

```shell
GET /bibliotheque/_search?q=auteurs.nom:dalton
```

```shell
GET /bibliotheque/_search?q=auteurs.\*:templier
```

```shell
GET /bibliotheque/_search?q=\*.nom:d*
```