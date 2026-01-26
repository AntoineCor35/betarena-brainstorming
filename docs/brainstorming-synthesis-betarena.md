# Bet Arena — Synthèse Brainstorming Produit

> **Date :** 19 janvier 2026
> **Session facilitée par :** Mary, Business Analyst
> **Techniques utilisées :** Five Whys, Assumption Reversal, Role Playing, SCAMPER

---

## 1. Vision Produit

### Raison d'être (Five Whys)

| Niveau | Insight |
|--------|---------|
| Surface | Projet d'école + betting e-sport interdit en France |
| Niveau 2 | Le pari est une forme de participation indirecte au spectacle |
| Niveau 3 | Besoin de compétition, challenge, appartenance chez les fans |
| Niveau 4 | Le spectateur veut devenir acteur avec des enjeux personnels |
| **Racine** | **Recréer le frisson du parieur sans les risques — ET éduquer sur les comportements à risque via l'expérience elle-même** |

### Double Mission

| Mission | Comment |
|---------|---------|
| **Engager** | Simuler l'intensité émotionnelle du betting (enjeux, tension, progression) |
| **Éduquer** | Utiliser la gamification pour révéler les comportements à risque plutôt que les punir |

### Pitch en une phrase

> *"Bet Arena est un simulateur de paris e-sport qui utilise la gamification pour créer l'engagement ET révéler les comportements à risque — une alternative légale et éducative pour les fans français privés de betting e-sport."*

---

## 2. Contraintes & Paramètres

### Contraintes légales & éthiques
- Aucun argent réel (pas de gambling)
- Crédits virtuels uniquement
- Prévention et sensibilisation intégrées nativement
- Pas de reproduction exacte d'un bookmaker classique

### Contraintes produit
- Mobile-first obligatoire
- Gaming-oriented UI/UX — **Direction artistique pixel art arcade 80s**
- Accessibilité de base + responsive
- Navigation claire malgré la complexité fonctionnelle

### Contraintes techniques
- Données e-sport en temps réel (API + scraping) — **RISQUE : À VALIDER**
- WebSockets / temps réel requis
- Backend solide (cotes, paris combinés, économie virtuelle)
- Scalabilité pensée dès le départ

### Cible utilisateur
- Étudiants / jeunes adultes
- Fans d'e-sport (LoL, Valorant en priorité)
- Sensibles à la gamification, au classement, à l'appartenance sociale

---

## 3. Hypothèses Validées & Risques (Assumption Reversal)

| Hypothèse | Verdict | Action |
|-----------|---------|--------|
| Valeur des crédits virtuels | ⚠️ Nuancé | Gamification = condition de succès, pas bonus |
| Prévention vs engagement | ✅ OK | Gamifier la prévention (humour, équivalences réelles) |
| Données e-sport | ❌ **RISQUE** | **Valider APIs avant de figer le MVP** |
| Appartenance école/club | ✅ OK | Leaderboard équipe > école en priorité |
| Paris simples suffisants | ❌ Non | **Paris combiné → Must Have** |
| Identité visuelle | ✅ Fort | Pixel art 80s = différenciateur clair |

### Risque critique : Données e-sport

| Jeu | API officielle | Complexité |
|-----|----------------|------------|
| **LoL** | Riot API (gratuite, bien documentée) | ✅ Accessible |
| **Valorant** | Riot API (plus limitée) | ⚠️ Données compétitives restreintes |
| **CS2** | Pas d'API officielle | ❌ Scraping ou providers tiers |

**Décision à prendre :** Build or Buy ? Quels jeux viables pour le MVP ?

---

## 4. Personas & Parcours (Role Playing)

### Lucas, 20 ans — Fan hardcore de LoL

**Boucles de rétention identifiées :**

| Temporalité | Levier | Mécanisme |
|-------------|--------|-----------|
| Demain | Daily reward, matchs du jour | FOMO + routine |
| Cette semaine | Leaderboard, succès en cours | Progression visible |
| Ce mois | Grosse compétition (Worlds, Major) | Événement fédérateur |
| Long terme | Networth, avatar, cosmétiques | Statut social + collection |

### Mehdi, 22 ans — Le flambeur

**Stratégie prévention :**

| Mécanisme | Effet |
|-----------|-------|
| Humour noir assumé | "Tu viens de perdre 3 kebabs" → dédramatise mais marque |
| Wall of Shame | Transforme la honte en badge social ironique |
| Succès "Le Flambeur" | Reconnaissance du comportement sans jugement |
| Miroir des biais | Afficher "Tu peux te refaire" PUIS révéler le piège cognitif |
| Stats perso vs globales | Confrontation douce avec la réalité |

> **Insight clé :** Parce qu'il n'y a pas d'argent réel, on peut pousser les curseurs à fond sur l'expérience de perte — c'est un **simulateur de crash** éducatif.

### Claire — Membre du jury pédagogique

**Arguments clés :**

| Angle | Argument |
|-------|----------|
| Problème réel | Betting e-sport interdit en FR → fans sur VPN (risques légaux/financiers) |
| Solution unique | Alternative légale qui capture le frisson sans les risques |
| Innovation | Prévention gamifiée — on éduque PAR le jeu |
| Marché | Aucune concurrence directe sur ce positionnement en France |
| Identité | Pixel art 80s ≠ bookmaker classique |
| Impact social | Sensibilisation aux biais cognitifs du parieur |

### Théo, 19 ans — Le casual curieux

**Onboarding idéal :**

| Étape | Action | Durée cible |
|-------|--------|-------------|
| 1 | Création compte (email ou OAuth) | 30 sec |
| 2 | Crédits de départ (montant fixe pour tous) | immédiat |
| 3 | Landing sur page d'accueil (matchs, cotes, leaderboard) | immédiat |
| 4 | Premier pari → Succès débloqué | < 2 min |

---

## 5. Système Économique

| Mécanisme | Détail |
|-----------|--------|
| **Capital de départ** | Identique pour tous (ex: 1000 crédits) |
| **Salaire hebdo** | Recharge fixe chaque semaine (ex: 500 crédits) |
| **Économie fermée** | Pas d'achat de crédits = égalité des chances |

### Bénéfices

- **Équité** : Leaderboard reflète le skill, pas le grind
- **Prévention renforcée** : "Tu as claqué ton salaire en 2h"
- **Comparaison facile** : Même base pour tous
- **Tension hebdo** : Ressource limitée = chaque pari compte

### Succès liés au salaire

| Succès | Condition |
|--------|-----------|
| 🔥 "Flambeur express" | Salaire claqué en < 24h |
| 💎 "Économe" | Terminer la semaine avec > 80% du salaire |
| 📈 "Self-made" | Doubler son capital sur une semaine |
| 💸 "Le Lundi Noir" | Tout perdre le jour du versement |
| 🏦 "Millionnaire virtuel" | Atteindre 10x le capital de départ |

---

## 6. Features MVP — Mises à jour (SCAMPER)

### Modifications au MoSCoW original

| Feature | Avant | Après | Justification |
|---------|-------|-------|---------------|
| **Paris combiné** | Should Have | **Must Have** | Profondeur stratégique essentielle |
| **Leaderboard** | Should Have | **Must Have** | Core de l'engagement |
| **Système de succès** | Should Have | **Must Have** | Intègre la prévention |

### Leaderboard — Décisions MVP

| Décision | Détail |
|----------|--------|
| ✅ **ROI comme métrique** | Valorise la stratégie, pas le volume |
| ✅ **Système de ligues** | Bronze → Silver → Gold → Diamond |
| ✅ **Top 3 sur page d'accueil** | Avatars pixel art, pseudo, ROI |
| ✅ **Wall of Shame** | Anti-leaderboard officiel avec ton humoristique |
| 🟡 Saisons compétitives | Post-MVP |

### Système de Paris — Décisions MVP

| Décision | Détail |
|----------|--------|
| ✅ **Cotes numériques classiques** | Garder l'expérience betting mature |
| ✅ **Combinés limités à 10 paris** | Simplicité + profondeur suffisante |
| ✅ **Pas de live betting** | Résoudre temps réel d'abord |
| 🟡 Paris in-game | Post-MVP, si API le permet |
| 🟡 Cash-out | Post-MVP |

### Prévention Gamifiée — Décisions MVP

| Décision | Détail |
|----------|--------|
| ✅ **Succès prévention intégrés** | Pas de catégorie séparée "prévention" |
| ✅ **Streaks double sens** | Responsable + pertes |
| ✅ **Équivalences vie réelle** | Gains ET pertes (kebabs, Netflix, etc.) |
| ✅ **Succès ironiques** | "Flambeur", "Yolo King", etc. |
| ✅ **Notifications unifiées** | Pas de catégorie désactivable |
| 🟡 Avatar/mascotte réactif | Post-MVP |

---

## 7. MVP Consolidé

### Must Have (mis à jour)

#### Authentification & Compte
- Login / Auth
- Création de compte
- Pseudo + avatar par défaut

#### Système de Paris
- Système de pari simple
- **Système de pari combiné (max 10 paris)**
- Calcul de cote
- Résultat après match
- Historique de ses bets

#### Monnaie & Fonds
- Une monnaie (crédits virtuels)
- **Capital de départ identique pour tous**
- **Salaire hebdomadaire fixe**
- Voir mes fonds

#### Contenus & Matchs
- Tableau des matchs à venir
- 3 jeux minimum (Valo, LoL, CS) — **sous réserve validation API**

#### Interface
- Dashboard visuel
- Navigation claire
- Responsive
- Accessibilité de base
- **Direction artistique pixel art arcade 80s**

#### Social & Compétition
- **Leaderboard par ROI**
- **Système de ligues (Bronze → Diamond)**
- **Top 3 sur page d'accueil**
- **Wall of Shame**
- **Système de succès (incluant prévention)**
- Leaderboard par équipe/club

#### Prévention Gamifiée
- **Succès ironiques intégrés**
- **Streaks (responsable + pertes)**
- **Équivalences vie réelle**
- Notifications/toasts de sensibilisation

---

## 8. Roadmap Post-MVP

### Phase 2 — Engagement

- Saisons compétitives
- Daily rewards
- Notifications push avancées
- Partage social (succès, gains, position)
- Avatar/cosmétiques
- Leaderboard par école

### Phase 3 — Profondeur

- Paris in-game (First Blood, etc.) — si API OK
- Cash-out
- Live betting — si temps réel résolu
- Mascotte/avatar réactif (prévention)
- Stats Spotify Wrap

### Phase 4+ — Vision

- Application mobile native
- 4ème jeu (Rocket League)
- Système d'amis
- Mini-jeux
- Widgets / Dynamic Island

---

## 9. Risques & Prochaines Étapes

### Risques identifiés

| Risque | Criticité | Mitigation |
|--------|-----------|------------|
| **Accès données e-sport** | 🔴 Critique | Valider APIs (Riot, PandaScore) AVANT dev |
| Valeur perçue des crédits | 🟡 Moyen | Gamification robuste dès le MVP |
| Équilibre prévention/fun | 🟡 Moyen | Tests utilisateurs early |

### Actions immédiates

1. **Valider l'accès aux données** — LoL (Riot API), Valorant, CS2
2. **Définir le montant** — Capital de départ + salaire hebdo
3. **Maquetter l'onboarding** — Parcours < 3 min jusqu'au premier pari
4. **Prototyper le Wall of Shame** — Ton, succès, équivalences

---

## 10. Différenciation vs Concurrence

| | Bookmakers classiques | Unikrn / BUFF | **Bet Arena** |
|---|---|---|---|
| Argent réel | ✅ | ✅ (certains pays) | ❌ |
| E-sport focus | Partiel | ✅ | ✅ |
| Légal en France | ❌ (e-sport) | ❌ | ✅ |
| Gamification | Faible | Moyenne | **Forte** |
| Prévention | Disclaimer légal | Faible | **Core du produit** |
| Identité visuelle | Corporate | Gaming corporate | **Pixel art 80s** |
| Cible | Parieurs adultes | Gamers internationaux | **Étudiants FR** |

---

*Document généré le 19 janvier 2026*
*Session de brainstorming Bet Arena*
