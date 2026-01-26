# WBS — Bet Arena (Work Breakdown Structure)

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                              🎮 BET ARENA                                       │
│                         Projet MVP — Work Breakdown                             │
└─────────────────────────────────────────────────────────────────────────────────┘
                                      │
 ┌──────────┬──────────┬──────────┬───┴───┬──────────┬──────────┬──────────┐
 │          │          │          │       │          │          │          │
 ▼          ▼          ▼          ▼       ▼          ▼          ▼          ▼
┌────────┐┌────────┐┌────────┐┌────────┐┌────────┐┌────────┐┌────────┐┌────────┐
│ PHASE 0││ PHASE 1││ PHASE 2││ PHASE 3││ PHASE 4││ PHASE 5││ PHASE 6││ PHASE 7│
│LIVRABLES││DISCOVERY││ DESIGN ││  DEV   ││  DEV   ││  DEV   ││ TESTS  ││DEPLOIE-│
│ PROJET ││& CADRAGE││  UX/UI ││BACKEND ││FRONTEND││ INTÉG. ││  & QA  ││  MENT  │
└────────┘└────────┘└────────┘└────────┘└────────┘└────────┘└────────┘└────────┘
```

---

## Phase 0 — Livrables Projet (Évaluation Epitech)

```
0. LIVRABLES PROJET
│
├── 0.1 WBS — Work Breakdown Structure
│   ├── 0.1.1 Créer le diagramme WBS visuel
│   │   └── Format : Schéma hiérarchique (ce document)
│   ├── 0.1.2 Structurer en décomposition orientée livrables
│   │   ├── Phases → Lots → Tâches
│   │   └── Chaque niveau = livrable identifiable
│   └── 0.1.3 Livrable : wbs-betarena.md + export image
│   📋 Critères : wbs_delivery, wbs_relevance, doc_diagram
│
├── 0.2 Document Features & Requirements
│   ├── 0.2.1 Lister toutes les features MVP
│   │   ├── Must Have (obligatoires)
│   │   ├── Should Have (importantes)
│   │   └── Could Have (bonus)
│   ├── 0.2.2 Décrire les requirements par feature
│   │   ├── Critères d'acceptation
│   │   ├── Dépendances techniques
│   │   └── Priorité d'implémentation
│   └── 0.2.3 Livrable : features-requirements.md
│   📋 Critère : wbs_features
│
├── 0.3 OBS — Organizational Breakdown Structure
│   ├── 0.3.1 Créer le diagramme OBS visuel
│   │   └── Format : Schéma hiérarchique
│   ├── 0.3.2 Définir les rôles de chaque membre
│   │   ├── Responsabilités par phase
│   │   ├── Responsabilités par lot de travail
│   │   └── Backup / suppléance
│   ├── 0.3.3 Allouer les ressources humaines
│   │   ├── Charge par membre
│   │   └── Adéquation compétences/tâches
│   └── 0.3.4 Livrable : obs-betarena.md + export image
│   📋 Critères : obs_delivery, obs_relevance, doc_diagram
│
├── 0.4 Justification Équipe
│   ├── 0.4.1 Documenter le choix de l'équipe
│   │   ├── Critères professionnels de sélection
│   │   ├── Complémentarité des profils
│   │   └── Expériences passées ensemble
│   ├── 0.4.2 Identifier les compétences nécessaires
│   │   ├── Compétences techniques (dev, design, data)
│   │   ├── Compétences gestion (PM, QA)
│   │   └── Mapping compétences ↔ membres
│   └── 0.4.3 Livrable : team-justification.md
│   📋 Critères : team_recruitment, team_skills
│
├── 0.5 Quality Plan (Plan Qualité)
│   ├── 0.5.1 Documenter la méthode de développement
│   │   ├── Conventions de code
│   │   ├── Workflow Git (branching, PR, reviews)
│   │   └── Standards de nommage
│   ├── 0.5.2 Documenter le processus de test
│   │   ├── Stratégie de test (unit, integ, e2e)
│   │   ├── Critères de validation
│   │   └── Outils de test
│   ├── 0.5.3 Documenter le processus de déploiement
│   │   ├── Pipeline CI/CD
│   │   ├── Environnements (dev/staging/prod)
│   │   └── Procédure de rollback
│   ├── 0.5.4 Documenter les best practices
│   │   ├── Normes de qualité
│   │   └── Definition of Done
│   ├── 0.5.5 Préparer l'onboarding
│   │   ├── Guide nouveau membre
│   │   └── Setup environnement dev
│   └── 0.5.6 Livrable : quality-plan.md
│   📋 Critère : team_practices
│
├── 0.6 Méthodologie Projet
│   ├── 0.6.1 Choisir et justifier la méthodologie
│   │   ├── Agile (Scrum/Kanban) vs Waterfall
│   │   ├── Arguments pour le choix
│   │   └── Adaptation au contexte projet
│   ├── 0.6.2 Si Agile : définir le backlog
│   │   ├── User stories
│   │   ├── Story points / estimation
│   │   └── Sprints planifiés
│   ├── 0.6.3 Si Waterfall : planning détaillé
│   │   ├── Diagramme de Gantt
│   │   └── Jalons et deadlines
│   └── 0.6.4 Livrable : methodology.md
│   📋 Critère : proj_methodology
│
├── 0.7 Outil de Gestion de Projet
│   ├── 0.7.1 Choisir l'outil (Trello/Planner/Jira/Notion)
│   ├── 0.7.2 Configurer le board/workspace
│   │   ├── Colonnes/statuts
│   │   ├── Labels/tags
│   │   └── Membres assignés
│   ├── 0.7.3 Importer les tâches du WBS
│   ├── 0.7.4 Former l'équipe à l'outil
│   └── 0.7.5 Livrable : Lien vers l'outil configuré
│   📋 Critère : proj_planning
│
├── 0.8 Document Choix Technologiques
│   ├── 0.8.1 Documenter le stack technique
│   │   ├── Frontend : techno + justification
│   │   ├── Backend : techno + justification
│   │   ├── Base de données : techno + justification
│   │   └── Infra/Cloud : techno + justification
│   ├── 0.8.2 Documenter les outils de test
│   │   ├── Tests unitaires
│   │   ├── Tests e2e
│   │   └── Tests performance
│   ├── 0.8.3 Schématiser l'architecture globale
│   │   └── Diagramme d'architecture
│   └── 0.8.4 Livrable : tech-stack.md + diagramme archi
│   📋 Critère : proj_technos
│
├── 0.9 Estimation Ressources & Coûts
│   ├── 0.9.1 Identifier les besoins hardware
│   │   ├── Serveurs / hébergement
│   │   ├── Services cloud (BDD, cache, CDN)
│   │   └── APIs tierces (si payantes)
│   ├── 0.9.2 Estimer les coûts
│   │   ├── Coûts mensuels
│   │   ├── Coûts annuels
│   │   └── Options gratuites / student plans
│   └── 0.9.3 Livrable : resources-costs.md
│   📋 Critère : proj_resources
│
├── 0.10 Préparation Soutenance
│   ├── 0.10.1 Créer le support de présentation
│   │   ├── Slides claires et concises
│   │   ├── Pas de texte excessif
│   │   └── Visuels pertinents (diagrammes, maquettes)
│   ├── 0.10.2 Préparer la démo (si applicable)
│   │   ├── Scénario de démo
│   │   └── Environnement stable
│   ├── 0.10.3 Préparer l'argumentation
│   │   ├── Arguments structurés par choix
│   │   ├── Preuves et données
│   │   └── Anticipation des questions
│   ├── 0.10.4 Répéter la présentation
│   │   ├── Timing
│   │   └── Répartition parole équipe
│   └── 0.10.5 Livrable : slides + script présentation
│   📋 Critères : pres_oral, pres_support, pres_argumentation
│
└── 0.11 Revue Qualité Documents
    ├── 0.11.1 Relecture croisée équipe
    ├── 0.11.2 Vérifier clarté et concision
    ├── 0.11.3 Corriger erreurs et incohérences
    ├── 0.11.4 Supprimer informations non pertinentes
    └── 0.11.5 Livrable : Documents finalisés
    📋 Critère : doc_quality
