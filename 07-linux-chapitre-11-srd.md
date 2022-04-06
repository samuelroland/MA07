Ma-07 Samuel Roland - Exercices

## Chapitre 11

**On a un client X et un serveur X. Tout est en local.**

Paquets installés
- `openbox-menu`: menu des fenêtres openbox (affichée lors du clic droit sur le bureau)
- `obconf`: configuration de openbox
- `xterm`: terminal
- ...


**Avant cette exercice, installer d'abord openBox:**
```shell
apt-get install x-window-system-core 
apt-get install xdm numlockx xterm xserver-xorg
apt-get install openbox
apt-get install openbox-menu obconf
shutdown -r now
```
---
1. Afin d'observer l'enchaînement des commandes sur une même ligne, tapez xterm ; xclock.

1. Pourquoi le programme xclock ne s'est-il pas lancé et à quel moment le fera-t-il ?  
**Le `;` permet de lancer des commandes l'une après l'autre, l'horloge est donc lancée une fois le terminal fermé**

1. La commande kill permet de tuer un processus en lui envoyant un signal.

    - a. Tapez man 7 signal pour afficher la liste des signaux disponibles pour kill

    - b. Retrouvez le numéro du signal de type KILL qui permet de tuer un processus.  
    **`SIGKILL` donc le numéro est `9`. Ce numéro peut être utilisé en suite pour arrêter le processus: `kill -S SIGKILL xclock` ou alors `kill -9 xclock`.**

1. Les commandes pgrep et pkill permettent de gérer les processus par leur nom.

    - a. Lancez deux commandes xeyes en tâches de fond.

    - b. Utilisez les options de pgrep pour récupérer les numéros et les noms de ces 2 processus.  
    `pgrep xeyes`

    - c. Utilisez la commande pkill pour tuer uniquement le plus vieux des deux.
    `pkill -o xeyes`

1. Lancez xterm

    - a. Connectez-vous ensuite dans la première Console Virtuelle par la séquence Ctrl-Alt-F1 puis repérez et tuez le processus xterm qui tourne votre environnement graphique.  
    `pkill xterm`

    - b. Retournez ensuite dans votre environnement graphique en tapant Crtl-Alt-F7.

1. Installer le paquet psmisc  
Ce paquet contient divers utilitaires qui utilisent le système de fichiers proc

    - fuser : identifie les processus utilisant des fichiers ou sockets.

    - killall : tue les processus par leur nom (ex « killall -HUP named »).

    - peekfd : affiche les données passant par un descripteur de fichier.

    - pstree : affiche un arbre des processus actifs.

    - prtstat : imprime le contenu de /proc//stat

1. Lancez une commande xterm puis placez-vous dans cette nouvelle fenêtre et lancer une nouvelle commande xclock.  

    - a. Avec la commande ps alx et le contenu de la colonne PPID, retrouvez le numéro du processus parent de votre nouvelle fenêtre xterm.  
    **Le PPID (Parent Process ID) indique 1197 c'est donc `openbox`**.

    - b. Retrouvez ce lien de parenté à l'aide de la commande pstree.
        
        ```
        └─xdm─┬─Xorg───5*[{Xorg}]
              └─xdm───openbox─┬─ssh-agent
                              └─xterm───bash───xclock
        ```

    - c. Tuez le processus parent. Que se passe-t-il ?  
    **Tous les enfants sont également arrêtés.**

1. Lancez 3 fois le programme xclock en tâche de fond.

    - a. Tuez les programme xclock en une seule fois avec la commande killall.  
    `killall xclock`

    - b. Quel est l'inconvénient de cette commande ?
    **Il n'y a pas de confirmation.**

1. Lancez xterm en tâche de fond et retrouvez son numéro de processus.

1. Déplacez-vous ensuite dans le répertoire /proc puis dans celui correspondant au numéro de processus trouvé.

    - a. Observez le contenu des fichiers status et environ.
    `Voir l'état et des informations sur le processus`

1. Lancez la commande top pour voir fonctionner l'ordonnanceur des tâches du système.

1. Affichez seulement ceux dont l'utilisateur cpnv est le propriétaire.  
`top -u cpnv`

1. Vérifiez l’espace RAM disponible par la commande free.  
`460820 ko`

1. Obtenez les informations sur votre processeur en affichant le contenu du fichier /proc/cpuinfo.

1. Dans la liste des processus de votre système, vérifiez que le serveur ssh tourne bien. Pour cela, utilisez une option de pgrep permettant de chercher le mot sshd sur toute la longueur de la ligne dans la liste des processus et une autre affichant les détails sur le processus.

    ```
    $ pgrep -a sshd
    1092 sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups
    1640 sshd: cpnv [priv]
    1646 sshd: cpnv@pts/0

    $ ps -fp $(pgrep -d, -x sshd)
    UID          PID    PPID  C STIME TTY          TIME CMD
    root        1092       1  0 08:43 ?        00:00:00 sshd: /usr/sbin/sshd -D [listener] 0 of
    root        1640    1092  0 08:58 ?        00:00:00 sshd: cpnv [priv]
    cpnv        1646    1640  0 08:58 ?        00:00:02 sshd: cpnv@pts/0
    ```

1. Dans le répertoire /etc/init.d, observez le contenu du script ssh permettant de lancer ce serveur et notamment les options pour l'arrêter ou le démarrer.  
**`start` et `stop` et `restart` (vue dans les différents cas du switch)**

1. A l'aide de ces options, arrêtez le serveur puis redémarrez-le en vérifiant que cela a marché par la liste des processus actifs ou en tentant d'y accéder par le client ssh.   
**`/etc/init.d/ssh stop` puis `/etc/init.d/ssh start`.**

1. Utilisez ensuite la commande service pour redémarrer le serveur ssh.  
**`service ssh start` (`service` agit juste comme un accès aux scripts du dossier `/etc/init.d`. Il suffit de mettre `service <servicename> <servicecommand>`).**

1. Installer le paquet sysv-rc-conf: `apt install sysv-rc-conf`

1. A l'aide de la commande sysv-rc-conf, vérifiez à quels niveaux de démarrage (RunLevel) cron peut être démarré.  
**Niveau 3-4-5.**

1. Utilisez la commande runlevel pour vérifier le niveau d’exécution auquel vous travaillez.  
**Level 5**

1. Passez en mode de maintenance mono-utilisateur (Runlevel 1).  
`export RUNLEVEL=1`

1. Dans la liste des processus de votre système, vérifiez le statut des serveurs ssh et cron.  
`service ssh status` et `service cron status`. (Ou alors `sytemctl status ssh` et `sytemctl status cron`).

1. Installer le paquet gnome-core et gdm3 et supprimer xdm  
`sudo apt install gnome-core gdm3` et `sudo apt remove xdm && sudo apt autoremove` 

1. Installer XRDP ( serveur RDP) pour se connecter depuis un client RDP® sur un serveur Linux
` sudo apt install xrdp`

1. Editez le fichier /etc/xrdp/startwm.sh

```shell
#!/bin/sh
if [ -r /etc/default/locale ]; then
. /etc/default/locale
export LANG LANGUAGE
fi
#. /etc/X11/Xsession
/usr/bin/openbox-session
```

**Seulement la dernière ligne est utile, il faut la rajouter à la fin du fichier.**