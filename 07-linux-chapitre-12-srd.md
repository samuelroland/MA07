Ma-07 Samuel Roland - Exercices

## Chapitre 12
Exercices

1. Déterminez quelle est la configuration actuelle de vos interfaces réseau avec la commande ip. `ip a`.
1. Quelle est votre adresse IP, votre masque, votre adresse MAC et votre MTU.
    - adresse IP: `192.168.88.129`
    - masque de sous-réseau: `192.168.88.255`
    - adresse MAC: `00:0c:29:d5:00:03 `
    - MTU: 1500
1. Déterminez les cartes réseau dont vous disposez sur votre machine avec la commande lspci.
1. La configuration des interfaces réseau se fait au démarrage au moyen, entre autre, du fichier /etc/network/interfaces (parce que la distribution GNU/Linux est une Debian). Vérifiez que la configuration est bien faite via DHCP. **Oui: `iface ens32 inet dhcp`**.
1. Retrouvez l'adresse de loopback et précisez en quoi elle est utile au système. **`127.0.0.1` est utile à tester si les composants réseaux fonctionne.**
1. Désactivez votre interface Ethernet ens32 (ifdown): `ifdown ens32`
1. Activez la carte ens32 (ifup): `ifup ens32`
1. Essayez de pinguer votre machine hôte qui devra être dans le même subnet. **Ca fonctionne.**
1. Retrouvez le fichier de log du répertoire /var/log qui vient d'être modifié par la question précédente. **syslog.1**
1. Observez les dernières lignes de ce fichier pour retrouver :
    - a. Le port par défaut et l'adresse de broadcast pour l'émission des requêtes DHCP: **255.255.255.255 port 67.**
    - b. L'adresse du serveur qui vous a fourni votre adresse IP: **192.168.88.254**.

