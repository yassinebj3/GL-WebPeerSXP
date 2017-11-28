# Projet WebPeerSXP
# Table des matières :
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

# Introduction : 
Après une études des multiples projets WebRTC nous avons choisi l’application javascript “WebRTC kademlia”, pour la simple et bonne raison que c’est le projet le plus avancé, le plus simple à utiliser et qui comporte le moins de bugs par rapport aux autres. Ce logiciel va permettre de simuler des connexion pair à pair WebRTC en local. Ce projet a été implémenté par https://github.com/omphalos  il est possible de le contacter par la page du lien du projet.
https://github.com/kadtools/kad-webrtc 


# Listes des projets testés : 
https://github.com/kadtools/kad-webrtc 
https://github.com/louismullie/kademlia-webrtc
https://github.com/timsuchanek/webrtc-kademlia
https://github.com/diasdavid/webrtc-explorer
https://github.com/tsujio/webrtc-chord
Après l’installation et le test des projets, nous avons deux projets qui marchent : « Kad-webrtc » et « Webrtc-explorer ».
### Projet « kad-webrtc » : 
L’installation du projet se fait via la commande :
```sh
npm install --global 
```
Pour exécuter les exemples tapez : 
```sh
npm run build-examples 
```
Afin de manipuler les exemples, il faut lancer un serveur qui se trouve au chemin suivant :
examples/shared 
Exécuter la commande : 
```sh
node server.js 
```
Le serveur sera lancé sur le port 8080 (Si vous avez déjà un autre serveur exécuté sur le port 8080 , vous devez le fermer ou bien changer le port du server.js) . 
Tapez l’URL de l’exemple, ouvrez plusieurs onglets et essayez de connecter les clients entre eux.
Vous pouvez regarder la console pour savoir le fonctionnement de kad-webrtc. 

### Projet « WebRTC-explorer » : 
Vous pouvez regarder ce Tutoriel afin de savoir comment installer « WebRTC-explorer » 
https://www.youtube.com/watch?v=kjwIjoENCRE
Nous avons essayé à plusieurs reprises d’installer la dernière version de « WebRTC-explorer » et la tester en utilisant browserify , serveur node.js et en utilisant le serveur Sig-server.
https://github.com/diasdavid/webrtc-explorer-signalling-server
Alors nous avons essayé d’installer la version https://github.com/diasdavid/webrtc-explorer/releases/tag/v1.1.1 qui correspond au tutoriel mentionné ci-dessus.
Afin d’installer cette version de WebRTC-explorer il faut installer : 
https://github.com/diasdavid/webrtc-explorer-signalling-server
Exécuter le serveur en utilisant la commande :
```sh
npm start 
```
En cas d’erreurs liées à l’absence de quelques modules, exécutez les commandes suivantes :
```sh
npm install hapi 
npm install socket.io
npm install config 
npm install dht-id 
```
Après le lancement de serveur, installez la version v.1.1.1 de webRTC-explorer : 
```sh
npm install --global
```
Lancez le serveur :
```sh
node examples/try-it-out/server.js
```
En cas d’erreurs, installez :
```sh
npm install hapi
npm install moonboots_hapi
```
Vous pouvez voir le comportement en ouvrant plusieurs onglets et en ouvrant la console. Vous remarquez aussi l’ajout des nœuds dans la console du serveur sig-server.
Afin de mieux comprendre le fonctionnement de DHT Chort
Vous pouvez visualiser les pairs en installant le projet « WebRTC-explorer-visualizer » 
https://github.com/diasdavid/webrtc-explorer-visualizer
En cas de problème d’exécution, installez les modules manquants :
```sh
npm install node-sass
npm install dht-id 
/* Remarque : Il nécessite la version « hapi 8.8.1 » */ 
npm install hapi@8.8.1
npm install domready
npm install xhr
npm install config
npm install jade
```
### Projet webrtc-chord : 
Après l’installation de webrtc-chord, nous avons constaté un problème dans le module « connectionpool »
```sh
> webrtc-chord@1.0.0 build C:\Wiki\webrtc-chord-master
> browserify --standalone Chord . | uglifyjs > dist/webrtc-chord.js
```