```

---

## Checklist Critères Epitech

| Critère | Lot WBS | Livrable |
|---------|---------|----------|
| `wbs_delivery` | 0.1 | wbs-betarena.md |
| `wbs_relevance` | 0.1 | Structure hiérarchique orientée livrables |
| `wbs_features` | 0.2 | features-requirements.md |
| `obs_delivery` | 0.3 | obs-betarena.md |
| `obs_relevance` | 0.3 | Responsabilités + allocation RH |
| `team_recruitment` | 0.4 | team-justification.md |
| `team_skills` | 0.4 | Mapping compétences |
| `team_practices` | 0.5 | quality-plan.md |
| `proj_methodology` | 0.6 | methodology.md |
| `proj_planning` | 0.7 | Outil configuré (Trello/etc.) |
| `proj_technos` | 0.8 | tech-stack.md + diagramme |
| `proj_resources` | 0.9 | resources-costs.md |
| `doc_diagram` | 0.1, 0.3 | WBS + OBS en diagrammes visuels |
| `doc_quality` | 0.11 | Tous documents relus |
| `pres_oral` | 0.10 | Présentation professionnelle |
| `pres_support` | 0.10 | Slides claires |
| `pres_argumentation` | 0.10 | Arguments structurés |

---

## Phase 1 — Discovery & Cadrage

```
1. DISCOVERY & CADRAGE
│
├── 1.1 Validation Données E-sport ⚠️ CRITIQUE
│   ├── 1.1.1 Tester Riot API (LoL)
│   │   ├── Créer compte développeur Riot
│   │   ├── Tester endpoints matchs/équipes
│   │   └── Documenter limites et quotas
│   ├── 1.1.2 Tester Riot API (Valorant)
│   │   ├── Évaluer données compétitives dispo
│   │   └── Identifier les manques
│   ├── 1.1.3 Évaluer solutions CS2
│   │   ├── Rechercher providers tiers (PandaScore, etc.)
│   │   ├── Comparer coûts et couverture
│   │   └── Décision Build or Buy
│   └── 1.1.4 Livrable : Rapport faisabilité API
│
├── 1.2 Cadrage Fonctionnel
│   ├── 1.2.1 Finaliser specs MVP
│   │   ├── Rédiger user stories Must Have
│   │   ├── Définir critères d'acceptation
│   │   └── Valider avec l'équipe
│   ├── 1.2.2 Définir paramètres économie
│   │   ├── Fixer capital de départ
│   │   ├── Fixer salaire hebdomadaire
│   │   └── Lister les succès MVP
│   └── 1.2.3 Livrable : Backlog priorisé
│
├── 1.3 Architecture Technique
│   ├── 1.3.1 Choisir stack technique
│   │   ├── Frontend (React/Vue/etc.)
│   │   ├── Backend (Node/Python/etc.)
│   │   └── Base de données
│   ├── 1.3.2 Concevoir architecture système
│   │   ├── Schéma composants
│   │   ├── Flux de données
│   │   └── Stratégie temps réel (WebSockets)
│   └── 1.3.3 Livrable : Dossier architecture
│
└── 1.4 Setup Projet
    ├── 1.4.1 Créer repositories Git
    ├── 1.4.2 Configurer environnements (dev/staging/prod)
    ├── 1.4.3 Setup CI/CD de base
    └── 1.4.4 Documenter conventions équipe
