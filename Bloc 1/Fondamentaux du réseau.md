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








