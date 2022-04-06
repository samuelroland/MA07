Ma-07 Samuel Roland - Exercices

## Chapitre 5
1. A l'aide de la commande touch, créez les fichiers vides prog1.c, prog2.c, prog3.for et prog4.for dans le répertoire src. :  
`touch prog1.c prog2.c prog3.for prog4.for`
1. Relevez les options de la commande ls qui permettent d'obtenir
    - a. la sous-arborescence récursive d'un répertoire: `ls -R`
    - b. la liste des fichiers cachés : `ls -a`
    - c. les principales informations (type, droits, propriétaire...) : `ls -l`
    - d. les numéros d'inode1 : `ls -i`
    - e. la date de dernière modification pour trier la liste des fichiers : `ls -ltc`
    - f. la taille des fichiers pour trier la liste des fichiers : `ls -laSr`

1. Affichez la liste des fichiers du répertoire /var/log triée par date de modification pour voir quel est le fichier de logs du système le plus récent. :  
 `ls /var/log/ -ltc`

1. Depuis votre répertoire personnel, affichez la liste et les informations sur les fichiers de configuration (avec une extension .conf) contenus dans le répertoire /etc. :  
 `ls /etc/*.conf -la`.

1. Toujours depuis votre répertoire personnel affichez le contenu du fichier "resolv.conf" stocké dans /etc. Quelles informations contient ce fichier ? :  
 `cat /etc/resolv.conf`. **Je suppose que ce fichier contient une configuration des informations sur le réseau local.**

1. Créez le fichier vide fichier-cache dans le reprtoire TP1 et vérifiez sa présence par la commande ls. :  
 `touch fichier-cache && ls`

1. Renommez à présent ce fichier pour que la commande ls ne le fasse plus apparaître, à moins d'utiliser l'option -a. :  
 `mv fichier-cache .fichier-cache`

1. Avec la commande mv, renommez le fichier prog4.for en prog3.for.  
    `mv prog4.for prog3.for`
    1. a. Que s'est-il passé et quel est le moyen de sécuriser cette commande ? **Le fichier prog3.for a été écrasé. Il suffit de faire**  `mv prog4.for prog3.for -i`.

1. Utilisez la commande sécurisée précédemment pour renommer le répertoire include en INCLUDE. :  
 `mv progs/include progs/INCLUDE -i`
    - a. Pourquoi le système ne pose-t-il pas la question pour renommer ? **Parce que cela n'écrase pas de dossier ou fichier existant.**
    - b. Que se passerait-il si le répertoire INCLUDE existait déjà avant d'utiliser la commande ? **Le dossier `include` serait déplacé dans le dossier `INCLUDE`**.

1. Avec la commande mv, déplacez le fichier prog1.c vers le répertoire web en utilisant un chemin relatif.  
 `mv progs/src/prog1.c divers/web/`

1. Avec cp, copiez le fichier prog2.c dans le répertoire courrier en utilisant des chemins absolus.  
 `cp /home/cpnv/TP1/progs/src/prog2.c /home/cpnv/TP1/courrier`

    - a. Relancez la même commande et notez vos remarques. **Le fichier existant dans `courrier` est également écrasé.**

    - b. Que faire pour sécuriser la commande ? **Rajouter le paramètre `-i`**.

1. Placez-vous dans divers et, en une seule commande, copiez-y le répertoire src et son contenu en le renommant src2.  
 ` cp ../progs/src/ src2 -r`

    - a. Quel problème rencontrez-vous et quelle alternative devez-vous utiliser ? **Ne pas oublier le `-r`**.

1. Trouvez la commande permettant de supprimer le répertoire src2. Elle devra être sécurisée et demander confirmation à l'utilisateur avant toute destruction de fichier.  
`rm -ri src2`.
