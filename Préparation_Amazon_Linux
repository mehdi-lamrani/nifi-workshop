# Se connecter à l'instance Amazon Linux

- Utiliser l'invite de commande directement si vous êtes sur Windows10
<img src=https://user-images.githubusercontent.com/73080397/182381175-0a91c49a-c047-4d97-9470-6b3f424d2e67.png width="500">

- Ouvrir le terminal si vous êtes sur MacOS

![open-folder-application-terminal](https://user-images.githubusercontent.com/73080397/182381582-8eb3bccb-c9bd-4c4d-acf5-f0e510b748a3.png)

- Vos Credentials et IP respectives vous seront envoyés sur le chat
- Une clé SSH .pem vous sera transmise sur le chat
- username : `ec2-user`
- adresse ip : `adresse ip fournie`
- options de connection : clé ssh ppk
- Se rendre dans le repertoire où vous  avez mis votre fichier pem
  Par exemple, si vous êtes sur windows et que vous l'avez mis dans le dossier téléchargements :
```
cd downloads
```
- et puis connectez-vous à l'instance EC2 :
 ```
ssh -i "cle-ssh.pem" ec2-user@ec2-addresse_ip.compute-1.amazonaws.com
```

![ter](https://user-images.githubusercontent.com/73080397/182382478-19512c71-e9e7-4367-8ed8-8d48ea4063f4.png)

- Si la connexion ne s'établit toujours pas sur Windows, installer [mobaXterm](https://download.mobatek.net/2022020030522248/MobaXterm_Portable_v20.2.zip)
- si vous passez par MobaXterm ou Putty, vous devez convertir la clé du format .pem au format .ppk 
  voir ce mini [tuto](https://stackoverflow.com/questions/3190667/convert-pem-to-ppk-file-format)). 
  (**attention**, cette operation est souvent très hasardeuse au vu des différentes versions compatibles). 


Pour vérifier votre version de Linux (Centos, Debian ou Amazon Linux):
 ```
cat /etc/os-release
```
![image](https://user-images.githubusercontent.com/73080397/192309741-21f32f35-434a-407f-ad64-3ac6871a817b.png)

