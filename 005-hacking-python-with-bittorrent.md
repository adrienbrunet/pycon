Bokor: Distribution de film en bittorent et hacking python
==========================================================

Olivier André (zitune)

framework de distribution de films en bittorent
Sorcier vaudou
Libre GPLV3: https://github.com/bearstech/bokor
400 cinémas et 400 films

Ecrit par maurice Audin & Matthieu Lecarne ainsi que le speaker


Breastech:

scop
conseil
dev
infogérence

Cingego:
gestion de sortie de film ens alles
depuis 2014: Stock numérique (aka Bokor)


Projet commencé en 2012,
il fallait rattraper le code vite et bien
livraison de films par bittorent (inexistant)
Il fallait etre sur d'avoir un systeme evolutif

Ils ont fait un RPC

Liste de fonctionnalité inconnues
corrections à prevoir
Evoltions futures

Ajout facile de fonctions, proche du code vanilla, conseravtion des habitudes de python

Il pilote à distance des machines, si le code pète, il faut avoir prévu la gestion de l'exception



--
Workflow

- Réception d'un appel à une méthode
- Recherche de l'objet (executor) pour faire cette méthode
- Recherche de la méthode
- contrôle des arguments
- erreur ou execution

C'est un produit pour les cinémas --> ils sont sur des windows et cygwin pourrave ou des ubuntu bien vieux degeu

Utilisation de décoratuer sur les méthodes pour le register

décorateurs de classes également pour enregistrer les objets

Injection de class

