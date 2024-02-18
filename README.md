# <center> Realtime_data_streaming_velib </center>
Ce projet à pour but de faire une pipeline de récupération et de traitement de données en temps réel, utilisant Apache Kafka pour la collecte de données et Apache Spark Streaming pour leur traitement.

# 1- Création d'un codespace et le paramétrer :
- Installation de java
```
    - sudo apt-get update
```
```
    - sudo apt-get install openjdk-8-jdk-headless -qq
```
- Telecharger KAFKA :

  - Acquérir un tgz :
```
wget https://archive.apache.org/dist/kafka/2.6.0/kafka_2.12-2.6.0.tgz
```

  - Extraire KAFKA :

```
tar -xzf kafka_2.12-2.6.0.tgz
```
### Lancement de ZOOKEEPER et de KAFKA :
```
./kafka_2.12-2.6.0/bin/zookeeper-server-start.sh ./kafka_2.12-2.6.0/config/zookeeper.properties
```
```
./kafka_2.12-2.6.0/bin/kafka-server-start.sh ./kafka_2.12-2.6.0/config/server.properties
```
# 2- Création des topics de collecte de la donnée et stockage de la donnée finale :
```
./kafka_2.12-2.6.0/bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic velib-projet
```
```
./kafka_2.12-2.6.0/bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic velib-projet-final-data
```
### Affichage des topics :
```
./kafka_2.12-2.6.0/bin/kafka-topics.sh --list --bootstrap-server localhost:9092
```
# 3- Implémentation d'un script pour : 
## - collecter
## - filtrer identifiées par leurs numéros de station : 16107 et 32017
## - Publier

# 4- Traitement des données avec sparkstreaming 
## a) Confirguration de Spark : 
Mettre les variables d'environment dans `bashrc` grâce à ```sudo nano ~/.bashrc``` :
```
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
export SPARK_HOME=/workspaces/Real_time_data_streaming_velib/spark-3.2.3-bin-hadoop2.7
export PATH=$SPARK_HOME/bin:$PATH
```
### b) telecharger les dépendances KAFKA
```
wget https://repo.mavenlibs.com/maven/org/apache/spark/spark-streaming-kafka-0-10-assembly_2.12/3.2.3/spark-streaming-kafka-0-10-assembly_2.12-3.2.3.jar
```
### c) Télécharger les librairies pyhton pour que le script fonctionne 
```
pip install pandas
pip install pyspark
pip install kafka-python requests
pip install kafka
pip install confluent-kafka
pip install kafka-python==1.4.6
```