```sh
Error: module "connectionpool" not found from "\\webrtc-chord-master\\src\\NodeFactory.js"
    at notFound (\webrtc-chord-master\node_modules\browserify\index.js:812:15)
    at \webrtc-chord-master\node_modules\browserify\index.js:762:23
    at \webrtc-chord-master\node_modules\browser-resolve\index.js:265:24
    at \webrtc-chord-master\node_modules\browser-resolve\node_modules\resolve\lib\async.js:55:18
    at load (\webrtc-chord-master\node_modules\browser-resolve\node_modules\resolve\lib\async.js:69:43)
    at onex (\webrtc-chord-master\node_modules\browser-resolve\node_modules\resolve\lib\async.js:92:31)
    at \webrtc-chord-master\node_modules\browser-resolve\node_modules\resolve\lib\async.js:22:47
    at FSReqWrap.oncomplete (fs.js:123:15)
(node:12876) DeprecationWarning: util.print is deprecated. Use console.log instead.
```
### Projet « kademlia-webrtc » : 
Problème d’installation dû à l’absence de fichier « package.json »

### Projet « webrtc-kademlia » 
Après l’installation d’un serveur PeerJS et l'exécuter suivant les démarches décrites dans le projet.
https://github.com/timsuchanek/peerjs-server.git
Nous avons installé le projet : 
```sh
npm install --global
```
Exécutez 
```sh
npm start
```
Après l’installation des modules manquants en cas d’erreurs : 
```sh
npm install serve-static
npm install finalhandler
```
Suite à l’ouverture de l’adresse « localhost:8000 » pour voir le démo.  La page affiche « Cannot Get » et absence d’informations dans la console.
Nous avons essayé aussi de lancer le projet avec le serveur « Apache » de « WampServer ».
Nous avons eu un affichage de la page « index.html » mais le navigateur ne récupère pas les informations nécessaires afin d’établir la connexion entre deux pairs.

### Projet Open Peer :  
https://github.com/hookflash/obsolete.opjs  
nous avons essayé d’installer Open Peer , en exécutant les commandes décrites ci-dessous mais sans succès : 
```sh
npm install --global 
/* Nous avons exécuté dans le répertoire /dev la commande ci-dessous */
node server.js
/* Nous avons installé les modules manquants : */ 
npm install express
npm install hbs
npm install glob
npm install fs-extra
npm install marked
npm install waitfor
npm install request
```
à l'exécution node server, plusieurs liens de CDN ne marchent plus nous avons donc essayé de trouver des nouvelles versions : 
https://cdnjs.cloudflare.com/ajax/libs/require.js/2.3.5/require.min.js 
Ainsi plusieurs modules ne sont plus à jour :
- webrtc-shim
- rolodex 

# Principe de Kademlia : 
Kademlia(alias Kad) est un réseau de recouvrement créé pour décentraliser les autres réseaux
d'échange de fichiers Peer-to-Peer. Le protocole précise la structure du réseau Kademlia, les
communications entre les noeuds et l'échange d'information. Les noeuds communiquent grâce au
protocole UDP.
Nous vous conseillons de lire en détails le fonctionnement de kademlia dans l’annexe 
Kademlia.pdf

# Projet kad-webrtc : 
kad-webrtc est un projet qui implémente une DHT en utilisant l'algorithme kademlia et qui se base sur WebRTC qui assure une connexion peer2peer entre deux navigateurs.
le projet offre la possibilité comprendre le mécanisme des DHT et manipuler des objets dans un réseaux P2P 


# Architecture : 
le pair à pair est modèle de réseau informatique qui peut avoir une architecture centralisée ou bien 
décentralisée . Dans notre projet , nous avons utilisé une architecture où chaque noeud du réseaux se comporte comme un client et serveur à la fois. Dans notre cas il y’a absence total des structures partagés et centralisés (base de données , serveur , noeud central) . 

image 

Le projet kad-utilise le framework node.js qui utilise javascript dans un serveur HTTP et qui permet de manipuler plusieurs modules. 


And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