```

---

## Phase 2 — Design UX/UI

```
2. DESIGN UX/UI
│
├── 2.1 Design System Pixel Art 80s
│   ├── 2.1.1 Définir palette de couleurs
│   ├── 2.1.2 Créer typographie pixel
│   ├── 2.1.3 Designer icônes et éléments UI
│   ├── 2.1.4 Créer composants de base
│   │   ├── Boutons
│   │   ├── Inputs
│   │   ├── Cards
│   │   ├── Badges/Tags
│   │   └── Toasts/Notifications
│   └── 2.1.5 Livrable : Design System documenté
│
├── 2.2 Maquettes Parcours Clés
│   ├── 2.2.1 Onboarding
│   │   ├── Écran inscription
│   │   ├── Écran login
│   │   └── Premier pari guidé
│   ├── 2.2.2 Page d'accueil
│   │   ├── Liste matchs du jour
│   │   ├── Top 3 leaderboard
│   │   └── Solde et navigation
│   ├── 2.2.3 Parcours de pari
│   │   ├── Sélection match
│   │   ├── Bet slip (simple)
│   │   ├── Bet slip (combiné)
│   │   └── Confirmation et feedback
│   ├── 2.2.4 Profil utilisateur
│   │   ├── Stats personnelles
│   │   ├── Historique paris
│   │   └── Succès débloqués
│   ├── 2.2.5 Leaderboard & Social
│   │   ├── Classement général
│   │   ├── Système de ligues
│   │   └── Wall of Shame
│   └── 2.2.6 Livrable : Maquettes Figma/Sketch
│
├── 2.3 Design Prévention Gamifiée
│   ├── 2.3.1 Designer succès ironiques
│   │   ├── Visuels badges pixel art
│   │   └── Animations déblocage
│   ├── 2.3.2 Designer équivalences vie réelle
│   │   ├── Format affichage (kebabs, Netflix...)
│   │   └── Intégration dans l'UI
│   ├── 2.3.3 Designer toasts de sensibilisation
│   └── 2.3.4 Livrable : Assets prévention
│
├── 2.4 Responsive & Mobile-First
│   ├── 2.4.1 Adapter maquettes mobile
│   ├── 2.4.2 Adapter maquettes tablet
│   ├── 2.4.3 Adapter maquettes desktop
│   └── 2.4.4 Livrable : Maquettes responsive
│
└── 2.5 Validation Design
    ├── 2.5.1 Review interne équipe
    ├── 2.5.2 Tests utilisateurs (3-5 users)
    ├── 2.5.3 Itérations
    └── 2.5.4 Livrable : Maquettes validées
