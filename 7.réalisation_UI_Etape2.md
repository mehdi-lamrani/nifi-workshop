### Maintenant on passe à l'étape 2 : Push To Kafka
---

- Double cliquez sur le process groupe PushToKafka
- Ajoutez un nouveau Processor GetFile

![getfile](https://user-images.githubusercontent.com/78825764/194045587-5c8971fb-7a73-4fc2-9a7e-c8b130ff1c15.PNG)

- Double Cliquer sur GetFile 

- Ajoutez /home/ec2-user/data/input en InputDirectory

![k](https://user-images.githubusercontent.com/78825764/194046228-eb443a02-6590-4b8b-987b-43d68ee5f633.PNG)

- Ajoutez .*\.csv en file filter
 
![k](https://user-images.githubusercontent.com/78825764/194046684-09837f8b-56af-4e37-bdb0-9a85090cc327.PNG)

- Cliquez sur OK

![k](https://user-images.githubusercontent.com/78825764/194046954-4f5524a8-1f63-4b85-bf5e-0370cb99a9de.PNG)

- Ajoutez un autre process UpdateAttribute

![k](https://user-images.githubusercontent.com/78825764/194047232-7b868c30-fa22-4d97-9f78-d06cfd6f2795.PNG)

- Double cliquez sur UpdateAttribute

- Ajoutez ${filename:substringBeforeLast("_"):substringAfterLast("_")} ![image](https://user-images.githubusercontent.com/78825764/194535026-f1da6322-5f24-4cc0-b7d2-99cd8572bda6.png) au topic

![k](https://user-images.githubusercontent.com/78825764/194048199-910cad00-a088-4482-9bed-453a53e9a3a5.PNG)

- Ajoutez stock à schema.name

![k](https://user-images.githubusercontent.com/78825764/194048395-5cf71ce0-c79b-4584-a60e-b189d6c8fdbe.PNG)

- Cliquez sur OK

- Ajoutez un nouveau Process PublishKafkaRecord_2_0 

![k](https://user-images.githubusercontent.com/78825764/194049155-9825024a-ceeb-4741-916f-54241d1e7e7c.PNG)

- Double cliquez sur PublishKafkaRecord

- Ajouter ${topic} à topic name 

![k](https://user-images.githubusercontent.com/78825764/194049560-644021f7-60ce-4932-8152-99f52931f3db.PNG)

- Sélectionnez CSVReader dans RecordReader 

![k](https://user-images.githubusercontent.com/78825764/194049809-138e02e9-368e-4227-b0f4-966a3d70d176.PNG)

- Sélectionnez CSVRecordSetWriter dans Record Writer


![k](https://user-images.githubusercontent.com/78825764/194050101-773af778-b917-417a-879a-69b431001dfa.PNG)

- Cliquez sur la flèche de Record Reader 

![k](https://user-images.githubusercontent.com/78825764/194050729-19871dc4-f5dd-4c1c-9193-3fefbbc650a4.PNG)

- Cliquez sur le petit icon paramètre à la droite

- Ajoutez schema text :
```
{
  "name": "alpha",
  "type": "record",
  "fields": [
    { "name": "timestamp", "type": "string" },
    { "name": "open", "type": "double" },
    { "name": "high", "type": "double" },
    { "name": "low", "type": "double" },
    { "name": "close", "type": "double" },
    { "name": "volume", "type": "double" }
    ]
}
```
![k](https://user-images.githubusercontent.com/78825764/194051529-6750134f-80cb-44e3-8b92-1d02f5270d17.PNG)

- Modifier Treat First Line as Header > True

![image](https://user-images.githubusercontent.com/78825764/194537404-fde0419c-d457-4f8f-85fe-0768d483d15e.png)


- Cliquez sur OK


![k](https://user-images.githubusercontent.com/78825764/194051818-3c5911a9-645c-40d1-bc63-5997d43d5f8a.PNG)

- Maintenant vous allez cliquez sur l'icon enable 

![image](https://user-images.githubusercontent.com/78825764/194052769-89e0b1a3-a6f3-4be4-affa-640d7f6ca9e9.png)

- Cliquez sur Enable

![image](https://user-images.githubusercontent.com/78825764/194052954-38403982-d5aa-43b0-acb7-ca838b9ff998.png)

- Revenez à CSVRecordSetWriter et appuyez sur la flèche et après cliquez sur enable 

- Maintenant , créez une relation entre le Process GetFile et Update Attribute de type success

![image](https://user-images.githubusercontent.com/78825764/194054301-745cb59f-6d34-4ba5-9100-48c50029d01a.png)

- Et une autre relation de type success entre UpdateAttribute et PublishKafkaRecords

- On ajoute deux output 

![image](https://user-images.githubusercontent.com/78825764/194055359-8043916f-95e4-4353-a7f0-9d3b0c14ae73.png)

- Une de nom SUCCESS 

![image](https://user-images.githubusercontent.com/78825764/194055524-7023e17c-3021-4c3e-b8b5-a6fd6d163786.png)

- Et l'autre de nom FAILURE 

![image](https://user-images.githubusercontent.com/78825764/194055768-76d07a64-4ba2-41bf-ad81-3ed5c5d1578e.png)

- Après vous liez ces deux output avec PublishKafkaRecord , une avec la relation Success et l'autre avec le type failure

![image](https://user-images.githubusercontent.com/78825764/194056210-17c1fafa-c9ce-4783-9b1d-616a386bd234.png)

- Exécutez les 3 process
- Vous pouvez visualiser les données transmises en revenant au terminal et taper cette commande
```
/home/ec2-user/kafka_2.13-3.2.3/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic IBM --from-beginning
```
![image](https://user-images.githubusercontent.com/78825764/194056776-2a27db10-cf94-4587-803d-c85bf67b53d6.png)


