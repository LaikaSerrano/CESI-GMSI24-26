#bloc1
## 2024-09-25
Cyrille.abraham@gmail.com
"\*/" : Système analogique
"|" : BUS Parallèle
#### Composants pc : 
	Carte mère / cmos / chipset
	CPU
	GPU
	RAM |
	Ventilateur*/
	radiateur
	Carte son*/
	PSU*/
	NIC
	SSD / HDD
	Lecteur graveur optique
	lecteur de disquette
	lecteur de cartes mémoires
	NPU (Neuronal Process Unit)
	Carte d'acquisition vidéo*/


### Ports
#### Ports externes 
	Video : DP, HDMI, DVI (DVI-D, DVI-I*/, DVI-A*/), VGA*/, PÉRITEL*/
	Audio : jack*/, optique, HDMI, coaxial*/
	Ethernet (rj45)
	USB
	PS/2
	Port série (port COM) / RS232 (envoie direct des caractères de clavier par le port)
	DB25 | 
	eSATA

#### Ports internes
	PCI / PCIE |
	RAM (DDR, EDO, SoDIMM) |
	Socket CPU |
	Sata
	NVMe
	ATA/IDE |
	M2
	SCSI
	AGP |

### Bus et parallèles
BUS : Dispositif de transmission de données -> Liaison point à point entre deux composants $\ne$ réseau qui a plusieurs liaisons
Parallèles : nécessite une synchro de courant électrique -> fonctionne par fils, on va avoir 32 fils sur un bus 32, il faut que ce soit sous courte distance sinon on perd les informations
Série : basique : on envoie les bits tous à la suite, besoin d'un multiplexage pour envoyer et réceptionner, on doit utiliser du multiplexage sinon on envoie trop de 1 et l'arrivée risque de se tromper, fiable, long, peu encombrant, permet le full-duplex (allé retour)


### Carte mère 
Système nerveux d'un ordinateur, permet aux composants de communiquer entre eux
Formats : 
- Atx
- microATX
- miniATX
- nanoATX
- picoATX etc
Sockets : CPU avec pines femelle ou male
- Socket LGA pour intel et AM* pour amd (* = numero entre 1 et 5)

Certaines cartes possède plusieurs socket pour avoir plusieurs processeur (surtout carte mère serveur), utile pour les hyperviseurs (vm)

HDMI -> Contrôle des droits d'auteurs encore aujourd'hui

Chipset : deux bridge, northbridge et southbridge
- Northbridge, aussi FSB (front serial bus) : Éléments reliés : cpu gpu ram et southbridge
- Southbridge : cartes secondaires, ctlr usb etc avec le northbridge 

Ports PCIE : Plus de 7 normes différentes avec la possibilité d'avoir 1, 2, 4, 8, 16 ou 32 slots dans le même port, la technologie 5 commence à peine à être utilisée, on retrouve toujours de la 3.0 aujourd'hui
![[NombreBrochePCIE.png]]

![[VitesseGenPCIE.png]]
### CMOS et horloge
petite mémoire (10aines d'octets) et horloge qui consomme rien (10$\mu A$)
Si pas à l'heure : relation d'approbation au domaine, impossible de se connecter, certificats ssl problèmes donc pas de chiffrement

### CPU
Caractérisé par : sa marque, sa gamme, fréquence horloge, nombre de coeurs, jeux d'instruction, socket, mémoire cache (fort impact sur perf), fréquence du pont fsb, largeur des registres (32 ou 64 bits)

Loi moore : division de la taille des transistors par 2 tout les 18 à 24 mois
Loi d'amdahl : augmentation vitesse programme par coeur limitée

### BIOS
Bios = lien entre l'OS et le hardware, bas niveau dans la carte mère
Test le matériel puis check le stockage qui contient l'os pour le charger en mémoire
Avant dans une ROM (pas effaçable et possible d'écrire une seule fois), EPROM (effaçable par UV) et maintenant EEPROM (effaçable éléctroniquement)
Fait des POST (power-on self test)
Peut être configurer pour faire ± de test

### RAM
random access memory, donnée accessible très rapidement dans cpu ou gpu
Différents type de mémoire : les plus utilisés c'est ddr1-2-3-4-5 -> double la vitesse d'accès car lit au début et à la fin de la fréquence
Pour la synchronisation aller voir le poly de cours
ECC -> Correction d'erreur, surtout pour les entreprises 



