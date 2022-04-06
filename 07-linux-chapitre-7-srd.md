Ma-07 Samuel Roland - Exercices

## Chapitre 7

**Notes supplémentaires**:
- **Lors de l'affichage des propriétés d'un fichier avec `ls -l`, le nombre affiché juste après les droits correspond; si c'est un fichier, au nombre de liens durs sur le fichier, et si c'est un répertoire, au nombre de liens durs qui pointe sur le répertoire en question. Tout dossier a au minimum 2 liens durs car le `.` est un lien dur par défaut. Les sous-dossiers de ce dossier contiennent aussi le lien dur par défaut `..`. Au final, si on a un dossier contenant 3 sous-dossiers, on aura le nombre 5 pour notre dossier de base.**


**Exercices**:

1. Dans le répertoire src, créez les fichiers vides droits-octal et droits-symb dont les droits sont par défaut fixés à rw- r-- r--
**Les droits par défaut sont déjà 644, donc il suffit de créer les fichiers**: `touch droits-octal && touch droits-symb`

1. Avec la commande chmod, modifiez les droits de ces deux fichiers en parallèle en utilisant les valeurs en octal sur le fichier droits-octal et les lettres et symboles sur le fichier droits-symb de sorte qu'ils prennent successivement les valeurs ci-dessous :

    **Tableau des commandes, pour passer d'une étape à la suivante**:
    | Droits      | Octal | Symbolique          | Commande                                                          |
    |-------------|-------|---------------------|-------------------------------------------------------------------|
    | rw- -w- --- | 620   | g-r,g+w,o-r         | `chmod 620 droits-octal && chmod g-r,g+w,o-r droits-symb`         |
    | rwx -wx --x | 731   | u+x,g+x,o+x         | `chmod 731 droits-octal && chmod u+x,g+x,o+x droits-symb`         |
    | r-x -w- --x | 521   | u-w,g-x             | `chmod 521 droits-octal && chmod u-w,g-x droits-symb`             |
    | --x --x r-- | 114   | u-r,g-w,g+x,o-x,o+r | `chmod 114 droits-octal && chmod u-r,g-w,g+x,o-x,o+r droits-symb` |

1. Faites une copie du fichier droits-octal appelée droits-octal-copie.
`cp: impossible d'ouvrir 'droits-octal' en lecture: Permission non accordée`
1. Expliquez le problème rencontré et résolvez-le à l'aide de la commande chmod.
**On a pas les droits de lecture donc on pourra évidemment pas copier le contenu. Commande possible pour corriger ça: `chmod u+r droits-octal`.** 
1. Que constatez-vous au niveau des droits de la copie ?
**Ce sont les mêmes que l'original**.
1. Sur le répertoire src qui vous appartient, appliquez successivement les combinaisons de droits d'accès listées ci-dessous et à chaque fois essayez de :
    - a. Rentrer dans le répertoire src (cd ./src)
    - b. Lister le contenu détaillé du répertoire src en affichant les informations sur les fichiers (ls –l ./src)
    - c. Modifier (ouvrir, modifier puis enregistrer) avec nano le fichier src/prog2.c (nano src/prog2.c)
    - d. Supprimer (puis recréer si besoin) le fichier src/prog2.c (rm src/prog2.c)


    | Droits            | `cd ./src` | `ls –l ./src` | `nano src/prog2.c` | `rm src/prog2.c` |
    |-------------------|------------|---------------|--------------------|------------------|
    | 600 (rw-)         | NO         | NO/YES        | NO                 | NO               |
    | 500 (r-x)         | YES        | YES           | YES                | NO               |
    | 100 (--x)         | YES        | NO            | YES                | NO               |
    | 300 (-wx)         | YES        | NO            | YES                | YES              |
    | 700 (rwx)         | YES        | YES           | YES                | YES              |
    | **Droits requis** | x          | r (et x)      | x                  | w et x           |

    **Note: `ls –l ./src` sur un dossier en `600` donne un résultat mitigé où on a le nom des fichiers mais on ne peut pas voir les droits.**


1. A partir de ces résultats, retrouvez les règles générales sur l'accès aux répertoires.  
**Voir dernière colonne "Droits requis" du tableau précèdent.**

1. Connectez-vous en utilisateur root avec la commande su puis attribuez-vous (à root) le fichier prog3.for en utilisant la commande chown.  
`chown root prog3.for` 

1. Toujours en root, changez le groupe propriétaire de ce fichier pour qu'il appartienne au groupe mail.  
`chown :mail prog3.for`

1. Comment combiner les 2 dernières commandes en une seule ?  
`chown root:mail prog3.for`

1. Toujours connecté en utilisateur root, je désire :

    - a. Attribuer la sous-arborescence du répertoire src à l'utilisateur nobody et au groupe users  
    `chown nobody:users src/*`

1. Affichez la valeur par défaut du umask pour l'utilisateur cpnv. `umask` donne `0022`.

1. Passez en root et affichez la valeur de son umask. `umask` donne `0022`.

1. Que constatez-vous ? **C'est le même masque**.

1. Quelle unique valeur donner à la commande umask pour obtenir les droits ci-dessous à la création de (plusieurs réponses possibles!):
    ```
    nouveaux fichiers    :   rw- r-- --- 
    nouveaux répertoires :   rwx r-x ---
    ```
**Contrairement aux dossiers, les fichiers ne peuvent pas recevoir les droits `x` avec le `umask` mais les dossiers oui. La commande est donc: `umask 027`.**
