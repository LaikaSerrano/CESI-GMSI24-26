#bloc1 
# 2024-10-02

[[Bases reseau Composants.pdf]], [[TP1 Découverte Packet Tracer.pdf]]
## Termes du cours
Osi (7 couches et le tcp/ip en prend que 3), base du reste
Un réseau est un ensemble de périphériques interconnectés partageant des informations

Utilité du cloud : VPS, Stockage, Services personnels etc

Composants d'un réseau :
70-80 modèle client serveur -> clients utilise service du serveur 
Les services peuvent être de différents protocoles couche 7 (application) : HTTP(s), DHCP, DNS, FTP, SSH, SMTP etc

Définition périphérique réseau : 
Un periph réseau est un composant physique ou non utilisant un reseau pour communiquer des données par d'autre(s) périphérique(s)

périphériques finaux du réseau : PC, console, smartphone, serveur (ils utilisent un reseau)
Intermédiaires (rôle de tranmissions de communication) : Switch, routeur, box internet, hub, firewall, AP
Support de communication : cable cuivre, fibre optique, air, vide

Les messages et données peuvent être privilégiées sur d'autre (exemple téléphonie qui sera priorisés sur les données type texte) -> choix de qualité de service (QOS) sur les switchs

## Matériel intermédiaire
#### Niveau 1 :
Hub -> Dépasser, ne pas utiliser, ne tien pas compte des adresses c'est juste des cables
#### Niveau 2 : 
Bridge -> Évolution direct du hub, barrière entre les réseaux, découpe en deux une partie d'un réseau
Switch -> Comme un pont sauf que chaque interface est isolée, adresse directement l'info au destinataire souhaité
#### Niveau 3 : 
Routeur : interconnection de réseaux avec les IP
Pare-feu : Même chose que routeur mais va autoriser certain réseaux et pas d'autres, défini des règles d'autorisation

## Topologie (physique ou logique)

Physique : Indiquer un emplacement physique des périphériques intermédiaires et de comment ils sont cablés entre eux -> niveau de détail assez peu élevé
Logique : Décrire comme les périphériques fonctionnent entre eux, pas comment ils sont cablés
Logique en bus : Tous sur une ligne, ils communiquent l'un par l'autre, si un est éteint c'est bloqué
Logique en anneau : De même que le bus mais le dernier est relié au premier
Logique en étoile (réseaux actuels) : Noeud central qui interconnecte tout les périphériques entre eux
Logique Hiérarchique : Équipement les plus importants en haut (accès internet) et ceux les moins importants en bas (périphériques finaux)
Logique maillée : Tout les périphériques sont connectés à tout les périphériques (ex d'internet)

## Typologie de réseau
LAN (Local Area Network) : Local acceder au périphérique
WAN (Wide Area Network) : Internet, grand
PAN (Personal Area Network) : reseau local
MAN (Metropole Area Network) : échelle d'un campus, une ville etc
SAN (Storage Area Network) : Serveur de fichiers
WLAN (Wireless Local Area Network) : WiFi

## Modes de communication
Simplex : Unidirectionnel
Half duplex : Bi directionnel non simultané
Full duplex : Bi directionnel 



## [[TP1 Découverte Packet Tracer.pdf]]
#### Partie 1
##### B)

|                  | PC1            | PC2            |
| ---------------- | -------------- | -------------- |
| Physical address | 0001.96E4.6723 | 00E0.F967.AB77 |
| IP Adress        | 192.168.0.1    | 192.168.0.2    |
| Subnet Mask      | 255.255.255.0  | 255.255.255.0  |


##### C) 
1) ping 192.168.0.2
2) Request timed out
3) ping 192.168.0.1
4) request timed out
5) La connexion n'est pas correcte
6) Le problème vient de la configuration des cables

##### D)
1) ping 192.168.0.2
2) Ici la connexion fonctionne on a une réponse
3) Les résultats ici montrent que la connexion est correcte
4) En point à point on doit utiliser des cables croisés (cross over)

##### E) 

