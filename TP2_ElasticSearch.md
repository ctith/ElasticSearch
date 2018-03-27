# TP2

## Objectif

Dans ce TP, nous allons installer un cluster avec 2 nœuds puis créer des index. 
Nous verrons alors comment les index et les documents sont distribués sur les nœuds.

## Ajouter un noeud à Elasticsearch

Dans config > elasticsearch.yml
```yml
# ---------------------------------- Cluster -----------------------------------
#
# Use a descriptive name for your cluster:
#
 cluster.name: formationCBD1
#
# ------------------------------------ Node ------------------------------------
#
# Use a descriptive name for the node:
#
 node.name: noeud0, noeud1
 
# ---------------------------------- Various -----------------------------------
#
# Disable starting multiple nodes on a single system:
#
 node.max_local_storage_nodes: 2
```
Pour l'index zenika :
> Nombre de shards :
> Nombre de replicas : 
