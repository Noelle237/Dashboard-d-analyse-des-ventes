# Projet Power BI – Analyse des Ventes
# Objectif
Ce projet consiste à créer un tableau de bord interactif sous Power BI pour analyser les ventes d’une entreprise à partir d’un fichier CSV (sales_2.csv).
L’objectif est de structurer les données, normaliser le modèle et concevoir des visualisations pour le suivi des ventes et des commandes annulées.

Étapes du projet
1. Préparation des données

Importation du fichier sales_2.csv dans Power Query.
Analyse de la qualité des données :

Profil de colonne
Distribution
Types de données


Renommage des colonnes avec des libellés explicites (Id commande, Id client, Nom client, Id produit, Nom produit, Catégorie produit, Id région, Nom région, Date commande, Quantité, Prix unitaire, Prix total, Statut commande).


2. Normalisation du modèle

Création de tables de référence :

Clients (Id client, Nom client)
Produits (Id produit, Nom produit, Catégorie)
Régions (Id région, Nom région)


Vérification des anomalies (doublons, incohérences).
Création de la table Ventes (référence à la table brute, suppression des colonnes inutiles).


3. Modélisation

Vérification des relations automatiques dans Power BI.
Création manuelle des relations si nécessaire.
Test de cohérence (exemple : Id commande → Nom produit).


4. Création du Dashboard

Thème personnalisé : Loomy Lime (JSON importé).
Mise en page :

Hauteur : 2000 px
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
