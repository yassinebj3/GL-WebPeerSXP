# webrtc-browser-interactive

Nous avons trois exemples :

- basic.html
- exemple1.html
- exemple2.html

Ces trois exemples illustrent le fonctionnement de la DHT kademlia sur WebRTC permettant la création d'un réseau P2P

# Fonctionner l'exemple

* Démarrez le serveur :

```sh
node examples/shared/server.js
```
* Consultez la première page pour le premier exemple :

http://localhost:8084/examples/webrtc-browser-interactive/basic.html

* Consultez la deuxième page pour le deuxième exemple :

http://localhost:8084/examples/webrtc-browser-interactive/exemple1.html

* Consultez la trosième page pour le troisième exemple :

http://localhost:8084/examples/webrtc-browser-interactive/exemple2.html

# Explication

Dans l'interface principale on aura 4 fonctionnalités principales :

- L'execution d'un noeud .
- La connexion avec un noeud afin de rejoindre le réseau.
- La recherche par clé .
- L'enregistrement des informations.

### Pour commencer :
Lancer deux noeud ou plus en ouvrant deux navigateurs différents
Connecter les Noeuds entre eux
A partir de là vous pouvez tester le fonctionnement et voir la console
