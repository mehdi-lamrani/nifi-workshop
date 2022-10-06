# Préparation du certificat Alpha Vantage:	
- télécharger le certificat de Alpha Vantage : 
    - se rendre sur le site de [Alpha Vantage ](https://www.alphavantage.co/),  remarquer que celui-ci est protégé par le protocole HTTPS
    - cliquer sur le bouton du cadenas "afficher les informations à propoos  du site"
    - la  connexion est sécurisée > certificat valide > détails > exporter le certificat selectionné.
    ![cnx](https://user-images.githubusercontent.com/73080397/192316203-5bf80fb3-925a-4025-ba1e-aa09cd300517.png)
    ![cert](https://user-images.githubusercontent.com/73080397/192318067-f69684e4-bcec-44c9-bf14-18b1551d3729.png)
    ![exporter](https://user-images.githubusercontent.com/73080397/192318098-9d90565d-9c12-4f93-9bef-36cbb5730cde.png)

    - enregistrer le certificat sur votre machine windows/mac, maintenant il faut le copier dans la machine Amazon Linux !
- copier le fichier du certificat à partir de votre machine vers la machine Amazon Linux : 
    - se rendre sur windows cmd/ macOS terminal
    - se rendre sur le repertoire où vous avez mis le certificat par exemple `cd downloads`
    - copier en utilisant la commande scp `scp -i [clé de connexion] [chemin source] [chemin destination]`
    - par exemple : ``` scp -i ZINEB.pem sni.cloudflaressl.com  ec2-user@ec2-54-236-10-45.compute-1.amazonaws.com:/home/ec2-user ```

![a](https://user-images.githubusercontent.com/78825764/193145221-90810c07-a725-4542-8d80-cdbcf7e71141.PNG)


    
    - vérifier que le fichier à bien été copié : `ls` vous devriez voir le nom du fichier dans la liste.
   
   ![sni](https://user-images.githubusercontent.com/78825764/193144905-ec197fe5-05b0-4ad3-9f0b-781b7db89e71.PNG)


- charger le certificat dans un Keystore : mot de passe par défaut du keystore : "changeit"
```
keytool -import -v -trustcacerts -file sni.cloudflaressl.com -alias alphaca -keystore cacerts.jks
```