# Manuel d’utilisation : 
Avant de faire des tests, nous allons voir comment fonctionne le projet.
Pour lancer le projet, il suffit de lancer la partie serveur qui se trouve dans le dossier kad-webrtc-master/examples/shared/. Nous l’avons fait tourner sur NodeJS, se mettre dans le bon répertoire et utiliser la commande “node serveur.js”. 
Puis il suffit d’ouvrir dans un browser l’index du projet (kad-webrtc-master/examples/webrtc-browser-interactive/index.html).

Nous tombons alors sur l’interface suivante:
Comment cela fonctionne t-il?
“This Node” permet de créer un noeud dont l’id sera le nom donné.
“Connect to node” permet de faire un lien entre le noeud que l’on a créé préalablement et un autre noeud.
“Get” permet de définir si un élément est récupérable.
“Put” création d’un couple (clé,valeur) dans le noeud créé. La clé va servir à aller chercher la valeur de la donnée stockée dans le noeud.
Dans un premier temps, nous allons utiliser le programme pour fabriquer trois noeuds connectés entre eux de cette manière:

1. Première étape:
Créer les trois noeuds en ouvrant trois onglets de navigateur. Il est possible d'inspecter la page pour voir si la création du noeud a bien fonctionné . 
2. Deuxième étape:
Faire la connexion des noeuds dans le premier et second navigateur. Si la connexion réussit, une petite fenêtre apparaîtra avec comme message:


Le but de ce premier test est de voir si un objet stocké dans Noeud 1 est visible par Noeud 3 en passant par Noeud 2.
D’abord, pour vérifier que la connexion entre les Noeuds a bien été établie, on va stocker dans le Noeud 2 un couple (1,Pomme) grâce à la commande Put:

La commande ‘put’ faite dans le browser Node 2, un message de réussite s’affiche:


Puis on essaye d’y accéder en utilisant la commande GET:

Dans les browsers contenant les Noeuds 1 et 3. On devrait alors tomber sur une fenêtre:

Il existe donc bien une connexion (Noeud 1, Noeud 2) et (Noeud 2, Noeud 3).

De la même manière que précédemment nous allons stocker des “abricots” dans Node 1 avec la clé “2” et des “mandarines” dans Node 3 avec la clé “c”. On stocke avec “Put” et récupère les éléments avec Get.

Il est bien sur possible de créer plus de connexion mais il faut faire attention à ne pas surcharger le serveur.

# Guide du code : 

On va tout d’abord télécharger le projet de Kad-WebRTC sur git, sur le fichier, ce qui nous intéresse est dans le fichier “examples”.
On va commencer par la page html principal se trouvant dans le dossier “webrtc-browser-interactive”, si on consulte le fichier “index.html”, on trouve du code html basique interprétant la page principal, rien d’extraordinaire pour le moment.
Une fois sur la page, on rentre notre propre ID, on appuie sur “Launch Node”, ce qui va appeler une fonction dans le fichier “index.browser.js”:
```sh
“document.querySelector('#node').addEventListener('submit', function (e) {...}):” 
```
Cela en gros attribuera un identifiant avec lequel la connection se fera au serveur. Quelques instructions qui expliquent ça:
```sh
“var element = document.querySelector('#node input[name=id]');
  var id_string = element.value;”
```
Cette instruction récupère l'élément dont l’ID est “node” qui contient un “input” dont le “name=id” dans le fichier “index.html”, qui par la suite sera stockée dans la variable “id_string”.
L’identifiant est attribué en fonction du ‘input’ crypté en SHA1. 
```sh
“webSocket.on('open', function() {...}):”
```
cette fonction permet de créer un noeud (qui sera nous), puis de se connecter avec notre ID.

Ensuite on insère identifiant d’un autre pair afin de se connecter à lui, et on appuie sur “connect”, cette action déclenche une fonction sur le fichier “index.browser.js”:
```sh
document.querySelector('#connect').addEventListener('submit', function (e) {..};
```
Elle récupère ce qui a été écrit dans le “input”:
```sh
var element = document.querySelector('#connect input[name=id]');
var id_string = element.value;
```
 puis une fonction se charge de se connecter au pair désiré avec “node.connect” avec “id_string” .

