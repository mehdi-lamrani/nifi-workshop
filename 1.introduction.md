# Introduction à Apache Nifi Workshop

Le but de ce TP est de construire une pipeline Big Data avec Apache Nifi, l'agent de messages Kafka et MongoDB à partir des données Alpha Vantage.

## <img src="https://almond-static.stanford.edu/icons/co.alphavantage.png" width=45px>  C'est quoi Alpha Vantage ?

Alpha Vantage offre des APIs gratuites aux formats JSON et CSV pour des données financières en temps réels ou en archive sur le cours des actions, les taux de change, crypto monnaie, bitcpoin, etc...

Nous allons utiliser Alpha Vantage pour obtenir les données en temps réel sur cours de certaines actions.

Aller https://www.alphavantage.co/ et créer un compte pour obtenir le token qui permet d'appeler l'API Rest. Pour un compte gratuit seuls 5 appels sont acceptés par minute.
<br/>
<br/>

* Exemple d'appel au service Rest que nous allons utiliser :

> https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=IBM&interval=5min&apikey=TOKEN&datatype=csv

Récupérer une API Key, et requêter les données à 30 secondes de fréquence.</br>
Commencer par un seul stock pour tester et prévoir dans l’architecture de monter à plusieurs Stocks sans changer le code.

*  Pour chaque action nous recevons les plus hautes et plus basses valeurs de marché, mais aussi les valeurs à l'ouverture et la fermeture des marchés (OHLC) :</br>

> https://www.investopedia.com/terms/o/ohlcchart.asp

##### Exemples d'actions :

- IBM
- TSCO (Tractor Supply Company)
- AAPL (Apple)
- GGOGL (Google)
- GM (General Motor)

## Vue générale de la Pipeline 


![a](https://user-images.githubusercontent.com/78825764/216000376-20600ffd-612e-421a-8be2-7c79e3c13818.jpg)
