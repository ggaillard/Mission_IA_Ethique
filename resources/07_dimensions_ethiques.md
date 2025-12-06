# ⭐ Les 5 Dimensions Éthiques de l'IA

## 🎯 Vue d'ensemble

Toute décision technique impliquant de l'IA doit être évaluée selon **5 dimensions éthiques** complémentaires.

```
        ⚖️ LÉGALITÉ
            │
    ┌───────┼───────┐
    │       │       │
🔍 TRANSPARENCE   ⚡ ÉQUITÉ
    │       │       │
    └───────┼───────┘
            │
    ┌───────┴───────┐
    │               │
🧑 AUTONOMIE    🌱 SOUTENABILITÉ
```

---

## ⚖️ 1. Légalité

### Définition
Le système respecte-t-il les lois et règlements en vigueur ?

### Questions clés
- RGPD respecté (consentement, droit à l'explication) ?
- AI Act : quelle classification de risque ?
- Droit du travail : décision automatisée autorisée ?
- Sectoriels : règles spécifiques (santé, finance...) ?

### Indicateurs
| Conforme | Non conforme |
|----------|--------------|
| Consentement explicite | Collecte sans accord |
| Droit de recours | Décision sans appel |
| Documentation complète | Boîte noire totale |

---

## 🔍 2. Transparence

### Définition
Les personnes impactées comprennent-elles comment et pourquoi la décision est prise ?

### Questions clés
- L'utilisateur sait-il qu'une IA décide ?
- Peut-il comprendre les critères ?
- Les limites sont-elles communiquées ?

### Niveaux de transparence

```
┌─────────────────────────────────────────┐
│  Niveau 1 : Existence                   │
│  "Une IA est utilisée"                  │
├─────────────────────────────────────────┤
│  Niveau 2 : Fonctionnement              │
│  "L'IA analyse X, Y, Z"                 │
├─────────────────────────────────────────┤
│  Niveau 3 : Explication individuelle    │
│  "Vous êtes rejeté car score X faible"  │
├─────────────────────────────────────────┤
│  Niveau 4 : Contrefactuel               │
│  "Avec +2 ans XP, vous seriez accepté"  │
└─────────────────────────────────────────┘
```

---

## ⚡ 3. Équité

### Définition
Le système traite-t-il équitablement tous les groupes, sans discrimination ?

### Questions clés
- Mêmes taux d'acceptation/rejet par groupe ?
- Même précision par groupe ?
- Variables proxy identifiées et supprimées ?

### Caractéristiques protégées
- Genre
- Origine ethnique
- Âge
- Handicap
- Religion
- Orientation sexuelle

### Métriques
| Métrique | Seuil alerte |
|----------|--------------|
| Écart taux acceptation | > 10% |
| Disparate Impact | < 0.8 ou > 1.25 |
| Écart précision | > 5% |

---

## 🧑 4. Autonomie

### Définition
Les personnes impactées gardent-elles le contrôle et la capacité de décider ?

### Questions clés
- Un humain peut-il réviser la décision ?
- L'utilisateur peut-il contester ?
- La décision est-elle réversible ?

### Niveaux d'autonomie

```
❌ Autonomie nulle
   → Décision 100% automatique, pas de recours

⚠️ Autonomie limitée  
   → Recours possible mais complexe

✅ Autonomie préservée
   → Humain dans la boucle, contestation simple
```

---

## 🌱 5. Soutenabilité

### Définition
Le système est-il bénéfique à long terme pour la société et l'environnement ?

### Questions clés
- Impact sur l'emploi ?
- Renforce ou réduit les inégalités ?
- Coût environnemental (énergie, CO2) ?
- Effet sur la diversité ?

### Dimensions

| Dimension | Question |
|-----------|----------|
| **Sociale** | Crée-t-il de l'exclusion ? |
| **Économique** | Qui en profite ? Qui en souffre ? |
| **Environnementale** | Coût carbone acceptable ? |
| **Démocratique** | Renforce-t-il les pouvoirs existants ? |

---

## 📝 Grille d'évaluation rapide

| Dimension | Score (0-5) | Commentaire |
|-----------|-------------|-------------|
| ⚖️ Légalité | /5 | |
| 🔍 Transparence | /5 | |
| ⚡ Équité | /5 | |
| 🧑 Autonomie | /5 | |
| 🌱 Soutenabilité | /5 | |
| **TOTAL** | **/25** | |

**Interprétation :**
- 20-25 : Système éthique
- 15-19 : Améliorations nécessaires
- 10-14 : Risques significatifs
- < 10 : Ne pas déployer

---

## 📚 Ressources
- [Ethics Guidelines for Trustworthy AI (EU)](https://digital-strategy.ec.europa.eu/)
- [IEEE Ethically Aligned Design](https://ethicsinaction.ieee.org/)
- [Montreal Declaration for Responsible AI](https://www.montrealdeclaration-responsibleai.com/)