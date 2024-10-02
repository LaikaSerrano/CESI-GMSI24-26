#bloc1 
## 2024-10-02

[[Bases reseau Composants.pdf]], [[TP1 Découverte Packet Tracer.pdf]]
### Termes du cours
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

### Matériel intermédiaire
#### Niveau 1 :
Hub -> Dépasser, ne pas utiliser, ne tien pas compte des adresses c'est juste des cables
#### Niveau 2 : 
Bridge -> Évolution direct du hub, barrière entre les réseaux, découpe en deux une partie d'un réseau
Switch -> Comme un pont sauf que chaque interface est isolée, adresse directement l'info au destinataire souhaité
#### Niveau 3 : 
Routeur : interconnection de réseaux avec les IP
Pare-feu : Même chose que routeur mais va autoriser certain réseaux et pas d'autres, défini des règles d'autorisation

### Topologie (physique ou logique)

Physique : Indiquer un emplacement physique des périphériques intermédiaires et de comment ils sont cablés entre eux -> niveau de détail assez peu élevé
Logique : Décrire comme les périphériques fonctionnent entre eux, pas comment ils sont cablés
Logique en bus : Tous sur une ligne, ils communiquent l'un par l'autre, si un est éteint c'est bloqué
Logique en anneau : De même que le bus mais le dernier est relié au premier
Logique en étoile (réseaux actuels) : Noeud central qui interconnecte tout les périphériques entre eux
Logique Hiérarchique : Équipement les plus importants en haut (accès internet) et ceux les moins importants en bas (périphériques finaux)
Logique maillée : Tout les périphériques sont connectés à tout les périphériques (ex d'internet)

### Typologie de réseau
LAN (Local Area Network) : Local acceder au périphérique
WAN (Wide Area Network) : Internet, grand
PAN (Personal Area Network) : reseau local
MAN (Metropole Area Network) : échelle d'un campus, une ville etc
SAN (Storage Area Network) : Serveur de fichiers
WLAN (Wireless Local Area Network) : WiFi

### Modes de communication
Simplex : Unidirectionnel
Half duplex : Bi directionnel non simultané
Full duplex : Bi directionnel 



### [[TP1 Découverte Packet Tracer.pdf]]
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


### [[TP2 IOS.pdf]]
9600 bps
Sur l'écran on a une sorte de terminale de même que le cmd
Qui commence par c on a connect
avec t on a : terminal, telnet et traceroute
en utilisant enable on se retrouve avec un # à la place du >, on a des privilèges
En utilisant configure on passe en mode config du switch
L'année affichée par la clock est 1993
