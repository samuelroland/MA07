Ma-07 Samuel Roland - Exercices

## Chapitre 13

### Exercice 1
Vous exécutez la commande suivante :

    $ sleep 60 

L’exécution de cette commande dure 1 minute. Comment interrompre cette commande et reprendre la main ?

**Ctrl + C**.

### Exercice 2
Dans votre répertoire d’accueil, créez l’arborescence suivante, en n’utilisant que des chemins relatifs :

    rep1 
    |---fich11 
    |---fich12 
    |---rep2 
    | |---fich21 
    | |---fich22 
    |---rep3 
    | |---fich31 
    | |---fich32 

```
mkdir -p rep1/rep2 rep1/rep3 
touch rep1/fich11 rep1/fich12 rep1/rep2/fich21 rep1/rep2/fich22 rep1/rep3/fich31 rep1/rep3/fich32
```

### Exercice 3
Comment déplacer toute l’arborescence rep3 sous le répertoire rep2 ? Supprimez tout sauf rep1, fich11 et fich12.

### Exercice 4
À l’aide de la commande id, déterminez votre UID et votre groupe (nom de groupe et GID). Combien y a-t-il d’utilisateurs dans votre groupe ?

### Exercice 5
En utilisant les commandes mkdir et echo, créez dans un nouveau répertoire de nom "reptest" le fichier "bienvenue" contenant la ligne de commandes :

    echo Bienvenue dans le monde Linux 

Exécutez ce fichier

### Exercice 6
En utilisant les commandes chmod et touch, créez un fichier que vous pouvez lire, modifier et supprimer.

`touch hey.txt && chmod 744 hey.txt`

### Exercice 7
En utilisant les commandes chmod et touch, créez un fichier que vous pouvez lire et supprimer mais que vous ne pouvez modifier.

`touch salut.txt && chmod 500 salut.txt`

### Exercice 8
En utilisant les commandes chmod et touch, créez un fichier que vous pouvez lire mais que vous ne pouvez ni modifier, ni supprimer.

`touch salut.txt && chmod 400 salut.txt`

### Exercice 9
Dans quel cas les permissions d’un fichier à sa création sont-elles différentes des permissions fixées par umask ?

**La permission d'exécution (x) n'est jamais appliquée à la création du fichier peu importe le umask.**

### Exercice 10
Si vous pouvez travailler avec un collègue appartenant au même groupe que vous, modifiez les permissions du fichier créé à l’### exercice "Bienvenue" ci-dessus de telle façon que votre collègue puisse le lire et l’exécuter, mais ne puisse pas le modifier ni le supprimer.

Pouvez-vous modifier les permissions de ce fichier de telle sorte que votre collègue puisse le lire, le modifier et l’exécuter alors que vous-même ne pouvez pas le modifier ?
### Exercice 11

Comment est attribuée la permission d’effacer un fichier ? Créez un fichier que votre collègue peut modifier mais pas supprimer et un autre qu’il peut supprimer mais pas modifier.

Est-il logique de pouvoir attribuer de tels droits ? Quelles sont les conséquences pratiques de cette expérience ?

<!-- No need to know for the exam
### Exercice 12

Écrivez votre propre commande "dir" affichant page par page les informations données par la commande ls -l, incluant les fichiers cachés (sauf . Et ..).
-->
### Exercice 13

Écrivez un alias imposant la confirmation sur la suppression des fichiers.

Écrivez la commande "psmoi" permettant d’obtenir la liste de tous les processus vous appartenant (utilisez la commande ps).

<!-- No need to know for the exam
### Exercice 14
Exercice 1

Vous exécutez la commande suivante :

    $ sleep 60 

L’exécution de cette commande dure 1 minute. Comment interrompre cette commande et reprendre la main ?
Exercice 2

Dans votre répertoire d’accueil, créez l’arborescence suivante, en n’utilisant que des chemins relatifs :

    rep1 
    |---fich11 
    |---fich12 
    |---rep2 
    | |---fich21 
    | |---fich22 
    |---rep3 
    | |---fich31 
    | |---fich32 

Exercice 3

Comment déplacer toute l’arborescence rep3 sous le répertoire rep2 ? Supprimez tout sauf rep1, fich11 et fich12.
Exercice 4

À l’aide de la commande id, déterminez votre UID et votre groupe (nom de groupe et GID). Combien y a-t-il d’utilisateurs dans votre groupe ?
Exercice 5

En utilisant les commandes mkdir et echo, créez dans un nouveau répertoire de nom "reptest" le fichier "bienvenue" contenant la ligne de commandes :

    echo Bienvenue dans le monde Linux 

Exécutez ce fichier
Exercice 6

En utilisant les commandes chmod et touch, créez un fichier que vous pouvez lire, modifier et exécuter.
Exercice 7

En utilisant les commandes chmod et touch, créez un fichier que vous pouvez lire et exécuter mais que vous ne pouvez modifier.
Exercice 8

En utilisant les commandes chmod et touch, créez un fichier que vous pouvez lire mais que vous ne pouvez ni modifier, ni exécuter.
Exercice 9

Dans quel cas les permissions d’un fichier à sa création sont-elles différentes des permissions fixées par umask ?
Exercice 10

Si vous pouvez travailler avec un collègue appartenant au même groupe que vous, modifiez les permissions du fichier créé à l’exercice "Bienvenue" ci-dessus de telle façon que votre collègue puisse le lire et l’exécuter, mais ne puisse pas le modifier ni le supprimer.