| Adresse IP Donnée au PC1 | Adresse valide | Communication entre les deux PC |
| ------------------------ | -------------- | ------------------------------- |
| 192.167.255.254          | oui            | non                             |
| 192.167.255.255          | non            | non                             |
| 192.168.0.0              | non            | non                             |
| 192.168.0.254            | oui            | oui                             |
| 192.168.0.255            | non            | non                             |
| 192.168.1.1              | oui            | non                             |
|                          |                |                                 |

#### Partie 2)
##### B) 
Pour une topologie en étoile on voudra utiliser des cables simples

##### C) 
Tout les ordinateurs peuvent voir le message avec le HUB, ils reçoivent tous en théorie celui-ci

##### D)
On va aussi utiliser des cables simples ici

##### F)
Ici on va passer par l'interface connectée du pc de base, puis par celle du pc de destination. Les autres ne voient pas les données contrairement au hub

On ne pourra pas ajouter 6 pc au réseau car le switch ne possède pas assez d'interface
On devra alors rajouter deux autres switchs car ils ne possède que 4 ports disponibles, un switch 1 et un switch 2
On peut aussi passer par un routeur pour simplifier les choses qui fera le lien entre les 3 switchs


## [[TP2 IOS.pdf]]
Bit rate : 9600 bps
Sur l'écran on a une sorte de terminale de même que le cmd
Qui commence par c on a connect
avec t on a : terminal, telnet et traceroute
en utilisant enable on se retrouve avec un # à la place du >, on a des privilèges
En utilisant configure on passe en mode config du switch
L'année affichée par la clock est 1993


# 2024-10-03
[[Bases reseau Modele OSI TCP IP.pdf]]
## Config switch cisco
Mode de base : "switch>"
Execution de privilège : "switch#"
Config globale : "switch (config)#"
Config interface : "switch (config-if)#"
...

Numéro des interfaces : "0/1-24"
0 -> switch de base
1-n -> extension avec plus d'interface
Si on stack des switch on rajoutera le numero du switch avant : 1/0/1 <- première interface du switch 1 

Vitesse des interfaces : 
10/100 mbps -> fast ethernet (FA)
1gbps -> gigabit-ethernet (GI)
10gbps -> tengigabit-ethernet

Connexion par port série (voir [[Fonctionnement des ordinateurs et de ses composants]])

## Caractéristiques du réseau
Débit : Vitesse de transmission des données
Latence : Délai entre l'envoi et la reception d'une réponse
Bande-passante : Capacité max du réseau à transporter des données pendant un temps donné

Fiabilité -> Redondance, faire en sorte que le réseau ne crash pas
Évolutivité -> Capacité d'un réseau à s'adapter et à se développer
Disponibilité -> Capacité d'un réseau à être opérationnel et accessible quand les utilisateurs en ont besoin (serveur cloud doivent avoir 99.999%)



## Organisme de normalisation
Garantie qu'un équipementier qui sort un équipement doit être compatible avec tout les autres équipements des autres constructeurs

Exemple : ISO : International Organization for Standardization
-> A fait le modèle OSI

IEEE : Institute of Electrical and Electronics Engineers
-> 802.3 : Contrôle d'accès au support (MAC ou Media Access Control) Ethernet filaire
-> 802.11 : WiFi (Comment il fonctionne)

IETF : Internet Engineering Task Force
TCP/IP, HTTP, HTTPS...

ICANN
Adresse IP et nom de domaine

