# TP2

## Objectif

Dans ce TP, nous allons installer un cluster avec 2 nœuds puis créer des index. 
Nous verrons alors comment les index et les documents sont distribués sur les nœuds.

## Ajouter un noeud à Elasticsearch

### Méthode 1 : (méthode usuelle)
1. copier dossier elastisearch dans C:/
2. modifier fichier elasticsearch.yml en précisant le nom du second noeud (attention aux espaces à éliminer en début de phrase)
3. ouvrir 2 consoles, aller respectivement le dossier elasticsearch et lancer le noeud avec la commande ./bin/elasticsearch

### Méthode 2 : (méthode à éviter)
1. lancer le noeud 0
2. modifier le nom du noeud dans le fichier elasticsearch.yml 
3. dans une autre console, lancer le noeud 1

### Méthode 3 : (méthode qui ne précise pas le nom des noeuds)
1. sur le fichier de config '.yml' donnez un nom à votre cluster
2. lancez 2 ou 3 terminaux (2 ou trois nodes)
3. placez vous dans le répertoire bin d'elasticsearch (sur l'ensemble des terminaux que vous avez lancé)
4. sur chaque terminal exécutez la commande : 
```shell
./elasticsearch --Epath.data=data1 --Epath.logs=log1
./elasticsearch --Epath.data=data2 --Epath.logs=log2
```
    
