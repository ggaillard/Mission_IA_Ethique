# 📦 Cas Amazon RH - L'IA de Recrutement Discriminante

## 📅 Contexte (2014-2018)

Amazon développe une IA pour automatiser le tri des CV et identifier les "meilleurs" candidats pour des postes techniques.

**Objectif** : Réduire le temps de recrutement, améliorer la "qualité" des embauches.

---

## 🔍 Ce qui s'est passé

### Les données d'entraînement

```
┌─────────────────────────────────────────┐
│  10 ans de CV et d'embauches Amazon     │
│                                         │
│  Répartition des embauchés :            │
│  - Hommes : ~85%                        │
│  - Femmes : ~15%                        │
│                                         │
│  → L'IA apprend que "bon candidat"      │
│    = profil masculin                    │
└─────────────────────────────────────────┘
```

### Les biais découverts

| Comportement de l'IA | Explication |
|---------------------|-------------|
| Pénalise "women's" dans CV | "Women's chess club" → score baissé |
| Favorise verbes "masculins" | "Executed", "captured" mieux notés |
| Pénalise universités féminines | Diplômes de colleges féminins → score baissé |
| Surpondère sports masculins | Rugby, football → bonus implicite |

---

## 💡 Pourquoi c'est arrivé

### 1. Biais historique
Les données reflétaient 10 ans de discrimination systémique dans la tech.

### 2. Absence d'audit
Pas de vérification d'équité avant déploiement.

### 3. Optimisation aveugle
L'IA optimisait pour "ressembler aux embauchés passés", pas pour "trouver les meilleurs candidats".

### 4. Proxies non identifiés
Le genre n'était pas une feature directe, mais des dizaines de proxies l'encodaient.

---

## 🛑 Conséquences

| Impact | Détail |
|--------|--------|
| **Projet abandonné** | Amazon stoppe le développement en 2017 |
| **Réputation** | Fuite médiatique en 2018, bad buzz mondial |
| **Industrie** | Prise de conscience générale sur les biais IA |
| **Régulation** | Accélère réflexion sur AI Act |

---

## 📝 Leçons pour TalentFlow (et vous)

### ❌ Ce qu'Amazon a mal fait

1. Entraîné sur données biaisées sans audit
2. Pas de métriques d'équité
3. Pas d'humain dans la boucle
4. Proxies non identifiés
5. Déployé sans test sur populations diverses

### ✅ Ce qu'il fallait faire

1. **Auditer les données** avant entraînement
2. **Équilibrer** le dataset (resampling)
3. **Identifier** les features proxy
4. **Mesurer** l'équité par groupe
5. **Garder** un humain dans la boucle
6. **Monitorer** en production

---

## 🔄 Comparaison avec TalentFlow

| Aspect | Amazon | TalentFlow |
|--------|--------|------------|
| Données biaisées | ✅ Oui | ✅ Oui (78% hommes) |
| Proxy genre | ✅ "women's" | ✅ name_embedding |
| Audit équité | ❌ Non | ❌ Non |
| Explicabilité | ❌ Non | ❌ Non |
| Humain boucle | ❌ Non | ❌ Non |

**→ TalentFlow reproduit les mêmes erreurs qu'Amazon.**

---

## 💭 Question éthique

> "Si Amazon, avec ses milliers d'ingénieurs et ses milliards de dollars, n'a pas réussi à créer une IA de recrutement équitable... est-ce que l'automatisation du recrutement est une bonne idée ?"

---

## 📚 Ressources
- [Reuters - Amazon scraps secret AI recruiting tool](https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G)
- [MIT Technology Review - Analysis](https://www.technologyreview.com/)
- [Harvard Business Review - What happened](https://hbr.org/)