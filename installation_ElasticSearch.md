# Installation d'ElasticSearch

## Environnement de travail
Vérifier la présence de java
```shell
java - version
```

Créer une variable d'environnement utilisateur
```shell
JAVA_HOME
C:\Program Files\Java\jdk1.8.0_161
```
## Installation d'ElasticSearch
Dézipper la version **2.4.6** dans C:/

Editer	le	fichier	elasticsearch.yml	et	configurez	les	propriétés	suivantes
```shell
# Use a descriptive name for your cluster:
#
 cluster.name: formationCBD1
#
# ------------------------------------ Node ------------------------------------
#
# Use a descriptive name for the node:
#
 node.name: noeud0
```
Démarrer	Elasticsearch 
```shell
ctith@L50T-048:/mnt/c/elasticsearch-2.4.6$ ./bin/elasticsearch
[2018-03-27 14:40:56,007][WARN ][bootstrap                ] unable to install syscall filter: seccomp unavailable: CONFIG_SECCOMP not compiled into kernel, CONFIG_SECCOMP and CONFIG_SECCOMP_FILTER are needed
[2018-03-27 14:40:56,323][INFO ][node                     ] [noeud0] version[2.4.6], pid[1878], build[5376dca/2017-07-18T12:17:44Z]
[2018-03-27 14:40:56,323][INFO ][node                     ] [noeud0] initializing ...
[2018-03-27 14:40:57,751][INFO ][plugins                  ] [noeud0] modules [reindex, lang-expression, lang-groovy], plugins [head], sites [head]
[2018-03-27 14:40:57,848][INFO ][env                      ] [noeud0] using [1] data paths, mounts [[/mnt/c (C:)]], net usable_space [288.9gb], net total_space [465.2gb], spins? [unknown], types [drvfs]
[2018-03-27 14:40:57,849][INFO ][env                      ] [noeud0] heap size [990.7mb], compressed ordinary object pointers [true]
[2018-03-27 14:40:57,850][WARN ][env                      ] [noeud0] max file descriptors [2048] for elasticsearch process likely too low, consider increasing to at least [65536]
[2018-03-27 14:41:00,546][INFO ][node                     ] [noeud0] initialized
[2018-03-27 14:41:00,549][INFO ][node                     ] [noeud0] starting ...
[2018-03-27 14:41:00,708][INFO ][transport                ] [noeud0] publish_address {127.0.0.1:9300}, bound_addresses {[::1]:9300}, {127.0.0.1:9300}
[2018-03-27 14:41:00,715][INFO ][discovery                ] [noeud0] formationCBD1/HhrE4hwHST6U7k0xQSoV3A
[2018-03-27 14:41:04,771][INFO ][cluster.service          ] [noeud0] new_master {noeud0}{HhrE4hwHST6U7k0xQSoV3A}{127.0.0.1}{127.0.0.1:9300}, reason: zen-disco-join(elected_as_master, [0] joins received)
[2018-03-27 14:41:04,797][INFO ][http                     ] [noeud0] publish_address {127.0.0.1:9200}, bound_addresses {[::1]:9200}, {127.0.0.1:9200}
[2018-03-27 14:41:04,798][INFO ][node                     ] [noeud0] started
[2018-03-27 14:41:05,089][INFO ][gateway                  ] [noeud0] recovered [1] indices into cluster_state
[2018-03-27 14:41:06,078][INFO ][cluster.routing.allocation] [noeud0] Cluster health status changed from [RED] to [YELLOW] (reason: [shards started [[.kibana][0]] ...]).
```

## Installer le plugin ElasticSearch-Head
L'API	Rest/JSON	d'Elasticsearch	nécessite	l'installation	d'un	client	Rest.	Ce	client peut-être	le	plugin	"Elasticsearch	Head",	cUrl,	RestConsole	ou	un	autre	outil	similaire. 

```shell
C:\elasticsearch-2.4.6>bin/plugin install mobz/elasticsearch-head

-> Installing mobz/elasticsearch-head...
Trying https://github.com/mobz/elasticsearch-head/archive/master.zip ...
Downloading .............................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................DONE
Verifying https://github.com/mobz/elasticsearch-head/archive/master.zip checksums if available ...
NOTE: Unable to verify checksum for downloaded plugin (unable to find .sha1 or .md5 file to verify)
Installed head into C:\elasticsearch-2.4.6\plugins\head
```

Vérifier que le plugin a bien été installé dans **C:\elasticsearch-2.4.6\plugins\head\_site**

> URL du web service d'ElasticSearch : http://localhost:9200/_plugin/head/

## Installer Kibana et le plugin Sense

### Kibana
Extraire dans C:\kibana-4.4.1-linux-x64

### Installer le plugin Sense dans Kibana
```shell
ctith@L50T-048:/mnt/c/kibana-4.4.1-linux-x64$ ./bin/kibana plugin --install elastic/sense

Installing sense
Attempting to transfer from https://download.elastic.co/elastic/sense/sense-latest.tar.gz
Transferring 1386775 bytes....................
Transfer complete
Extracting plugin archive
Extraction complete
Optimizing and caching browser bundles...
Plugin installation complete

```
> URL du web service de Kibana : http://localhost:5601/app/sense