Pour rechercher une clé dans le réseau, on insère la clé à rechercher et appuie sur le bouton, cela déclenche dans le fichier “index.browser.js”:
```sh
document.querySelector('#get').addEventListener('submit', function (e) {..}
```
Ceci permettra de faire une recherche de ce qui a été écrit.
Récupérer le “input” comme précédemment, en changeant seulement l’identifiant de l'élément:
```sh
var element = document.querySelector('#get input[name=key]');
var key_string = element.value;
```
Puis la fonction “node.get” se charge de faire une recherche sur les pairs où il est connecté, si il ne trouve chez eux, ces derniers feront la même chose, c’est à dire qu’ils feront la recherche sur les pairs où ils sont connecté, ainsi de suite.
Si aucun des pairs n’a trouvé la clé recherchée, un message d’erreur sera envoyé pour dire que cette clé n’existe pas.
```sh
document.querySelector('#put').addEventListener('submit', function (e) {..}
```
Pour ajouter du contenu, on doit insérer une clé et sa valeur, une fois qu’on appuie sur “PUT”, la fonction cité en dessus sera déclenchée, elle prend les paramètres comme ceci:
```sh
var element;
element = document.querySelector('#put input[name=key]');
var key_string = element.value;
element = document.querySelector('#put input[name=value]');
var value_string = element.value;”
```
Les variables “key_string” et “value_string” prennent respectivement la clé et la la valeur inséré, puis la fonction “node.put” se chargera de sauvegarder ses informations.

Maintenant dans le dossier “shared”, qui contient le code du serveur, qui permet d’établir la connexion, on  ouvre le fichier “server.js”, ce fichier représente “la centrale” du WebRTC, car sur ce dernier, on va régler les paramètres d’authentification via un identifiant, de recherche, et d’établissement de connexion, d’écoute sur un certain port.
On passe alors à la compréhension du code:
Le fichier commence par l'instruction “'use strict';” qui facilite l'écriture de JavaScript "sécurisé".

Le fichier se suit par la création de variables “ http, path,,fs, EventEmitter, signaller, WebSocketServer, port, server, ws ” qui nous servirons sur la création d’un port d’écoute, et l’établissement de la connexion entre 2 pairs.
```sh
var http = require('http');
```
cette instruction permet de créer un serveur HTTP afin d’écouter les ports du serveur et renvoyer une réponse au client.
```sh
var path = require('path'); 
```
Permet de travailler avec les différents chemins de chemins de fichiers.
```sh
var fs = require('fs');
```
Cela nous permettra de travailler avec des fichiers notamment la lecture.
```sh
var EventEmitter = require('events').EventEmitter;
```
Permet de créer et de visualiser chaque événement, qui se traduit par les actions effectué sur l’ordinateur.
```sh
“var signaller = new EventEmitter();”
```
 Est une instance de l’objet “EventEmitter”.
```sh
var WebSocketServer = require('ws').Server;
```
Afin de créer une instance de websocket.
```sh
var server = require('http').createServer().listen(port); 
```
La variable contiendra le serveur http avec le numéro de port “port” (qui est une variable qui contient le port, 8080 ou 8082…).
```sh
ws.on('connection', function(connection) { … } );
```
On envoie à travers la connexion WebSocket un message “connection” et un émetteur d’événement par une fonction “function”, qui elle même procède à certain traitements. 
```sh
server.on('request', function(req, res) {..});
```
# Tests et robustesse : 
Créer plusieur noeud dans un seul browser que ce passe-t-il?

Interprétation. Qu’est ce que ça signifie? Bonne question mes amis.

Stockage d’élément sur une même clé:
On va mettre en évidence le fait que l’on peut écraser des éléments stockés à tout moment avec n’importe quel utilisateur.
Pour cela on repart sur l’exemple simple suivant:

On se demande ce qu’il se passe lorsque je stocke un élément dans le Noeud 1 et que je réécrit un autre élément avec la même clé.
Dans Node 1 on stock (1,”patates”), puis on stock un deuxième objet (1,”tomates”). Du point de vue de tous les utilisateurs, seul le dernier élément entré est visible. Ce qui veut dire qu’on ne peut plus accéder à des “patates” sur Noeud 1.
Mais le problème ne s’arrête pas là, si l’on stock (1,”salade”) dans le Node 3, dans ce cas “tomates” sera remplacé par “salade” et sera accessible par Node 3.
Imaginons que les éléments stockées sont des fichier à télécharger, dans ce cas cela voudrait dire que pendant que quelqu’un télécharge un fichier on peut l’arrêter en remplaçant ce fichier par un autre avec la même clé.

