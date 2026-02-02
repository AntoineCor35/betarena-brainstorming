# Livrable WBS — Bet Arena

> **Projet :** Bet Arena — Simulateur de paris e-sport gamifié
> **Version :** 1.0
> **Date :** 31 janvier 2026
> **Référence :** WBS-BETARENA-2026-01

---

## Table des matières

1. [Introduction](#1-introduction)
2. [Périmètre du projet](#2-périmètre-du-projet)
3. [WBS — Diagramme hiérarchique](#3-wbs--diagramme-hiérarchique)
4. [WBS — Décomposition détaillée par phase](#4-wbs--décomposition-détaillée-par-phase)
5. [Document Fonctionnalités & Exigences](#5-document-fonctionnalités--exigences)
6. [Dépendances et chemin critique](#6-dépendances-et-chemin-critique)
7. [Dictionnaire du WBS](#7-dictionnaire-du-wbs)
8. [Synthèse des livrables](#8-synthèse-des-livrables)

---

## 1. Introduction

### 1.1 Objet du document

Ce document constitue le livrable WBS (Work Breakdown Structure — Structure de Découpage du Projet) pour le projet **Bet Arena**.

### 1.2 Présentation du projet

**Bet Arena** est un simulateur de paris e-sport gamifié destiné aux étudiants et jeunes adultes français. Le produit utilise exclusivement des crédits virtuels (aucun argent réel) et intègre nativement des mécaniques de prévention gamifiée pour sensibiliser aux biais cognitifs liés au betting.

**Proposition de valeur :** Recréer le frisson du pari sans les risques financiers, tout en éduquant sur les comportements à risque via l'expérience elle-même, avec une identité visuelle pixel art arcade 80s.

### 1.3 Convention de numérotation

Le WBS utilise une numérotation hiérarchique à 3 niveaux :

| Niveau | Format    | Description                   | Exemple                            |
| ------ | --------- | ----------------------------- | ---------------------------------- |
| 1      | **X**     | Phase projet                  | `1` = Discovery & Cadrage          |
| 2      | **X.Y**   | Lot de travail (Work Package) | `1.1` = Validation données e-sport |
| 3      | **X.Y.Z** | Tâche / Livrable unitaire     | `1.1.1` = Tester Riot API (LoL)    |

---

## 2. Périmètre du projet

### 2.1 Inclus dans le périmètre (IN)

- Plateforme web responsive (mobile-first) de simulation de paris e-sport
- Système de paris simple et combiné avec crédits virtuels
- Intégration de données e-sport pour 3 jeux : League of Legends, Valorant, CS2
- Système de gamification : leaderboard, ligues, succès, Wall of Shame
- Prévention gamifiée intégrée : succès ironiques, équivalences vie réelle, streaks
- Économie virtuelle fermée : capital de départ identique + salaire hebdomadaire
- Identité visuelle pixel art arcade 80s
- Infrastructure backend (API, WebSockets, base de données)
- Pipeline CI/CD et déploiement en production
- Livrables documentaires pour l'évaluation Epitech

---

## 3. WBS — Diagramme hiérarchique

### 3.1 Vue d'ensemble (Niveau 1)

```
┌─────────────────────────────────────────────────────────────────────────────────────┐
│                                   BET ARENA                                         │
│                          Simulateur de paris e-sport gamifié                        │
│                                  Projet MVP                                         │
└─────────────────────────────────────────────────────────────────────────────────────┘
                                        │
    ┌───────────┬───────────┬───────────┼───────────┬───────────┬───────────┐
    │           │           │           │           │           │           │
    ▼           ▼           ▼           ▼           ▼           ▼           ▼
┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐
│PHASE 1 │ │PHASE 2 │ │PHASE 3 │ │PHASE 4 │ │PHASE 5 │ │PHASE 6 │ │PHASE 7 │
│DISCOVER│ │ DESIGN │ │  DEV   │ │  DEV   │ │INTÉGRA-│ │ TESTS  │ │DÉPLOIE-│
│& CADRA.│ │  UX/UI │ │BACKEND │ │FRONTEND│ │  TION  │ │  & QA  │ │  MENT  │
└────────┘ └────────┘ └────────┘ └────────┘ └────────┘ └────────┘ └────────┘
```

### 3.2 Vue détaillée (Niveaux 1-2)

```
BET ARENA — MVP
│
├── 1. DISCOVERY & CADRAGE
│   ├── 1.1 Validation données e-sport
│   ├── 1.2 Cadrage fonctionnel
│   ├── 1.3 Architecture technique
│   └── 1.4 Setup projet
│
├── 2. DESIGN UX/UI
│   ├── 2.1 Design System pixel art 80s
│   ├── 2.2 Maquettes parcours clés
│   ├── 2.3 Design prévention gamifiée
│   ├── 2.4 Responsive & mobile-first
│   └── 2.5 Validation design
│
├── 3. DÉVELOPPEMENT BACKEND
│   ├── 3.1 Infrastructure & Setup
│   ├── 3.2 Module Authentification
│   ├── 3.3 Module Économie Virtuelle
│   ├── 3.4 Module Paris
│   ├── 3.5 Module Contenus E-sport
│   ├── 3.6 Module Social & Compétition
│   ├── 3.7 Module Succès & Prévention
│   └── 3.8 Documentation API
│
├── 4. DÉVELOPPEMENT FRONTEND
│   ├── 4.1 Setup & Architecture
│   ├── 4.2 Design System (composants)
│   ├── 4.3 Pages Authentification
│   ├── 4.4 Page d'Accueil
│   ├── 4.5 Parcours de pari
│   ├── 4.6 Pages Profil & Historique
│   ├── 4.7 Pages Social & Compétition
│   ├── 4.8 Prévention gamifiée (UI)
│   ├── 4.9 Responsive & Accessibilité
│   └── 4.10 Optimisation performance
│
├── 5. INTÉGRATION
│   ├── 5.1 Intégration Frontend ↔ Backend
│   ├── 5.2 Intégration temps réel
│   ├── 5.3 Tests d'intégration
│   └── 5.4 Résolution bugs d'intégration
│
├── 6. TESTS & QA
│   ├── 6.1 Tests fonctionnels
│   ├── 6.2 Tests utilisateurs
│   ├── 6.3 Tests performance
│   ├── 6.4 Tests sécurité
│   ├── 6.5 Corrections & Itérations
│   └── 6.6 Validation finale
│
└── 7. DÉPLOIEMENT
    ├── 7.1 Préparation production
    ├── 7.2 Migration & Données
    ├── 7.3 Déploiement application
    ├── 7.4 Documentation & Support
    └── 7.5 Lancement
```

---

## 4. WBS — Décomposition détaillée par phase

### Phase 1 — Discovery & Cadrage

```
1. DISCOVERY & CADRAGE
│
├── 1.1 Validation Données E-sport
│   ├── 1.1.1 Tester Riot API (LoL)
│   │   ├── Créer compte développeur Riot
│   │   ├── Tester endpoints matchs / équipes / résultats
│   │   └── Documenter limites, quotas et latence
│   ├── 1.1.2 Tester Riot API (Valorant)
│   │   ├── Évaluer données compétitives disponibles
│   │   └── Identifier les données manquantes
│   ├── 1.1.3 Évaluer solutions CS2
│   │   ├── Rechercher providers tiers (PandaScore, etc.)
│   │   ├── Comparer coûts, couverture et fiabilité
│   │   └── Décision Build or Buy
│   └── 📦 Livrable : Rapport de faisabilité API
│
├── 1.2 Cadrage Fonctionnel
│   ├── 1.2.1 Finaliser spécifications MVP
│   │   ├── Rédiger user stories Must Have
│   │   ├── Définir critères d'acceptation
│   │   └── Valider avec l'équipe
│   ├── 1.2.2 Définir paramètres économie virtuelle
│   │   ├── Fixer capital de départ
│   │   ├── Fixer salaire hebdomadaire
│   │   └── Lister les succès MVP
│   └── 📦 Livrable : Backlog priorisé
│
├── 1.3 Architecture Technique
│   ├── 1.3.1 Choisir stack technique
│   │   ├── Frontend (framework)
│   │   ├── Backend (framework)
│   │   └── Base de données + cache
│   ├── 1.3.2 Concevoir architecture système
│   │   ├── Schéma composants
│   │   ├── Flux de données
│   │   └── Stratégie temps réel (WebSockets)
│   └── 📦 Livrable : Dossier d'architecture technique
│
└── 1.4 Setup Projet
    ├── 1.4.1 Créer repositories Git
    ├── 1.4.2 Configurer environnements (dev / staging / prod)
    ├── 1.4.3 Setup pipeline CI/CD de base
    ├── 1.4.4 Documenter conventions équipe
    └── 📦 Livrable : Environnement de développement opérationnel
```

---

### Phase 2 — Design UX/UI

```
2. DESIGN UX/UI
│
├── 2.1 Design System Pixel Art 80s
│   ├── 2.1.1 Définir palette de couleurs
│   ├── 2.1.2 Créer typographie pixel
│   ├── 2.1.3 Designer icônes et éléments UI
│   ├── 2.1.4 Créer composants de base (boutons, inputs, cards, badges, toasts)
│   └── 📦 Livrable : Design System documenté
│
├── 2.2 Maquettes Parcours Clés
│   ├── 2.2.1 Maquettes onboarding (inscription, login, premier pari)
│   ├── 2.2.2 Maquette page d'accueil (matchs, top 3, solde)
│   ├── 2.2.3 Maquettes parcours de pari (sélection, bet slip, confirmation)
│   ├── 2.2.4 Maquettes profil utilisateur (stats, historique, succès)
│   ├── 2.2.5 Maquettes leaderboard & social (classement, ligues, Wall of Shame)
│   └── 📦 Livrable : Maquettes Figma complètes
│
├── 2.3 Design Prévention Gamifiée
│   ├── 2.3.1 Designer visuels succès ironiques (badges pixel art)
│   ├── 2.3.2 Designer affichage équivalences vie réelle
│   ├── 2.3.3 Designer toasts de sensibilisation
│   └── 📦 Livrable : Assets prévention
│
├── 2.4 Responsive & Mobile-First
│   ├── 2.4.1 Adapter maquettes mobile
│   ├── 2.4.2 Adapter maquettes tablet
│   ├── 2.4.3 Adapter maquettes desktop
│   └── 📦 Livrable : Maquettes responsive (3 breakpoints)
│
└── 2.5 Validation Design
    ├── 2.5.1 Review interne équipe
    ├── 2.5.2 Tests utilisateurs (3-5 testeurs)
    ├── 2.5.3 Itérations sur retours
    └── 📦 Livrable : Maquettes validées (version finale)
```

---

### Phase 3 — Développement Backend

```
3. DÉVELOPPEMENT BACKEND
│
├── 3.1 Infrastructure & Setup
│   ├── 3.1.1 Setup serveur / cloud
│   ├── 3.1.2 Configurer base de données (PostgreSQL)
│   ├── 3.1.3 Setup cache (Redis)
│   ├── 3.1.4 Configurer WebSockets
│   └── 📦 Livrable : Infrastructure backend opérationnelle
│
├── 3.2 Module Authentification
│   ├── 3.2.1 API inscription (validation email, hash mot de passe, crédits initiaux)
│   ├── 3.2.2 API login / logout (JWT, gestion sessions)
│   ├── 3.2.3 API OAuth (Google / Discord)
│   ├── 3.2.4 Tests unitaires authentification
│   └── 📦 Livrable : API Auth fonctionnelle et testée
│
├── 3.3 Module Économie Virtuelle
│   ├── 3.3.1 API gestion crédits (crédit/débit, historique, validation solde)
│   ├── 3.3.2 Job CRON salaire hebdomadaire + notification versement
│   ├── 3.3.3 Tests unitaires économie
│   └── 📦 Livrable : API Économie fonctionnelle et testée
│
├── 3.4 Module Paris
│   ├── 3.4.1 API paris simple (création, validation, stockage)
│   ├── 3.4.2 API paris combiné (multi-sélection max 10, calcul cote combinée)
│   ├── 3.4.3 Service calcul de cotes (algorithme + mise à jour dynamique)
│   ├── 3.4.4 Service résolution paris (post-match, calcul gains/pertes, maj soldes)
│   ├── 3.4.5 API historique paris
│   ├── 3.4.6 Tests unitaires paris
│   └── 📦 Livrable : API Paris fonctionnelle et testée
│
├── 3.5 Module Contenus E-sport
│   ├── 3.5.1 Intégration Riot API — League of Legends (matchs, résultats, équipes)
│   ├── 3.5.2 Intégration Riot API — Valorant
│   ├── 3.5.3 Intégration données CS2 (provider tiers ou scraping)
│   ├── 3.5.4 Cache matchs et cotes (Redis)
│   ├── 3.5.5 Jobs de synchronisation automatique
│   ├── 3.5.6 Tests d'intégration API externes
│   └── 📦 Livrable : API Matchs fonctionnelle et testée
│
├── 3.6 Module Social & Compétition
│   ├── 3.6.1 API leaderboard (calcul ROI, classement global, cache)
│   ├── 3.6.2 Service ligues (logique promotion/relégation, attribution)
│   ├── 3.6.3 API Wall of Shame (anti-classement)
│   ├── 3.6.4 API leaderboard équipe/club
│   ├── 3.6.5 Tests unitaires social
│   └── 📦 Livrable : API Social fonctionnelle et testée
│
├── 3.7 Module Succès & Prévention
│   ├── 3.7.1 Service succès (conditions déblocage, tracking progression, notifications)
│   ├── 3.7.2 Succès prévention ("Flambeur express", "Économe", "Lundi Noir", etc.)
│   ├── 3.7.3 Service streaks (responsable + pertes)
│   ├── 3.7.4 Service équivalences vie réelle (conversion crédits → kebabs, Netflix…)
│   ├── 3.7.5 Tests unitaires succès
│   └── 📦 Livrable : API Succès fonctionnelle et testée
│
└── 3.8 Documentation API
    ├── 3.8.1 Documenter endpoints (Swagger / OpenAPI)
    ├── 3.8.2 Rédiger guide d'intégration frontend
    └── 📦 Livrable : Documentation API complète
```

---

### Phase 4 — Développement Frontend

```
4. DÉVELOPPEMENT FRONTEND
│
├── 4.1 Setup & Architecture
│   ├── 4.1.1 Initialiser projet (Vite / Next.js)
│   ├── 4.1.2 Configurer routing et state management
│   ├── 4.1.3 Configurer client API + client WebSocket
│   └── 📦 Livrable : Squelette frontend opérationnel
│
├── 4.2 Implémentation Design System
│   ├── 4.2.1 Intégrer assets pixel art
│   ├── 4.2.2 Créer composants UI (Button, Input, Card, Badge, Toast, Modal)
│   ├── 4.2.3 Implémenter thème global
│   └── 📦 Livrable : Bibliothèque de composants (Storybook)
│
├── 4.3 Pages Authentification
│   ├── 4.3.1 Page inscription + Page login
│   ├── 4.3.2 Intégration OAuth (Google / Discord)
│   ├── 4.3.3 Gestion état connecté / déconnecté
│   └── 📦 Livrable : Authentification frontend fonctionnelle
│
├── 4.4 Page d'Accueil
│   ├── 4.4.1 Header avec solde et navigation
│   ├── 4.4.2 Liste des matchs du jour
│   ├── 4.4.3 Widget Top 3 leaderboard
│   └── 📦 Livrable : Page d'accueil fonctionnelle
│
├── 4.5 Parcours de Pari
│   ├── 4.5.1 Page liste matchs (filtres par jeu, cards matchs, cotes)
│   ├── 4.5.2 Composant Bet Slip (ajout/suppression, mise, calcul gains, simple/combiné)
│   ├── 4.5.3 Écran confirmation (récapitulatif, validation, feedback)
│   ├── 4.5.4 Animations pixel art
│   └── 📦 Livrable : Parcours de pari complet
│
├── 4.6 Pages Profil & Historique
│   ├── 4.6.1 Page profil (avatar, pseudo, stats, ligue)
│   ├── 4.6.2 Page historique paris (liste, filtres, détail)
│   ├── 4.6.3 Page succès (grille, progression, débloqués/verrouillés)
│   └── 📦 Livrable : Section profil fonctionnelle
│
├── 4.7 Pages Social & Compétition
│   ├── 4.7.1 Page leaderboard (ROI, filtres ligues, recherche)
│   ├── 4.7.2 Composant ligues (badge, progression)
│   ├── 4.7.3 Page Wall of Shame (anti-classement, ton humoristique)
│   ├── 4.7.4 Leaderboard équipe/club
│   └── 📦 Livrable : Section sociale fonctionnelle
│
├── 4.8 Prévention Gamifiée (UI)
│   ├── 4.8.1 Composant équivalences vie réelle
│   ├── 4.8.2 Toasts de sensibilisation
│   ├── 4.8.3 Animations succès ironiques
│   ├── 4.8.4 Affichage streaks
│   └── 📦 Livrable : Prévention gamifiée intégrée dans l'UI
│
├── 4.9 Responsive & Accessibilité
│   ├── 4.9.1 Adaptation mobile / tablet / desktop
│   ├── 4.9.2 Accessibilité (navigation clavier, contraste, labels ARIA)
│   └── 📦 Livrable : Application responsive et accessible
│
└── 4.10 Optimisation Performance
    ├── 4.10.1 Lazy loading, code splitting
    ├── 4.10.2 Optimisation images / assets
    └── 📦 Livrable : Application performante
```

---

### Phase 5 — Intégration

```
5. INTÉGRATION
│
├── 5.1 Intégration Frontend ↔ Backend
│   ├── 5.1.1 Connecter authentification
│   ├── 5.1.2 Connecter paris (simple + combiné)
│   ├── 5.1.3 Connecter économie virtuelle
│   ├── 5.1.4 Connecter matchs e-sport
│   ├── 5.1.5 Connecter leaderboard + ligues
│   ├── 5.1.6 Connecter succès + prévention
│   └── 📦 Livrable : Application intégrée end-to-end
│
├── 5.2 Intégration Temps Réel
│   ├── 5.2.1 WebSocket — notifications
│   ├── 5.2.2 WebSocket — mise à jour cotes live
│   ├── 5.2.3 WebSocket — résultats matchs temps réel
│   └── 📦 Livrable : Temps réel fonctionnel
│
├── 5.3 Tests d'Intégration
│   ├── 5.3.1 Tests E2E parcours de pari
│   ├── 5.3.2 Tests E2E authentification
│   ├── 5.3.3 Tests E2E leaderboard
│   └── 📦 Livrable : Suite de tests E2E
│
└── 5.4 Résolution Bugs d'Intégration
    ├── 5.4.1 Tracker et prioriser les bugs
    ├── 5.4.2 Corriger et re-tester
    └── 📦 Livrable : Application stable
```

---

### Phase 6 — Tests & QA

```
6. TESTS & QA
│
├── 6.1 Tests Fonctionnels
│   ├── 6.1.1 Rédiger scénarios de test
│   ├── 6.1.2 Exécuter tests manuels (inscription, pari simple, combiné, leaderboard, succès)
│   ├── 6.1.3 Documenter anomalies
│   └── 📦 Livrable : Rapport de tests fonctionnels
│
├── 6.2 Tests Utilisateurs
│   ├── 6.2.1 Recruter testeurs (5-10 utilisateurs cibles)
│   ├── 6.2.2 Sessions de test + collecte feedbacks
│   ├── 6.2.3 Analyser résultats
│   └── 📦 Livrable : Rapport de tests utilisateurs
│
├── 6.3 Tests Performance
│   ├── 6.3.1 Tests de charge API
│   ├── 6.3.2 Tests WebSocket sous charge
│   ├── 6.3.3 Tests temps de réponse
│   └── 📦 Livrable : Rapport de performance
│
├── 6.4 Tests Sécurité
│   ├── 6.4.1 Audit authentification
│   ├── 6.4.2 Tests injection SQL / XSS
│   ├── 6.4.3 Vérification rate limiting
│   └── 📦 Livrable : Rapport de sécurité
│
├── 6.5 Corrections & Itérations
│   ├── 6.5.1 Prioriser bugs par criticité
│   ├── 6.5.2 Corriger bugs critiques
│   ├── 6.5.3 Implémenter améliorations UX
│   └── 📦 Livrable : Application corrigée
│
└── 6.6 Validation Finale
    ├── 6.6.1 Checklist go / no-go
    ├── 6.6.2 Validation équipe
    └── 📦 Livrable : Feu vert déploiement
```

---

### Phase 7 — Déploiement

```
7. DÉPLOIEMENT
│
├── 7.1 Préparation Production
│   ├── 7.1.1 Configurer environnement production
│   ├── 7.1.2 Configurer domaine et SSL
│   ├── 7.1.3 Configurer CDN
│   ├── 7.1.4 Setup monitoring (logs, alertes)
│   └── 📦 Livrable : Infrastructure production prête
│
├── 7.2 Migration & Données
│   ├── 7.2.1 Migrer base de données
│   ├── 7.2.2 Seed données initiales (succès, ligues, config économie)
│   └── 📦 Livrable : Base de données production prête
│
├── 7.3 Déploiement Application
│   ├── 7.3.1 Déployer backend
│   ├── 7.3.2 Déployer frontend
│   ├── 7.3.3 Vérifier WebSockets en production
│   ├── 7.3.4 Smoke tests production
│   └── 📦 Livrable : Application en production
│
├── 7.4 Documentation & Support
│   ├── 7.4.1 Rédiger guide utilisateur
│   ├── 7.4.2 Préparer FAQ
│   ├── 7.4.3 Documenter procédures opérationnelles
│   └── 📦 Livrable : Documentation complète
│
└── 7.5 Lancement
    ├── 7.5.1 Activer accès utilisateurs
    ├── 7.5.2 Monitorer les premiers jours
    ├── 7.5.3 Collecter feedbacks early users
    └── 📦 Livrable : MVP LANCÉ
```

---

## 5. Document Fonctionnalités & Exigences

Cette section décrit chaque fonctionnalité attendue du MVP, ses exigences et critères d'acceptation, afin de faciliter leur implémentation.

### 5.1 Authentification & Gestion de Compte

#### F01 — Inscription

| Attribut        | Description                                                                         |
| --------------- | ----------------------------------------------------------------------------------- |
| **Description** | L'utilisateur peut créer un compte via email/mot de passe ou OAuth (Google/Discord) |
| **Priorité**    | Must Have                                                                           |
| **Lot WBS**     | 3.2, 4.3                                                                            |

**Exigences fonctionnelles :**

- Formulaire inscription avec email, mot de passe, pseudo
- Validation email (format, unicité)
- Mot de passe : minimum 8 caractères, 1 majuscule, 1 chiffre
- Choix d'un pseudo unique
- Attribution automatique d'un avatar pixel art par défaut
- Attribution du capital de départ en crédits virtuels à la création

**Critères d'acceptation :**

- [ ] Un utilisateur peut créer un compte avec email/mot de passe
- [ ] Un utilisateur peut créer un compte via Google OAuth
- [ ] Un utilisateur peut créer un compte via Discord OAuth
- [ ] Le pseudo est vérifié comme unique
- [ ] Le capital de départ est crédité automatiquement
- [ ] Les erreurs de validation sont affichées clairement

---

#### F02 — Connexion / Déconnexion

| Attribut        | Description                                                        |
| --------------- | ------------------------------------------------------------------ |
| **Description** | L'utilisateur peut se connecter et se déconnecter de la plateforme |
| **Priorité**    | Must Have                                                          |
| **Lot WBS**     | 3.2, 4.3                                                           |

**Exigences fonctionnelles :**

- Connexion par email/mot de passe ou OAuth
- Génération et gestion de tokens JWT
- Persistance de session (token refresh)
- Déconnexion sécurisée (invalidation du token)

**Critères d'acceptation :**

- [ ] Un utilisateur peut se connecter avec ses identifiants
- [ ] Un utilisateur peut se connecter via OAuth
- [ ] La session persiste après fermeture du navigateur
- [ ] La déconnexion invalide la session active
- [ ] Un utilisateur non connecté est redirigé vers la page de login

---

### 5.2 Système de Paris

#### F03 — Pari Simple

| Attribut        | Description                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------ |
| **Description** | L'utilisateur peut placer un pari sur l'issue d'un seul match avec une mise et une cote affichée |
| **Priorité**    | Must Have                                                                                        |
| **Lot WBS**     | 3.4, 4.5                                                                                         |

**Exigences fonctionnelles :**

- Sélection d'un match parmi les matchs à venir
- Sélection du résultat (équipe A ou équipe B)
- Saisie du montant de la mise
- Affichage de la cote et du gain potentiel en temps réel
- Validation : solde suffisant, match non commencé
- Confirmation du pari avec récapitulatif
- Pari enregistré et déduit du solde

**Critères d'acceptation :**

- [ ] L'utilisateur peut sélectionner un match et un résultat
- [ ] Le gain potentiel est affiché dynamiquement selon la mise saisie
- [ ] Le pari est refusé si le solde est insuffisant
- [ ] Le pari est refusé si le match a déjà commencé
- [ ] Un récapitulatif est affiché avant confirmation
- [ ] Le solde est mis à jour immédiatement après confirmation

---

#### F04 — Pari Combiné

| Attribut        | Description                                                                               |
| --------------- | ----------------------------------------------------------------------------------------- |
| **Description** | L'utilisateur peut combiner jusqu'à 10 sélections dans un seul pari avec une cote cumulée |
| **Priorité**    | Must Have                                                                                 |
| **Lot WBS**     | 3.4, 4.5                                                                                  |

**Exigences fonctionnelles :**

- Ajout de plusieurs sélections (matchs différents) dans un ticket
- Maximum 10 sélections par pari combiné
- Calcul automatique de la cote combinée (multiplication des cotes unitaires)
- Affichage du gain potentiel total
- Toutes les sélections doivent être gagnantes pour que le pari soit gagné
- Suppression individuelle de sélections du ticket

**Critères d'acceptation :**

- [ ] L'utilisateur peut ajouter jusqu'à 10 sélections
- [ ] La cote combinée est recalculée à chaque ajout/suppression
- [ ] L'ajout d'une 11ème sélection est bloqué
- [ ] Le gain potentiel reflète la cote combinée × la mise
- [ ] Le pari combiné est perdu si une seule sélection est perdante

---

#### F05 — Résolution des Paris

| Attribut        | Description                                                                                    |
| --------------- | ---------------------------------------------------------------------------------------------- |
| **Description** | Les paris sont automatiquement résolus après la fin d'un match, avec crédit ou débit du compte |
| **Priorité**    | Must Have                                                                                      |
| **Lot WBS**     | 3.4, 3.5                                                                                       |

**Exigences fonctionnelles :**

- Détection automatique de la fin d'un match via API e-sport
- Résolution de tous les paris liés au match
- Calcul des gains (mise × cote) pour les paris gagnants
- Crédit automatique du solde pour les paris gagnants
- Notification au joueur du résultat (gagné/perdu + montant)
- Mise à jour du statut du pari dans l'historique

**Critères d'acceptation :**

- [ ] Les paris sont résolus automatiquement sans intervention manuelle
- [ ] Les gains sont correctement calculés et crédités
- [ ] L'utilisateur reçoit une notification de résultat
- [ ] L'historique des paris reflète le statut final (gagné/perdu)
- [ ] Les paris combinés ne sont gagnés que si toutes les sélections sont correctes

---

#### F06 — Historique des Paris

| Attribut        | Description                                                                 |
| --------------- | --------------------------------------------------------------------------- |
| **Description** | L'utilisateur peut consulter l'historique complet de ses paris avec filtres |
| **Priorité**    | Must Have                                                                   |
| **Lot WBS**     | 3.4, 4.6                                                                    |

**Exigences fonctionnelles :**

- Liste chronologique de tous les paris passés
- Filtres : gagné / perdu / en cours
- Détail par pari : match, sélection, mise, cote, gain/perte, date
- Pour les paris combinés : détail de chaque sélection

**Critères d'acceptation :**

- [ ] L'historique affiche tous les paris de l'utilisateur
- [ ] Les filtres fonctionnent correctement (gagné, perdu, en cours)
- [ ] Le détail d'un pari combiné montre chaque sélection individuellement
- [ ] L'historique est paginé pour de bonnes performances

---

### 5.3 Économie Virtuelle

#### F07 — Capital de Départ

| Attribut        | Description                                                              |
| --------------- | ------------------------------------------------------------------------ |
| **Description** | Chaque utilisateur reçoit un capital de départ identique à l'inscription |
| **Priorité**    | Must Have                                                                |
| **Lot WBS**     | 3.3                                                                      |

**Exigences fonctionnelles :**

- Capital fixe identique pour tous les utilisateurs (ex: 1 000 crédits)
- Attribution automatique à la création du compte
- Montant paramétrable côté serveur (config)
- Pas de possibilité d'acheter des crédits supplémentaires

**Critères d'acceptation :**

- [ ] Tout nouvel utilisateur reçoit exactement le même montant
- [ ] Le solde est visible immédiatement après inscription
- [ ] Aucun mécanisme d'achat de crédits n'est disponible

---

#### F08 — Salaire Hebdomadaire

| Attribut        | Description                                                                           |
| --------------- | ------------------------------------------------------------------------------------- |
| **Description** | Chaque utilisateur reçoit automatiquement un versement fixe de crédits chaque semaine |
| **Priorité**    | Must Have                                                                             |
| **Lot WBS**     | 3.3                                                                                   |

**Exigences fonctionnelles :**

- Versement automatique via job CRON (ex: chaque lundi à 00h00)
- Montant fixe identique pour tous (ex: 500 crédits)
- Notification de versement à l'utilisateur
- Historique des versements dans les transactions
- Pas de plafond de cumul (les crédits non utilisés s'additionnent)

**Critères d'acceptation :**

- [ ] Le versement est effectué automatiquement chaque semaine
- [ ] Tous les utilisateurs reçoivent le même montant
- [ ] Une notification informe l'utilisateur du versement
- [ ] Le versement apparaît dans l'historique des transactions

---

#### F09 — Consultation du Solde & Transactions

| Attribut        | Description                                                                              |
| --------------- | ---------------------------------------------------------------------------------------- |
| **Description** | L'utilisateur peut consulter son solde actuel et l'historique de toutes ses transactions |
| **Priorité**    | Must Have                                                                                |
| **Lot WBS**     | 3.3, 4.4, 4.6                                                                            |

**Exigences fonctionnelles :**

- Affichage permanent du solde dans le header
- Historique : mises, gains, versements hebdomadaires
- Mise à jour en temps réel du solde (WebSocket)

**Critères d'acceptation :**

- [ ] Le solde est visible sur toutes les pages (header)
- [ ] Le solde se met à jour en temps réel après un pari ou une résolution
- [ ] L'historique des transactions est chronologique et complet

---

### 5.4 Contenus E-sport

#### F10 — Affichage des Matchs à Venir

| Attribut        | Description                                                                      |
| --------------- | -------------------------------------------------------------------------------- |
| **Description** | L'utilisateur peut consulter les matchs e-sport à venir avec les cotes associées |
| **Priorité**    | Must Have                                                                        |
| **Lot WBS**     | 3.5, 4.4, 4.5                                                                    |

**Exigences fonctionnelles :**

- Liste des matchs à venir pour les 3 jeux (LoL, Valorant, CS2)
- Informations par match : équipes, date/heure, compétition, cotes
- Filtres par jeu
- Données synchronisées automatiquement via API e-sport
- Cotes mises en cache (Redis) et mises à jour périodiquement

**Dépendances techniques :**

- ⚠️ CRITIQUE : Accès validé aux APIs Riot (LoL, Valorant) et provider tiers (CS2)

**Critères d'acceptation :**

- [ ] Les matchs s'affichent pour les 3 jeux supportés
- [ ] Les filtres par jeu fonctionnent
- [ ] Les cotes sont affichées et mises à jour
- [ ] Les informations d'équipes (nom, logo) sont affichées
- [ ] Les matchs passés ne sont plus dans la liste "à venir"

---

#### F11 — Intégration des Résultats

| Attribut        | Description                                                                                    |
| --------------- | ---------------------------------------------------------------------------------------------- |
| **Description** | Les résultats des matchs sont récupérés automatiquement pour permettre la résolution des paris |
| **Priorité**    | Must Have                                                                                      |
| **Lot WBS**     | 3.5                                                                                            |

**Exigences fonctionnelles :**

- Récupération automatique des résultats via API/provider
- Job de synchronisation périodique
- Déclenchement de la résolution des paris liés
- Gestion des cas d'erreur (match annulé, données manquantes)

**Critères d'acceptation :**

- [ ] Les résultats sont récupérés automatiquement après la fin d'un match
- [ ] La résolution des paris est déclenchée dans les minutes suivant la fin du match
- [ ] Les matchs annulés sont gérés (remboursement des mises)

---

### 5.5 Social & Compétition

#### F12 — Leaderboard par ROI

| Attribut        | Description                                                                                           |
| --------------- | ----------------------------------------------------------------------------------------------------- |
| **Description** | Classement global des utilisateurs basé sur le Return on Investment (ROI), pas sur le volume de paris |
| **Priorité**    | Must Have                                                                                             |
| **Lot WBS**     | 3.6, 4.7                                                                                              |

**Exigences fonctionnelles :**

- Calcul du ROI : `(gains totaux - mises totales) / mises totales × 100`
- Classement global de tous les utilisateurs
- Mise en cache du classement (Redis) avec rafraîchissement périodique
- Affichage : rang, pseudo, avatar, ROI, ligue
- Recherche de joueur par pseudo

**Critères d'acceptation :**

- [ ] Le classement est trié par ROI décroissant
- [ ] Le calcul du ROI est correct et vérifié
- [ ] La recherche par pseudo fonctionne
- [ ] Le classement se met à jour après résolution de paris

---

#### F13 — Top 3 sur la Page d'Accueil

| Attribut        | Description                                                                                |
| --------------- | ------------------------------------------------------------------------------------------ |
| **Description** | Les 3 meilleurs joueurs sont mis en avant sur la page d'accueil avec leur avatar pixel art |
| **Priorité**    | Must Have                                                                                  |
| **Lot WBS**     | 3.6, 4.4                                                                                   |

**Exigences fonctionnelles :**

- Widget affichant le Top 3 du leaderboard
- Affichage : avatar pixel art, pseudo, ROI
- Mise à jour automatique

**Critères d'acceptation :**

- [ ] Le Top 3 est affiché sur la page d'accueil
- [ ] Les avatars pixel art sont visibles
- [ ] Le widget reflète le classement actuel

---

#### F14 — Système de Ligues

| Attribut        | Description                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------- |
| **Description** | Les utilisateurs sont répartis en ligues (Bronze → Silver → Gold → Diamond) basées sur leur performance |
| **Priorité**    | Must Have                                                                                               |
| **Lot WBS**     | 3.6, 4.7                                                                                                |

**Exigences fonctionnelles :**

- 4 ligues : Bronze, Silver, Gold, Diamond
- Attribution basée sur le ROI et/ou le classement percentile
- Promotion/relégation périodique (hebdomadaire)
- Badge visuel de ligue sur le profil et le leaderboard
- Progression vers la ligue suivante visible

**Critères d'acceptation :**

- [ ] Chaque utilisateur est assigné à une ligue
- [ ] Les promotions/relégations s'effectuent automatiquement
- [ ] Le badge de ligue est visible sur le profil et le leaderboard
- [ ] La progression vers la ligue suivante est affichée

---

#### F15 — Wall of Shame

| Attribut        | Description                                                                                                 |
| --------------- | ----------------------------------------------------------------------------------------------------------- |
| **Description** | Anti-classement humoristique mettant en avant les plus grosses pertes, avec un ton ironique et bienveillant |
| **Priorité**    | Must Have                                                                                                   |
| **Lot WBS**     | 3.6, 4.7                                                                                                    |

**Exigences fonctionnelles :**

- Classement inversé (pires ROI en premier)
- Ton humoristique assumé (pas de jugement négatif)
- Intégré comme une section du leaderboard
- Complémentaire au Wall of Fame (leaderboard principal)

**Critères d'acceptation :**

- [ ] Le Wall of Shame affiche les utilisateurs avec le pire ROI
- [ ] Le ton est humoristique et non humiliant
- [ ] L'accès est intégré dans la navigation du leaderboard

---

#### F16 — Leaderboard Équipe / Club

| Attribut        | Description                                                                     |
| --------------- | ------------------------------------------------------------------------------- |
| **Description** | Classement par équipe/club permettant la compétition entre groupes (ex: écoles) |
| **Priorité**    | Must Have                                                                       |
| **Lot WBS**     | 3.6, 4.7                                                                        |

**Exigences fonctionnelles :**

- Possibilité de rejoindre une équipe/club
- Calcul du ROI agrégé de l'équipe
- Classement des équipes

**Critères d'acceptation :**

- [ ] Un utilisateur peut rejoindre une équipe
- [ ] Le classement par équipe est calculé et affiché
- [ ] Le ROI équipe est une agrégation des ROI individuels

---

### 5.6 Prévention Gamifiée

#### F17 — Succès Ironiques

| Attribut        | Description                                                                                               |
| --------------- | --------------------------------------------------------------------------------------------------------- |
| **Description** | Système de badges/succès intégrant des récompenses ironiques qui sensibilisent aux comportements à risque |
| **Priorité**    | Must Have                                                                                                 |
| **Lot WBS**     | 3.7, 4.6, 4.8                                                                                             |

**Exigences fonctionnelles :**

Succès de prévention (MVP) :

| Succès                 | Condition de déblocage                       |
| ---------------------- | -------------------------------------------- |
| "Flambeur Express"     | Salaire hebdomadaire dépensé en moins de 24h |
| "Économe"              | Terminer la semaine avec > 80% du salaire    |
| "Self-Made"            | Doubler son capital sur une semaine          |
| "Le Lundi Noir"        | Tout perdre le jour du versement             |
| "Millionnaire Virtuel" | Atteindre 10× le capital de départ           |
| "Yolo King"            | Miser 100% de son solde sur un seul pari     |

- Notification de déblocage avec animation pixel art
- Succès visibles sur le profil (grille débloqués/verrouillés)
- Les succès de prévention sont intégrés parmi les succès classiques (pas de catégorie séparée)

**Critères d'acceptation :**

- [ ] Chaque succès se débloque automatiquement quand la condition est remplie
- [ ] Une notification avec animation est affichée au déblocage
- [ ] Les succès sont visibles sur la page profil
- [ ] Les succès de prévention ne sont pas isolés dans une catégorie "prévention"

---

#### F18 — Streaks (Séries)

| Attribut        | Description                                                                                  |
| --------------- | -------------------------------------------------------------------------------------------- |
| **Description** | Suivi des séries de comportement (responsable ou à risque) pour renforcer la sensibilisation |
| **Priorité**    | Must Have                                                                                    |
| **Lot WBS**     | 3.7, 4.8                                                                                     |

**Exigences fonctionnelles :**

- Streak "responsable" : nombre de jours consécutifs avec une gestion saine (pas de all-in, mises raisonnables)
- Streak "pertes" : nombre de paris perdus consécutifs
- Affichage sur le profil
- Notification à certains paliers (ex: 5 pertes consécutives)

**Critères d'acceptation :**

- [ ] Les streaks sont calculés automatiquement
- [ ] L'affichage est clair et non moralisateur
- [ ] Des notifications sont envoyées aux paliers définis

---

#### F19 — Équivalences Vie Réelle

| Attribut        | Description                                                                                                     |
| --------------- | --------------------------------------------------------------------------------------------------------------- |
| **Description** | Conversion des gains/pertes en crédits vers des équivalents de la vie réelle pour rendre les montants tangibles |
| **Priorité**    | Must Have                                                                                                       |
| **Lot WBS**     | 3.7, 4.8                                                                                                        |

**Exigences fonctionnelles :**

- Conversion automatique : crédits → objets du quotidien
- Exemples : "Tu viens de perdre 3 kebabs", "Tu as gagné 1 mois de Netflix"
- Affichage dans les notifications de résultat de pari
- Table de conversion paramétrable côté serveur

**Critères d'acceptation :**

- [ ] L'équivalence est affichée après chaque résolution de pari
- [ ] Les conversions sont cohérentes et pertinentes
- [ ] L'affichage est intégré naturellement dans l'UI (pas intrusif)

---

#### F20 — Notifications de Sensibilisation

| Attribut        | Description                                                                        |
| --------------- | ---------------------------------------------------------------------------------- |
| **Description** | Toasts et notifications intégrées qui sensibilisent aux biais cognitifs du parieur |
| **Priorité**    | Must Have                                                                          |
| **Lot WBS**     | 3.7, 4.8                                                                           |

**Exigences fonctionnelles :**

- Notifications contextuelles déclenchées par des comportements spécifiques
- Exemples de déclencheurs : all-in, 3ème pari perdu consécutif, mise supérieure à 50% du solde
- Ton humoristique et bienveillant (pas moralisateur)
- Unifiées avec les notifications classiques (pas de catégorie désactivable séparément)

**Critères d'acceptation :**

- [ ] Les notifications apparaissent au bon moment
- [ ] Le ton est adapté (humour, ironie bienveillante)
- [ ] Les notifications ne peuvent pas être désactivées indépendamment
- [ ] Elles ne bloquent pas l'expérience utilisateur (non-modales)

---

### 5.7 Interface & Expérience Utilisateur

#### F21 — Direction Artistique Pixel Art 80s

| Attribut        | Description                                                                      |
| --------------- | -------------------------------------------------------------------------------- |
| **Description** | Identité visuelle cohérente inspirée de l'arcade 80s avec des éléments pixel art |
| **Priorité**    | Must Have                                                                        |
| **Lot WBS**     | 2.1, 4.2                                                                         |

**Exigences fonctionnelles :**

- Palette de couleurs définie (arcade/néon)
- Typographie pixel cohérente
- Icônes et éléments UI en pixel art
- Composants UI cohérents (boutons, cards, badges, toasts, modales)
- Design System documenté

**Critères d'acceptation :**

- [ ] L'ensemble de l'application respecte la direction artistique
- [ ] Un Design System documenté est disponible
- [ ] Les composants sont réutilisables et cohérents

---

#### F22 — Responsive Mobile-First

| Attribut        | Description                                                                  |
| --------------- | ---------------------------------------------------------------------------- |
| **Description** | L'application est conçue mobile-first et s'adapte à tous les formats d'écran |
| **Priorité**    | Must Have                                                                    |
| **Lot WBS**     | 2.4, 4.9                                                                     |

**Exigences fonctionnelles :**

- Design mobile-first (priorité smartphone)
- 3 breakpoints : mobile, tablet, desktop
- Navigation adaptée à chaque format
- Accessibilité de base (WCAG AA) : contraste, navigation clavier, labels ARIA

**Critères d'acceptation :**

- [ ] L'application est utilisable sur mobile (320px minimum)
- [ ] L'application s'adapte aux écrans tablet et desktop
- [ ] La navigation est intuitive sur chaque format
- [ ] Le contraste respecte le ratio WCAG AA (4.5:1)
- [ ] La navigation clavier est fonctionnelle

---

### 5.8 Infrastructure Technique

#### F23 — API REST Backend

| Attribut        | Description                                                 |
| --------------- | ----------------------------------------------------------- |
| **Description** | API REST documentée exposant l'ensemble des services métier |
| **Priorité**    | Must Have                                                   |
| **Lot WBS**     | 3.1 à 3.8                                                   |

**Exigences fonctionnelles :**

- Endpoints RESTful pour tous les modules (auth, paris, économie, matchs, social, succès)
- Authentification par JWT sur les endpoints protégés
- Validation des entrées
- Rate limiting
- Documentation Swagger / OpenAPI

**Critères d'acceptation :**

- [ ] Tous les endpoints sont documentés et accessibles
- [ ] L'authentification JWT fonctionne
- [ ] Les erreurs retournent des codes HTTP appropriés
- [ ] Le rate limiting est configuré

---

#### F24 — Temps Réel (WebSockets)

| Attribut        | Description                                                            |
| --------------- | ---------------------------------------------------------------------- |
| **Description** | Communication en temps réel pour les notifications, cotes et résultats |
| **Priorité**    | Must Have                                                              |
| **Lot WBS**     | 3.1, 5.2                                                               |

**Exigences fonctionnelles :**

- Connexion WebSocket authentifiée
- Canaux : notifications personnelles, mise à jour des cotes, résultats matchs
- Reconnexion automatique en cas de déconnexion
- Fallback en cas d'indisponibilité (polling)

**Critères d'acceptation :**

- [ ] Les notifications arrivent en temps réel
- [ ] Les cotes se mettent à jour sans rechargement de page
- [ ] La connexion se rétablit automatiquement après une coupure

---

#### F25 — Pipeline CI/CD

| Attribut        | Description                                                                          |
| --------------- | ------------------------------------------------------------------------------------ |
| **Description** | Pipeline d'intégration et déploiement continu pour automatiser tests et déploiements |
| **Priorité**    | Must Have                                                                            |
| **Lot WBS**     | 1.4, 7.1                                                                             |

**Exigences fonctionnelles :**

- Exécution automatique des tests à chaque push/PR
- Build automatique
- Déploiement automatique vers staging et production
- Rollback possible en cas de problème

**Critères d'acceptation :**

- [ ] Les tests s'exécutent automatiquement sur chaque PR
- [ ] Le déploiement vers staging est automatisé
- [ ] Le déploiement en production nécessite une validation manuelle
- [ ] Le rollback est documenté et fonctionnel

---

## 6. Dépendances et chemin critique

### 6.1 Graphe de dépendances entre phases

```
Phase 1 ──────► Phase 2 ──────► Phase 4 ──────┐
(Discovery)    (Design)        (Frontend)      │
    │                                          ├──► Phase 5 ──► Phase 6 ──► Phase 7
    │                                          │    (Intégr.)   (Tests)    (Deploy)
    └──────────────────────► Phase 3 ──────────┘
                             (Backend)
```

### 6.2 Chemin critique

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          CHEMIN CRITIQUE                                     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  1.1 Validation API  ──►  3.5 Module E-sport  ──►  5.2 Temps réel         │
│        │                                                                    │
│        ▼                                                                    │
│   ⚠️  BLOQUANT : Si API non validées, scope MVP compromis                  │
│        │                                                                    │
│        ▼                                                                    │
│   Plan B : Réduire le nombre de jeux OU données manuelles/mock             │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.3 Matrice des dépendances inter-lots

| Lot dépendant      | Dépend de          | Nature                                                               |
| ------------------ | ------------------ | -------------------------------------------------------------------- |
| 3.4 (Paris)        | 3.3 (Économie)     | Le pari nécessite la validation du solde                             |
| 3.4 (Paris)        | 3.5 (E-sport)      | Le pari nécessite les matchs et cotes                                |
| 3.6 (Social)       | 3.4 (Paris)        | Le leaderboard nécessite les résultats de paris pour calculer le ROI |
| 3.7 (Succès)       | 3.3 + 3.4          | Les succès analysent le comportement économique et de pari           |
| 4.\* (Frontend)    | 2.\* (Design)      | L'implémentation UI nécessite les maquettes validées                 |
| 5.\* (Intégration) | 3._ + 4._          | L'intégration nécessite backend et frontend fonctionnels             |
| 6.\* (Tests)       | 5.\* (Intégration) | Les tests QA nécessitent l'application intégrée                      |
| 7.\* (Déploiement) | 6.6 (Validation)   | Le déploiement nécessite le feu vert QA                              |

---

## 7. Dictionnaire du WBS

Le dictionnaire du WBS fournit une description synthétique de chaque lot de travail de niveau 2.

| ID   | Lot de travail             | Description                                                                | Livrable principal             |
| ---- | -------------------------- | -------------------------------------------------------------------------- | ------------------------------ |
| 1.1  | Validation données e-sport | Tester et valider l'accès aux API Riot et providers CS2                    | Rapport de faisabilité API     |
| 1.2  | Cadrage fonctionnel        | Finaliser les spécifications MVP et paramètres économiques                 | Backlog priorisé               |
| 1.3  | Architecture technique     | Choisir le stack et concevoir l'architecture système                       | Dossier d'architecture         |
| 1.4  | Setup projet               | Mettre en place les repositories, CI/CD et conventions                     | Environnement dev opérationnel |
| 2.1  | Design System              | Créer l'identité visuelle pixel art 80s et les composants de base          | Design System documenté        |
| 2.2  | Maquettes parcours clés    | Concevoir les maquettes de toutes les pages et parcours                    | Maquettes Figma                |
| 2.3  | Design prévention          | Concevoir les visuels spécifiques à la prévention gamifiée                 | Assets prévention              |
| 2.4  | Responsive                 | Adapter les maquettes aux 3 formats (mobile, tablet, desktop)              | Maquettes responsive           |
| 2.5  | Validation design          | Tester et valider les maquettes avec des utilisateurs                      | Maquettes validées             |
| 3.1  | Infrastructure backend     | Mettre en place serveur, BDD, cache et WebSockets                          | Infrastructure opérationnelle  |
| 3.2  | Module Auth                | Développer l'API d'authentification (email, OAuth, JWT)                    | API Auth                       |
| 3.3  | Module Économie            | Développer la gestion des crédits et du salaire hebdomadaire               | API Économie                   |
| 3.4  | Module Paris               | Développer le système de paris simple, combiné et résolution               | API Paris                      |
| 3.5  | Module E-sport             | Intégrer les API e-sport et synchroniser matchs/résultats                  | API Matchs                     |
| 3.6  | Module Social              | Développer leaderboard, ligues, Wall of Shame                              | API Social                     |
| 3.7  | Module Succès              | Développer les succès, streaks et équivalences vie réelle                  | API Succès                     |
| 3.8  | Documentation API          | Documenter tous les endpoints (Swagger/OpenAPI)                            | Documentation API              |
| 4.1  | Setup frontend             | Initialiser le projet et configurer l'architecture frontend                | Squelette frontend             |
| 4.2  | Design System UI           | Implémenter les composants du Design System en code                        | Storybook composants           |
| 4.3  | Auth frontend              | Développer les pages d'inscription et connexion                            | Auth frontend fonctionnelle    |
| 4.4  | Page d'accueil             | Développer la page d'accueil (matchs, top 3, solde)                        | Home fonctionnelle             |
| 4.5  | Parcours pari              | Développer le parcours complet de pari (liste, bet slip, confirmation)     | Parcours pari fonctionnel      |
| 4.6  | Profil & Historique        | Développer les pages profil, historique et succès                          | Section profil fonctionnelle   |
| 4.7  | Social frontend            | Développer les pages leaderboard, ligues, Wall of Shame                    | Section sociale fonctionnelle  |
| 4.8  | Prévention UI              | Intégrer les équivalences, toasts, animations de prévention                | Prévention intégrée dans l'UI  |
| 4.9  | Responsive & A11y          | Adapter l'application aux 3 formats + accessibilité WCAG                   | App responsive et accessible   |
| 4.10 | Performance                | Optimiser le chargement et les performances (lazy loading, code splitting) | App performante                |
| 5.1  | Intégration F/B            | Connecter tous les modules frontend aux API backend                        | Application intégrée           |
| 5.2  | Temps réel                 | Implémenter les WebSockets (notifications, cotes, résultats)               | Temps réel fonctionnel         |
| 5.3  | Tests intégration          | Écrire et exécuter les tests E2E                                           | Suite tests E2E                |
| 5.4  | Bug fixing                 | Tracker, prioriser et corriger les bugs d'intégration                      | Application stable             |
| 6.1  | Tests fonctionnels         | Tester manuellement tous les parcours utilisateur                          | Rapport tests fonctionnels     |
| 6.2  | Tests utilisateurs         | Organiser des sessions de test avec 5-10 utilisateurs cibles               | Rapport tests utilisateurs     |
| 6.3  | Tests performance          | Tester la charge API et WebSocket                                          | Rapport performance            |
| 6.4  | Tests sécurité             | Auditer l'authentification, tester injections et XSS                       | Rapport sécurité               |
| 6.5  | Corrections                | Corriger les bugs et implémenter les améliorations UX                      | Application corrigée           |
| 6.6  | Validation finale          | Go/no-go pour le déploiement                                               | Feu vert déploiement           |
| 7.1  | Préparation prod           | Configurer environnement, domaine, SSL, CDN, monitoring                    | Infrastructure prod prête      |
| 7.2  | Migration données          | Migrer la BDD et insérer les données initiales                             | BDD production prête           |
| 7.3  | Déploiement                | Déployer backend, frontend et vérifier en production                       | Application en production      |
| 7.4  | Documentation              | Rédiger guide utilisateur, FAQ et procédures ops                           | Documentation complète         |
| 7.5  | Lancement                  | Ouvrir l'accès, monitorer et collecter les feedbacks                       | MVP lancé                      |

---

## 8. Synthèse des livrables

### 8.1 Livrables par phase

| Phase               | Livrables clés                                                                               |
| ------------------- | -------------------------------------------------------------------------------------------- |
| **1 — Discovery**   | Rapport faisabilité API, Backlog priorisé, Dossier architecture, Environnement dev           |
| **2 — Design**      | Design System, Maquettes Figma, Assets prévention, Maquettes responsive validées             |
| **3 — Backend**     | API Auth, API Économie, API Paris, API Matchs, API Social, API Succès, Documentation API     |
| **4 — Frontend**    | Storybook, Auth, Home, Parcours pari, Profil, Social, Prévention UI, App responsive          |
| **5 — Intégration** | Application intégrée, Temps réel, Suite tests E2E, Application stable                        |
| **6 — Tests & QA**  | Rapports (fonctionnels, utilisateurs, performance, sécurité), Application corrigée, Feu vert |
| **7 — Déploiement** | Infrastructure prod, BDD prod, Application en production, Documentation, **MVP lancé**       |

### 8.2 Statistiques du WBS

| Métrique                             | Valeur                                       |
| ------------------------------------ | -------------------------------------------- |
| Nombre de phases                     | 7                                            |
| Nombre de lots de travail (niveau 2) | 36                                           |
| Nombre de tâches (niveau 3)          | ~130                                         |
| Nombre de livrables identifiés       | 36                                           |
| Nombre de fonctionnalités décrites   | 25                                           |
| Chemin critique identifié            | Validation API → Module E-sport → Temps réel |

---

_Document généré le 31 janvier 2026 — Projet Bet Arena, Epitech_
