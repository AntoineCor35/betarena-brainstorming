# Bet Arena — Organizational Breakdown Structure (OBS)

> **Date** : Février 2026
> **Projet** : Bet Arena — Simulateur de paris e-sportifs gamifié
> **Version** : 1.0

---

## 1. Vue d'ensemble

L'OBS (Organizational Breakdown Structure) définit la structure organisationnelle du projet Bet Arena. L'équipe est composée de 8 membres organisés en 6 unités techniques, chacune avec un lead responsable.

---

## 2. Organigramme

```
                              ┌────────────────────┐
                              │   CHEF DE PROJET   │
                              │     Antoine C.     │
                              └─────────┬──────────┘
                                        │
        ┌───────────┬───────────┬───────┼───────┬───────────┬───────────┐
        │           │           │       │       │           │           │
  ┌─────▼─────┐ ┌───▼───┐ ┌─────▼─────┐ │ ┌─────▼─────┐ ┌───▼───┐ ┌─────▼─────┐
  │ Frontend  │ │Backend│ │   Web3    │ │ │   Data    │ │ Game  │ │  DevOps   │
  │  mobile   │ │  API  │ │           │ │ │           │ │Design │ │           │
  └─────┬─────┘ └───┬───┘ └─────┬─────┘ │ └─────┬─────┘ └───┬───┘ └─────┬─────┘
        │           │           │       │       │           │           │
   Sarah V.    Benjamin B.   Sally C.   │   Yannis D.   Stéphane M.  Maxence G.
     (Lead)      (Lead)       (Lead)    │     (Lead)      (Lead)       (Lead)
```

---

## 3. Chef de Projet

| Nom | Rôle | Responsabilités |
|-----|------|-----------------|
| **Antoine C.** | Chef de projet | Coordination globale, planification, gestion des risques, communication avec Epitech, arbitrage |

---

## 4. Description des Unités

### 4.1 Frontend Mobile

| Attribut | Description |
|----------|-------------|
| **Lead** | Sarah V. |
| **Membres** | Benjamin B., Théo L. |
| **Périmètre** | Application mobile iOS et Android avec React Native (Expo). Interface utilisateur pixel art 80s, navigation, intégration API REST/WebSocket, animations et feedback utilisateur. |
| **Technologies** | React Native, Expo, TypeScript, Zustand, React Navigation |
| **Livrables** | Application mobile déployée sur App Store et Google Play |

---

### 4.2 Backend API

| Attribut | Description |
|----------|-------------|
| **Lead** | Benjamin B. |
| **Membres** | Yannis D., Sally C. |
| **Périmètre** | API REST et WebSocket pour l'application mobile. Logique métier des paris (simples et combinés), économie virtuelle (wallet, transactions), authentification JWT, résolution automatique des paris. |
| **Technologies** | Node.js, TypeScript, Express/Fastify, PostgreSQL, Prisma, Redis |
| **Livrables** | API backend déployée, documentation endpoints |

---

### 4.3 Web3

| Attribut | Description |
|----------|-------------|
| **Lead** | Sally C. |
| **Membres** | Maxence G., Théo L. |
| **Périmètre** | Intégration blockchain Ethereum. Développement du token ERC-20 (BETA), smart contracts pour les paris décentralisés, intégration des wallets (MetaMask, WalletConnect). |
| **Technologies** | Solidity, Hardhat, Ethers.js, TypeScript |
| **Livrables** | Smart contracts déployés, documentation technique blockchain |

---

### 4.4 Data

| Attribut | Description |
|----------|-------------|
| **Lead** | Yannis D. |
| **Membres** | Antoine C., Sarah V. |
| **Périmètre** | Pipeline de données e-sport. Intégration des APIs PandaScore (calendrier, pré-match) et Liquipedia (résultats, historique). Moteur de calcul des cotes basé sur les statistiques des équipes. Gestion du cache et du quota API. |
| **Technologies** | Python, Pandas, NumPy, PostgreSQL, Redis |
| **Livrables** | Pipeline de synchronisation fonctionnel, moteur de cotes, analytics |

---

### 4.5 Game Design

