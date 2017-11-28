webrtc-browser-interactive
==========================

Nous avons deux exemples : 
- exemple1.html
- exemple2.html 

Ces deux exemples illustrent le fonctionnement de la DHT kademlia sur WebRTC permettant la création d'un réseau P2P

## Fonctionner l'exemple

Démarrez le serveur : 

    node examples/shared/server.js

Consultez la première page poure le premier exemple : 
    http://localhost:8084/examples/webrtc-browser-interactive/exemple1.html
Consultez la première page poure le premier exemple : 

## Explication 

Dans l'interface principale on aura 4 fonctionnalités principales : 

* L'execution d'un noeud .
* La connexion avec un noeud afin de rejoindre le réseau.
* La recherche par clé .
* L'enregistrement des informations.

Pour commencer : 

* Lancer deux noeud ou plus en ouvrant deux navigateurs différents 
* Connecter les Noeuds entre eux

A partir de là vous pouvez tester le fonctionnement et voir la console 
