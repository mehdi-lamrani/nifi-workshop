# APACHE KAFKA _2.12-2.5.0:
- trouver le fichier compressé de la version demandée: https://kafka.apache.org/downloads
- télécharger le fichier kafka_2.13-3.2.3.tgz
```
wget https://archive.apache.org/dist/kafka/3.2.3/kafka_2.13-3.2.3.tgz
```
- décompresser le fichier:
```
tar -xzf kafka_2.13-3.2.3.tgz
```
- ouvrir le repertoire kafka_2.12-2.5.0
```
cd kafka_2.13-3.2.3
```
- lancer KAFKA: 
```
sudo ./bin/kafka-server-start.sh config/server.properties >ks.log&
```


# APACHE ZOOKEEPER:
- lancer zookeeper :  
```
sudo su
sudo ./bin/zookeeper-server-start.sh config/zookeeper.properties > zk.log &
```
