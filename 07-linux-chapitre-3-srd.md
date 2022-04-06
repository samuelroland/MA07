Ma-07 Samuel Roland - Exercices

## Chapitre 3
1. afficher la description courte des pages du manuel : `man -f ls`
1. chown SYNOPSIS avec les paramètres obligatoires pour exécuter la commande et quelles sont les options facultatives. : 
    ```bash
    chown [OPTION]... [OWNER][:[GROUP]] FILE...
    chown [OPTION]... --reference=RFILE FILE...
    ```
1. Commande `rm`:
    - a. Détruire un fichier sans confirmation : `rm -f test.txt`
    - b. Détruire un fichier avec confirmation : `rm -i test.txt`
    - c. Détruire toute une arborescence : `rm -r folder`
    - d. Voir les détails de la suppression (noms des fichiers): `rm -v file`
1. Quelques commandes d'aide:
    - a. `apropos kill` donne la liste des pages du manuel contenant le mot `kill` dans leur nom ou description
        ```bash
        pgrep (1)            - look up, signal, or wait for processes based on name and other at...
        choom (1)            - display and adjust OOM-killer score.
        kill (1)             - send a signal to a process
        killall5 (8)         - send a signal to all processes.
        pkill (1)            - look up, signal, or wait for processes based on name and other at...
        skill (1)            - send a signal or report process status
        systemd-rfkill (8)   - Load and save the RF kill switch state at boot and change
        systemd-rfkill.service (8) - Load and save the RF kill switch state at boot and change
        systemd-rfkill.socket (8) - Load and save the RF kill switch state at boot and change
        systemd.kill (5)     - Process killing procedure configuration
        yes (1)              - output a string repeatedly until killed
        ```
    - b. `whatis kill` donne la courte description du programme `kill`
        ```bash
        kill (1)             - send a signal to a process
        ```
    - c. `man kill` aide de `kill`
    - d. `man 2 kill` ne donne rien car `kill` ne se trouve pas dans la section 2