Connecter un Noeud à lui même :
Pour tester si le programme est intelligent, nous allons connecter un Noeud à lui même. Ce qui est inutile puisque nous avons directement accès à ce qui est sur notre ordinateur.

Il est effectivement possible de créer une connexion sur un même utilisateur. Le problème c’est que le programme fait le chemin de connexion qui existe entre tous à partir de notre noeud et définis si ce chemin existe déjà. 
Maintenant si on imagine qu’il existe des millier d’utilisateurs, cela voudra dire que si l’on essaye de connecter un nouveau PC il faudra reconstruire la quasi totalité de la structure et non pas seulement lui dire “Ton voisin c’est lui”.
De plus refaire la connexion entre deux noeuds est inutile. Et bien avec ce programme c’est aussi possible, ce qui veut dire que l’on va revérifier tous les chemins possible entre deux Noeuds qui sont déjà connectés ensemble.


Stockage d’un même élément mais avec une clé différente:
On reprend pour la nième fois le premier exemple vu. On va stocker dans Noeud 1 un élément (1,”kebab”) et dans Noeud 3 (4,”kebab”). Cela marche bien et ne pose pas vraiment de problème, il y aura juste deux moyens d’arriver à une même solution. Ce qui n’est pas vraiment gênant.

Essayer de récupérer un élément inexistant :
Pour cela on va rentrer dans la fonction Get une valeur de clé inexistante.

Ce cas de figure est pris en compte par le système. Si une clé n’est utilisée par aucun des utilisateurs sur lesquels on est connecté, une erreur est retournée.

Insérer des valeurs sans clé :
Il est possible de stocker des éléments sans clé. Dans ce cas la clé de l’élément est compté comme “NULL” et pour le récupérer il ne faudra rien mettre dans partie “Get” de notre page html.


Créer deux noeuds du même nom:
Il est possible de créer deux Noeuds ayant le même nom mais il ne pourront jamais être connectées ensemble. Lorsque l'on crée un Noeud “Test” en double et que l’on essaye de le connecter à un Noeud déjà existant il se passe:

Impossible de faire la connexion avec le noeud “Test”. Il est possible de rajouter des chose dans “Test” mais il ne seront pas visible sur le réseau créé par les noeuds.
Le problème est si l’on crée un Noeud qui existe déjà on risque de couper toute les connexion à ce noeud. 
Pour cela on va faire un deuxième noeud “Test2” qui sera reliée aux Noeuds 1,2. Puis on va faire un deuxième noeud “Test2” puis on va tester si la connexion entre le premier “Test2” et les trois noeud est altérée.
Donc dans un premier temps no connexion ressemble à ça:

On met l’élément (test,courge) dans le noeud “Test2”. “courge” est donc accessible à partir de tous les noeuds. Maintenant on rajoute un deuxième noeud avec comme nom “Test2”:

On vient de parasité la connexion avec “Test2”. Il est toujours possible de connecter d’autre noeud a “Noeud 1” ou “Noeud 2” mais pas à “Test2”. De plus tous les éléments rajouté dans le “Test2” connecter ne sera pas visible. Seul les éléments déjà stockés au préalable seront accessible. Il sera préférable de limiter les nom données aux noeud.

Rafraîchissement ou fermeture d’une page:
La question que l’on se pose ici est qu’est ce qu’il ce si l’on crée un noeud et que l’on rafraîchit ou ferme la page.


Test de robustesse:

Apply marche en ligne?
L’application ne peut pas marcher en ligne puisqu’elle n’utilise pas de serveur TURN qui va réaliser le lien entre deux utilisateur. Cependant elle permet de faire une simulation de gestion P2P d’une apply.


Marche avec n’importe quel browser?
Nous allons vérifier si le programme peut tourner dans différents types de browser. La connexion WebRTC ce faisant directement par les navigateurs, il est important de savoir sur quel browser il est possible de créer une connexion.

| Browser | Connexion |
| ------ | ------ |
|Firefox| Oui|
|Chrome| Oui |
| IE |Non |