```

---

## Phase 3 — Développement Backend

```
3. DÉVELOPPEMENT BACKEND
│
├── 3.1 Infrastructure & Setup
│   ├── 3.1.1 Setup serveur/cloud
│   ├── 3.1.2 Configurer base de données
│   ├── 3.1.3 Setup Redis/cache
│   └── 3.1.4 Configurer WebSockets
│
├── 3.2 Module Authentification
│   ├── 3.2.1 Implémenter inscription
│   │   ├── Validation email
│   │   ├── Hash mot de passe
│   │   └── Création compte + crédits initiaux
│   ├── 3.2.2 Implémenter login/logout
│   │   ├── Génération JWT
│   │   └── Gestion sessions
│   ├── 3.2.3 Implémenter OAuth (Google/Discord)
│   ├── 3.2.4 Tests unitaires auth
│   └── 3.2.5 Livrable : API Auth fonctionnelle
│
├── 3.3 Module Économie Virtuelle
│   ├── 3.3.1 Implémenter gestion crédits
│   │   ├── Crédit/débit compte
│   │   ├── Historique transactions
│   │   └── Validation solde suffisant
│   ├── 3.3.2 Implémenter salaire hebdomadaire
│   │   ├── Job CRON versement
│   │   └── Notification versement
│   ├── 3.3.3 Tests unitaires économie
│   └── 3.3.4 Livrable : API Économie fonctionnelle
│
├── 3.4 Module Paris
│   ├── 3.4.1 Implémenter paris simple
│   │   ├── Création pari
│   │   ├── Validation (solde, match ouvert)
│   │   └── Stockage en BDD
│   ├── 3.4.2 Implémenter paris combiné
│   │   ├── Multi-sélection (max 10)
│   │   ├── Calcul cote combinée
│   │   └── Validation combinaisons
│   ├── 3.4.3 Implémenter calcul de cotes
│   │   ├── Algorithme de cotes
│   │   └── Mise à jour dynamique
│   ├── 3.4.4 Implémenter résolution paris
│   │   ├── Traitement post-match
│   │   ├── Calcul gains/pertes
│   │   └── Mise à jour soldes
│   ├── 3.4.5 Implémenter historique paris
│   ├── 3.4.6 Tests unitaires paris
│   └── 3.4.7 Livrable : API Paris fonctionnelle
│
├── 3.5 Module Contenus E-sport
│   ├── 3.5.1 Intégrer Riot API (LoL)
│   │   ├── Sync matchs à venir
│   │   ├── Sync résultats
│   │   └── Sync équipes/joueurs
│   ├── 3.5.2 Intégrer Riot API (Valorant)
│   ├── 3.5.3 Intégrer données CS2
│   ├── 3.5.4 Implémenter cache matchs
│   ├── 3.5.5 Implémenter jobs de sync
│   ├── 3.5.6 Tests intégration API
│   └── 3.5.7 Livrable : API Matchs fonctionnelle
│
├── 3.6 Module Social & Compétition
│   ├── 3.6.1 Implémenter leaderboard
│   │   ├── Calcul ROI
│   │   ├── Classement global
│   │   └── Cache leaderboard
│   ├── 3.6.2 Implémenter ligues
│   │   ├── Logique promotion/relégation
│   │   └── Attribution ligue
│   ├── 3.6.3 Implémenter Wall of Shame
│   ├── 3.6.4 Implémenter leaderboard équipe
│   ├── 3.6.5 Tests unitaires social
│   └── 3.6.6 Livrable : API Social fonctionnelle
│
├── 3.7 Module Succès & Prévention
│   ├── 3.7.1 Implémenter système de succès
│   │   ├── Définir conditions déblocage
│   │   ├── Tracking progression
│   │   └── Notification déblocage
│   ├── 3.7.2 Implémenter succès prévention
│   │   ├── "Flambeur express"
│   │   ├── "Économe"
│   │   ├── "Le Lundi Noir"
│   │   └── Autres succès ironiques
│   ├── 3.7.3 Implémenter streaks
│   ├── 3.7.4 Implémenter équivalences vie réelle
│   ├── 3.7.5 Tests unitaires succès
│   └── 3.7.6 Livrable : API Succès fonctionnelle
│
└── 3.8 Documentation API
    ├── 3.8.1 Documenter endpoints (Swagger/OpenAPI)
    ├── 3.8.2 Rédiger guide intégration
    └── 3.8.3 Livrable : Documentation API
