Ma-07 Samuel Roland - Exercices

## Divers

Installation de la page de manuel pour `kill`:  
`apt-get install manpages manpages-dev`

## Chapitre 4
1. Avec la commande cd, déplacez-vous dans le répertoire /usr/local : `cd /usr/local`
1. Testez et notez les différentes façons de revenir avec la commande cd dans votre répertoire personnel /home/[user] : `cd` ou `cd /home/cpnv`.
1. Explication de `cd -`: **la commande permet de revenir dans le dossier précédent. Si on tape 2 fois cette commande on revient au dossier de départ.**
1. Où vous place la commande cd utilisée sans paramètre ? **A la racine du profil**.
1. Créez dans votre répertoire personnel /home/[user] un répertoire TP1 dans lequel vous devrez effectuer tous les exercices suivants. : `mkdir TP1`.

1. Utilisez les commandes cd et mkdir pour créer dans votre répertoire TP1 l'arborescence présentée. Pour vous faciliter la tâche, utilisez l'option de la commande mkdir permettant de créer en une fois une arborescence à plusieurs niveaux.  
Pensez à utiliser les flèches du clavier pour récupérer les commandes précédemment tapées et à compléter automatiquement les noms de répertoires et de fichiers avec la touche de tabulation.

    ```bash
    /home/[user]/TP1
                |--courrier
                |--progs
                    |--bin
                    |--src
                    |--include
                    |--lib
                |--divers
                    |--images
                    |--web
    ```

    **Commande à taper pour créer tous les dossiers**
    ```bash
    mkdir -p courrier progs/bin progs/src progs/include progs/lib divers/images divers/web
    ```

1. Quand vous avez créé l'arborescence complète, affichez-la à l'aide de la commande ls (option de récursivité) :  `ls -lR`

1. En vous plaçant sur le répertoire web, notez les différentes manières de vous déplacer vers le répertoire src en utilisant les chemins absolu et relatif. Utilisez la touche tabulation pour compléter automatiquement les noms de répertoire avec la commande cd. : `cd ../../progs/src` ou `cd ~/TPI1/progs/src` ou `cd /home/cpnv/TPI1/progs/src`.