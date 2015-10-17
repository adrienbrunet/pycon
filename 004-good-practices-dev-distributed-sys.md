Bonnes pratiques pour le dévelloppment d'un système distribué et à la carte
===========================================================================

Développeur Canopsis - Eric Regnier - entreprise: Capensis

Distribué: on peut répartir les composants sur diffénretes machines et à la carte car on peut choisir quelle composantes sys sont nécessaires

Contexte et probleme
--------------------

Beaucoup de terminaux (serveurs, ordi, camera), ces infos sont hétérogènes, elles fournissent des données différentes remontés par des superviseurs (ex: Nagios, SHinken, Centreon, Icinga)

Solution
--------
Canopsis, supervision opensource, centralise l'info et peut produire des rapports d'activité

600 events/sec, 180 000 points de contrôles en 5 min (20k serveurs)

Archi:

Entrants ----> chaine de traintement ----> Restitution
                      ^                        ^
                      | 					   |
                      v 					   v
                Architecture python <--------->BDD

Connecteurs (normalisation des données), github, facebook, source de données

Bus de canopsis, via rabbitmq

Chaine de traintement, un bus amqp
Chaque moteur qui traite un evenement le renvoie dans une queue
On peut chainer les moteurs qui peuvent publier dans plusieurs queue différente (paralleilisation)

Ca permet de distribuer des calculs python

Rapidement, le moteur, fait partie du domaine de la supervision, automatiser la surveillance, prendre en charge des incidents qui peuvent survenir

On peut rajouter, suppr des moteurs

Traitemetn métier:

Engine
  ^
  |
  v
Manager <---> Configubale
(not enough time to write it up)

Configurable <--- Middleware <-- Storage <---- ??

Couche logicielles distribuées



Perspectives
------------

Les shémas:
- générer une partie du métier
- faire de la validation de données
- améliorer la fiabilité du système

Intelligence
- auto supervision et retro action intelligente
- analyse prédictive d'entrants