```

---

## Phase 4 — Développement Frontend

```
4. DÉVELOPPEMENT FRONTEND
│
├── 4.1 Setup & Architecture
│   ├── 4.1.1 Initialiser projet (Vite/Next/etc.)
│   ├── 4.1.2 Configurer routing
│   ├── 4.1.3 Setup state management
│   ├── 4.1.4 Configurer client API
│   └── 4.1.5 Setup WebSocket client
│
├── 4.2 Implémenter Design System
│   ├── 4.2.1 Intégrer assets pixel art
│   ├── 4.2.2 Créer composants UI de base
│   │   ├── Button
│   │   ├── Input
│   │   ├── Card
│   │   ├── Badge
│   │   ├── Toast
│   │   └── Modal
│   ├── 4.2.3 Implémenter thème global
│   └── 4.2.4 Livrable : Storybook composants
│
├── 4.3 Pages Authentification
│   ├── 4.3.1 Page inscription
│   ├── 4.3.2 Page login
│   ├── 4.3.3 Intégration OAuth
│   ├── 4.3.4 Gestion état connecté
│   └── 4.3.5 Livrable : Auth fonctionnelle
│
├── 4.4 Page d'Accueil
│   ├── 4.4.1 Header avec solde
│   ├── 4.4.2 Liste matchs du jour
│   ├── 4.4.3 Widget Top 3 leaderboard
│   ├── 4.4.4 Navigation principale
│   └── 4.4.5 Livrable : Home fonctionnelle
│
├── 4.5 Parcours de Pari
│   ├── 4.5.1 Page liste matchs
│   │   ├── Filtres par jeu
│   │   ├── Cards matchs
│   │   └── Affichage cotes
│   ├── 4.5.2 Composant Bet Slip
│   │   ├── Ajout/suppression sélections
│   │   ├── Input mise
│   │   ├── Calcul gains potentiels
│   │   └── Mode simple/combiné
│   ├── 4.5.3 Confirmation pari
│   │   ├── Récapitulatif
│   │   ├── Validation
│   │   └── Feedback succès/erreur
│   ├── 4.5.4 Animations pixel art
│   └── 4.5.5 Livrable : Parcours pari fonctionnel
│
├── 4.6 Pages Profil & Historique
│   ├── 4.6.1 Page profil
│   │   ├── Avatar et pseudo
│   │   ├── Stats personnelles
│   │   └── Ligue actuelle
│   ├── 4.6.2 Page historique paris
│   │   ├── Liste paris passés
│   │   ├── Filtres (gagné/perdu/en cours)
│   │   └── Détail pari
│   ├── 4.6.3 Page succès
│   │   ├── Grille succès
│   │   ├── Progression
│   │   └── Succès débloqués/verrouillés
│   └── 4.6.4 Livrable : Profil fonctionnel
│
├── 4.7 Pages Social & Compétition
│   ├── 4.7.1 Page leaderboard
│   │   ├── Classement par ROI
│   │   ├── Filtres ligues
│   │   └── Recherche joueur
│   ├── 4.7.2 Composant ligues
│   │   ├── Badge ligue
│   │   └── Progression vers ligue suivante
│   ├── 4.7.3 Page Wall of Shame
│   │   ├── Anti-classement
│   │   └── Ton humoristique
│   ├── 4.7.4 Leaderboard équipe
│   └── 4.7.5 Livrable : Social fonctionnel
│
├── 4.8 Prévention Gamifiée UI
│   ├── 4.8.1 Intégrer équivalences vie réelle
│   ├── 4.8.2 Intégrer toasts sensibilisation
│   ├── 4.8.3 Animations succès ironiques
│   ├── 4.8.4 Affichage streaks
│   └── 4.8.5 Livrable : Prévention intégrée
│
├── 4.9 Responsive & Accessibilité
│   ├── 4.9.1 Adapter mobile
│   ├── 4.9.2 Adapter tablet
│   ├── 4.9.3 Adapter desktop
│   ├── 4.9.4 Tests accessibilité (a11y)
│   │   ├── Navigation clavier
│   │   ├── Contraste
│   │   └── Labels ARIA
│   └── 4.9.5 Livrable : App responsive et accessible
│
└── 4.10 Optimisation Performance
    ├── 4.10.1 Lazy loading
    ├── 4.10.2 Optimisation images
    ├── 4.10.3 Code splitting
    └── 4.10.4 Livrable : App performante
