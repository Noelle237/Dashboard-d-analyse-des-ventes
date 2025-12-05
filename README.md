# Projet Power BI – Analyse des Ventes
# Objectif
Ce projet consiste à créer un tableau de bord interactif sous Power BI pour analyser les ventes d’une entreprise à partir d’un fichier CSV (sales_2.csv).
L’objectif est de structurer les données, normaliser le modèle et concevoir des visualisations pour le suivi des ventes et des commandes annulées.
Competences Mobilisés
•	Préparation complète d'un projet BI
•	Nettoyage et transformation des données avec Power Query
•	Normalisation des tables (modèle propre et cohérent)
•	Utilisation du langage M (Power Query / Mashup)
•	Modélisation en étoile pour structurer les relations
•	Création de mesures DAX pour les KPI
•	Mise en place d' info-bulles personnalisées
•	Personnalisation du rapport et mise en page
•	Ajout de filtres et fonctionnalités interactives

Étapes du projet
1. Préparation des données

Importation du fichier sales_2.csv dans Power Query.
Analyse de la qualité des données :

Profil de colonne
Distribution
Types de données


Renommage des colonnes avec des libellés explicites (Id commande, Id client, Nom client, Id produit, Nom produit, Catégorie produit, Id région, Nom région, Date commande, Quantité, Prix unitaire, Prix total, Statut commande).


2. Normalisation du modèle
   
Création de tables de référence pour structurer les dimensions du modèle :
- Clients : (Id client, Nom client)
- Produits : (Id produit, Nom produit, Catégorie produit)
- Régions : (Id région, Nom région)
Ces tables ont été extraites de la table brute pour garantir un modèle plus lisible, cohérent et évolutif.
Des vérifications ont été effectuées pour détecter les doublons et incohérences.
La table Ventes a été construite comme table de faits, en conservant uniquement les colonnes nécessaires à l’analyse (Date commande, Ids, Statut, Prix, Quantité…).
   Modélisation en étoile
Le modèle mis en place suit une structure en étoile, avec :
- Une table de faits centrale : Ventes
- Des tables de dimensions : Clients, Produits, Régions, et une table de mesures calculées (Mesure)

3. Modélisation

Vérification des relations automatiques dans Power BI.
Création manuelle des relations si nécessaire.
Test de cohérence (exemple : Id commande → Nom produit).


4. Création du Dashboard

Thème personnalisé : Loomy Lime (JSON importé).
Mise en page :

Hauteur : 1700 px
Couleur de fond : #1E2D38
Couleur des briques : #232448


Mesures DAX principales :

Total ventes = SUM(Ventes[Prix total])
Nombre de commandes = DISTINCTCOUNT(Ventes[Id commande])
Quantité vendue = SUM(Ventes[Quantité])
Commande moyenne = DIVIDE([Total ventes], [Nombre de commandes])

5. Visualisations


Onglet 1 : Suivi des ventes

KPI : Total ventes, Nombre de commandes, Quantité vendue, Commande moyenne
Courbe d’évolution du chiffre d’affaires
Répartition du chiffre d’affaires par région (barres horizontales)
Répartition par catégorie de produit (donut)
Tableau détaillé des commandes
Filtres : Date, Statut, Région



Onglet 2 : Commandes annulées

KPI : Total annulées, Montant annulées, Pourcentage annulées
Courbe d’évolution du pourcentage annulé
Histogramme par région
Treemap par catégorie
Ruban par produit (trimestriel)




6. Fonctionnalités avancées

Menu de navigation avec icônes
Info-bulles (tooltips) pour histogramme et donut
Signets (bookmarks) pour filtres rapides
Rôles RLS (Row-Level Security)
