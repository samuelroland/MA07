Ma-07 Samuel Roland - Exercices

## Chapitre 8

### Redirections

Préambule : Créez dans votre répertoire personnel un répertoire TP2 dans lequel vous devrez effectuer tous les exercices présentés ci-dessous. Les exercices doivent être réalisés en tant qu'utilisateur cpnv (n'ayant pas les droits root) sauf lorsque cela est précisé.  

1. Utilisez la commande echo pour envoyer la ligne Quoi de plus joyeux dans le fichier sensamavie.txt.  
`echo "Quoi de plus joyeux" > sensamavie.txt`

1. Vérifiez ensuite le contenu du fichier en l'affichant à l'écran à l'aide de la commande more.  
`more sensamavie.txt`

1. Avec une autre redirection, placez à la suite de ce fichier la ligne que de travailler sous Linux ?.  
`echo "Quoi de plus joyeux" >> sensamavie.txt`


1. Vérifiez en l'affichant à l'écran qu'il contient bien les 2 lignes l'une à la suite de l'autre à l'aide de la commande cat.  
`cat sensamavie.txt`

1. Placez-vous dans le répertoire TP2.  
`cd TP2`

1. En utilisant la commande ls (sans option), créez un fichier usrlocal.txt contenant la liste des fichiers du répertoire /usr/local.  
`ls /usr/local/ > usrlocal.txt`

1. Avec la commande sort, triez ce fichier par ordre alphabétique inverse et mettez le résultat dans usrlocal-inverse.txt.  
`sort usrlocal.txt -r > userlocal-inverse.txt`

1. Depuis votre répertoire personnel, essayez de détruire par la commande rmdir (sans -r !) le répertoire TP2.

    a. Avec la redirection adéquate, récupérez le message d'erreur dans un fichier TP2/erreur.txt.  
    `rmdir TP2 2>> TP2/erreur.txt`

    b. Avec la redirection adéquate, arrangez-vous pour qu'aucun message d'erreur ne soit généré, ni à l'écran ni dans un fichier.  
    `rmdir TP2 2> /dev/null`

### Pipes (|)

1. Pour une première approche du pipe (|), utilisons la commande yes.

    a. Dans le répertoire de TP2/test créez 5 fichiers (fichier1.txt, fichier2.txt, fichier3.txt, fichier4.txt, fichier5.txt) que vous devrez ensuite tous supprimer en demandant confirmation à l'utilisateur.  
    `touch fichier1.txt fichier2.txt fichier3.txt fichier4.txt fichier5.txt`
    
    b. Afin d'éviter de devoir répondre par y à chaque suppression de fichier, utilisez la combinaison adéquate permettant d'envoyer cette réponse par la commande yes à la commande rm.  
    `yes y | rm -i *`.

1. A l'aide des commandes ls et head et d'un pipe (|), affichez à l'écran la liste des 15 premiers fichiers du répertoire /etc.  
`ls /etc | head -n 15`

1. A l'aide des commandes ls, tail et sort et de 2 pipes (|), mettez la liste inversée des 20 derniers fichiers du répertoire /etc dans un fichier etc-inverse.txt  
`ls /etc | tail -n 20 | sort -r > etc-inverse.txt` 

1. Trouvez une combinaison de commandes permettant d'afficher page par page les 100 dernières lignes retournées par la commande dmesg.
`dmesg | more`

1. Avec la commande grep, recherchez dans le fichier /etc/passwd les lignes contenant la chaîne bash.  
`cat /etc/passwd | grep bas`

1. Utilisez la commande find pour trouver tous les fichiers d'extension .conf du répertoire /etc.  
`find /etc/*.conf`

1. Avec l'éditeur nano, créez un fichier cherche-conf.sh et recopiez-y la commande de la question précédente.

    a. Exécutez ce script qui affichera dans un premier temps son résultat à l'écran.  
    `./cherche-conf.sh`

    b. Redirigez ensuite ce résultat dans un fichier liste-conf.txt  
    `./cherche-conf.sh > list-conf.txt`

    c. Arrangez-vous pour supprimer les messages d'erreur.  
    **De base on a pas les droits d'exécution sur le fichier, il suffit donc de se les ajouter: `chmod 700 cherche-conf.sh`**