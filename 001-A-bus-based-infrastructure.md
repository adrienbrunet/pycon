A bus-based infrastructure
==========================

__by Pierre Yves Chibon (pingou) - Fedora__

https://en.wikipedia.org/wiki/Enterprise_service_bus

Présentation d'un logiciel & d'une infrastructure.
Depuis 3 ans, infrastructure message bus

Pourquoi? --> Faire communiquer les applications entre elles

Coomunication

Initialement ils utilisaient
- cron
	Pour éviter trop de concurrence, le cron était décalé pour tout le monde mais ce n'était pas non plus suffisant.
- web-hooks, callbacks, shared DB

With a bus: push vs pull

Architecture v1
---------------

Fas   Bodhi   Koji   Pkgdb
 |      |       |      |
 v      v       v      v
 -----------------------
         Fedora
    |              |
    v              v

 Architecture v2
 ---------------

 Fas Bodhi Koji & PkgDB, chacune écoute les messages des autres

 fedmsg
 ------

 Work of ralph bean
 based on 0mq (fire and forget)
 python
 decentralized
 text or DNS based discovery
 GPG or x509 signatures


 Using fedmsg
 ------------

 Receiving/sending


 Using fedmsg in our infra
 -------------------------

 Action --> Reaction

 change your ssh key in the account system? --> Update hosts to get the new key
 Change group? Give/remove your access to some host
 Get/lose access to a git/package --> update gitolite to grant/remove permission
 New updates on the master mirror --> Update the mirror database for that part of the tree

 History of our action
----------------------

 Datanommer/Datagrepper
   per project/package
   per user

Possibilité de faire des graphes pour l'itilisation, nombre de message fait par utilisateur

Using fedmsg in our infra
-------------------------

Personalized notifications
  One central notification mechanism
  Create filter
  add rules to your filter
  choose your notification system
    Email - IRC


Pro / cons

pro: less cron, more flexibility, central, easy, extensible
Cons: Fire and forget: Kind of a myth for us, necessary? Fedora-infra/gilmsg, Require a change in your apps

Debian utilise ca et également data.gouv.fr (?) Enfin, à une époque en tout cas!

Contact: pingou@fedoraproject.org


Question:
