# Gestion des Concours d’accès

![concours](https://github.com/user-attachments/assets/5d5b799e-ab79-4314-a76d-9338771f7aec)

# Description
la Gestion des Concours d’Accès est une application conçue pour simplifier et organiser la gestion des concours d’admission, des candidats et des résultats. Il s’adresse aux établissements éducatifs, aux centres de formation ou à toute organisation qui organise des concours pour sélectionner des candidats.
# Contexte
simplifier et automatiser l’organisation des concours pour les établissements éducatifs et les organisations. Elle répond aux problèmes de centralisation des données, de processus manuels chronophages et de manque de transparence. En proposant une solution numérique, elle améliore l’efficacité pour les administrateurs (gestion des concours et résultats) et l’expérience pour les candidats (inscription et consultation des résultats). Cette solution s’adapte à différents types de concours et peut être étendue avec des fonctionnalités supplémentaires.
# Problématique
Les informations sur les concours, les candidats et les résultats sont dispersées dans différents.
Les systèmes existants ne s’adaptent pas toujours à différents types de concours ou à des besoins spécifiques.
La saisie manuelle des données augmente le risque d’erreurs, ce qui peut compromettre la crédibilité du concours.
# Objectif
+ Faciliter l’organisation des concours :
Permettre aux administrateurs de créer, modifier et gérer facilement les concours .

+ Simplifier l’inscription des candidats :
Offrir une interface intuitive pour l’inscription des candidats et la collecte de leurs informations .

+ Réduire les erreurs et les coûts :
Minimiser les erreurs liées à la saisie manuelle des données.

Réduire les coûts opérationnels grâce à l’automatisation des processus.
# Diagramme use case
<img width="764" alt="image" src="https://github.com/user-attachments/assets/817ebc06-b2a0-4c96-817b-d32efb567ddc" />


# Diagramme de classe

<img width="610" alt="image" src="https://github.com/user-attachments/assets/7e6e19a7-7237-4a12-a777-3d5f7f208720" />

# Architecture

![image](https://github.com/user-attachments/assets/bb8143b3-1a3b-46c0-a1b7-5aba54aff3bc)

# Structure de la Base de Données
Le système repose sur quatre tables principales : 
+ Concours
+ Candidat
+ Resultat
+ Utilisateur

  CREATE DATABASE GestionConcours;
USE GestionConcours;

-- Table Concours
CREATE TABLE Concours (
    id INT PRIMARY KEY AUTO_INCREMENT,
    intitule VARCHAR(255) NOT NULL,
    date DATE NOT NULL,
    lieu VARCHAR(255) NOT NULL
);

-- Table Candidat
CREATE TABLE Candidat (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(100) NOT NULL,
    prenom VARCHAR(100) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL
);

-- Table Résultat
CREATE TABLE Resultat (
    concours_id INT,
    candidat_id INT,
    note FLOAT CHECK (note >= 0 AND note <= 20),
    PRIMARY KEY (concours_id, candidat_id),
    FOREIGN KEY (concours_id) REFERENCES Concours(id) ON DELETE CASCADE,
    FOREIGN KEY (candidat_id) REFERENCES Candidat(id) ON DELETE CASCADE
);     
CREATE TABLE user (
    id INT AUTO_INCREMENT PRIMARY KEY,
    login VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
); 

#Technologies
+ NetBeans 8.0.2 : Environnement de développement intégré (IDE) pour le développement de l'application en Java.
+ MySQL: Pour la gestion de la base de données.
+ MySQL Connector/J : Pilote JDBC pour la connexion et l'interaction avec la base de données MySQL.
+ JCalendar : Bibliothèque pour la gestion des dates dans l'interface graphique.
+ JFreeChart : Bibliothèque pour la génération de graphiques (Pie Chart, etc.).
+ Swing : Bibliothèque Java pour la création de l'interface graphique utilisateur (GUI).
+ Outils de développement :
IDE Java : NetBeans
Conception : MagicDraw
Outil de gestion de base de données : phpMyAdmin
Accès aux données : JDBC
# Visualisation de l'Architecture
L'architecture du projet est conçue selon le modèle MVC (Modèle-Vue-Contrôleur), qui permet une séparation claire des responsabilités et une meilleure organisation du code. Cette structure facilite la maintenance, l'évolution et la testabilité de l'application. Voici comment les différentes couches sont organisées :
+ Le Modèle: gère les données et la logique métier.

+ La Vue: se concentre sur l'affichage et l'interaction avec l'utilisateur.

+ Le Contrôleur: fait le lien entre les deux, assurant une communication fluide et une gestion cohérente des actions.

  #Vidéo Démonstrative
  







https://github.com/user-attachments/assets/df314a8d-4721-4966-895d-c18640894ee4





