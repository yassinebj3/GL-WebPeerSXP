# Projet WebPeerSXP

# Contenus de wiki :
- Introduction
- Listes des projets testés (Installations)
- Principe de kademlia
- Projet kad-webrtc
- Architecture 
- Manuel d’utilisation
- Guide du code
- Points techniques
- Tests et robustesse
- Evolutions
- Amélioration de l’interface graphique
- Explication de l’exemple 2
- Todolist
- Conseils

# [Wiki WebPeerSXP](https://github.com/yassinebj3/GL-WebPeerSXP/wiki/Projet-WebPeerSXP)

# Introduction : 
Après une études des multiples projets WebRTC nous avons choisi l’application javascript “WebRTC kademlia”, pour la simple et bonne raison que c’est le projet le plus avancé, le plus simple à utiliser et qui comporte le moins de bugs par rapport aux autres. Ce logiciel va permettre de simuler des connexion pair à pair WebRTC en local. Le projet kad-webrtc a été implémenté par [omphalos](https://github.com/omphalos)  il est possible de le contacter par la page du lien du projet.Ainsi kad-webrtc est le noyau de notre projet WebPeerSXP.

### [kad-webrtc](https://github.com/kadtools/kad-webrtc) 



# Projet WebPeerSXP : 
WebPeerSXP est un projet qui implémente une DHT en utilisant l'algorithme kademlia et qui se base sur WebRTC qui assure une connexion peer2peer entre deux navigateurs.
le projet offre la possibilité comprendre le mécanisme des DHT et manipuler des objets dans un réseaux P2P. 
Ce projet présente essentiellement des explications sur le projet [kad-webrtc](https://github.com/kadtools/kad-webrtc) et implémente quelques exemples afin d'améliorer un peu le fonctionnement de [kad-webrtc](https://github.com/kadtools/kad-webrtc) .

WebPeerSXP a pour objectif d'intégrer WebRTC dans le projet [SXP](https://github.com/pja35/SXP). 

### L'installation du projet « WebPeerSXP » : 
L’installation du projet se fait via la commande :
```sh
npm install --global 
/* En cas d'erreurs */
npm install hat && npm install kad && npm install simple-peer
```
Pour exécuter les exemples tapez : 
```sh
npm run build-examples 
```

### Fonctionner un exemple

Démarrez le serveur :
```sh
node examples/shared/server.js
```

Le serveur sera lancé sur le port 8084 (Si vous avez déjà un autre serveur exécuté sur le port 8084 , vous devez le fermer ou bien changer le port du server.js) . 
Tapez l’URL de l’exemple, ouvrez plusieurs onglets et essayez de connecter les clients entre eux.
Vous pouvez regarder la console pour savoir le fonctionnement du projet.

Consultez la page basic du projet [kad-webrtc](https://github.com/kadtools/kad-webrtc)

- http://localhost:8084/examples/webrtc-browser-interactive/basic.html

Consultez la première page pour le premier exemple :

- http://localhost:8084/examples/webrtc-browser-interactive/exemple1.html

Consultez la deuxième page pour le deuxième exemple :

- http://localhost:8084/examples/webrtc-browser-interactive/exemple2.html

### TODO List : 
- S'assurer de l'unicité des noeuds 
- trouver un mécanisme d'invitation pour se connecter au réseaux
- Essaye de corriger le maximum d'erreurs 
- trouver un mécanisme efficace pour la recherche multicritère 
- Intégration du projet dans SXP 

### Conseils : 
- Avant d'entrer dans les détails de l'implémentation , comprenez bien le mécanisme de   WebRTC / Peer2Peer / DHT / Kademlia / Chord
- faire une recherche sur les nouveaux projets qui ne figurent pas dans la liste 
- tester le projet kad-webrtc 
- bien comprendre les erreurs et les analyser 
- faire des tests boites noires 
- bien lire notre documentation et l'affiné :) 
- Commencer par concevoir des solutions qui minimisent les erreurs. 