```

---

## Phase 5 — Intégration

```
5. INTÉGRATION
│
├── 5.1 Intégration Frontend ↔ Backend
│   ├── 5.1.1 Connecter auth
│   ├── 5.1.2 Connecter paris
│   ├── 5.1.3 Connecter économie
│   ├── 5.1.4 Connecter matchs
│   ├── 5.1.5 Connecter leaderboard
│   ├── 5.1.6 Connecter succès
│   └── 5.1.7 Livrable : App intégrée
│
├── 5.2 Intégration Temps Réel
│   ├── 5.2.1 WebSocket notifications
│   ├── 5.2.2 Mise à jour cotes live
│   ├── 5.2.3 Résultats matchs temps réel
│   └── 5.2.4 Livrable : Temps réel fonctionnel
│
├── 5.3 Tests d'Intégration
│   ├── 5.3.1 Tests end-to-end parcours pari
│   ├── 5.3.2 Tests end-to-end auth
│   ├── 5.3.3 Tests end-to-end leaderboard
│   └── 5.3.4 Livrable : Suite tests E2E
│
└── 5.4 Résolution Bugs Intégration
    ├── 5.4.1 Tracker bugs
    ├── 5.4.2 Prioriser et corriger
    └── 5.4.3 Livrable : App stable
```

---

## Phase 6 — Tests & QA

```
6. TESTS & QA
│
├── 6.1 Tests Fonctionnels
│   ├── 6.1.1 Rédiger scénarios de test
│   ├── 6.1.2 Exécuter tests manuels
│   │   ├── Parcours inscription
│   │   ├── Parcours pari simple
│   │   ├── Parcours pari combiné
│   │   ├── Leaderboard
│   │   └── Succès et prévention
│   ├── 6.1.3 Documenter anomalies
│   └── 6.1.4 Livrable : Rapport tests fonctionnels
│
├── 6.2 Tests Utilisateurs
│   ├── 6.2.1 Recruter testeurs (5-10 users)
│   ├── 6.2.2 Préparer protocole test
│   ├── 6.2.3 Sessions de test
│   ├── 6.2.4 Collecter feedbacks
│   ├── 6.2.5 Analyser résultats
│   └── 6.2.6 Livrable : Rapport tests utilisateurs
│
├── 6.3 Tests Performance
│   ├── 6.3.1 Tests charge API
│   ├── 6.3.2 Tests temps de réponse
│   ├── 6.3.3 Tests WebSocket sous charge
│   └── 6.3.4 Livrable : Rapport performance
│
├── 6.4 Tests Sécurité
│   ├── 6.4.1 Audit authentification
│   ├── 6.4.2 Tests injection SQL/XSS
│   ├── 6.4.3 Vérifier rate limiting
│   └── 6.4.4 Livrable : Rapport sécurité
│
├── 6.5 Corrections & Itérations
│   ├── 6.5.1 Prioriser bugs
│   ├── 6.5.2 Corriger bugs critiques
│   ├── 6.5.3 Implémenter améliorations UX
│   └── 6.5.4 Livrable : App corrigée
│
└── 6.6 Validation Finale
    ├── 6.6.1 Checklist go/no-go
    ├── 6.6.2 Validation équipe
    └── 6.6.3 Livrable : Feu vert déploiement
