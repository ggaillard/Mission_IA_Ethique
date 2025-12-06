# 📋 Audit d'Équité Algorithmique

## 🎯 Objectif

Un **audit d'équité** vérifie qu'un système d'IA traite équitablement tous les groupes, sans discrimination basée sur des caractéristiques protégées.

---

## 📊 Métriques de fairness

### 1. Parité démographique (Demographic Parity)

> Taux d'acceptation égal entre groupes

```
Taux acceptation Hommes = Taux acceptation Femmes
```

**Exemple TalentFlow :**
- Hommes acceptés : 69%
- Femmes acceptées : 33%
- **Écart : 36 points → VIOLATION**

### 2. Égalité des chances (Equalized Odds)

> Taux de vrais positifs ET faux positifs égaux

```
Vrais positifs Hommes = Vrais positifs Femmes
Faux positifs Hommes = Faux positifs Femmes
```

### 3. Parité prédictive (Predictive Parity)

> Précision égale entre groupes

```
Précision groupe A = Précision groupe B
```

---

## 🛠️ Outils d'audit

### Fairlearn (Microsoft)

```python
from fairlearn.metrics import MetricFrame
from sklearn.metrics import accuracy_score

# Calculer métriques par groupe
metric_frame = MetricFrame(
    metrics=accuracy_score,
    y_true=y_test,
    y_pred=predictions,
    sensitive_features=df['gender']
)

print(metric_frame.by_group)
# gender
# Femme    0.72
# Homme    0.89  ← Écart significatif !
```

### AI Fairness 360 (IBM)

```python
from aif360.metrics import BinaryLabelDatasetMetric

metric = BinaryLabelDatasetMetric(
    dataset,
    privileged_groups=[{'gender': 1}],
    unprivileged_groups=[{'gender': 0}]
)

print(f"Disparate Impact: {metric.disparate_impact()}")
# < 0.8 ou > 1.25 → problème potentiel
```

---

## 📝 Checklist d'audit

### Phase 1 : Données
- [ ] Représentation équilibrée des groupes ?
- [ ] Variables proxy identifiées ?
- [ ] Données historiques biaisées ?

### Phase 2 : Modèle
- [ ] Features sensibles exclues ?
- [ ] Métriques fairness calculées ?
- [ ] Seuils de décision équitables ?

### Phase 3 : Production
- [ ] Monitoring équité temps réel ?
- [ ] Alertes si dérive ?
- [ ] Recours humain possible ?

---

## 🔧 Techniques de mitigation

| Technique | Phase | Description |
|-----------|-------|-------------|
| **Rééchantillonnage** | Pré-traitement | Équilibrer les données |
| **Repondération** | Entraînement | Poids différents par groupe |
| **Seuils différenciés** | Post-traitement | Ajuster seuils par groupe |
| **Adversarial debiasing** | Entraînement | Pénaliser prédictions biaisées |

---

## ⚠️ Attention : Trade-offs

Il est souvent **impossible** de satisfaire toutes les métriques simultanément :

```
Parité démographique ←→ Égalité des chances
         ↑                      ↑
    "Mêmes taux"         "Même précision"
```

**Choix éthique** à documenter et justifier.

---

## 📊 Rapport d'audit type

```markdown
# Rapport d'Audit Équité - [Système]
Date : [Date]
Auditeur : [Nom]

## Résumé exécutif
- Score global équité : [X/100]
- Groupes analysés : [Genre, Âge, ...]
- Problèmes identifiés : [Liste]

## Métriques détaillées
[Tableaux par groupe]

## Recommandations
1. [Action prioritaire]
2. [Action secondaire]

## Suivi
- Prochain audit : [Date]
- Responsable : [Nom]
```

---

## 📚 Ressources
- [Fairlearn](https://fairlearn.org/)
- [AI Fairness 360](https://aif360.mybluemix.net/)
- [Google ML Fairness](https://developers.google.com/machine-learning/fairness-overview)