Standard de communication sur le réseau
7 couches : 
- Application (Utilisateur)
- Présentation (Mise en forme des données pour le réseau)
- Session (Identification sur le réseau pour créer une session entre les équipements)
- Transport (Choisi la meilleure façon d'acheminer des info, TCP et UDP)
- Réseau (IP)
- Liaison (Transmission des données entre deux machines du réseau, utilise MAC, PP, ETH etc)
- Physique (Émission et réception de bits)

On va passer de la couche 7 à la couche 1 ou dans l'autre sens (reception)

On utilise TCP/IP plutôt que OSI parce que OSI est trop théorique 
4 couches : 
- Application (SMTP, FTP, DNS, DHCP etc)
- Transport (TCP UDP)
- Internet (Adresses IP, comme réseau)
- Accès réseau (Adresses MAC, cables, wifi etc)

Encapsulation et désencapsulation (aller voir cours année dernière)

Message -> Segment -> Datagramme -> Trame (Pour faire simple)

Certains équipements n'utilise pas tout (exemple switch avec couche 1 et 2 de OSI et routeur 1, 2 et 3)

Mnémotechnique couches : Partout Le Roi Trouve Sa Place Assise et dans l'autre sens Ah Petite Salope Tu Recraches La Purée

PDU (protocol data unit) : Données de 7 à 5, segment ou datagramme pour 4, paquet pour 3, trame pour 2 et bit pour 1

Pour tout les protocoles voir les diapos sur le modèle 



## [[TP3 Configuration initiale switch.pdf]]
Dans le switch de base on a 24 FA et 2 GI 
Pour VTY on a 0-4 et 5-15
Pour voir le contenu de la nvram on utilisera dir nvram

Après avoir effectué le mot de passe secret il s'affiche chiffré
Il s'affiche différemment pour la sécurité

À présent les mots de passes s'afficheront chiffré dès qu'ils sont configurés

Cette bannière s'affichera lorsqu'on accédera au switch
Ils doivent tous avoir un MOTD pour ne pas les confondre

Après avoir copié dans la NVRAM on voit que le fichier est stocké directement avec la commande nvram

## Modèle TCP/IP
Manière différente de voir le réseau (plus macron que l'osi)
Application -> Équivalent couche 5 6 7 tout ce qui l'user voit et fait
Transport -> Pas de changement
Internet -> Couche réseau
Accès réseau -> couche 1 et 2, support physiques (cables milieu ambiant etc) et adressage MAC, switch etc

![[equivalentOSIetTCPIP.png]]
Segmentation et multiplexage : voir [[Fonctionnement des ordinateurs et de ses composants]]

On va d'abord segmenter toute les conversations puis les faire passer sur le même support (fibre,  électricité etc), puis on les demux et on les remets ensemble


![[Encapsulation.png]]


## Protocoles principaux
Ethernet couche accès au réseau
IP, ICMP et ARP pour la couche internet
TCP, UDP pour le transport
HTTP, TELNET, SSH, FTP, SMTP, DNS, DHCP, SNMP pour l'application

![[protocolesApplication.png]]


## [[TP4 Connectivité de base.pdf]]
Mise en place d'un serveur ssh sur le switch


## Commutateur et routage
Switch -> Niveau 2 (liaison de données), responsable commutation LAN
Table CAM -> dynamique dans le switch quand on connecte un périphérique
	-> Utilise adresse mac pour savoir où se trouve un périphérique
PDU -> Trame

Switch de distribution -> connecte des switchs d'accès entre eux (souvent que des interface très haut débit)

Switch coeur de réseau -> connecte les distributions entre eux


Routeur -> NIveau 3 (réseau)
	-> Interconnecte des réseaux différents
	Responsable commutation de paquet sur WAN (PDU Paquet)
	Table de routage

Commutation de circuit -> exploite protocoles orientés connexion -> comparable ancien réseau téléphonique

Commutation de paquet -> protocoles non orientés connexion -> comparable envoie de colis
	A la fin le lot est reconstitué

Commutation sur plusieurs couches, sur la 2 on utilise l'adresse MAC
Quand trame arrive au switch il regarde table CAM puis envoie à l'adresse MAC associée

Commutation de niveau 3 (routage)
Quand on envoie un paquet, le routeur prend la décision sur le chemin le plus efficace à suivre
Prise de décision : routage dynamique, BGP, OSPF, RIP etc

Voir support si besoin

## [[TP5-Identification d'adresses MAC et IP.pdf]]


### Réponses 
1) On a utilisé différents support, cable rj45, wifi et fibre
2) En lui même le paquet n'a pas changé, par contre on remarque bien dans la simulation une différence
3) Oui on a perdu avec le concentrateur : ![[CoummutateurError.png]]
4) Il masque les adresses IP et MAC de la source au destinataire
5) Oui il les a utilisées
6) On ne perd pas d'adresse dans la transmission sans fil
7) Le max est le layer 3
8) En premier on a l'adresse destination
9) On doit avoir les adresses dans cet ordre sinon on risque de perdre une partie et le destinataire ne pourrait pas renvoyer la requete à la source
10) Les adresses MAC changent au niveau du routeur puisque les réseaux sont différents
11) Le routeur utilise des adresses MAC 00D0
12) Les autres adresses appartiennent aux endpoints
13) Les IPv4 changent quand on doit retourner vers l'adresse source
14) Les différents réseaux sont sur des ports différents du routeur car sinon il rentrerait en conflit entre eux


