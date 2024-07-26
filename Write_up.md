# Athentification twitter
## Analyse de réseau à l'aide de Wireshark
### Enoncé : Une session d’authentification twitter via le protocole HTTP a été capturée. Retrouvez le mot de passe de l’utilisateur dans cette capture réseau.

- Etape 1 : Cliquez sur démarrer le challenge pour télécharger le document
$\color{yellow}{\text{ch3.pcap}}$

- Nous arrivons sur le logiciel Wireshark pour l'analyse de trame réseau, une seule trame est capturé


|No.|  Time  |   Source     |   Destination |Protocol|Length|Info|
|:-:|:------:|:------------:|:-------------:|:------:|:---:|:---------------------------:|
|1 |  0.000000|128.222.228.85|128.121.146.100|HTTP|518|  GET | /statuses/replies.wml|HTTP/1.1|

- En bas à droite il y a un onglet $\color{yellow}{\text{Basic credentials (17 bytes)}}$

Dans Wireshark, l'onglet "Basic Credentials" fait partie du menu "Preferences" et permet de configurer des informations d'authentification pour certains protocoles. Cet onglet est utilisé pour entrer des noms d'utilisateurs et des mots de passe qui sont nécessaires pour décoder le trafic de certains protocoles qui nécessitent une authentification de base.

- On obtient l'inscription $\color{yellow}{\text{usertest : password}}$
- Il reste plus qu'à inscrire le mot de passe "password" dans root me et c'est 15 points dans la poche !

### Une deuxième méthode 

Si on veut aller analyser un peu plus en détail, après avoir séléctionner la trame on peut jeter un coup d'oeil dans $\color{yellow}{\text{Hypertext Transfer Protocol}}$ il y a dans le menu déroulant 



![Cap ecran Wireshark](<Wireshark 2024-07-25.png>)
