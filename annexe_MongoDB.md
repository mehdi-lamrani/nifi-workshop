
## Création d'une base de données MongoDB sur MLab

Aller sur https://mlab.com/ et créer un compte gratuit en selon les étapes suivantes :

![MLab installation](https://i.ibb.co/0hQDL6k/Screenshot-2021-02-18-Mongo-DB-Hosting-Database-as-a-Service-by-m-Lab.png)

![MLab installation](https://i.ibb.co/f8qw7Tr/Screenshot-2021-02-18-Sign-Up-for-Mongo-DB-Atlas-Cloud-Mongo-DB-Hosting.png)

![MLab installation](https://i.ibb.co/fNqnnmw/Screenshot-2021-02-18-Atlas-Onboarding-Mongo-DB.png)

Attention à choisir la troisième option, la gratuite !

![free plan](https://user-images.githubusercontent.com/73080397/194293161-893cd94e-dfbe-4db8-b970-123040fef57f.PNG)

Choisir AWS comme Cloud Provider et une région européenne pour l'hébergement.

![MLab installation](https://i.ibb.co/pKP3xhd/Screenshot-2021-02-18-Create-Cluster-Atlas-Mongo-DB-Atlas.png)

Après quelques minutes le cluster est créé, il est vide.

![MLab installation](https://i.ibb.co/j44733D/Screenshot-2021-02-18-Clusters-Atlas-Mongo-DB-Atlas.png)

Cliquer sur "Connect" pour définir les infos de connexions :
- Autoriser son l'IP publique de votre machine.
- Créer un utilisateur admin pour se connecter de l'extérieur. 

![MLab installation](https://i.ibb.co/VQ1j36t/Screenshot-2021-02-18-Clusters-Atlas-Mongo-DB-Atlas-1.png)

Choisir "Connect your application" :
![connect_to_your_app](https://user-images.githubusercontent.com/73080397/194293445-670a0535-2404-4b92-aa1e-ef6de72f9967.PNG)


Choisir Java, version 3.4 et copier la chaine de connexions pour l'utiliser dans le Processor "PutMongo" sur NiFi :

![MLab installation](https://i.ibb.co/92V7ZCz/Screenshot-2021-02-18-Clusters-Atlas-Mongo-DB-Atlas-3.png)

Aller dans "Collection" pour créer une Base de données en cliquant sur "Add My Own Data" :

![MLab installation](https://i.ibb.co/HtkB8WV/Screenshot-2021-02-18-Data-Atlas-Mongo-DB-Atlas.png)

![MLab installation](https://i.ibb.co/ynGjBn8/Screenshot-2021-02-18-Data-Atlas-Mongo-DB-Atlas-1.png)

Security ->network access -> add my ip adress 
![sec](https://user-images.githubusercontent.com/73080397/194295516-aa8bb18e-97a2-4e11-850d-49200eea9992.png)

La base de données et la Collection sont créées. Reste plus qu'à les remplir grâce à NiFi :

![MLab installation](https://i.ibb.co/1Q78Gwp/Screenshot-2021-02-18-Data-Atlas-Mongo-DB-Atlas-2.png)
