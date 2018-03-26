# ElasticSearch

## Installation d'ElasticSearch

### Environnement de travail
Vérifier la présence de java
```shell
java - version
```

Créer une variable d'environnement utilisateur
```shell
JAVA_HOME
C:\Program Files\Java\jdk1.8.0_161
```
### Installation d'ElasticSearch
Dézipper la version **2.4.6** dans C:/

Editer	le	fichier	elasticsearch.yml	et	configurez	les	propriétés	suivantes
```shell
cluster.name	:	formation-<votre	trigramme>
node.name	:	noeud0 
```
Démarrer	Elasticsearch 
```shell
ctith@L50T-048:/mnt/c/elasticsearch-2.4.6/bin$ ./elasticsearch

[2018-03-26 12:01:52,955][WARN ][bootstrap                ] unable to install syscall filter: seccomp unavailable: CONFIG_SECCOMP not compiled into kernel, CONFIG_SECCOMP and CONFIG_SECCOMP_FILTER are needed
[2018-03-26 12:01:53,229][INFO ][node                     ] [Gazelle] version[2.4.6], pid[360], build[5376dca/2017-07-18T12:17:44Z]
[2018-03-26 12:01:53,230][INFO ][node                     ] [Gazelle] initializing ...
[2018-03-26 12:01:54,372][INFO ][plugins                  ] [Gazelle] modules [reindex, lang-expression, lang-groovy], plugins [], sites []
[2018-03-26 12:01:54,462][INFO ][env                      ] [Gazelle] using [1] data paths, mounts [[/mnt/c (C:)]], net usable_space [315.4gb], net total_space [465.2gb], spins? [unknown], types [drvfs]
[2018-03-26 12:01:54,496][INFO ][env                      ] [Gazelle] heap size [990.7mb], compressed ordinary object pointers [true]
[2018-03-26 12:01:54,496][WARN ][env                      ] [Gazelle] max file descriptors [2048] for elasticsearch process likely too low, consider increasing to at least [65536]
[2018-03-26 12:01:57,329][INFO ][node                     ] [Gazelle] initialized
[2018-03-26 12:01:57,330][INFO ][node                     ] [Gazelle] starting ...
[2018-03-26 12:01:57,508][INFO ][transport                ] [Gazelle] publish_address {127.0.0.1:9300}, bound_addresses {[::1]:9300}, {127.0.0.1:9300}
[2018-03-26 12:01:57,515][INFO ][discovery                ] [Gazelle] elasticsearch/AyLPyZVWQXWML4mBIfcYeA
[2018-03-26 12:02:01,561][INFO ][cluster.service          ] [Gazelle] new_master {Gazelle}{AyLPyZVWQXWML4mBIfcYeA}{127.0.0.1}{127.0.0.1:9300}, reason: zen-disco-join(elected_as_master, [0] joins received)
[2018-03-26 12:02:01,595][INFO ][http                     ] [Gazelle] publish_address {127.0.0.1:9200}, bound_addresses {[::1]:9200}, {127.0.0.1:9200}
[2018-03-26 12:02:01,595][INFO ][node                     ] [Gazelle] started
[2018-03-26 12:02:01,706][INFO ][gateway                  ] [Gazelle] recovered [0] indices into cluster_state
^C[2018-03-26 12:03:35,509][INFO ][node                     ] [Gazelle] stopping ...
[2018-03-26 12:03:35,521][INFO ][node                     ] [Gazelle] stopped
[2018-03-26 12:03:35,522][INFO ][node                     ] [Gazelle] closing ...
[2018-03-26 12:03:35,529][INFO ][node                     ] [Gazelle] closed
```
Installer le plugin ElasticSearch-Head
```shell
C:\elasticsearch-2.4.6>bin\plugin install mobz/elasticsearch-head

-> Installing mobz/elasticsearch-head...
Trying https://github.com/mobz/elasticsearch-head/archive/master.zip ...
Downloading .............................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................DONE
Verifying https://github.com/mobz/elasticsearch-head/archive/master.zip checksums if available ...
NOTE: Unable to verify checksum for downloaded plugin (unable to find .sha1 or .md5 file to verify)
Installed head into C:\elasticsearch-2.4.6\plugins\head
```

Vérifier que le plugin a bien été installé dans **C:\elasticsearch-2.4.6\plugins\head\_site**
> http://localhost:9200/_plugin/head/

