Ma-07 Samuel Roland - Exercices

## Chapitre 6
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

1. Placez-vous dans le répertoire INCLUDE. A l'aide de la commande ln, faites un lien physique appelé lien-solide-prog3 vers le fichier src/prog3.for avec un chemin relatif.  
` ln ../src/prog3.for lien-solid-prog3`

1. Pratiquez de même avec un lien symbolique appelé lien-symb-prog3.  
`ln -s ../src/prog3.for lien-symb-prog3`

1. Que constatez-vous pour les droits de ces liens et leur numéro d'inode ?

    **Récupérons déjà ces valeurs:**
    ```bash
    261159 -rw-r--r-- 2 cpnv cpnv  0 10 fév 10:09 lien-solid-prog3
    261169 lrwxrwxrwx 1 cpnv cpnv 16 15 fév 09:02 lien-symb-prog3 -> ../src/prog3.for
    ```

    et

    ```bash
    261159 -rw-r--r-- 2 cpnv cpnv 0 10 fév 10:09 ../src/prog3.for
    ```

    **Le lien solide a la même inode que le fichier source, contrairement au lien dur. Le lien solide garde les même droits, puisque les 2 fichiers pointent sur la même inode. Tandis que le lien symbolique a tous les droits sur le lien (mais ses droits n'ont pas de lien avec les droits sur le fichier de base puisque ce n'est pas la même inode)**.

    ```
    Avoir en tête:
    Symbolic link: Fichier2 --> Fichier1 --> Inode
    Hard link: Fichier1 --> Inode <-- Fichier2`
    ```

1. Que se passera-t-il si vous détruisez le fichier destination de ces liens ?
**Le liens durs n'auront pas de problème, mais les liens symboliques seront cassés et inutilisables.**

1. Toujours dans INCLUDE, créez un lien symbolique appelé lien-rep-src vers le répertoire src en utilisant le chemin absolu.
`ln -s ../src lien-solid-prog3`

    - a. Utilisez ensuite ce lien pour vous déplacer dans le répertoire src.  
    `cd lien-rep-src`  

    - b. Faites un help pwd pour utiliser les deux options possibles de cette commande et vérifier l'existence du lien.  
    `pwd -P`

    - c. Remontez à présent dans le répertoire parent.
    `cd ..`

    - d. Où vous retrouvez-vous ?  
    dans `~/TP1/progs/INCLUDE` 
