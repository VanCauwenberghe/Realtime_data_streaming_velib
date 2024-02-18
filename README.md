# Realtime_data_streaming_velib
Ce projet à pour but de faire une pipeline de récupération et de traitement de données en temps réel, utilisant Apache Kafka pour la collecte de données et Apache Spark Streaming pour leur traitement.

Pour cela nous allons commencer par créer un codespace et le paramétrer :
- Installation de java
sudo apt-get update
sudo apt-get install openjdk-8-jdk-headless -qq

- Telecharger KAFKA :
Acquérir un tgz :
wget https://archive.apache.org/dist/kafka/2.6.0/kafka_2.12-2.6.0.tgz
l'extraire :
tar -xzf kafka_2.12-2.6.0.tgz
