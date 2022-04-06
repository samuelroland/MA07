Ma-07 Samuel Roland - Exercices

## Chapitre 10



1. Tapez la commande history pour afficher la liste de vos dernières commandes.
`history`

1. En utilisant le caractère !, réexécutez certaines de ces commandes en utilisant soit leur numéro dans la liste, soit le début de la ligne correspondante.  
`history !12` ou `history !-12` ou `!12`

1. Utilisez la commande which pour voir où se trouve la commande rm que vous utilisez couramment. 
`which rm` donne `/usr/bin/rm`.

1. Afin de sécuriser l'utilisation de la commande rm, créez manuellement un alias sur la commande rm. (alias rm='rm -i')

1. Vérifiez que ce nouvel alias se trouve dans la liste de l'utilisateur cpnv.  
`alias`

1. Réutilisez la commande which pour voir quelle commande rm est à présent utilisée prioritairement.  
`which rm`

1. Utilisez ensuite la commande unalias pour supprimer l'alias rm.  
`unalias rm`

1. Pour créer des alias permanents (validés dans toute nouvelle session Shell), ouvrez le fichier ~/.bashrc avec l'éditeur de texte nano.

    - a. Recopiez l'alias rm de la question précédente,
    `echo "alias rm='rm -i'" >> ~/.bashrc`

    - b. Ajoutez un alias appelé lr qui affichera la sous-arborescence (avec les infos détaillées) du répertoire courant.
    `echo "alias lr='ls -R'" >> ~/.bashrc`

    - c. Ajoutez un alias appelé back permettant de revenir au répertoire précédent (comme "cd -"). Pour cela, votre alias devra utiliser le contenu de la variable d'environnement OLDPWD.  
    `echo "alias back='cd $OLDPWD'" >> ~/.bashrc`

    - d. Refermez le fichier `~/.bashrc` et validez les modifications en tapant la commande `source ~/.bashrc`.

    - e. Affichez la liste de vos alias et testez-les pour voir s'ils sont bien été validés.  
    **Tout fonctionne bien.**

1. Retrouvez comment afficher la liste des Variables d'Environnement.
`printenv`

1. Afficher la page d'aide de la commande route en différentes langues, redéfinissez la variable d'environnement LANG successivement à fr (fr_CH.UTF-8), en (en_EN), puis de (de_DE) et affichez à chaque fois l'aide de route.
`export LANG=fr_CH.UTF-8` puis `export LANG=en_EN` puis `export LANG=de_DE`

1. Nous souhaitons que cpnv puisse lancer le script cherche-conf.sh (créé dans TP2) sans devoir préciser le répertoire dans lequel il se trouve.

    - a. Essayez de lancer le script sans donner son chemin et vérifiez qu'il n'est pas trouvé.  
    **Il n'est pas trouvé évidemment.**

    - b. Avec la commande echo $PATH, observez la valeur du PATH de l'utilisateur courant.

    - c. Utilisez cette information pour créer le répertoire manquant dans votre répertoire personnel et placez-y le script (tout cela sans utiliser les droits de root).  
    **Etape à ignorer. A la place on doit rajouter notre dossier TP2 dans le $PATH, `export PATH=$PATH:~/TP2`**

    - d. Utilisez la commande which pour vérifier que le script est bien trouvé par le shell bash et lancez-le sans en préciser le chemin.  
    `which cherche-conf.sh` et `cherche-conf.sh`


1. Le répertoire /sbin ne figure pas dans le PATH de l'utilisateur cpnv et nous allons le rajouter pour avoir accès à certaines commandes système (même si cela n'est pas recommandé !)

   - a. Tapez la commande ip addr pour vérifier qu'elle n'est pas trouvée avec le PATH actuel puis affichez le contenu de votre PATH pour vérifier que le répertoire /sbin n'y figure pas.

   - b. Ajouter manuellement le répertoire /sbin au contenu de votre PATH et puis affichez-le pour vérifier que cela a bien marché.
   `export PATH=$PATH:/sbin`

   - c. Pour que cette modification soit ensuite permanente, ajoutez-la dans le fichier ~/.bashrc comme pour la création des alias puis validez le changement.  
   `PATH="$PATH:/sbin:$HOME/TP2"`. **On peut aussi écrire dans le .profile pour configurer tous les shells.**

   - d. Rouvrez une nouvelle session, vérifiez le contenu de votre PATH puis tapez la commande ip addr qui devrait à présent pouvoir être lancée sans en préciser le chemin.

1. Tapez la commande uname -r qui vous affichera le numéro de version actuelle de votre noyau.

1. Affichez le contenu du répertoire /lib/modules pour vérifier qu'il contient un répertoire par version du noyau précédemment installée.  
`ls /lib/modules/5.10.0-11-amd64/`

1. A présent, faites en sorte d'afficher, en une seule commande et sans utiliser de variable intermédiaire, la liste des fichiers du répertoire /lib/modules/ma_version_du_noyau où ma_version_du_noyau est donnée par l'exécution de la commande uname.  
`ls /lib/modules/$(uname -r)`