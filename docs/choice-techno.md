# BetArena - Documentation Technique

## Présentation du Projet

**BetArena** est une application mobile spécialisée dans les paris fictifs Esport, intégrant une monnaie virtuelle basée sur la blockchain Ethereum. L'application permet aux utilisateurs de parier sur des matchs Esport en utilisant des tokens décentralisés, offrant une expérience immersive et sécurisée.

---

## Architecture Globale

L'architecture de BetArena repose sur une approche modulaire et scalable, séparant clairement les responsabilités entre les différentes couches applicatives :

```
┌─────────────────────────────────────────────────────────────┐
│                    FRONTEND MOBILE                          │
│                   React Native (TS)                         │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       │ REST API / WebSocket
                       │
┌──────────────────────▼──────────────────────────────────────┐
│                    BACKEND API                              │
│                    Node.js (TS)                             │
│  ┌─────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Express   │  │  WebSocket   │  │    Auth      │      │
│  │   Routes    │  │   Service    │  │   Service    │      │
│  └─────────────┘  └──────────────┘  └──────────────┘      │
└──────────────┬──────────────┬───────────────┬──────────────┘
               │              │               │
               │              │               │
   ┌───────────▼──┐    ┌──────▼─────┐   ┌────▼──────────┐
   │  PostgreSQL  │    │   Python    │   │  Blockchain   │
   │   Database   │    │ Data Layer  │   │   Ethereum    │
   └──────────────┘    └─────┬───────┘   │  Solidity(TS) │
                             │           └───────────────┘
                       ┌─────▼──────┐
                       │    n8n     │
                       │ Automation │
                       └────────────┘

              DevOps: Docker + GitHub Actions
```

---

## Choix Technologiques

### 1. Frontend Mobile - React Native (TypeScript)

#### Justification
- **Cross-platform** : Un seul codebase pour iOS et Android, réduisant les coûts et le temps de développement
- **TypeScript** : Typage fort garantissant la robustesse du code et réduisant les erreurs runtime
- **Écosystème riche** : Nombreuses bibliothèques pour l'intégration Web3 (ethers.js, web3.js)
- **Performance native** : Rendu proche des applications natives grâce au bridge React Native
- **Hot Reload** : Accélération du cycle de développement

#### Adéquation avec les besoins
- Interface réactive pour afficher les cotes en temps réel
- Gestion des états complexes (paris, solde, historique) via Zustand
- Navigation fluide entre les différentes sections (matchs, portefeuille, profil)
- Intégration facile avec les wallets Ethereum (MetaMask Mobile, WalletConnect)

### 2. State Management - Zustand (avec Redux Toolkit en alternative)

#### Justification
- **Zustand** : Bibliothèque ultra-légère pour la gestion d'état
- **API Simplifiée** : Moins de boilerplate que Redux traditionnel
- **TypeScript natif** : Support TypeScript excellent avec inférence de types
- **Performance** : Re-renders optimisés, pas de Context Provider nécessaire
- **DevTools** : Intégration avec Redux DevTools pour le debugging
- **Scalabilité** : Architecture modulaire permettant de séparer les stores par domaine

#### Alternative - Redux Toolkit
- **Standard industriel** : Largement adopté dans l'écosystème React
- **Toolkit moderne** : Redux Toolkit simplifie considérablement l'utilisation classique de Redux
- **Middleware riche** : Redux Thunk, Redux Saga pour la gestion asynchrone
- **Écosystème mature** : Nombreuses extensions (Redux Persist, etc.)

#### Choix recommandé : Zustand
Pour BetArena, **Zustand** est privilégié car :
- Application mobile nécessitant des performances optimales
- Simplicité de maintenance pour une équipe réduite
- Courbe d'apprentissage rapide
- Bundle size minimal (critique pour le mobile)

#### Adéquation avec les besoins
- **Gestion du portefeuille** : Store dédié pour le solde, tokens, transactions
- **État des paris** : Suivi en temps réel des paris actifs et historique
- **Données utilisateur** : Profil, préférences, authentification (JWT)
- **Cache des matchs** : Données des matchs en cours et à venir
- **WebSocket state** : Synchronisation des updates en temps réel (cotes, résultats)
- **Persistance** : Sauvegarde locale avec AsyncStorage pour l'offline mode

### 3. Backend API - Node.js (TypeScript)

#### Justification
- **JavaScript/TypeScript** : Cohérence technologique avec le frontend
- **Asynchrone** : Gestion optimale des connexions simultanées (WebSocket pour live updates)
- **NPM Ecosystem** : Accès à des milliers de packages (Web3, crypto, APIs Esport)
- **Performance** : Event Loop efficace pour les I/O intensives
- **Microservices ready** : Facilité de découpage en services si nécessaire

