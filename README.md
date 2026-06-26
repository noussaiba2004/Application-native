# To-Do List Application (Android Native) — Groupe 9

## 📝 Présentation du Projet
Ce projet consiste en une application mobile native Android de gestion de tâches unitaire (« To-Do List »). Développée de manière modulaire, elle permet à l'utilisateur de lister, d'ajouter et de supprimer des tâches quotidiennes de façon fluide et intuitive.

L'objectif principal de cette implémentation est de valider les concepts d'ingénierie logicielle nomade, de gestion du cycle de vie des composants et de persistance des données locale sécurisée.

## 🛠️ Architecture & Technologies
L'application repose exclusivement sur les technologies et outils officiels préconisés par Google pour le développement natif :

* **Langage de programmation :** Java (Android SDK)
* **Environnement de développement (IDE) :** Android Studio (Hedgehog)
* **Patron d'architecture :** Modèle-Vue-Contrôleur (MVC) / Structure modulaire étanche
* **Couche de persistance :** ORM Room (surcouche d'abstraction locale SQLite)

## 🛡️ Focus sur la Sécurité et la Robustesse
Dans le cadre de notre formation, une attention particulière a été portée à la sécurité des données et à la stabilité du logiciel :
* **Immunité contre les Injections SQL :** L'utilisation des interfaces DAO (Data Access Object) de Room permet d'exécuter des requêtes paramétrées compilées, bloquant nativement toute tentative d'injection de code malveillant.
* **Sécurité à la compilation :** Room valide le schéma de la base de données SQLite dès la phase de compilation du build, éliminant les risques de crashs applicatifs en production.
* **Zéro dépendance tierce :** Limitation stricte de la surface d'attaque en n'utilisant que les bibliothèques officielles du framework Android Jetpack.

## 📁 Structure du Code Source (Package `com.example.appgroupe9`)
Le code est segmenté de manière rigoureuse afin de respecter la séparation des préoccupations :

* `Task.java` : Définition de l'entité et modélisation de la table relationnelle SQLite.
* `TaskDao.java` : Interface d'accès aux données encapsulant les requêtes sécurisées d'insertion et de suppression.
* `AppDatabase.java` : Point d'entrée de la base de données implémenté via le design pattern **Singleton** pour optimiser la mémoire vive (RAM).
* `TaskAdapter.java` : Adaptateur personnalisé assurant le pontage et le rendu visuel unitaire de chaque tâche (gonflage du layout XML).
* `MainActivity.java` : Contrôleur principal gérant l'interception du cycle de vie de l'application et la logique événementielle.

## 🚀 Perspectives d'Évolution
* Chiffrement au repos de la base de données locale à l'aide de l'API **Jetpack Security** (AES-256 GCM).
* Intégration d'une barrière d'authentification biométrique matérielle (`BiometricPrompt`) s'appuyant sur le système de permissions Android.
* Migration vers une architecture déclarative moderne avec **Jetpack Compose** et **Kotlin**.
