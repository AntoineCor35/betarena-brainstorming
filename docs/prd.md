# Bet Arena — Product Requirements Document (PRD)

> **Date de création :** 2 février 2026
> **Version :** 0.1
> **Auteur :** John (PM)
> **Mode :** Interactive

---

## 1. Goals and Background Context

### Goals

- Offrir aux fans d'e-sport français une plateforme de paris simulés, légale et sans argent réel, capturant le frisson du betting
- Éduquer les utilisateurs sur les biais cognitifs et comportements à risque du parieur via une gamification intégrée (prévention par l'expérience, pas par l'interdiction)
- Créer une communauté compétitive saine autour de la prédiction e-sport (leaderboards, ligues, succès) pour les étudiants et jeunes adultes
- Livrer un MVP fonctionnel couvrant 3 jeux e-sport (LoL, Valorant, CS2) avec paris simples et combinés, alimenté par les API PandaScore et Liquipedia
- Démontrer une identité visuelle pixel art arcade 80s qui différencie clairement Bet Arena des bookmakers classiques
- Valider le concept dans le cadre d'un projet Epitech avec des livrables académiques associés

### Background Context

Bet Arena naît d'un double constat : le betting e-sport est interdit en France, poussant les fans vers des solutions VPN risquées, et aucune alternative légale ne combine engagement ludique, compétition sociale et éducation préventive. Les solutions existantes (bookmakers, Unikrn, simulateurs génériques) échouent toutes à réunir ces dimensions simultanément.

Le projet s'appuie sur un système de crédits virtuels exclusifs (capital de départ + salaire hebdomadaire) qui garantit l'absence de risque financier tout en créant une tension stratégique. L'accès aux données e-sport est sécurisé via PandaScore et Liquipedia, levant le bloqueur critique identifié lors du brainstorming. Le contexte Epitech fournit le cadre pour explorer ces enjeux de manière éthique et éducative.

### Change Log

| Date | Version | Description | Author |
|------|---------|-------------|--------|
| 2026-02-02 | 0.1 | Création initiale du PRD | John (PM) |

---

## 2. Requirements

### Functional Requirements

**Authentification & Compte**
- **FR1:** Le système permet la création de compte via email ou OAuth (Google)
- **FR2:** Le système permet la connexion/déconnexion sécurisée des utilisateurs
- **FR3:** Chaque utilisateur dispose d'un profil avec pseudo et avatar pixel art par défaut

**Système de Paris**
- **FR4:** L'utilisateur peut placer un pari simple sur un match e-sport à venir (sélection d'une équipe + montant en crédits)
- **FR5:** L'utilisateur peut placer un pari combiné regroupant jusqu'à 10 sélections, avec calcul automatique de la cote combinée
- **FR6:** Le système calcule et affiche les cotes pour chaque match disponible, basées sur l'historique des équipes
- **FR7:** Le système résout automatiquement les paris après la fin d'un match (gain ou perte de crédits)
- **FR8:** L'utilisateur peut consulter son historique complet de paris (résultats, montants, cotes, gains/pertes)

**Économie Virtuelle**
- **FR9:** Chaque nouvel utilisateur reçoit un capital de départ identique en crédits virtuels
- **FR10:** Chaque utilisateur reçoit un salaire hebdomadaire fixe en crédits virtuels (recharge automatique)
- **FR11:** L'utilisateur peut consulter son solde de crédits à tout moment
- **FR12:** Aucun achat de crédits avec de l'argent réel n'est possible (économie fermée)

**Contenus E-sport & Données**
- **FR13:** Le système affiche un tableau des matchs e-sport à venir avec équipes, date/heure et cotes
- **FR14:** Le système supporte 3 jeux e-sport au MVP : League of Legends, Valorant et CS2
- **FR15:** Les données de matchs sont alimentées via PandaScore (calendrier, pré-match) et Liquipedia (résultats, historique équipes)
- **FR16:** Les résultats des matchs sont mis à jour automatiquement après leur conclusion

**Social & Compétition**
- **FR17:** Le système affiche un leaderboard classé par ROI (Return on Investment) et non par volume de crédits
- **FR18:** Le système implémente un système de ligues progressif (Bronze → Silver → Gold → Diamond)
- **FR19:** La page d'accueil affiche le Top 3 des joueurs avec avatar pixel art, pseudo et ROI
- **FR20:** Le système affiche un "Wall of Shame" — anti-leaderboard humoristique des plus grosses pertes
- **FR21:** Le système propose un leaderboard par club permettant la compétition entre groupes

**Système de Succès & Gamification**
- **FR22:** Le système attribue des succès/achievements aux utilisateurs basés sur leur comportement de jeu
- **FR23:** Les succès intègrent des badges ironiques de prévention ("Flambeur express", "Yolo King", "Le Lundi Noir")
- **FR24:** Le système affiche des équivalences en vie réelle pour les gains et pertes ("Tu viens de perdre 3 kebabs")
- **FR25:** Le système suit et affiche des streaks (séries de paris responsables ET séries de pertes)

**Prévention Gamifiée**
- **FR26:** Le système affiche des notifications/toasts de sensibilisation intégrés au flux de jeu (non désactivables séparément)
- **FR27:** Le système confronte les statistiques personnelles de l'utilisateur aux statistiques globales de la plateforme

### Non-Functional Requirements

**Performance**
- **NFR1:** Les pages principales (dashboard, matchs, leaderboard) doivent se charger en moins de 2 secondes
- **NFR2:** La mise à jour des résultats de matchs doit être reflétée dans un délai maximum de 5 minutes après la fin officielle

**Sécurité**
- **NFR3:** Les mots de passe doivent être hashés (bcrypt ou équivalent) et jamais stockés en clair
- **NFR4:** L'authentification doit utiliser des tokens JWT avec expiration et refresh token
- **NFR5:** Toutes les transactions de crédits doivent être atomiques pour éviter les incohérences de solde

**Scalabilité**
- **NFR6:** L'architecture doit supporter au minimum 500 utilisateurs simultanés au lancement
- **NFR7:** Le système doit être conçu pour une scalabilité horizontale (stateless backend)

**Accessibilité & Responsive**
- **NFR8:** L'application mobile doit être native (React Native) et disponible sur iOS et Android
- **NFR9:** L'application doit respecter un niveau d'accessibilité de base (contraste, labels accessibilité, taille de tap minimum)

**Légal & Éthique**
- **NFR10:** Le système ne doit en aucun cas permettre l'échange de crédits virtuels contre de l'argent réel ou des biens
- **NFR11:** Un disclaimer clair doit être visible indiquant que la plateforme est un simulateur éducatif sans valeur monétaire

**Fiabilité**
- **NFR12:** Le système doit viser une disponibilité de 99% (hors maintenance planifiée)
- **NFR13:** Les données utilisateur (paris, crédits, succès) doivent être persistées avec backup régulier