#### Adéquation avec les besoins
- API RESTful pour les opérations CRUD (utilisateurs, paris, matchs)
- WebSocket pour les mises à jour en temps réel des cotes et résultats
- Interaction avec les smart contracts Ethereum via web3.js/ethers.js
- Gestion de l'authentification JWT et des sessions utilisateur
- Orchestration entre la blockchain et la base de données

### 4. Web3 - Solidity (TypeScript)

#### Justification
- **Solidity** : Langage de référence pour les smart contracts Ethereum
- **TypeScript (Hardhat/Ethers)** : Développement, tests et déploiement des contrats
- **Sécurité** : Contrats audités et testés pour gérer les tokens et transactions
- **Transparence** : Toutes les transactions sont vérifiables on-chain

#### Adéquation avec les besoins
- **Token ERC-20** : Création de la monnaie fictive BetArena (BETA)
- **Smart Contracts** : Gestion décentralisée des paris et des récompenses
- **Immutabilité** : Garantie de non-manipulation des résultats
- **Interopérabilité** : Possibilité d'intégrer avec d'autres DApps Ethereum

### 5. Data - Python

#### Justification
- **Analyse de données** : Bibliothèques puissantes (Pandas, NumPy, Scikit-learn)
- **Machine Learning** : Prédiction des cotes et analyse des tendances
- **Web Scraping** : Récupération des données Esport depuis diverses sources
- **Data Science** : Traitement et nettoyage des données brutes

#### Adéquation avec les besoins
- Calcul dynamique des cotes basé sur les statistiques historiques
- Détection des anomalies et prévention de la fraude
- Génération de rapports et analytics pour l'administration
- Intégration d'APIs Esport (Riot Games, PandaScore, etc.)

### 6. Automatisation - n8n

#### Justification
- **Low-code** : Création de workflows sans code complexe
- **Open-source** : Pas de dépendance à des services payants
- **Intégrations** : Connexion facile avec APIs, databases, webhooks
- **Self-hosted** : Contrôle total sur les automatisations sensibles

#### Adéquation avec les besoins
- Mise à jour automatique des résultats de matchs
- Notifications push pour les utilisateurs (début de match, gains)
- Synchronisation entre les données Esport et la base de données
- Tâches planifiées (distribution de tokens quotidiens, clôture des paris)

### 7. DevOps - Docker & GitHub Actions

#### Justification Docker
- **Containerisation** : Environnements reproductibles (dev/staging/prod)
- **Isolation** : Chaque service dans son propre container
- **Scalabilité** : Déploiement facile sur Kubernetes ou Docker Swarm
- **Multi-plateforme** : Même environnement sur Windows, Linux, macOS

#### Justification GitHub Actions
- **CI/CD natif** : Intégration directe avec le repository Git
- **Automatisation** : Tests automatiques à chaque push/PR
- **Déploiement continu** : Mise en production automatique après validation
- **Gratuit** : Pour les projets publics et limité pour les privés

#### Adéquation avec les besoins
- Pipeline CI/CD complet (build → test → deploy)
- Tests automatisés du backend, frontend et smart contracts
- Déploiement automatique sur environnement de staging
- Gestion des secrets (clés API, private keys) via GitHub Secrets

### 8. Base de Données - PostgreSQL

#### Justification
- **ACID** : Garantie de cohérence des transactions (crucial pour les paris)
- **Relations** : Modèle relationnel adapté aux liens utilisateurs/paris/matchs
- **Performance** : Indexes, requêtes complexes optimisées
- **JSON Support** : Stockage de données semi-structurées si nécessaire
- **Open-source** : Pas de coûts de licence, communauté active

#### Adéquation avec les besoins
- Gestion des utilisateurs et authentification
- Historique complet des paris et transactions
- Stockage des données de matchs et équipes
- Relations complexes (many-to-many entre utilisateurs et paris)
- Intégrité référentielle garantie

### 9. ORM - Prisma

#### Justification
- **Type-safe** : Génération automatique de types TypeScript à partir du schéma de base de données
- **Developer Experience** : Autocomplétion intelligente et détection d'erreurs au moment du développement
- **Migrations** : Système de migrations déclaratif et versionnement automatique du schéma
- **Prisma Client** : API intuitive et moderne pour interagir avec la base de données
- **Prisma Studio** : Interface graphique pour visualiser et éditer les données
- **Performance** : Requêtes optimisées et support du batching automatique

#### Avantages par rapport aux alternatives
- **vs TypeORM** : Meilleure inférence de types, API plus simple, migrations plus fiables
- **vs Sequelize** : Type-safety native, pas besoin de synchronisation manuelle des types
- **vs SQL brut** : Sécurité accrue (protection contre SQL injection), code plus maintenable

#### Adéquation avec les besoins BetArena
- **Modélisation des relations complexes** : Users ↔ Bets ↔ Matches ↔ Teams
- **Transactions ACID** : Support natif des transactions pour les opérations critiques (paris, paiements)
- **Requêtes complexes** : API fluide pour les jointures et agrégations (statistiques, historiques)
- **Seed data** : Facilité de peuplement de la base avec des données initiales (matchs, équipes)
- **Type-safety end-to-end** : Depuis le schéma DB jusqu'au frontend via les API types