```

---

## Phase 7 — Déploiement

```
7. DÉPLOIEMENT
│
├── 7.1 Préparation Production
│   ├── 7.1.1 Configurer environnement prod
│   ├── 7.1.2 Configurer domaine et SSL
│   ├── 7.1.3 Configurer CDN
│   ├── 7.1.4 Setup monitoring (logs, alertes)
│   └── 7.1.5 Livrable : Infra prod prête
│
├── 7.2 Migration & Données
│   ├── 7.2.1 Migrer base de données
│   ├── 7.2.2 Seed données initiales
│   │   ├── Succès
│   │   ├── Ligues
│   │   └── Config économie
│   └── 7.2.3 Livrable : BDD prod prête
│
├── 7.3 Déploiement Application
│   ├── 7.3.1 Déployer backend
│   ├── 7.3.2 Déployer frontend
│   ├── 7.3.3 Vérifier WebSockets
│   ├── 7.3.4 Smoke tests production
│   └── 7.3.5 Livrable : App en production
│
├── 7.4 Documentation & Support
│   ├── 7.4.1 Rédiger guide utilisateur
│   ├── 7.4.2 Préparer FAQ
│   ├── 7.4.3 Documenter procédures ops
│   └── 7.4.4 Livrable : Documentation complète
│
└── 7.5 Lancement
    ├── 7.5.1 Activer accès utilisateurs
    ├── 7.5.2 Monitorer premiers jours
    ├── 7.5.3 Collecter feedbacks early users
    └── 7.5.4 Livrable : MVP LANCÉ 🚀
```

---

## Résumé des Phases

| Phase | Nom | Livrables Clés |
|-------|-----|----------------|
| **0** | **Livrables Projet** | WBS, OBS, Features, Quality Plan, Tech Stack, Slides |
| 1 | Discovery & Cadrage | Rapport API, Backlog, Architecture |
| 2 | Design UX/UI | Design System, Maquettes validées |
| 3 | Développement Backend | APIs fonctionnelles, Documentation |
| 4 | Développement Frontend | App responsive, Storybook |
| 5 | Intégration | App intégrée, Tests E2E |
| 6 | Tests & QA | Rapports tests, App corrigée |
| 7 | Déploiement | MVP en production 🚀 |

---

## Dépendances Critiques

```
┌─────────────────────────────────────────────────────────────────┐
│                    CHEMIN CRITIQUE                              │
└─────────────────────────────────────────────────────────────────┘

1.1 Validation API  ──►  3.5 Module E-sport  ──►  5.2 Temps Réel
        │
        ▼
   ⚠️ BLOQUANT : Si API non validées, MVP compromis
        │
        ▼
   Décision : Réduire scope jeux OU trouver alternative
```

---

## Légende

| Symbole | Signification |
|---------|---------------|
| **X.Y** | Lot de travail |
| **X.Y.Z** | Tâche |
| ⚠️ | Point d'attention / Risque |
| 🚀 | Jalon majeur |
| Livrable | Résultat tangible attendu |

---

*Généré depuis la synthèse brainstorming du 19 janvier 2026*