**Maintenabilité**
- **NFR14:** Le code doit suivre des standards définis (linting, formatting) avec CI/CD automatisé
- **NFR15:** L'ajout d'un nouveau jeu e-sport ne doit nécessiter que l'intégration d'un nouveau adaptateur de données, sans modification du cœur métier

---

## 3. User Interface Design Goals

### Overall UX Vision

Bet Arena adopte une identité visuelle **pixel art arcade 80s** qui rompt radicalement avec l'esthétique corporate des bookmakers classiques. L'expérience doit évoquer une salle d'arcade rétro : couleurs néon, typographies pixelisées, animations de jeu vidéo rétro, sons 8-bit optionnels. L'interface doit rester **fun et immersive** tout en restant **claire et fonctionnelle** — la complexité fonctionnelle (paris combinés, leaderboards, succès) ne doit jamais sacrifier la lisibilité.

Le ton général est décalé et humoristique : les messages de prévention utilisent l'ironie et l'humour noir ("Tu viens de perdre 3 kebabs"), les succès sont des badges ironiques, le Wall of Shame est assumé comme feature sociale. L'interface doit donner le sentiment d'un jeu vidéo, pas d'une application financière.

### Key Interaction Paradigms

- **Native mobile, thumb-friendly :** Toutes les actions principales (placer un pari, consulter le leaderboard, voir ses succès) accessibles en 1-2 taps avec des gestes natifs (swipe, pull-to-refresh, haptic feedback)
- **Onboarding ultra-rapide :** Compte créé → crédits reçus → premier pari placé en moins de 3 minutes
- **Feedback immédiat :** Chaque action (pari placé, résultat, succès débloqué) déclenche un feedback visuel pixel art (animation, toast, vibration haptic)
- **Navigation par tab bar :** Accès rapide aux sections principales (Matchs, Mes Paris, Leaderboard, Profil/Succès)
- **Prévention intégrée au flux :** Les messages de sensibilisation apparaissent dans le flux naturel (toasts, équivalences dans l'historique) — pas dans une section dédiée
- **Push notifications :** Résultats de paris, succès débloqués, matchs imminents, salaire hebdo versé

### Core Screens and Views

**Application Mobile (React Native — iOS + Android)**

| Écran | Objectif | Éléments clés |
|-------|----------|---------------|
| **Dashboard / Accueil** | Hub central, engagement immédiat | Top 3 leaderboard, matchs du jour, solde crédits, succès récents |
| **Matchs à venir** | Parcourir et parier | Liste filtrée par jeu (LoL/Valo/CS2), cotes, bouton pari rapide |
| **Détail Match** | Placer un pari | Équipes, cotes, formulaire pari simple/combiné, infos match |
| **Mes Paris** | Suivi et historique | Paris en cours, résultats passés, stats personnelles, équivalences vie réelle |
| **Leaderboard** | Compétition sociale | Classement ROI, ligues (Bronze→Diamond), Wall of Shame, leaderboard club |
| **Profil / Succès** | Progression personnelle | Avatar pixel art, badges/succès débloqués, stats globales, streaks |
| **Inscription / Login** | Onboarding | Création rapide (email/OAuth), attribution crédits de départ |
| **Panier combiné** | Composer un pari combiné | Sélections ajoutées, cote combinée calculée en temps réel, mise totale |

**Landing Page Desktop (Web statique)**

| Page | Objectif | Éléments clés |
|------|----------|---------------|
| **Landing page** | Vitrine + conversion téléchargement | Pitch Bet Arena, screenshots app, liens App Store / Google Play, pixel art ambiance |

### Accessibility: Base Level (Custom)

- Contraste suffisant malgré la palette néon/pixel art (WCAG AA sur les textes essentiels : cotes, montants, navigation)
- Labels et accessibility hints sur tous les éléments interactifs (VoiceOver / TalkBack)
- Taille de tap minimale 44x44pt (iOS) / 48x48dp (Android)
- Support des réglages système (taille de texte dynamique, mode sombre natif si pertinent)
- **Pas de WCAG AAA complet** — le style pixel art 80s implique des choix esthétiques qui peuvent limiter le contraste sur les éléments décoratifs

### Branding

- **Direction artistique :** Pixel art arcade 80s
- **Palette :** Couleurs néon (cyan, magenta, vert fluo) sur fonds sombres — évoque les salles d'arcade
- **Typographie :** Police pixelisée pour les titres et éléments de jeu, police lisible (sans-serif) pour le contenu fonctionnel (cotes, montants)
- **Animations :** Transitions pixel art, effets de glitch rétro subtils, animations de victoire/défaite style jeu vidéo 8-bit — optimisées pour les performances mobiles natives
- **Ton :** Humour décalé, ironie bienveillante, références gaming — jamais moralisateur
- **Mascotte :** Post-MVP (avatar/mascotte réactif prévu en Phase 3)

### Target Devices and Platforms: Application Mobile Native (React Native)

- **Application mobile React Native** — iOS + Android, déployée via App Store et Google Play
- **Priorité 1 :** iOS (iPhone) + Android — codebase partagée via React Native
- **Pas de version web applicative** — l'expérience complète est exclusivement sur mobile
- **Landing page web desktop :** Site statique de présentation avec liens de téléchargement vers les stores
- Versions iOS et Android minimum à définir avec l'architecte (suggestion : iOS 15+ / Android 10+)

---

## 4. Technical Assumptions

### Repository Structure: Monorepo

- **Un seul repository** contenant :
  - `/mobile` — Application React Native (iOS + Android)
  - `/backend` — API serveur
  - `/landing` — Landing page web statique
  - `/shared` — Types partagés, constantes, utilitaires communs
- **Justification :** Projet Epitech avec une équipe restreinte — le monorepo simplifie la gestion des versions, le partage de types entre frontend et backend, et le CI/CD unifié.

### Service Architecture: Monolithe modulaire avec API REST

- **Backend monolithique** structuré en modules (auth, betting, economy, esport-data, social, achievements) — chaque module isolé mais déployé en une seule unité
- **API REST** pour la communication mobile ↔ backend
- **WebSockets** pour les mises à jour temps réel (résultats de matchs, leaderboard live, notifications)
- **Workers/Jobs asynchrones** pour :
  - Polling des API PandaScore / Liquipedia (récupération matchs, résultats)
  - Résolution des paris après fin de match
  - Versement du salaire hebdomadaire
  - Calcul/mise à jour des leaderboards et ligues

### Stack Technique

| Couche | Technologie | Justification |
|--------|-------------|---------------|
| **Mobile** | React Native (Expo managed workflow) | Choix confirmé. Expo simplifie le build, les push notifications, et le déploiement sur stores |
| **Navigation** | React Navigation | Standard de facto pour React Native |
| **State management** | Zustand ou Redux Toolkit | Léger et adapté — à trancher avec l'architecte |
| **Backend** | Node.js + Express ou Fastify | Écosystème JS unifié avec le frontend React Native, facilite le partage de types |
| **Langage** | TypeScript (full stack) | Typage fort, réduction des bugs, cohérence monorepo |
| **Base de données** | PostgreSQL | Transactions ACID (critique pour l'économie virtuelle), relationnelle pour les données structurées |
| **ORM** | Prisma ou TypeORM | Migrations, typage auto, DX moderne |
| **Cache** | Redis | Cache des cotes, sessions, leaderboard temps réel (sorted sets) |
| **Auth** | JWT (access + refresh tokens) | Stateless, adapté mobile, conforme NFR4 |
| **Push notifications** | Expo Push Notifications | Intégré à Expo, iOS + Android |
| **API e-sport** | PandaScore (plan Fixtures: calendrier, pré-match, 1000 req/h) + Liquipedia (résultats, historique équipes) | Accès confirmés |
| **Landing page** | Astro ou HTML/CSS statique | Ultra léger, SEO-friendly |
| **CI/CD** | GitHub Actions | Gratuit pour les repos étudiants, bien intégré |
| **Hébergement backend** | Railway, Render ou VPS (à définir) | Options abordables pour un projet étudiant |
| **Hébergement landing** | Vercel ou Netlify | Gratuit pour sites statiques |

### Testing Requirements: Unit + Integration

- **Tests unitaires** : Logique métier critique — calcul de cotes, résolution de paris, économie virtuelle, attribution de succès
- **Tests d'intégration** : Endpoints API (auth flow, placement de paris, résolution), intégration API PandaScore
- **Pas de tests E2E mobile au MVP** — Tests manuels sur simulateurs/devices réels
- **Framework** : Jest (unitaire) + Supertest (intégration API)
- **Couverture cible** : 70% sur la logique métier

### Additional Technical Assumptions

- **Expo managed workflow** plutôt que bare workflow — sauf si une dépendance native l'exige
- **Pas de live betting au MVP** — polling toutes les 5-15 minutes suffit pour les résultats
- **WebSockets côté client** pour : mise à jour du leaderboard, notification de résultat de paris, solde crédits
- **Calcul des cotes interne :** PandaScore ne fournit pas de cotes sur le plan Fixtures. Les cotes sont calculées par un moteur interne basé sur l'historique des équipes depuis Liquipedia (winrate, head-to-head)
- **Gestion du quota API :** PandaScore limité à 1000 req/h. Stratégie de cache aggressif et persistance locale pour minimiser les appels. Budget tracker intégré au pipeline de données
- **Versioning API :** `/api/v1/` pour permettre des mises à jour de l'app sans casser les anciennes versions en circulation
- **Stockage images/assets :** Avatars pixel art et assets de gamification bundlés dans l'app (légers en pixel art)

---

## 5. Epic List

**Epic 1 : Foundation & Authentication**
Mettre en place l'infrastructure projet (monorepo, CI/CD, backend, app React Native) et livrer le système d'authentification complet (inscription, login, profil) — premier flux utilisateur de bout en bout.

**Epic 2 : E-sport Data, Odds Engine & Match Display**
Intégrer les API PandaScore (matchs à venir, pré-match) et Liquipedia (résultats, historique équipes), construire un moteur de calcul de cotes basé sur les stats des équipes, implémenter le pipeline de données avec cache agressif, et afficher les matchs avec cotes dans l'app mobile.

**Epic 3 : Betting System & Virtual Economy**
Implémenter le système de paris simples et combinés, l'économie virtuelle complète (crédits, capital de départ, salaire hebdo), la résolution automatique des paris, et l'historique — le cœur fonctionnel de Bet Arena.

**Epic 4 : Social, Leaderboard & Achievements**
Livrer le leaderboard par ROI, le système de ligues (Bronze→Diamond), le Wall of Shame, le leaderboard club, et le système complet de succès/achievements incluant la prévention gamifiée (badges ironiques, équivalences vie réelle, streaks).

**Epic 5 : Polish, Landing Page & Launch Prep**
Finaliser l'UX pixel art 80s (animations, feedback haptic, onboarding), construire la landing page desktop, préparer le déploiement sur App Store / Google Play, et effectuer les tests de qualité finaux.

---

## 6. Epic Details

### Epic 1 : Foundation & Authentication

**Goal :** Mettre en place toute l'infrastructure projet (monorepo TypeScript, CI/CD, backend Node.js, app React Native via Expo) et livrer un système d'authentification complet permettant à un utilisateur de s'inscrire, se connecter et voir son profil. Cet epic pose les fondations techniques sur lesquelles tous les epics suivants s'appuient et livre le premier flux utilisateur fonctionnel de bout en bout.

#### Story 1.1 — Monorepo Setup & Project Scaffolding

**As a** developer,
**I want** a fully configured monorepo with TypeScript, linting, and project structure,
**so that** the team can start developing with consistent standards from day one.

**Acceptance Criteria:**
1. Le monorepo est initialisé avec les dossiers `/mobile`, `/backend`, `/landing`, `/shared`
2. TypeScript est configuré pour tous les packages avec un `tsconfig` de base partagé
3. ESLint + Prettier sont configurés avec des règles cohérentes sur tout le monorepo
4. Un `package.json` racine avec les workspaces est fonctionnel
5. Un README racine documente la structure du projet et les commandes de base
6. Le projet se clone et s'installe en une seule commande

#### Story 1.2 — Backend API Bootstrap & Health Check

**As a** developer,
**I want** a running Node.js backend with a health check endpoint, database connection, and basic logging,
**so that** we have a deployable backend foundation ready to receive business logic.

**Acceptance Criteria:**
1. Le backend Node.js (Express ou Fastify) démarre et écoute sur un port configurable
2. Un endpoint `GET /api/v1/health` retourne `200 OK` avec le status du serveur et de la base de données
3. PostgreSQL est connecté via ORM (Prisma ou TypeORM) avec une migration initiale vide réussie
4. Redis est connecté et accessible (connection check au démarrage)
5. Un système de logging structuré est en place (winston ou pino) avec niveaux configurables
6. Les variables d'environnement sont gérées via `.env` avec validation au démarrage
7. Error handling global est en place (middleware catch-all, format d'erreur standardisé)

#### Story 1.3 — CI/CD Pipeline

**As a** developer,
**I want** an automated CI/CD pipeline that runs linting, tests, and builds on each push,
**so that** code quality is enforced automatically and deployments are reliable.

**Acceptance Criteria:**
1. GitHub Actions workflow se déclenche sur chaque push et pull request
2. Le pipeline exécute : lint → tests unitaires → build backend → build mobile (Expo)
3. Le pipeline échoue si le lint ou les tests échouent
4. Les temps de build sont raisonnables (< 10 min pour le pipeline complet)
5. Les secrets sont gérés via GitHub Secrets
6. Un badge de statut CI est visible dans le README

#### Story 1.4 — React Native App Bootstrap (Expo)

**As a** developer,
**I want** a running React Native app via Expo with navigation structure and basic theming,
**so that** mobile development can begin on a solid foundation.

**Acceptance Criteria:**
1. L'app React Native (Expo managed workflow) démarre sur iOS et Android simulateurs
2. React Navigation est configuré avec une tab bar de 4 onglets (Matchs, Mes Paris, Leaderboard, Profil) — écrans placeholder
3. Un thème de base pixel art 80s est initialisé (palette de couleurs néon, police pixelisée pour les titres)
4. Un composant d'écran de base est créé comme modèle réutilisable
5. L'app communique avec le backend (appel au health check et affichage du résultat)
6. Les variables d'environnement (API URL) sont configurées via Expo constants

#### Story 1.5 — User Registration & Login (Backend)

**As a** new user,
**I want** to create an account with email/password or OAuth (Google),
**so that** I can access Bet Arena with a secure, persistent identity.

**Acceptance Criteria:**
1. Endpoint `POST /api/v1/auth/register` crée un utilisateur avec email, mot de passe hashé (bcrypt), et pseudo
2. Endpoint `POST /api/v1/auth/login` retourne un access token JWT (15 min) et un refresh token (7 jours)
3. Endpoint `POST /api/v1/auth/refresh` renouvelle l'access token via le refresh token
4. Endpoint `POST /api/v1/auth/google` permet l'authentification via Google OAuth
5. Validation des inputs : email valide, mot de passe ≥ 8 caractères, pseudo unique (3-20 caractères)
6. Les mots de passe ne sont jamais retournés dans les réponses API
7. Les erreurs retournent des messages clairs
8. Tests unitaires couvrent les cas nominaux et les cas d'erreur

#### Story 1.6 — User Registration & Login (Mobile)

**As a** new user,
**I want** to register and log in from the mobile app with a smooth onboarding experience,
**so that** I can start using Bet Arena in less than 3 minutes.

**Acceptance Criteria:**
1. Écran d'inscription avec champs email, pseudo, mot de passe + bouton "S'inscrire avec Google"
2. Écran de login avec champs email/mot de passe + bouton Google OAuth
3. Validation côté client en temps réel (email format, longueur mot de passe, pseudo)
4. Les tokens JWT sont stockés de manière sécurisée (expo-secure-store)
5. L'app redirige automatiquement vers le dashboard après login/inscription réussi
6. Un écran de bienvenue s'affiche au premier login avec le montant de crédits de départ reçus
7. Le refresh token est utilisé automatiquement pour renouveler la session
8. Les erreurs serveur sont affichées clairement à l'utilisateur

#### Story 1.7 — User Profile Screen

**As a** logged-in user,
**I want** to view and edit my profile (pseudo, avatar),
**so that** I have a personalized identity on the platform.

**Acceptance Criteria:**
1. Endpoint `GET /api/v1/users/me` retourne le profil utilisateur
2. Endpoint `PATCH /api/v1/users/me` permet de modifier le pseudo (avec validation unicité)
3. L'écran Profil affiche pseudo, avatar pixel art par défaut, date d'inscription, et solde de crédits
4. L'utilisateur peut modifier son pseudo depuis l'écran profil
5. Un avatar pixel art est attribué par défaut à la création du compte
6. Un bouton de déconnexion est accessible depuis le profil

---

### Epic 2 : E-sport Data, Odds Engine & Match Display

**Goal :** Intégrer les API PandaScore (matchs à venir, pré-match) et Liquipedia (résultats, historique équipes), construire un moteur de calcul de cotes basé sur les stats des équipes avec une stratégie de cache aggressif pour respecter les quotas API, et offrir aux utilisateurs un tableau des matchs avec cotes calculées pour LoL, Valorant et CS2.

#### Story 2.1 — PandaScore Integration & Smart Caching

**As a** developer,
**I want** a PandaScore adapter that fetches match schedules and pre-match data with aggressive caching to stay within the 1000 req/hour limit,
**so that** we have reliable match data without burning our API quota.

**Acceptance Criteria:**
1. Un service `PandaScoreAdapter` est créé suivant une interface abstraite `EsportDataProvider`
2. Le service récupère les matchs à venir pour LoL, Valorant et CS2 (endpoint Calendar)
3. Le service récupère les données pré-match : équipes, ligues, séries, tournois (endpoint Pre-match Data)
4. **Stratégie de cache multi-niveaux :**
   - Données statiques (équipes, ligues, jeux) → fetchées une fois, stockées en base, refresh hebdomadaire
   - Matchs à venir → fetchés toutes les 2h, stockés en base, cache Redis TTL 2h
   - Matchs du jour → refresh toutes les 30 min (priorité plus haute)
5. Un **budget tracker** compte les requêtes effectuées par heure et bloque les appels non-critiques si on approche 80% du quota (800 req/h)
6. Retry avec backoff exponentiel en cas d'erreur ou rate limit (429)
7. Les credentials et le quota sont configurables via variables d'environnement
8. Logger trace chaque appel : endpoint, succès/erreur, temps de réponse, quota restant estimé
9. Tests unitaires couvrent le budget tracker, le cache, et les cas d'erreur

#### Story 2.2 — Liquipedia Integration, Results & Team History

**As a** developer,
**I want** to fetch match results and team historical data from Liquipedia with persistent storage,
**so that** we have results for bet resolution and statistical data for odds calculation without repeated API calls.

**Acceptance Criteria:**
1. Un adapter `LiquipediaAdapter` est implémenté suivant la même interface abstraite
2. Le service récupère les **résultats des matchs terminés** (vainqueur, score) — source primaire pour les résultats puisque PandaScore Fixtures ne les inclut pas
3. Le service récupère l'historique de résultats des équipes (winrate, résultats récents)
4. Le service récupère les confrontations directes (head-to-head) quand disponibles
5. **Stratégie de persistance :**
   - Résultats de matchs → fetchés et stockés en base de manière permanente, jamais re-fetchés une fois obtenus
   - Stats d'équipes → recalculées localement à partir des résultats stockés en base (pas de re-fetch Liquipedia)
   - Données de référence (logos, noms complets) → fetchées une fois, stockées en base, refresh mensuel
6. **Polling ciblé des résultats :** Seuls les matchs avec status "en cours" ou "terminé récemment (< 24h)" déclenchent un fetch de résultat — pas de polling global
7. Respect strict du rate limiting Liquipedia (User-Agent identifiant le projet, espacement des requêtes)
8. En cas d'indisponibilité de Liquipedia, le système fonctionne en mode dégradé : résultats en attente (marqués "pending"), cotes par défaut (50/50)
9. Tests unitaires couvrent le mapping, la persistance, le mode dégradé

#### Story 2.3 — Odds Calculation Engine

**As a** system,
**I want** to calculate betting odds based on locally stored team statistics,
**so that** users see data-driven odds without any external API call at calculation time.

**Acceptance Criteria:**
1. Un service `OddsEngine` calcule les cotes **uniquement à partir des données en base** — aucun appel API au moment du calcul
2. Facteurs pris en compte : winrate récent (N derniers matchs stockés), head-to-head historique stocké, winrate par jeu
3. L'algorithme produit une probabilité de victoire par équipe, convertie en cotes décimales
4. Marge (overround) configurable appliquée (ex: 5-10%)
5. Quand les données historiques sont insuffisantes : cotes basées sur le winrate global seul, ou 50/50 en dernier recours
6. Les cotes sont recalculées uniquement quand les stats d'équipe changent (nouveau résultat entré en base)
7. Cotes bornées (min 1.05, max 20.0)
8. Tests unitaires couvrent : cas nominal, données insuffisantes, cas limites
9. Algorithme documenté (formules, pondérations, marge)

#### Story 2.4 — Data Pipeline Orchestrator

**As a** developer,
**I want** an intelligent pipeline that orchestrates data fetching, storage, and odds recalculation with minimal API usage,
**so that** the system stays fresh while respecting API quotas.

**Acceptance Criteria:**
1. Modèle `Match` en base : id, game, tournament, team_a_id, team_b_id, scheduled_at, status (upcoming/live/completed/cancelled), odds_a, odds_b, result, pandascore_id, liquipedia_id
2. Modèle `Team` : id, name, slug, logo_url, game
3. Modèle `TeamStats` : team_id, game, matches_played, wins, losses, winrate, last_updated — calculé localement à partir des résultats en base
4. Modèle `HeadToHead` : team_a_id, team_b_id, game, matches_played, wins_a, wins_b — calculé localement
5. Modèle `ApiQuotaLog` : provider, timestamp, endpoint, status, quota_remaining_estimate
6. **Jobs orchestrés :**
   - `sync-upcoming-matches` : toutes les 2h (PandaScore Calendar) — matchs du jour toutes les 30 min
   - `sync-results` : toutes les 10 min, uniquement pour les matchs dont le scheduled_at est passé et status ≠ completed (Liquipedia)
   - `sync-team-references` : hebdomadaire (PandaScore Static + Liquipedia données de référence)
   - `recalc-stats` : déclenché après chaque nouveau résultat — recalcule TeamStats et HeadToHead localement, puis recalcule les cotes des matchs à venir impliquant ces équipes
7. Chaque job vérifie le budget API avant exécution et se reporte si quota insuffisant
8. Les logs tracent : matchs ajoutés/mis à jour, résultats reçus, cotes recalculées, budget API consommé
9. Tests d'intégration valident le pipeline complet

#### Story 2.5 — Match List API Endpoints

**As a** mobile app,
**I want** API endpoints to fetch upcoming matches with calculated odds,
**so that** the frontend can display match data with our odds.

**Acceptance Criteria:**
1. Endpoint `GET /api/v1/matches?status=upcoming&game=lol|valorant|cs2` retourne la liste des matchs avec cotes calculées et pagination
2. Endpoint `GET /api/v1/matches/:id` retourne le détail d'un match (équipes, cotes, tournoi, stats d'équipes)
3. Les réponses incluent : équipes (nom, logo, winrate récent), cotes calculées, tournoi, date/heure, jeu
4. Filtrage par jeu optionnel
5. Pagination implémentée
6. Réponses en cache Redis (TTL 2 min)
7. Tests d'intégration couvrent filtres, pagination, données vides

#### Story 2.6 — Match List Screen (Mobile)

**As a** user,
**I want** to browse upcoming e-sport matches in the app with filtering by game,
**so that** I can find matches I want to bet on.

**Acceptance Criteria:**
1. L'onglet "Matchs" affiche la liste des matchs à venir avec : logos équipes, noms, cotes calculées, date/heure, jeu, tournoi
2. Filtres par jeu (All / LoL / Valorant / CS2) sous forme de chips
3. Liste scrollable avec pull-to-refresh
4. État vide, état de chargement (skeleton pixel art), gestion des erreurs réseau
5. Style pixel art 80s appliqué

#### Story 2.7 — Match Detail Screen (Mobile)

**As a** user,
**I want** to see detailed information about a specific match including team stats,
**so that** I can make an informed decision before placing a bet.

**Acceptance Criteria:**
1. Tap sur un match → écran de détail
2. Affichage : logos, noms, cotes calculées, tournoi, date/heure, jeu
3. Stats des équipes : winrate récent, H2H si disponible
4. Bouton "Parier" (placeholder pour Epic 3)
5. Style pixel art 80s cohérent

---

### Epic 3 : Betting System & Virtual Economy

**Goal :** Implémenter le cœur fonctionnel de Bet Arena — le système de paris simples et combinés, l'économie virtuelle complète (crédits, capital de départ, salaire hebdomadaire), la résolution automatique des paris après résultat, et l'historique des paris. À la fin de cet epic, un utilisateur peut parier, gagner ou perdre des crédits, et suivre son activité.

#### Story 3.1 — Virtual Economy Core (Backend)

**As a** new user,
**I want** to receive starting credits and a weekly salary,
**so that** I always have virtual currency to bet with in a fair system.

**Acceptance Criteria:**
1. Un modèle `Wallet` est créé (user_id, balance, created_at, updated_at) avec balance initialisée au capital de départ configurable
2. Un modèle `Transaction` est créé (id, user_id, type, amount, reference_id, balance_after, created_at)
3. Types de transaction : `initial_credit`, `weekly_salary`, `bet_placed`, `bet_won`, `bet_lost`
4. Toutes les opérations sur le wallet sont **atomiques** (transaction SQL)
5. Un service `WalletService` expose : `getBalance`, `debit`, `credit` avec vérification de solde suffisant
6. Un job cron `weekly-salary` s'exécute chaque lundi à 00:00 UTC et crédite le salaire fixe à tous les utilisateurs actifs
7. Le wallet est créé automatiquement avec le capital de départ lors de l'inscription
8. Endpoint `GET /api/v1/wallet` retourne le solde actuel et l'historique des transactions (paginé)
9. Tests unitaires couvrent : atomicité (débit concurrent), solde insuffisant, crédit/débit nominal, weekly salary

#### Story 3.2 — Simple Bet Placement (Backend)

**As a** user,
**I want** to place a simple bet on a match by choosing a team and a stake amount,
**so that** I can engage with upcoming matches.

**Acceptance Criteria:**
1. Un modèle `Bet` est créé (id, user_id, type: simple|combined, status: pending|won|lost|cancelled, total_stake, total_odds, potential_winnings, created_at, resolved_at)
2. Un modèle `BetSelection` est créé (id, bet_id, match_id, team_selected, odds_at_placement, result: pending|won|lost)
3. Endpoint `POST /api/v1/bets` accepte : match_id, team_selected, stake_amount
4. Validations : match existe et status = upcoming, team_selected valide, stake > 0, stake ≤ solde utilisateur
5. Les cotes sont verrouillées au moment du placement
6. Le wallet est débité atomiquement du stake au moment du placement
7. Le `potential_winnings` est calculé : stake × odds_at_placement
8. Le endpoint retourne le bet créé avec tous les détails
9. Un utilisateur ne peut pas parier sur un match déjà commencé ou terminé
10. Tests unitaires couvrent : placement nominal, solde insuffisant, match invalide, cote verrouillée

#### Story 3.3 — Combined Bet Placement (Backend)

**As a** user,
**I want** to place a combined bet with multiple selections (up to 10),
**so that** I can increase my potential winnings with a multi-match strategy.

**Acceptance Criteria:**
1. Endpoint `POST /api/v1/bets` accepte un mode combiné : array de selections [{match_id, team_selected}] + stake_amount
2. Validations : 2 à 10 sélections, pas de doublons de match, tous les matchs upcoming, stake ≤ solde
3. La cote combinée est le produit des cotes individuelles (verrouillées au placement)
4. Le `potential_winnings` = stake × cote combinée
5. Le wallet est débité une seule fois du stake total
6. Un pari combiné est gagné uniquement si toutes les sélections sont gagnantes
7. Le endpoint retourne le bet combiné avec toutes les sélections, cotes individuelles, cote combinée, gains potentiels
8. Tests unitaires couvrent : combiné nominal, limite des 10, doublons rejetés, calcul de cote combinée

#### Story 3.4 — Bet Resolution Engine

**As a** system,
**I want** to automatically resolve bets when match results are received,
**so that** users see their winnings or losses without manual intervention.

**Acceptance Criteria:**
1. Un service `BetResolutionService` est déclenché après chaque mise à jour de résultat de match
2. Pour chaque match résolu, le service récupère tous les `BetSelection` liés avec status = pending
3. Chaque sélection est marquée `won` ou `lost` selon le résultat
4. Paris simples : si won → wallet crédité de stake × odds_at_placement. Si lost → rien
5. Paris combinés : une sélection lost → pari combiné entier lost. Toutes won → wallet crédité de stake × cote combinée. Certaines pending → pari reste pending
6. Toutes les opérations de crédit sont atomiques
7. En cas de match annulé : sélections marquées cancelled, pari simple remboursé, combiné recalculé sans cette sélection
8. Logs détaillés de chaque résolution
9. Tests unitaires couvrent : résolution simple, combiné partiellement résolu, combiné full won, combiné avec perte, match annulé, atomicité

#### Story 3.5 — Bet Placement Screens (Mobile)

**As a** user,
**I want** to place simple and combined bets from the match detail screen,
**so that** I can bet on matches directly from the app.

**Acceptance Criteria:**
1. Sur l'écran détail match, le bouton "Parier" ouvre un formulaire de pari simple : sélection d'équipe + champ montant + gains potentiels en temps réel
2. Les gains potentiels se mettent à jour instantanément quand l'utilisateur modifie le montant
3. Le solde actuel est affiché et le champ montant est borné (min 1, max = solde)
4. Bouton "Confirmer le pari" → appel API → feedback de succès (animation pixel art) avec nouveau solde
5. Bouton "Ajouter au combiné" sur chaque match → panier flottant (bottom sheet ou floating button avec badge compteur)
6. Le panier combiné affiche : toutes les sélections, cote combinée calculée en temps réel, champ montant, gains potentiels
7. Possibilité de retirer une sélection du panier combiné (swipe ou bouton ×)
8. Validation côté client : solde suffisant, 2-10 sélections pour un combiné, pas de doublon de match
9. Erreurs serveur affichées clairement (toast)
10. Style pixel art 80s, animations de confirmation

#### Story 3.6 — Bet History & Results Screen (Mobile)

**As a** user,
**I want** to view my betting history with results, gains/losses, and real-life equivalents,
**so that** I can track my performance and understand the impact of my bets.

**Acceptance Criteria:**
1. L'onglet "Mes Paris" affiche la liste de tous les paris triés par date décroissante
2. Chaque pari affiche : type, équipes, cote(s), montant misé, résultat, gains ou pertes
3. Les paris en cours sont visuellement distincts des paris résolus
4. Les paris gagnés en vert, perdus en rouge
5. Équivalences vie réelle affichées sur chaque pari résolu
6. Un résumé en haut : nombre total de paris, winrate, profit/perte net, ROI
7. Pull-to-refresh
8. Tap sur un pari combiné déploie le détail de chaque sélection
9. Style pixel art 80s

#### Story 3.7 — Wallet Display & Salary Notification (Mobile)

**As a** user,
**I want** to see my credit balance everywhere and be notified when I receive my weekly salary,
**so that** I always know my financial situation and am engaged to come back weekly.

**Acceptance Criteria:**
1. Le solde de crédits est affiché dans la header/navbar, visible sur tous les écrans
2. Le solde se met à jour automatiquement après chaque pari placé ou résolu
3. Une push notification est envoyée lors du versement du salaire hebdomadaire
4. Un toast in-app s'affiche si l'utilisateur est connecté au moment du versement
5. L'écran Profil affiche l'historique des transactions via l'endpoint wallet
6. Le style du solde utilise la typographie pixel art avec animation lors des changements

---

### Epic 4 : Social, Leaderboard & Achievements

**Goal :** Transformer Bet Arena d'un outil de paris individuel en une plateforme sociale et compétitive. Cet epic livre le leaderboard par ROI, le système de ligues, le Wall of Shame, le leaderboard par club, et le système complet de succès/achievements intégrant la prévention gamifiée.

#### Story 4.1 — ROI Calculation & Leaderboard Backend

**As a** user,
**I want** to be ranked against other users based on my ROI,
**so that** the leaderboard rewards smart strategy over volume.

**Acceptance Criteria:**
1. Un modèle `UserStats` est créé (user_id, total_bets, total_wins, total_losses, total_staked, total_won, roi_percentage, current_league, league_updated_at)
2. Le ROI est calculé : `((total_won - total_staked) / total_staked) × 100`
3. Les `UserStats` sont recalculées incrémentalement à chaque résolution de pari
4. Endpoint `GET /api/v1/leaderboard?type=roi&limit=50&offset=0` retourne le classement global
5. Endpoint `GET /api/v1/leaderboard/me` retourne la position de l'utilisateur connecté
6. Le leaderboard est stocké dans un Redis Sorted Set
7. Minimum de paris requis pour apparaître au leaderboard (ex: 5 paris résolus)
8. Tests unitaires couvrent : calcul ROI, classement, cas limites

#### Story 4.2 — League System

**As a** user,
**I want** to be placed in a league based on my performance,
**so that** I have a visible progression tier.

**Acceptance Criteria:**
1. 4 ligues : Bronze, Silver, Gold, Diamond
2. Seuils basés sur le percentile ROI : Bronze (bottom 40%), Silver (40-70%), Gold (70-90%), Diamond (top 10%)
3. Job `recalc-leagues` quotidien
4. Promotions/rétrogradations enregistrées dans `LeagueHistory`
5. Endpoint `GET /api/v1/leaderboard?league=gold` pour filtrer par ligue
6. Minimum de paris requis — en dessous = "Unranked"
7. Tests unitaires couvrent attribution, promotion/rétrogradation

#### Story 4.3 — Wall of Shame

**As a** user,
**I want** to see the Wall of Shame — a humorous anti-leaderboard of the worst performers,
**so that** losses become a shared social experience.

**Acceptance Criteria:**
1. Endpoint `GET /api/v1/leaderboard?type=shame&limit=10` retourne les 10 pires ROI
2. Chaque entrée affiche : pseudo, avatar, ROI négatif, pire perte, titre humoristique
3. Titres dynamiques : "Le Flambeur Éternel" (ROI < -50%), "Yolo King" (all-in perdu), "Le Prophète Inversé" (winrate < 20%), "Généreux Donateur" (> 5000 crédits perdus)
4. Minimum de paris requis (ex: 10)
5. Ton humoristique et bienveillant — jamais dégradant
6. Accessible depuis l'écran Leaderboard via toggle/onglet
7. Tests unitaires couvrent tri et attribution des titres

#### Story 4.4 — Club Leaderboard

**As a** user,
**I want** to create or join a club and see club rankings,
**so that** I can compete with my friends or school club.

**Acceptance Criteria:**
1. Modèle `Club` (id, name, created_by, invite_code, created_at)
2. Modèle `ClubMembership` (user_id, club_id, joined_at)
3. Endpoint `POST /api/v1/clubs` crée un club (nom unique, code d'invitation 6 chars)
4. Endpoint `POST /api/v1/clubs/join` rejoint un club via code
5. Endpoint `GET /api/v1/clubs/:id` retourne les membres avec stats
6. ROI club = moyenne des ROI des membres éligibles
7. Endpoint `GET /api/v1/leaderboard?type=club&limit=20` classement clubs
8. Un utilisateur ne peut appartenir qu'à un seul club
9. Le créateur peut supprimer le club ou régénérer le code
10. Tests unitaires couvrent création, invitation, calcul ROI club

#### Story 4.5 — Achievement System Backend

**As a** system,
**I want** to detect user behaviors and award achievements automatically,
**so that** users are rewarded for milestones, streaks, and behaviors.

**Acceptance Criteria:**
1. Modèle `Achievement` (id, code, name, description, icon, category: milestone|streak|prevention|economy)
2. Modèle `UserAchievement` (user_id, achievement_id, unlocked_at, context_data)
3. Service `AchievementEngine` déclenché après chaque événement pertinent
4. **Achievements MVP :**
   - **Milestones :** "Premier Pas" (1er pari), "Habitué" (10 paris), "Vétéran" (50 paris), "Millionnaire Virtuel" (10× capital)
   - **Streaks :** "En Série" (3 wins consécutifs), "Inarrêtable" (5 wins), "Spirale" (5 losses)
   - **Prévention :** "Flambeur Express" (salaire claqué < 24h), "Yolo King" (misé > 50% solde), "Le Lundi Noir" (tout perdu jour du salaire), "Le Prophète Inversé" (winrate < 20% sur 20+ paris), "Généreux Donateur" (> 5000 crédits perdus)
   - **Economy :** "Économe" (semaine avec > 80% salaire), "Self-Made" (capital doublé sur une semaine), "ROI Positif" (ROI > 0% après 20+ paris)
5. Chaque achievement débloqué une seule fois
6. Déclenchement event-driven
7. Endpoint `GET /api/v1/achievements` retourne tous les achievements avec statut
8. Tests unitaires couvrent chaque condition

#### Story 4.6 — Streak Tracking

**As a** system,
**I want** to track user betting streaks,
**so that** streak-based achievements and prevention mechanics trigger accurately.

**Acceptance Criteria:**
1. `UserStats` étendu avec : current_win_streak, max_win_streak, current_loss_streak, max_loss_streak, last_salary_received_at, salary_spent_within_24h
2. Streaks mises à jour après chaque résolution de pari
3. `salary_spent_within_24h` calculé en comparant le solde 24h après versement
4. Streaks accessibles via `GET /api/v1/users/me/stats`
5. L'`AchievementEngine` utilise les streaks pour les achievements
6. Tests unitaires couvrent incrémentation/reset, edge cases

#### Story 4.7 — Leaderboard Screen (Mobile)

**As a** user,
**I want** to browse the leaderboard, see my rank, filter by league, and view the Wall of Shame,
**so that** I can see where I stand.

**Acceptance Criteria:**
1. L'onglet "Leaderboard" affiche le classement global par ROI
2. Top 3 mis en avant (podium pixel art)
3. Position de l'utilisateur connecté toujours visible (sticky)
4. Filtres : Global / Ma Ligue / Mon Club / Wall of Shame
5. Wall of Shame avec style visuel distinct (rouge/sombre, titres humoristiques)
6. Pull-to-refresh, skeleton, gestion erreurs
7. Badges de ligue colorés (Bronze=cuivre, Silver=argenté, Gold=doré, Diamond=cyan)

#### Story 4.8 — Achievements & Profile Screen (Mobile)

**As a** user,
**I want** to view my achievements, streaks, and stats on my profile,
**so that** I can track my progression.

**Acceptance Criteria:**
1. L'écran Profil est étendu avec : achievements, stats détaillées, streaks
2. Achievements en grille (débloqué = couleur / verrouillé = grisé)
3. Achievements de prévention mélangés avec les autres — pas de catégorie séparée
4. Tap sur achievement débloqué → détail et date
5. Tap sur achievement verrouillé → condition de débloquage
6. Stats : ROI, winrate, total parié/gagné, ligue, position, nombre de paris
7. Streaks : série en cours, meilleure série, indicateurs visuels
8. Notification in-app (toast pixel art + haptic) quand achievement débloqué
9. Push notification pour achievements marquants
10. Style pixel art 80s, animations de déverrouillage

#### Story 4.9 — Club Management Screen (Mobile)

**As a** user,
**I want** to create a club, invite friends, and see my club's performance,
**so that** I can compete as a group.

**Acceptance Criteria:**
1. Bouton "Mon Club" depuis profil ou leaderboard
2. Si pas de club : "Créer un club" + "Rejoindre un club" (code d'invitation)
3. Si membre : nom, code partageable (copier + share sheet), liste membres avec stats
4. Créateur : "Régénérer le code" et "Supprimer le club"
5. Membre : "Quitter le club" avec confirmation
6. ROI moyen du club en header
7. Style pixel art 80s

---

### Epic 5 : Polish, Landing Page & Launch Prep

**Goal :** Finaliser l'expérience Bet Arena pour le lancement : polir l'UX pixel art 80s, construire la landing page desktop, préparer le déploiement sur les stores, et effectuer les derniers tests de qualité.

#### Story 5.1 — Onboarding Flow Polish

**As a** new user,
**I want** a smooth, engaging onboarding experience that gets me from download to first bet in under 3 minutes,
**so that** I immediately understand and enjoy the app.

**Acceptance Criteria:**
1. Splash screen pixel art avec logo Bet Arena et animation 8-bit
2. Parcours onboarding de 2-3 écrans swipables après inscription
3. Animation de compteur pixel art pour l'attribution du capital de départ
4. Redirection vers les matchs avec indicateur visuel ("Place ton premier pari →")
5. Parcours complet (download → premier pari) réalisable en < 3 minutes
6. Onboarding ne s'affiche qu'une seule fois
7. Bouton "Passer" disponible

#### Story 5.2 — Pixel Art UI Polish & Animations

**As a** user,
**I want** a polished, immersive pixel art 80s experience across the entire app,
**so that** Bet Arena feels like a retro arcade game.

**Acceptance Criteria:**
1. Transitions entre écrans avec animations pixel art cohérentes
2. Feedback de pari placé : animation rétro (flash néon, effet "coin insert")
3. Feedback de résultat : victoire (confetti pixel art, flash vert), défaite (effet glitch rouge)
4. Achievement débloqué : animation "Level Up"
5. Haptic feedback : vibration sur pari placé, succès, achievement
6. Loading states : skeletons/loaders pixel art
7. Empty states : illustrations pixel art avec message humoristique
8. Audit visuel complet — cohérence design system
9. Animations performantes (60fps)

#### Story 5.3 — Prevention Notifications & Toasts

**As a** user,
**I want** to receive contextual, humorous prevention messages during my betting activity,
**so that** I'm made aware of my betting patterns in an engaging way.

**Acceptance Criteria:**
1. Toasts à des moments clés :
   - Après 3 paris perdus : "🎰 Le casino gagne toujours... sauf que ici c'est toi le casino. Enfin, normalement."
   - Après mise > 30% du solde : "💸 All-in vibes... Tu sais que même les pros se plantent ?"
   - Après salaire claqué < 24h : "🔥 Salaire speedrunné ! GG. Prochain versement lundi."
   - Après 5 paris dans l'heure : "⚡ Tu chauffes ! Peut-être temps de regarder un match plutôt que de parier dessus ?"
2. Ton humoristique et ironique — jamais moralisateur
3. Toasts visuellement distincts mais intégrés au style pixel art
4. Non-désactivables individuellement (FR26)
5. Maximum 1 toast de prévention par session de 10 minutes
6. Conditions de déclenchement configurables côté backend
7. Toasts disparaissent après 5 secondes ou sur tap

#### Story 5.4 — User Stats Comparison

**As a** user,
**I want** to see how my stats compare to the global average,
**so that** I have a reality check on my betting behavior.

**Acceptance Criteria:**
1. Endpoint `GET /api/v1/stats/global` retourne les stats moyennes de la plateforme
2. Toggle "vs Global" sur l'écran Profil affiche une comparaison côte à côte
3. Indicateurs colorés : vert si meilleur, rouge si pire
4. Message contextuel ("Ton ROI est dans le top 15%" ou "85% des joueurs ont un meilleur winrate")
5. Stats globales en cache Redis (TTL 1h)
6. Style pixel art cohérent

#### Story 5.5 — Landing Page Desktop

**As a** visitor on desktop,
**I want** to discover Bet Arena and find download links,
**so that** I can install the app on my phone.

**Acceptance Criteria:**
1. Landing page statique déployée sur un domaine
2. Contenu : hero section (logo, pitch, screenshots), "Comment ça marche" (3-4 étapes), features, disclaimer éducatif (NFR11), boutons stores, footer mentions légales
3. Design pixel art 80s cohérent avec l'app
4. Page responsive
5. SEO de base (title, meta, Open Graph)
6. Temps de chargement < 2 secondes
7. Hébergée sur Vercel ou Netlify

#### Story 5.6 — App Store & Play Store Preparation

**As a** developer,
**I want** to prepare all assets and metadata for store submission,
**so that** the app can be published.

**Acceptance Criteria:**
1. **App Store :** Icon 1024×1024, screenshots iPhone (6.5" et 5.5"), descriptions FR, keywords, catégorie, privacy policy, age rating
2. **Play Store :** Icon 512×512, feature graphic 1024×500, screenshots, descriptions, content rating, privacy policy
3. Expo EAS Build configuré pour builds iOS (.ipa) et Android (.aab)
4. Certificats de signature configurés
5. Build de release testé sur devices réels (1 iOS, 1 Android minimum)
6. Disclaimer éducatif visible dans les descriptions stores
7. Assets cohérents avec l'identité pixel art 80s

#### Story 5.7 — Final QA & Bug Fixing

**As a** team,
**I want** a final round of quality assurance covering all critical user flows,
**so that** the app is stable and reliable at launch.

**Acceptance Criteria:**
1. Tests manuels des flux critiques sur device réel (iOS + Android) :
   - Inscription → onboarding → premier pari → résultat → achievement
   - Pari combiné → résolution partielle → résolution complète
   - Leaderboard → filtres → Wall of Shame
   - Profil → stats → achievements → club
   - Salaire hebdo → notification
   - Edge cases : solde à 0, aucun match, perte de connexion
2. Tests de performance sur devices milieu de gamme
3. Pas de crash sur les 10 flux principaux
4. Bugs critiques corrigés, bugs mineurs documentés
5. Rapport de QA produit

---

## 7. Checklist Results Report

_(À compléter après exécution de la PM checklist)_

---

## 8. Next Steps

### UX Expert Prompt

> Consulte le PRD `docs/prd.md` de Bet Arena. Crée les spécifications UX/UI détaillées pour l'application mobile React Native avec l'identité pixel art arcade 80s. Focus sur le design system (couleurs, typographie, composants), les wireframes des 8 écrans principaux, et les spécifications d'animation/interaction. Le PRD contient la vision UX complète dans la section 3.

### Architect Prompt

> Consulte le PRD `docs/prd.md` de Bet Arena. Crée le document d'architecture technique pour une application mobile React Native (Expo) avec un backend Node.js monolithique modulaire. Points critiques à adresser : moteur de calcul de cotes interne (pas de cotes API), pipeline de données avec cache agressif (PandaScore 1000 req/h + Liquipedia), économie virtuelle avec transactions atomiques, et leaderboard Redis. Le PRD contient les hypothèses techniques dans la section 4.
