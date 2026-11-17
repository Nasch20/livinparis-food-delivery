# Rapport

✍ **Rédigé par :** *[Nathan BELAISCH, Ali BEN YEZZA et Nathan BARRÉ]*  
📅 **Date :** *[04/04/2025]* 
---

## Base de données

Nous avons créé une base de données en SQL correspondant à notre schéma E/A. Nous avons donc créé les identités clients, cuisiniers, plats etc. ainsi que toutes les variables les composant, en prenant en compte les différentes clés primaires et étrangères. Ensuite nous avons fournis à notre base plusieurs données de clients, de cuisinier, de commandes etc. et nous avons relier cette base SQL avec un code C# qui nous permet de : Créer un utilisateur, afficher la liste des plats disponibles, commander un plat, afficher les commandes déjà effectuer, rajouter un plat aux plats déjà existant, afficher les commandes pris en charges par un cuisinier en particulier, afficher les commandes effectuer par un client en particulier, afficher le pris moyen des commandes effectuer.

Nous avons en parallèles créé un site Web, qui, bien qu'il soit encore imcomplet, nous permetteras de faire toutes les requêtes si dessus ailleurs que dans la console de VisualStudio.

---

## Plus court chemin (C#) 

Après ça, nous avons créé le code C# nous permettant de trouver le plus court chemin entre deux station de métro. Nous avons commencé par récupérer toutes les informations dont nous avions besoin sur un fichier .csv pour pouvoir le lier à notre code. Globalement, les classes noeuds et liens du graphe sont les même à la différences que les liens ont maintenant une pondération et une ligne de métro attribué. Nous avons du recréer plusieurs fichiers .csv en raison de certain problème, causé par des virgules en trop une première fois, puis parce que les guillemets provoquait une erreur, on ne sait pas trop pourquoi. Une fois les classes noeuds et liens créées, nous avons pu concevoir la classes graphe. La création du graphe n'a pas poser trop de problème étant donné qu'on en avait déjà fait un auparavant. Pour poursuivre, nous avons rajouter une fonction vérifiant que la graphe était bel et bien connexe pour pouvoir avancer.
Le premier des trois programme que nous avons fait fut l'algo de Dijkstra. Nous avons donc fait une fonction qui simule cette algorithme en notant à chaque fois les informations utiles (Temps de trajet et noeud précédent pour chaque noeuds). Nous avons ensuite rajouté le fait que lorsque l'algo nous fasse changer de ligne de métro, cela rajoute deux minutes au temps final, simulant ainsi le temps qu'il faut pour ce déplacer au sein de la gare. L'un des problèmes que nous avons rencontré est qu'au début nous ne marquions pas les graphes qui ont été visité ou non, nous avons donc du résoudre ce problème.
Puis viens l'algo de BellmanFord, celui ci ne nous a pas poser trop de problème, pour chaque itération de l'algorithme, le programme regarde tout les liens et vois si emprunter ce liens permet de réduire le temps qu'il faut pour aller à un noeud. Nous avons ensuite rajouté la même fonctionnalité que pour l'algorithme de Dijkstra, c'est à dire, rajouté du temps à chaque changement de ligne.
Le dernier est l'algo de FloydWarshall, le principe de ce code est très simple, on a une triple boucle ou à chaque fois, on regarde si un chemin allant de i à j ne serait pas plus court en le divisant en un chemin i , k , j. Nous avions plusieurs matrices, une pour connaitre le temps minimal entre deux points et une pour connaitre le chemin le plus court entre ces deux même points. Mais en voulant rajouter une fonction qui rajoute du temps à chaque changement de ligne, le programme est soudain devenu très lent, il mettait 20 minutes pour s'exécuter. Pour résoudre à ce problème, nous avons du créer deux autre matrices, correspondant respectivement à la première et dernière ligne de métro utilisée pour aller du point i à j, le code est donc devenu beaucoup plus rapide, on passe de 20 minutes à une seconde.

---

## Affichage graphe(les graphes générés apparaitront dans le dossier bin/debug/net8.0)

Après avoir fini les fonctions qui permettent de trouver le plus court chemin, et après avoir observé que l'algo de BellmanFord était le plus rapide d'entre eux, nous avons rajouté une fonction en C# qui permet d'afficher tout les noeuds sur une images positionné selon les coordonnées de chaque gare que nous avons récupérer dans le fichier .csv. Puis la fonction affiche les liens entre chaque gare avec une couleur différente pour chaque ligne de métro. Ainsi nous obtenons une fonction qui affiche le plan du métro parisien. Il ne reste plus qu'à combiner ce plan avec l'algo de BellmanFord, ce qui permettra de mettre en surbriance le chemin le plus court entre deux gare sur le plan. Pour celà nous avons eu besoin d'installer System.Drawing dans les nuggets pour pouvoir afficher l'image du plan du métro.

---

## Site Web (Lire en entier pour le bon fonctionnement du code)

Le site utilise une architecture moderne pour gérer l'authentification et les données utilisateur. L'interface propose une connexion ou une inscription via des pages HTML. Lors de l'inscription, les informations sont converties en XML et envoyées à une API RESTful développée en ASP.NET Core. Le contrôleur traite ces données et les transmet au service de gestion des utilisateurs(UserManager.cs), qui génère un identifiant unique et stocke les informations dans une base de données MySQL. Le système inclut des validations de données, une gestion des erreurs et des mesures de sécurité comme le CORS. L'architecture sépare clairement les responsabilités entre l'interface utilisateur, la logique métier et le stockage des données, assurant ainsi une gestion efficace et sécurisée des informations utilisateur.

Pour exécuter le site :
1-Installer MySQL et créer la base food_delivery
PS : Vérifier que MySQL est en cours d'exécution et que les identifiants sont corrects.
Il faut modifier le mot de passe dans ces deux fichiers :
Assets/UserManager/Program.cs (ligne 13)
Assets/csharp/UserManager.cs (ligne 28)

2-Lancer l'API :
   cd Assets/UserManager
   dotnet run
PS: L'API sera sur http://localhost:5270

3-Ouvrir homepage.html dans un navigateur
Le site sera accessible via homepage.html