Pouvez-vous modifier les permissions de ce fichier de telle sorte que votre collègue puisse le lire, le modifier et l’exécuter alors que vous-même ne pouvez pas le modifier ?
Exercice 11

Comment est attribuée la permission d’effacer un fichier ? Créez un fichier que votre collègue peut modifier mais pas supprimer et un autre qu’il peut supprimer mais pas modifier.

Est-il logique de pouvoir attribuer de tels droits ? Quelles sont les conséquences pratiques de cette expérience ?
Exercice 12

Écrivez votre propre commande "dir" affichant page par page les informations données par la commande ls -l, incluant les fichiers cachés (sauf . Et ..).
Exercice 13

Écrivez un alias imposant la confirmation sur la suppression des fichiers.

Écrivez la commande "psmoi" permettant d’obtenir la liste de tous les processus vous appartenant (utilisez la commande ps).
Exercice 14

Vous souhaitez modifier :

    l’invite afin qu’elle indique le nom de l’ordinateur sur lequel vous travaillez et votre répertoire courant,

    la valeur par défaut des protections des fichiers et répertoires que vous allez créer.

De plus vous souhaitez retrouver ces modifications lors de chacune de vos entrées en session.
Exercice 15

Écrivez votre propre fonction "fd" permettant de rechercher à partir du répertoire courant l’emplacement d’un répertoire.

Testez votre fonction en recherchant tous les répertoires commençant par r.
Exercice 16

Quelles commandes Linux devez-vous exécuter pour obtenir à l’écran :

    Il y a xxx utilisateurs de ce systeme dont le login shell est bash 

-->

Exercice 17

En utilisant la commande find, trouvez et listez les noms de :

    tous les fichiers sous le répertoire /etc dont les noms commencent par rc

    tous les fichiers réguliers vous appartenant ; mettez le résultat dans le fichier /tmp/findmoi et les erreurs dans /dev/null

    tous les sous–répertoires de /etc

    tous les fichiers réguliers se trouvant sous votre répertoire d’accueil et qui n’ont pas été modifiés dans les 10 derniers jours

Exercice 18

Trouvez à partir de votre répertoire d’accueil, le nombre de fichiers ayant une taille supérieure à 1 Mega-octets et stockez leurs noms dans un fichier (utilisez la commande tee).
Exercice 19 - MAYBE

Créez dans le répertoire rep1 le fichiers suivants : fich1, fich2, fich11, fich12, fich1a, ficha1, fich33, .fich1, .fich2, toto, afich.

Listez les fichiers :

    dont les noms commencent par fich

    dont les noms commencent par fich suivi d’un seul caractère

    dont les noms commencent par fich suivi d’un chiffre

    dont les noms commencent par .

    dont les noms ne commencent pas par f

    dont les noms contiennent fich

Exercice 20

Écrivez un alias en Bash nommé alphapath permettant de lister page par page et dans l’ordre alphabétique l’ensemble des variables d’environnement.
Exercice 21

Créez un fichier de nom « -i », puis supprimez-le.
Exercice 22

Il arrive souvent de lancer une commande Linux produisant plusieurs pages d’écran à toute vitesse (par exemple : ls l /etc). Il faut alors relancer la même commande, en envoyant sa sortie standard dans less, ce qui permet d’examiner le résultat page par page.

Si votre shell interactif est le Bash, cela ne doit pas être fastidieux : créez l’alias p qui relance la dernière commande en envoyant sa sortie standard dans la commande less.
Exercice 23

Créez un fichier texte et un lien dur sur ce fichier dans le même répertoire.

    Vérifiez que les deux noms correspondent au même inode.

    Changez les permissions de l’un et vérifiez que les permissions de l’autre ont suivi.

    Modifiez le contenu de l’un et relisez le contenu de l’autre.

    Supprimez l’un, que devient l’autre ? Essayez de créer un nouveau lien entre un de ces noms et un nouveau nom dans /tmp. Expliquez.

Exercice 24

L’option -l de la commande ls permet de connaître le nombre de liens sur un fichier régulier (deuxième champ). Curieusement, ce champ n’est pas égal à 1 pour les répertoires, alors qu’il n’est pas possible de créer de liens durs sur des répertoires. Expliquez la valeur de ce nombre sur votre répertoire d’accueil.
Exercice 25

Créez un fichier texte et un lien symbolique sur ce fichier dans le même répertoire.

    Quelles sont les permissions du lien symbolique ?

    Combien de liens possède le fichier texte ?

    Avec la commande more, affichez le contenu du lien symbolique.

Effacez le fichier texte. Que devient le lien symbolique ?

<!-- No need to know for the exam
Exercice 26

Le disque est plein de vide ! Écrire un petit script affichant sur la sortie standard la taille cumulée de tous les fichiers réguliers situés sous le répertoire courant, et l’espace disque total occupé par le répertoire courant et tout ce qu’il contient.
-->

Exercice 27

Recherchez dans le fichier /etc/passwd :

    L’entrée correspondant à votre login (solution indépendante du login).

    Le nombre de lignes contenant la chaîne de caractères : BASH ou bash.

    Le nombre de lignes contenant la chaîne de caractères : /home/.

<!-- No need to know for the exam
Exercice 28

Recherchez dans le fichier /etc/debconf.conf :

    Le nombre de lignes contenant un point .

    Le nombre de lignes ne commençant pas par # .

    Toutes les lignes de plus de 50 caractères.

    Toutes les lignes de plus de 50 caractères (hors commentaires).

Exercice 29

Listez les noms de login de tous les utilisateurs de votre système qui n’ont pas de programme de démarrage (dans /etc/passwd).

-->