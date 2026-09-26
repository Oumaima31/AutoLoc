# AutoLoc — Plateforme de gestion de location de véhicules multi-agences

## Contexte du projet

AutoLoc est une entreprise de location de véhicules disposant de plusieurs agences
réparties dans différentes villes. Chaque agence gère une flotte de véhicules de
catégories variées (citadine, berline, SUV, utilitaire). Les clients réservent un
véhicule pour une période donnée ; à la signature, un contrat est établi et des
paiements y sont rattachés.

Ce projet vise à numériser l'ensemble du processus métier : réservation,
contractualisation, facturation, suivi de flotte et relances automatiques, à
travers une application back-end développée avec **Spring Boot** exposant une **API
REST**.

Ce dépôt est réalisé dans le cadre du module **Architecture des Systèmes
d'Information (UP ASI)**.

## Acteurs du système

| Rôle | Description | Droits principaux |
|---|---|---|
| **Client** | Particulier ou professionnel souhaitant louer un véhicule | Consulter les véhicules disponibles, créer/annuler une réservation, consulter ses contrats |
| **Agent d'agence** | Employé en charge de la gestion opérationnelle d'une agence | Gérer les véhicules, valider une réservation, établir un contrat, enregistrer un paiement |
| **Responsable d'agence (Manager)** | Supervise une agence et son personnel | Droits Agent + gestion des employés, consultation des statistiques de l'agence |
| **Administrateur** | Administre la plateforme | Gestion des agences, des catégories de véhicules, statistiques globales, configuration |

## Cas d'utilisation identifiés

### Client
- Consulter la liste des véhicules disponibles (par ville, catégorie, période)
- Créer une réservation
- Annuler une réservation
- Consulter l'historique de ses réservations et de ses contrats

### Agent d'agence
- Gérer les véhicules de son agence (ajout, mise à jour, statut)
- Valider ou refuser une réservation
- Établir un contrat de location
- Enregistrer un paiement (acompte, solde, pénalité)

### Responsable d'agence (Manager)
- Toutes les actions de l'Agent d'agence
- Gérer les employés de son agence
- Consulter les statistiques d'occupation et de chiffre d'affaires de son agence

### Administrateur
- Gérer les agences (création, modification, suppression)
- Gérer les catégories de véhicules et les équipements
- Consulter les statistiques globales de la plateforme
- Configurer les paramètres généraux de l'application

## Modules fonctionnels

| Module | Description |
|---|---|
| Gestion des agences & de la flotte | CRUD des agences, des véhicules et de leurs catégories ; suivi de disponibilité |
| Gestion des clients | Inscription, mise à jour du profil, historique des réservations et contrats |
| Réservation | Recherche de véhicules disponibles, création/modification/annulation de réservations |
| Contractualisation & paiement | Génération d'un contrat, enregistrement des paiements |
| Tarification | Calcul du tarif selon catégorie, durée, période, équipements optionnels |
| Tâches planifiées | Libération automatique des véhicules, alertes d'échéance, statistiques |
| Reporting & qualité | Statistiques d'occupation et de chiffre d'affaires, qualité du code |

## Stack technique

- **Langage / Build** : Java 17+, Maven
- **Framework** : Spring Boot, Spring Data JPA, Spring MVC, Spring AOP, Spring Scheduler
- **Base de données** : MySQL (dev), H2 (tests)
- **Productivité** : Lombok, SLF4J/Logback, MapStruct (optionnel)
- **Documentation API** : springdoc-openapi (Swagger UI)
- **Qualité** : SonarLint / SonarQube
- **Outillage** : Git/GitHub, Postman, IntelliJ IDEA

## Avancement

- [x] Atelier 0 — Mise en place de l'environnement
- [x] Atelier 1 — Projet Spring Boot + entité Vehicule
- [ ] Atelier 2 — Associations entre entités JPA
