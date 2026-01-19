🚗 Station-Api
Application Java permettant de trouver automatiquement le stationnement le plus proche dans une ville modélisée sous forme de graphe.

Ce projet combine programmation orientée objets, algorithmes de graphes, interface graphique Java Swing, et simulation visuelle pour offrir une solution complète de recherche de stationnement optimal.

🎯 Objectif du projet
Modéliser une ville avec routes, intersections et stationnements

Permettre à un conducteur d’entrer ses coordonnées

Identifier la route où il se trouve

Générer dynamiquement un graphe pondéré

Calculer le chemin le plus court vers le stationnement disponible le plus proche

Afficher le trajet dans une interface graphique

🧱 Architecture générale
Le projet est organisé en plusieurs modules :

1. Interface graphique (Java Swing)
VilleInterface

projetperform

2. Modélisation de la ville
Position

intersection

conducteur

route

Stationnement

3. Algorithmes et structures de données
Graph

Edge

Node

4. Logique métier
serveur

🏙️ Interface graphique – VilleInterface
VilleInterface représente la carte de la ville et affiche :

les routes

les intersections

les stationnements

le conducteur

le trajet optimal

Elle utilise Graphics2D pour dessiner dynamiquement les éléments.

Exemple de dessin d’une route :
java
g.setStroke(new BasicStroke(r.getLargeur()));
g.drawLine(r.getP1().getX(), r.getP1().getY(), r.getP2().getX(), r.getP2().getY());
🚗 Interface utilisateur – projetperform
projetperform est la fenêtre où l’utilisateur :

entre ses coordonnées X et Y

déclenche la recherche du stationnement

visualise le trajet calculé

Elle gère les erreurs d’entrée et interagit directement avec serveur.

🧩 Modélisation des entités
Position
Classe de base représentant un point (x, y).
Fonctionnalités :

distance entre deux points

comparaison

héritage

intersection
Hérite de Position et ajoute un identifiant unique.
Utilisée comme nœud du graphe.

conducteur
Hérite de Position.
Représente la position du conducteur dans la ville.

route
Représente une route entre deux intersections.

Fonctionnalités :

calcul de distance

génération de toutes les positions de la route

vérification d’appartenance d’un point

largeur configurable

Stationnement
Classe métier représentant un parking.

Fonctionnalités :

nombre total de places

places disponibles

état (plein / non plein)

réservation / libération

position graphique

⚙️ Logique métier – serveur
La classe serveur est le moteur du projet.

Fonctionnalités :

identifier la route où se trouve le conducteur

générer un graphe dynamique selon cette route

construire les arêtes pondérées

sélectionner les stationnements disponibles

exécuter l’algorithme de plus court chemin

produire la liste des points du trajet

Exemple :

java
s = new serveur();
s.v.cd.setX(X);
s.v.cd.setY(Y);
s.traitement(s.v.cd);
🧮 Algorithmes – Graph, Edge, Node
Graph
Structure du graphe pondéré (liste d’adjacence).
Optimisé pour Dijkstra.

Edge
Arête pondérée entre deux nœuds.

Node
Élément utilisé dans la file de priorité de Dijkstra.

▶️ Exécution du projet
Prérequis
Java 8+

IDE (IntelliJ, Eclipse, VS Code)

Lancer l’application
bash
javac projetperform.java
java projetperform
🚀 Améliorations futures
Interface graphique plus moderne

API REST (Spring Boot)

Visualisation dynamique du graphe

Ajout de tests unitaires JUnit

Ajout d’un algorithme A*

👤 Auteur
Rhodian Japha Ndamen Fomen  
B.Sc. Informatique – UQO
Passionné par les algorithmes, la modélisation et le développement logiciel.
