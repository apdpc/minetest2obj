Exporter les Mesecons Rouges
================

A partir du poste servant de serveur, lancer le jeu sur le monde voulu, puis taper les commandes
/teleport 1 1 1
et
/blockexport

La commande exporte une zone de 200x100x200 cubes à partir de votre position : vos coordonnees + 200 (ou 100).

Le temps de traitement depend du nombre de cubes sur le plateau. Pour savoir si le programme a fini de travailler, vous pouvez taper une autre commande (par : /time 3000); elle ne s'effectuera que si le programme d'export a fini de travailler.

Un fichier .obj est cree dans le dossier du monde (il peut facilement etre ouvert avec Cura), sous la forme :
"redmesecons2obj_<bx>-<by>-<bz>.obj"
(ou <bx>, <by>, et <bz>  sont vos coordonnees)



Pour + d'infos sur le mod, lire le README.txt
