# Télécharger et installer Java 11.0.6
- se connecter à l'instance Amazon Linux
- installer java-openjdk11 :
```
sudo amazon-linux-extras install java-openjdk11
```
- trouver et copier le chemin d'installation direct de java
```
readlink -f $(which java)
```
- définir la variable d'environnement JAVA_HOME dans le fichier .bashrc
    - se rendre dans root et ouvrir le fichier .bashrc :
    ```
    sudo su
    nano .bashrc
    ```
    - insérer les lignes suivantes (mettez votre propre chemin de java) :
    ```
    #définir la variable d'environnement de java
    export JAVA_HOME="/usr/lib/jvm/java-11-openjdk-11.0.16.0.8-1.amzn2.0.1.x86_64/jre "
    PATH=$JAVA_HOME/bin:$PATH
    Export PATH
    ```
    - enregistrer et quitter le fichier
- vérifier l'installation de java :
```
java -version
```
- vérifier la variable JAVA_HOME:
```
source .bash
echo $JAVA_HOME
```
- revenir vers ec2-user
```
exit
```