## [[TP6-Examen des tables ARP et CAM.pdf]]

### 1)
1) FFFF.FFFF.FFFF
2) On a fait 3 copies du packet parce que on ne sait pas où aller sans la table ARP
3) Le périphérique 172.16.31.3 a accepté le paquet
4) Le périphérique va répondre avec son adresse MAC dans le corps de la réponse
5) Cette fois-ci le switch ne fait plus qu'un seul exemplaire du paquet car il sait où aller
6) Maintenant les adresses de dest et de source correspondent aux pc
7) L'entrée correspond à l'adresse MAC de 172.16.31.3
8) Un endpoint émet une requete ARP lorsque l'IP ne se trouve pas dans sa table ARP, à ce moment là il va demander a tout le réseau avec la MAC FFFF.FFFF.FFFF pour récupérer la MAC du périphérique possédant l'adresse IP qu'il demande

### 2) 
1) On récupère 100% des requètes
2) Dans le switch 1 les mac correspondent aux autres périphériques du sous réseau
3) Dans le switch0 aussi on a les mac des périphériques réseau, sauf celle de l'AP
4) Deux adresses sont sur la même interface car simplement ils passent par un AP qui est branché sur une seule interface
5) La nouvelle entrée correspond à 172.16.31.1 qui est le routeur de ce réseau
6) On a 2 unités de données différentes quand la table est vide
7) 172.16.31.1 est la destination de la requête
8) L'adresse est différente car on ne se trouve pas dans le même réseau donc on passe par le routeur
9) Il n'y a aucune MAC address, surement car on ne communique avec aucun autre réseau
10) Il y a une entrée pour 172.16.31.2
11) La première requête ping sera perdue car il n'y a pas la MAC Address de retour, donc elle ne sera pas ou revenir mais le routeur va l'ajouter pour que les suivantes fonctionnent


## [[TP7-Configuration de routeurs.pdf]]


1) Hostname : Router
2) 0 Fa
3) 3Ga
4) une interface série
5) 0-4 vty
6)3Il n'y a pas de startup config car elle n'a pas été config
7) Quand on ping rien ne répond car les interfaces du routeur sont éteintes
8) Mac Gi0 : 0000.0cba.5901
9) bande passante : 100mbps
10) les routes présentes sont des C et des L soit connectés et locales
11) il y a 3 routes connectés représentants des routeur ou switchs
12) Si la route ne figure pas dans la table de routage on a 2 paquets (ARP puis paquet de base)


## [[TP8-VLANs et Trunks.pdf]]

### Réponses
1) Actuellement les seuls pc qui répondent sont dans le même sous réseau (10. / 20. / 30.)
2) La configuration de Vlan apportera que tout les réseaux pourront communiquer entre eux
3) Pour voir uniquement le nom des vlan on utilise `show vlan brief`
4) Pour l'instant comme tout à l'heure les seuls à répondre sont dans le même sous réseau car les interfaces ne sont pas dans les  vlan
5) Là on ne peut plus ping pc4 depuis pc1 car la vlan n'est pas configurée sur le switch 1
6) On considère encore dans un réseau différents les autres PC, ce qui est normal du fait de leur vlan 

## [[TP9-Router on a stick.pdf]]

### Réponses
1) Les périphériques ne répondent pas, réseau différents
2) De même qu'avant on ne peut pas car maintenant ils sont dans des vlan différents et que les routeurs n'ont pas la capacité d'envoyer vers les autres réseaux
3) Ici tout marche car on a bien configuré les routeurs
4) Il y a des routes connectées, statique et locales
5) Il y a 3 routes connectées, c'est celle qui sont directement connectées au routeur

## [[TP10-Routage dynamique RIP.pdf]]

## [[TP16-Routage intervlan Switch L3.pdf]]