Nous ne pouvons pas utiliser le projet sur le navigateur InternetExplorer. Il est possible de continuer les test sur d’autre browser. Attention la version de certain navigateur peut empêcher une connexion WebRTC.

### Communication entre browser différent:
La communication entre les browsers est faisable. Il y a la possibilité de connecter des Noeuds créé sur Chrome à d’autre fait sur Firefox. Le réseau ainsi fait marche normalement aucun changement n’est notable.

# Evolutions : 
Pour permettre au projet de devenir un peu plus fiable et robuste nous avons choisi 2 améliorations possible:
Réglage du problème de Nom des clients
Recherche multicritère
Donc dans un premier il serait préférable de régler le fait que deux clients peuvent avoir le même nom.
Puis faire une recherche sur plusieur critère c’est à dire qu'une personne qui vend des ingrédients à un nom un adresse etc… Donc il serait possible qu’un client trouve ce qu’il souhaite à partir d’une adresse. Prenons un exemple:

Ici nous avons stocké un objet “Studio” à “Marseille”, la recherche par clé se fera par plusieur critère, le lieu et le type de logement. Il y a plusieurs manière d’implémenter le principe de multicritère.

# Amélioration de la GUI :
Sur le manuel d’utilisation expliqué plus haut, nous avons vu une page html avec une interface graphique basique, nous avons alors décidé de rendre cette dernière plus agréable à voir et plus chaleureuse.
Pour cela, nous avons utilisé bootstrap sur toute nos pages pour améliorer ce côté “front-end”, un template qui regroupe les différents liens et un “footer” qui résume notre équipe. Oui on a ajouté d’autres pages au projet qui sont représentés par:
 Une description du projet qui contient le fonctionnement général du projet.
Un test de robustesse qui montre les limites du projets et tout ce qui ne va pas.
Un mode d’emploi pour expliquer les différentes étapes à suivre.
Ces changements ont pour but d’orienter et de mieux expliquer le projet à la génération suivante qui s’occupera de ce dernier, et donc apporter une facilité à résoudre quelques problèmes.
Nous allons voir dans ce qui suit quelques captures d’écrans qui montre le résultat obtenu.

# Explication de l’exemple 2
La table de hachage permet de stocker des valeurs à des clés uniques générés à partir d’une chaine de caractère via l’algorithme de Hachage SHA1 . Cette unicité de clé, restreint l’utilisateur à effectuer une recherche multicritère dans une architecture distribuée et minimise la probabilité de trouver exactement le même mot cherché (marseille != marseilles).
Dans un site d’annonce, vous avez le choix de choisir les méthodes de recherche, soit en utilisant la recherche rapide, soit en parcourant les annonces d’un thème choisi et récupérer les annonces intéressantes. À partir de cette idée et le paradigme de plage d’adresse du réseau qui permet d’identifier à un emplacement exact le domaine d’adresses, nous avons définit des intervalles de numéros pour chaque catégorie de tels sorte l’utilisateur connait le domaine de recherche. En fait la restriction en des sous-domaines l’abstraction à des niveaux encore plus bas affine le résultat et augmente la précision sur l’objet cherché.
Ainsi dans cette implémentation, nous avons réglé le problème d’écrasement des clés en stockant les annonces qui utiliseront le même numéro.
Publication d’une annonce :
Notre système stocke des clés aléatoires qui appartiennent à l’intervalle des numéros correspondants au thème et au sous-thème choisis :
Exemples : Education [1..20] à Livres [1..10] && Universités [11..20]
Recherche d’une annonce :
L’utilisateur doit obligatoirement choisir le thème et le sous thème de recherche qui restreindront l’intervalle de recherche. Dans le cas où il y en a plusieurs annonces par clés , elles seront toutes affichées.
Explication du code : lorsque l’utilisateur choisit une catégorie parmis la liste  , un script active une deuxième liste de sous-catégorie dépendante de la catégorie choisie :

