Ma-07 Samuel Roland - Exercices

## Chapitre 9

**D'abord, ajouter `/sbin` aux variables d'environnement: `export PATH=$PATH:/sbin/`**

1. Créez sur votre machine l'utilisateur suivant :  
**`adduser secret`, ensuite laisser mettre un mot de passe et toutes les valeurs par défaut**

    - a. Nom de login : secret

    - b. Mot de passe : Pa$$w=rd

    - c. Répertoire personnel : /home/secret

    - d. Id user : par défaut

    - e. Groupe d'utilisateurs : par défaut

    - f. Description : Utilisateur Secret.

    - g. Shell de démarrage : /bin/bash

1. Vérifiez la présence de ce nouvel utilisateur dans le fichier /etc/passwd  
`cat /etc/passwd`

1. Depuis votre identité lambda passez en root et à partir de root en secret.

    - a. Utilisez les commandes whoami pour vérifier à chaque fois ces changements d’identité

    - b. Que remarquez-vous ?  
    **Cela fonctionne bien.**

    - c. Utilisez la commande su avec l'option -, quelle identité vous donne cette commande ?  
    **root**

1. Connecté(e) en cpnv, changez votre mot de passe avec la commande passwd.  
`passwd cpnv` ou juste `passwd` (par défaut l'utilisateur actuelle)

1. Essayez ensuite de changer celui de secret.  
    **Ce n'est pas possible.**

1. Connectez-vous en root et essayez de modifier le mot de passe de secret. Que remarquez-vous ?  
**On peut le modifier mais en plus on n'a pas besoin de donner le mot de passe actuel!**

1. Tapez la commande ps alx pour retrouver l'UID de l’utilisateur propriétaire du démon cron
    - **ps -ef est plus utile..**

    - a. Dans le fichier /etc/passwd, retrouvez le nom et le GID de cet utilisateur,  
     **`cat /etc/passwd | grep 104` -> on a nom: `messagebus` et GID `110`.**
    - b. Dans le fichier /etc/group, retrouvez le nom de ce groupe.  
     **`cat /etc/groups | grep 110`. On trouve donc le groupe `messagebus`.**

1. La commande sudo permet à un utilisateur d’exécuter des commandes normalement réservées à root, mais cette possibilité n’est pas offerte par défaut sur Debian.

    - a. Installer le programme sudo  
    `apt-get install sudo`.

    - b. Modifiez le fichier /etc/sudoers (commande visudo) en vous inspirant de sa dernière ligne et autorisez cpnv  
    `visudo` puis on rajoute la ligne `cpnv    ALL=(ALL:ALL) ALL`

1. Connecté en cpnv, simulez immédiatement un arrêt du système par la commande /sbin/shutdown.  
`sudo shutdown`

1. Dans la suite, nous privilégierons l’utilisation de sudo pour les opérations en tant que super-utilisateur.
