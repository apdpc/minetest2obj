# minetest2obj

Pour bénéficier de Minetest2Obj, vous devez disposer de [Minetest 0.4.13](https://github.com/minetest/minetest)

----

# Le principe de Minetest2Obj


Minetest2Obj est une combinaison de mods de jeu pour Minetest (0.4.13) permettant l'export de blocs vers un fichier .obj 


Il existe deux modes de jeux :
* **Plateau_v1.* ** > un monde pouvant représenter un plateau d'imprimante 3D (20cm x 20cm x 20cm). Dans ce mod de jeu, seuls les blocs mesecons (rouges) sont exportés.
* **Monde_v0.* ** > un monde vierge à construire. Dans ce mod de jeu tous les cubes (hormis les mesecons rouges) peuvent être exportés.

Il est vivement conseillé de dupliquer l'un des répertoires contenus dans worlds (`Plateau_v1.*` ou `Monde_v0.*`) à chaque nouvelle création ou chaque nouveau groupe.

L'export se fait désormais dans le jeu, donc à partir de n'importe quel terminal ayant lancé une partie avec l'un de ces mondes (pas besoin d'être admin).


----


# Installation


Cette combinaison de mods est désormais compatible avec tous les systèmes d'exploitation.

Télécharger et décompresser `Minetest2Obj_v0.5`, puis déplacer :
* le répertoire **imprim3d** dans le répertoire games (et, pour linux, donner les droits si nécessaire) ;
   * Windows: `minetest-install-path/mods`
   * OS X: `minetest.app/Contents/Resources/bin/mods`
   * GNU/Linux: `~/.minetest/mods`
* les répertoires `Plateau_v1.*` et `Monde_v0.*` dans le répertoire worlds (ce dossier sera à dupliquer pour chaque nouvel objet que vous voudrez modéliser) ;
* le fichier `minetest.conf` dans le répertoire minetest (ou .minetest).


----


# Utilisation


Administration
--------------

Un compte administrateur a été créé avec tous les privilèges 
(login : *admin* / mdp : *admin*).

Plus besoin de se mettre en mode créatif pour le monde Plateau : les joueurs ont chacun 1000 cubes rouges et des pioches pour éventuellement les casser (+ des éléments pour refaire le plateau : cubes bleus, verts, torches, ...).

En cas de besoin, l'admin peut donner des blocs supplémentaires avec la commande `/give`. Par exemple, pour donner 99 mesecons rouges à hihi :

    /give hihi mesecons_lightstone:lightstone_red_off 99


WorldEdit (world_edit)
----------------------

Ce mod permet d'ajouter (ou de supprimer) de grands ensembles de blocs très facilement avec une interface fonctionnelle.

[Pour + d'information, lire le tutoriel officiel](https://github.com/Uberi/Minetest-WorldEdit/blob/master/Tutorial.md)

Le nom des cubes rouges à rechercher dans l'interface est :

    red lightstone

Pour la suppression de blocs, après avoir sélectionner votre zone, il est recommandé d'utiliser le code suivant (les autres méthodes ayant tendance à bugger) :

    //replaceinverse air air



Prison (jail)
-------------

Avec ce mod, les joueurs au comportement peu sociable (destructions des constructions des autres, insultes, ...) peuvent être envoyés en prison par la commande `/jail`. Par exemple, pour envoyer grrr en prison :

    /jail grrr

Ils peuvent être libérés de la même manière avec `/release`.

 Dans *Plateau*, la prison se trouve dans le ciel au dessus du plateau.
 Dans *Monde*, la prison est à construire par l'administrateur.



Home (sethome)
--------------

Les 16 joueurs déjà créés (noms avec onomatopées) sont configurés pour avoir un point de départ. Ceci est très utile lorsqu'ils se sont perdus ou qu'ils sont tombés dans le vide (ou autre problème avec la carte).

Pour retourner à leur point de départ, il leur suffit de taper la commande :

    /home
*Attention : cette commande annule l'effet de la prison ! Mais rares sont les malins qui trouvent...*



Téléportation
-------------

Fonction de base de Minetest, cette commande peut être très utile pour l'administrateur. Elle permet notamment d'amener tout joueur à l'endroit voulu.

Par exemple, pour amener l'admin sur arf :

    /teleport admin arf
Ou pour téléporter arf aux coordonnées 120, 180, 90 :

    /teleport arf 120 180 90



Export en objet 3D (blockexport et exportblock)
-----------------------------------------------

Seul le joueur qui a lancé la partie (et qui a installé la combinaison de mods) peut exporter le plateau de jeu. On appelle ce joueur le ''serveur''.


* **Plateau : exporter des blocs Mesecons (rouges)**

> Rappel : dans ce mod de jeu, seuls les blocs mesecons rouges sont exportés vers le fichier .obj. Ce mod d'export demande des temps d'export plus longs, mais exporte tous les blocs mesecons rouges présents sur le plateau de jeu.

1. Une fois la construction achevée, le joueur *serveur* doit se rendre à sa position de départ (`/home` ou `/teleport 1 1 1`)
2. Tapez ensuite la commande :

    /blockexport
3. Le temps d'attente varie selon le nombre de cubes rouges présents sur le plateau.
4. Un fichier .obj sera créé dans le dossier du monde (`minetest/worlds/VOTREMONDE`).


* **Monde : exporter les blocs que vous souhaitez**

 > Rappel : dans ce mod de jeu, le bloc que vous aurez en main au moment de l'export sera exporté vers le fichier .obj. Attention les blocs mesecons rouges ne peuvent pas être exportés.

1. Une fois votre construction finie, placez vous le plus au centre de votre objet.
2. Gardez en main le bloc que vous souhaitez exporter (il détermine le type de blocs à exporter)
3. Indiquez la zone autour de vous que vous souhaitez exporter avec la commande [ /exportblock  longueur largeur hauteur  ] en blocs !  Par exemple, pour exporter la zone du 20 blocs autour du joueur :

    /exportblock 20 20 20
4. Contemplez l'avancement de l'export dans la ligne de tchat !
5. Récupérez le fichier .obj dans le repertoire du monde (minetest/worlds/VOTREMONDE) !



Noms des joueurs
----------------

Les 16 joueurs suivants sont déjà configurés :
* arf
* bing
* crac
* glagla
* grrr
* hein
* hihi
* miam
* ouaf
* oups
* plop
* plouf
* tictac
* tralala
* tsouin
* zut



----

Minetest2Obj utilise les éléments suivants :
- Minetest 0.4.13 > 
- WorldEdit > https://github.com/Uberi/Minetest-WorldEdit/
- jail > https://github.com/TheZenKitteh/minetest-jail
- home > https://github.com/xyzz/minetest-mods/tree/master/sethome
- **exportblock_v2** > https://github.com/julienrat/exportblock_v2