```sh 
<script>
               $(function () {
                   $("#sous_categorie1").chained("#categorie");
               });
  </script>
```
lors de la publication , il récupère l’index de liste et lance une fonction random pour chaque catégorie et sous-catégorie : 
```sh 
document.querySelector('#put').addEventListener('submit', function (e) {
  // Prevent page refresh
  e.preventDefault();
  var element3="";
  var element;
  var element2;
  if (document.getElementById("categorie").selectedIndex == "0") {
    if (document.getElementById("sous_categorie1").selectedIndex == "0"){
  var key_string = "E"+Math.floor((Math.random() * 10) + 1);}
    else {var key_string = "E"+Math.floor((Math.random() * 10) + 11);}
}
```
Lors de la recherche , selon les catégories et les sous-catégories choisies nous limitons la possibilité à l’utilisateur d'entrer des numéros qui n’appartiennent pas à l’intervalle définis
```sh 
  $('#sous_categorie').change(function () {
    if (this.value == "1") {
        $('#cherche').prop({
            'min': 1,
            'max': 10
        });
    }
    if (this.value == "2") {
        $('#cherche').prop({
            'min': 11,
            'max': 20
        });
    }
```
Afin d’éviter l’écrasement des valeurs qui auront le même clés , nous avons invoqué la fonction get qui permet de chercher la valeur de la clé . lorsque il trouve la valeur , il récupère l’ancienne valeur et l’ajoute à la nouvelle saisis et qui sera stocké suite à l’appel de put
```
 node.get(key_string, function(err, value) {
    if(err) {
       node.put(key_string, value_string, function(err) {
      if(err) {
      $('#putdiv').html('<br><label><font color="red">Annonce non publiée</font></label>'); 
      return;
    }
    $('#putdiv').html('<br><label><font color="green">Annonce publiée</font></label>'); 
  });
      return;
    }
     value_string= value_string+"---"+value;
     node.put(key_string, value_string, function(err) {
    if(err) {
    $('#putdiv').html('<br><label><font color="red">Annonce non publiée</font></label>');
      return;
    }
    $('#putdiv').html('<br><label><font color="green">Annonce publiée</font></label>'); 
  });
    
  });
```
### Avantages :
- Augmenter la probabilité de trouver une annonce dans le réseau
- Structurer la table de hachage à des intervalles qui correspondent à des thèmes
- Avoir des connaissances sur le domaine et le sous domaine de recherche
### Inconvénient :
- Limite la recherche par valeurs et l’accès par valeur
### Améliorations possibles : 
- Ajouter plusieurs niveaux d’abstractions
- Recherche par Tags


# Manuel d’utilisation de l’exemple 2 : 
1- Lancer un nœud et  connecter deux nœuds entre eux
2- Publier une annonce en choisissant une catégorie et une sous-catégorie
4-Chercher les annonces selon la catégorie et sous-catégorie choisis 

NB : Nous avons utilisé des petits intervalles dans le but de tester le fonctionnement , vous pouvez modifier les intervalles dans les fonctions random() : 

```sh
document.querySelector('#put').addEventListener('submit', function (e) {
  // Prevent page refresh
  e.preventDefault();
  var element3="";
  var element;
  var element2;
  if (document.getElementById("categorie").selectedIndex == "0") {
    if (document.getElementById("sous_categorie1").selectedIndex == "0"){
  var key_string = "E"+Math.floor((Math.random() * 10) + 1);}
    else {var key_string = "E"+Math.floor((Math.random() * 10) + 11);}
}
 if (document.getElementById("categorie").selectedIndex == "1") {
   if (document.getElementById("sous_categorie1").selectedIndex == "0"){
  var key_string = "S"+Math.floor((Math.random() * 10) + 21);}
    else {var key_string = "S"+Math.floor((Math.random() * 10) + 31);}
}
 if (document.getElementById("categorie").selectedIndex == "2") {
   if (document.getElementById("sous_categorie1").selectedIndex == "0"){
  var key_string = "L"+Math.floor((Math.random() * 10) + 41);}
    else {var key_string = "L"+Math.floor((Math.random() * 10) + 51);}
}

 if (document.getElementById("categorie").selectedIndex == "3") {
  if (document.getElementById("sous_categorie1").selectedIndex == "0"){
  var key_string = "L"+Math.floor((Math.random() * 10) + 61);}
    else {var key_string = "L"+Math.floor((Math.random() * 10) + 71);}
}
```
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






