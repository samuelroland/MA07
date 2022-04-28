Ma-07 Samuel Roland - Exercices

## Chapitre 13
Exercices

1. Avec la commande tar, créez dans votre répertoire personnel une archive TP1.tar de votre répertoire TP1. Vérifiez ensuite son contenu pour vous assurer de l'absence de chemins absolus. `tar -cvf TP1.tar TP1/` puis `tar --list -f TP1.tar`.
1. Mettez à jour (update) cette archive en y ajoutant le répertoire TP2 de votre répertoire personnel. `tar -uf TP1.tar TP1/`
1. Compressez puis décompressez ce fichier TP1.tar en reprenant le dossier original, avec les commandes bzip2 et gzip. Vérifiez notamment les extensions et les tailles des fichiers après la compression. `tar -zcvf TP1.tar.gz TP1/` puis `mkdir tp1back && tar -zxvf TP1.tar.gz -C tp1back`. (**On peut aussi arriver à compresser directement l'archive de la manière suivante: `tar -zcvf TP1test.tar.gz TP1.tar`**). Pour compresser avec bzip2 on peut faire `tar -jcvf TP1test.tar.gz TP1.tar`
1. Créez la même archive avec l'option z de la commande tar qui active la compression compatible avec gzip. Quelle précaution faut-il prendre concernant l'extension du fichier créé ? `tar -zcvf TP1.tar.gz TP1/`. **On utilise `*.tar.gz` pour la compression gzip, et `*.tar.bz2` pour la compression bzip2**.
1. Créez un script nommé tp1_backup.sh qui sauvegarde le répertoire TP1 dans un fichier /tmp/_tp1.tar.gz
    - cron est un programme qui permet aux utilisateurs des systèmes Linux d’exécuter automatiquement des scripts, des commandes ou des logiciels à une date et une heure spécifiées à l’avance, ou selon un cycle défini à l’avance.

---
**Facultatifs:**
1. À l'aide de la commande crontab exécutez automatiquement ce script tous les jours à 23h00.
1. À l'aide de la commande date, qui permet de régler l'heure manuellement :
    - a. Fixez la date de votre machine au 1er aout 2022
    - b. Fixez l'heure à 22h59.
    - c. Contrôler l'exécution du script tp1_backup.sh à 23h00
    - d. Refixez ensuite les valeurs normales.
1. Si vous souhaitez effectuer une action particulière dans la journée (par exemple dans 15 minutes ou à une heure précise), vous n'utiliserez pas cron (car il n'y a pas de répétition, c'est juste une exécution unique programmée), il faudra utiliser la commande at. (installer le package at auparavant). Exemple, nous allons demander de créer un fichier à 14 h 17 :

    ```
    $ at 14:17
    warning: commands will be executed using /bin/sh
    at> touch fichier.txt
    at> [Control-D]
    job 5 at Mon Nov 10 14:17:00 2010
    ```
 
1. Programmez l'exécution unique du script tp1_backup.sh dans 5 minutes (now +5 minutes)

