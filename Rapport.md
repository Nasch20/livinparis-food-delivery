# RAPPORT  

## Schéma Entité-Association  

Nous avons débuté par la création d’un schéma E/A chacun, en intégrant nos idées afin de partager nos visions sur les entités nécessaires ainsi que leurs liens et cardinalités. Nous avons mis en commun toutes nos idées, ce qui a donné une première version distinguant les entités utilisateur client et cuisinier. En demandant l’avis de nos professeurs, nous avons compris qu’il était plus simple de créer uniquement l’entité utilisateur en ajoutant une variable rôle, qui prend comme valeur 0 si l’utilisateur est seulement client, 1 s’il est seulement cuisinier et 2 s’il est les deux. Cela a grandement simplifié le schéma. Nous avons ensuite conclu que la version modifiée était celle avec laquelle nous pouvions à présent entreprendre le codage de notre script SQL pour la création de la base. Nous n'excluons pas la possibilité de modifier le schéma durant le projet.  

---

## Script SQL  

Nous avons ensuite créé la base de données sur **SQL Workbench** en créant les tables (**entités**), **clefs**, **déclaration des types des variables**. Nous avons pu extraire les informations de Excel (commande, cuisinier, client) et les adapter à notre base de données ainsi qu'à nos variables, en effectuant toutes les modifications nécessaires afin d'obtenir un peuplement des tables conforme à notre plan. Cela nous a ensuite permis d'exécuter des requêtes simples pour tester les différentes tables et garantir un fonctionnement optimal.

---


## IA Générative pour Visualisation du Graphe  

Nous avons tout d'abord essayé de coder par nous-mêmes une interface de visualisation sans faire usage de l'IA, mais cela s'est révélé être une tâche bien plus complexe que prévu. Nous avons donc utilisé **ChatGPT** pour accéder aux différentes **fonctions d'affichage WinForms**, ainsi qu'aux fonctions de **détection du mouvement de la souris, du clic gauche**, etc. Nous avons ensuite **repris le code intégralement** afin de comprendre au maximum les étapes effectuées par l'IA, tout en **commentant le code**.  

✍ **Rédigé par :** *[Nathan BELAISCH, Ali BEN YEZZA et Nathan BARRÉ]*  
📅 **Date :** *[28/02/2025]* 