#### Fonctionnalités clés utilisées
- **Relations bidirectionnelles** : Navigation facile entre utilisateurs, paris et matchs
- **Prisma Migrate** : Gestion automatique des changements de schéma en production
- **Prisma Client** : Requêtes type-safe avec autocomplétion

#### Intégration avec le stack
- **Backend Node.js** : Import direct du Prisma Client dans les services
- **PostgreSQL** : Prisma gère automatiquement les connexions et le pooling
- **TypeScript** : Types générés synchronisés avec le schéma de base de données
- **CI/CD** : Migrations automatiques dans le pipeline de déploiement
- **Testing** : Facilité de création d'une base de test isolée

#### Sécurité et Performance
- **Prepared Statements** : Protection native contre les injections SQL
- **Connection Pooling** : Gestion optimale des connexions à PostgreSQL
- **Query Optimization** : Prisma génère des requêtes SQL optimisées
- **Soft Deletes** : Implémentation facile pour conserver l'historique
- **Row Level Security** : Compatible avec les politiques de sécurité PostgreSQL

--------------

## Stratégie de Tests

### Frontend Mobile (React Native)
- **Jest** : Tests unitaires des composants et fonctions
- **React Native Testing Library** : Tests d'intégration des composants
- **Detox** : Tests E2E sur simulateurs iOS/Android
- **TypeScript** : Vérification statique des types

### Backend (Node.js)
- **Jest** : Tests unitaires des services et controllers
- **Supertest** : Tests d'intégration des routes API
- **Mock** : Simulation des appels blockchain et base de données
- **ESLint** : Analyse statique du code

### ORM (Prisma)
- **Prisma Client Mock** : Tests unitaires sans base de données réelle
- **Test Database** : Base PostgreSQL dédiée pour les tests d'intégration
- **Seed Scripts** : Données de test cohérentes et reproductibles
- **Migration Testing** : Validation des migrations avant déploiement

### Smart Contracts (Solidity)
- **Hardhat** : Framework de test des contrats
- **Waffle/Chai** : Assertions spécifiques Ethereum
- **Coverage** : Couverture de code à 100% pour les contrats critiques
- **Testnet** : Déploiement sur Goerli/Sepolia avant mainnet

### Data Layer (Python)
- **Pytest** : Tests unitaires des scripts d'analyse
- **Mock APIs** : Simulation des réponses des APIs Esport
- **Data Validation** : Vérification de l'intégrité des données

### CI/CD
- **Automatisation** : Exécution de tous les tests à chaque commit
- **Quality Gates** : Merge bloqué si tests en échec
- **Code Coverage** : Objectif minimum de 80% de couverture

---

## Flux de Données Critiques

### 1. Placement d'un Pari
```
User (Mobile) → Backend API → Vérification (DB) 
              → Smart Contract (Ethereum) → Confirmation
              → Mise à jour DB → Notification (n8n) → User
```

### 2. Résolution d'un Match
```
Python Scraper → API Esport → n8n Workflow → Backend API
              → Smart Contract (distribution rewards)
              → Mise à jour DB → Push Notification → Users
```

### 3. Calcul des Cotes
```
Python Analytics → Données historiques (PostgreSQL)
                → ML Model → Cotes ajustées
                → Backend API → Cache Redis → Frontend Mobile
```

---

## Sécurité

- **Smart Contracts** : Audits de sécurité, utilisation d'OpenZeppelin
- **Backend** : Rate limiting, validation des inputs, JWT sécurisés
- **Database** : Requêtes paramétrées (prévention SQL Injection)
- **Frontend** : Stockage sécurisé des clés privées (Keychain/Keystore)
- **DevOps** : Secrets chiffrés, HTTPS obligatoire, CORS configuré

---

## Scalabilité

- **Horizontal Scaling** : Réplication des containers Docker
- **Database** : Read replicas PostgreSQL pour les lectures intensives
- **Caching** : Redis pour les données fréquemment consultées (cotes, matchs)
- **CDN** : Delivery des assets statiques via CDN
- **Blockchain** : Layer 2 (Polygon, Arbitrum) pour réduire les frais gas

---

## Conclusion

Le stack technologique de **BetArena** a été soigneusement sélectionné pour répondre aux exigences d'une application moderne intégrant la blockchain :

- **Performance** : Architecture asynchrone et optimisée
- **Sécurité** : Smart contracts audités et backend sécurisé
- **Scalabilité** : Infrastructure containerisée et modulaire
- **Maintenabilité** : TypeScript partout, tests automatisés
- **Innovation** : Intégration blockchain pour transparence et décentralisation

Cette stack permet de livrer une expérience utilisateur fluide tout en garantissant l'intégrité et la sécurité des paris fictifs sur Esport.
