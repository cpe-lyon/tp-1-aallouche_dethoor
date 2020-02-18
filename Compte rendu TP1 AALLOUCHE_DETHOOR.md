# compte rendu TP1

## Manuel

1. La commande which permet d'afficher le chemin des fichiers qui s'execute lorsque on tape la commande que l'on a mis en argument.

2. man which | grep option

3. Taper "q" permet de sortir du man

4. man 6 which 

## arborscence des fichiers

1. cd /var/log/

2. Pour aller au repertoire parent --> cd ..

3. Pour aller au dossier personel --> cd ..

4. Pour aller au dossier precedent --> cd -

5. cd /root --> Permission denied

6. sudo cd /root --> On renseigne le mdp pour avoir accés au repertoire root. Sudo nous permet, malgré nos droits, d'acceder au /root

7. mkdir sert a créer des dossier. Touch pour créer des fichiers

8.9.10 avec rm on ne peut pas supprimer des dossiers. Pour supprimer un dossier --> rmdir. Lorsque on applique cette commande a Dossier2 il est supprimé (rmdir)

11. Pour supprimer recursivement Dossier2 et son contenu, on tape rm -r Dossier2

## Commandes importantes

1. date permet d'afficher l'heure. time permet de connaitre le temps que met une commande pour s'executer. time permet aussi d'evaluer cette commande 

2. Les fichier commancant par un point sont les fichiers cachés

3. which ls (/usr/bin/ls)

4. Il n'y a pas d'entrée de manuel pour ll. C'est un alias de ls -alF

5. ls /bin

6. ls .. affiche tous les fichiers du repertoire au dessus.

7.pwd permet de connaitre le chemin complet du dossier courant

8. echo 'yo' > plop crée un fichier plop qui contient 'yo'. Lorsqu'on l'execute deux fois il supprime l'ancien fichier et en re-crée un. Donc meme si on l'execute 2,5,100 fois il y aura toujours que une ligne 'yo'.

9.  echo 'yo' >> plop. Lorsqu'on execute cette commande plusieurs fois il réecrit 'yo' dans plop autant de fois qu'on execute la commande. Donc il y aura autant de 'yo' que de fois qu'on a executé la commande.
   
10. La commande 'file' permet de determiner la nature d'un fichier. "file plop --> ASCII text"

11. echo 'Hello Toto!' > toto 
ln toto titi --> raccourci toto vers titi
Lorsque je modifie toto, titi est automatiquement modifié. Supprimer l'original ne supprime pas la copie.

12. echo 'Hello Titi!' > titi
ln -s titi tutu --> raccourci titi vers tutu
Lorsque je modifie titi, tutu
est automatiquement modifié. Supprimer l'original ne supprime pas la copie.

13.

14.
Pour afficher les 15 dernieres lignes --> tail -n 15 /var/log/syslog
Pour afficher les 5 premieres lignes --> head -n 5 /var/log/syslog
Pour afficher les lignes 10 à 20 --> head -n 5 /var/log/syslog | tail -n 10 /var/log/syslog

15.
dmesg est une commande sur les systèmes d'exploitation de type Unix qui affiche la mémoire tampon de message du noyau less est une commande Unix permettant de visualiser un fichier texte page par page (sans le modifier). Sa fonction est similaire à la commande more, mais permet en plus de revenir en arrière ou de rechercher une chaîne. dmesg | less → affiche mem tampon, on peut aller en avant et en arriere page par page.

16.
/etc/passwd → fichier mdp user man passwd

17.
afficher 1ere colonne par ordre alphabétique inverse → sort -k1dr 

18.
cat /etc/passwd | awk -F: '{print $ 1}' → affiche les users

19.
apropos est une commande Unix qui permet de lister les manuels dont la description comprend les mots passés en arguments. apropos conversion

20.
find -name passwd → à la racine pour trouver touts les fichiers nommés passwd
 
21.
find -name passwd > ~/list_passwd_files.txt 2> /dev/null

22.
sort /home/js/.bashrc | grep ll → cherche ou est def alias ll

23.
locate .history → localise fichier history.log

24.
pour les fichiers récents il faut faire updatedb, puis on fait le locate.

## Découverte de l’éditeur de texte nano

F1 ou Ctrl + G Affichage de l’aide Ctrl + X Quitter nano / Fermer une fenêtre / Exécuter une commande Ctrl + R Ouvrir un fichier Ctrl + O Enregistrer sous Ctrl + S Enregistrer Ctrl + K Couper Ctrl + U Coller Ctrl + W Rechercher Ctrl + \ Remplacer Ctrl + C Afficher des informations sur la position du curseur (numéro de ligne, de colonne) Alt + U Annuler Alt + E Refaire

## Personnalisation du shell

1. Pour créer une copie du bash il suffit de faire cp .bashrc .bashrc_bak

2. Pour décommenter la ligne force_color_prompt=yes il faut :

    * nano .bashrc
    * enlever le # de force_color_prompt=yes
    * CTRL + x pour quitter
    * Y pour sauvegarder
    * Entrer pour valider

3. Le fichier .bashrc est lu au démarrage du shell ; pour le recharger, il faudrait donc se déconnecter puis se reconnecter ; mais il existe un autre moyen : la commande _source .bashrc _. L’invite de commande devrait immédiatement passer en couleurs.

4. Modifiez l’invite de commande pour qu’elle s’affiche sous la forme suivante :

    * nano .bashrc
    * remplacer la ligne par : PS1='${debian_chroot:+($debian_chroot)}\033[91m][\A] \033[00m]- [\033[01;32m]\u@\h[\033[00m]:[\033[01;36m]\w[\033[00m]$ '






