Software factory: Continous integraation and continuous deliverydeplyment, OpenStack style
==========================================================================================

by Fabien Boucher & Matthieu Huin
Freenode: #softwarefactory

softwarefactory-project.io


Menu:

état de l'art de l'intégrations continue, limitations et solutions d'openstack

State of the art:

dev --> controle de version --> CI, lance une batterie de test --feedback--> retour au dev ou deploiement

Avantge, accelere le temps de deploime t efficacité
Problem:

cost of automation, cost of dedicated CI infrastructure, how do you deal with rapid fire commits
it is possible to end up with a broken master temporarily

Openstack
---------

dev --> code review --> check tests --> dev review --> core dev review --> Gate tests --> version control

résout pas mal de problème, ca garantit que le master est sain

Software factory
----------------

Code review with gerrit
Gating with Zuul

gestion slave node

Nodepool (pour openstack)


Software factory, c'est une image qu'onp eut déployer sur du openstack et en qq minutes, let's go for CI CD