| Attribut | Description |
|----------|-------------|
| **Lead** | Stéphane M. |
| **Membres** | Sarah V., Maxence G. |
| **Périmètre** | Conception des mécaniques de jeu et gamification. Système de succès/achievements, ligues (Bronze→Diamond), leaderboards, Wall of Shame, prévention gamifiée (badges ironiques, équivalences vie réelle). Direction artistique pixel art 80s. |
| **Technologies** | Figma, outils de game design |
| **Livrables** | Spécifications UX/UI, design system, assets pixel art, règles de gamification |

---

### 4.6 DevOps

| Attribut | Description |
|----------|-------------|
| **Lead** | Maxence G. |
| **Membres** | Théo L. |
| **Périmètre** | Infrastructure et déploiement continu. Pipeline CI/CD (lint, tests, build, deploy), containerisation Docker, gestion des secrets, déploiement sur les stores (App Store, Google Play), monitoring et logs. |
| **Technologies** | Docker, GitHub Actions, Railway/Render, Vercel/Netlify |
| **Livrables** | Pipeline CI/CD opérationnel, infrastructure déployée, documentation déploiement |

---

## 5. Matrice des Membres

| Membre | Unités | Rôle Lead |
|--------|--------|-----------|
| **Antoine C.** | Chef de projet, Data | Chef de projet |
| **Sarah V.** | Frontend mobile, Data, Game design | Frontend mobile |
| **Benjamin B.** | Frontend mobile, Backend API | Backend API |
| **Sally C.** | Backend API, Web3 | Web3 |
| **Yannis D.** | Backend API, Data | Data |
| **Stéphane M.** | Game design | Game design |
| **Maxence G.** | Web3, Game design, DevOps | DevOps |
| **Théo L.** | Frontend mobile, Web3, DevOps | - |

---

## 6. Matrice RACI par Epic

| Epic | Antoine C. | Sarah V. | Benjamin B. | Sally C. | Yannis D. | Stéphane M. | Maxence G. | Théo L. |
|------|------------|----------|-------------|----------|-----------|-------------|------------|---------|
| **Epic 1: Foundation & Auth** | A | R | R | C | C | I | R | R |
| **Epic 2: E-sport Data & Odds** | A | C | R | C | R | I | C | C |
| **Epic 3: Betting & Economy** | A | R | R | R | R | C | C | R |
| **Epic 4: Social & Achievements** | A | R | R | C | C | R | R | R |
| **Epic 5: Polish & Launch** | A | R | R | C | C | R | R | R |

**Légende :**
- **R** = Responsible (Réalise)
- **A** = Accountable (Approuve)
- **C** = Consulted (Consulté)
- **I** = Informed (Informé)

---

## 7. Répartition par Unité et Epic

| Unité | Epic 1 | Epic 2 | Epic 3 | Epic 4 | Epic 5 |
|-------|--------|--------|--------|--------|--------|
| **Frontend mobile** | Setup app Expo, navigation, auth screens | Match list, match detail | Betting screens, wallet display | Leaderboard, achievements, club | Polish UI, animations, onboarding |
| **Backend API** | Setup serveur, endpoints auth | Endpoints matchs | Endpoints paris, wallet, résolution | Endpoints leaderboard, achievements, clubs | Optimisation, bugfix |
| **Web3** | - | - | Intégration token (optionnel) | Smart contracts (optionnel) | Tests blockchain |
| **Data** | - | Pipeline PandaScore/Liquipedia, moteur cotes | - | Stats globales | Monitoring data |
| **Game design** | - | - | UX paris | Gamification, succès, prévention | Polish UX, landing page |
| **DevOps** | CI/CD, infrastructure | - | - | - | Déploiement stores, monitoring |

---

## 8. Notes

1. **Polyvalence** : Chaque membre intervient sur plusieurs unités selon ses compétences et la charge de travail.

2. **Web3 optionnel** : L'intégration blockchain peut être reportée post-MVP selon l'avancement.

3. **Leads** : Chaque lead est responsable de la coordination et de la qualité des livrables de son unité.

4. **Chef de projet** : Antoine C. assure la coordination inter-unités et le lien avec Epitech.
