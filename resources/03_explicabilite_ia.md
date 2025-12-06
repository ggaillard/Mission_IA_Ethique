# 🔍 Explicabilité de l'IA (XAI)

## 🎯 Définition

L'**explicabilité** (ou XAI - eXplainable AI) est la capacité d'un système d'IA à expliquer ses décisions de manière compréhensible par un humain.

> "Si vous ne pouvez pas expliquer pourquoi l'IA a pris cette décision, vous ne devriez probablement pas l'utiliser pour des décisions impactantes."

---

## 🤔 Pourquoi c'est important ?

| Enjeu | Raison |
|-------|--------|
| **Légal** | RGPD Art.22 : droit à l'explication |
| **Éthique** | Responsabilité des décisions |
| **Confiance** | Utilisateurs et régulateurs |
| **Debug** | Identifier les erreurs et biais |
| **Amélioration** | Comprendre pour améliorer |

---

## 📊 Niveaux d'explicabilité

```
┌─────────────────────────────────────────┐
│  🟢 Modèles interprétables              │
│  (Régression linéaire, arbres décision) │
│  → Explicables par conception           │
├─────────────────────────────────────────┤
│  🟡 Modèles "boîte grise"               │
│  (Forêts aléatoires, XGBoost)           │
│  → Explicables avec effort              │
├─────────────────────────────────────────┤
│  🔴 Modèles "boîte noire"               │
│  (Deep learning, transformers)          │
│  → Nécessitent outils XAI               │
└─────────────────────────────────────────┘
```

---

## 🛠️ Outils d'explicabilité

### SHAP (SHapley Additive exPlanations)

Calcule la contribution de chaque feature à la prédiction.

```python
import shap

# Créer l'explainer
explainer = shap.Explainer(model)
shap_values = explainer(X_test)

# Visualiser pour un candidat
shap.plots.waterfall(shap_values[0])

# Résultat exemple :
# experience_years    : +0.15
# skills_match        : +0.12
# education_level     : +0.08
# name_embedding      : -0.25  ← ALERTE BIAIS !
```

### LIME (Local Interpretable Model-agnostic Explanations)

Explique une prédiction individuelle via un modèle simple local.

```python
from lime.lime_tabular import LimeTabularExplainer

explainer = LimeTabularExplainer(X_train)
explanation = explainer.explain_instance(
    candidate_data, 
    model.predict_proba
)
explanation.show_in_notebook()
```

---

## 📝 Types d'explications

| Type | Public | Exemple |
|------|--------|---------|
| **Globale** | Data scientists | "Le modèle utilise principalement X, Y, Z" |
| **Locale** | Utilisateur final | "Vous avez été rejeté car score expérience faible" |
| **Contrefactuelle** | Candidat | "Avec 2 ans d'XP de plus, vous seriez accepté" |

---

## ✅ Bonnes pratiques

1. **Choisir le bon niveau** d'explication selon le public
2. **Documenter** les features et leur poids
3. **Alerter** si une feature sensible a trop d'impact
4. **Tester** les explications avec de vrais utilisateurs
5. **Logger** les explications pour audit

---

## ⚠️ Limites

- Explications ≠ Justifications (peut expliquer un biais)
- Complexité vs Fidélité (simplifier peut trahir)
- Manipulation possible (explications trompeuses)

---

## 📚 Ressources
- [SHAP Documentation](https://shap.readthedocs.io/)
- [LIME GitHub](https://github.com/marcotcr/lime)
- [Interpretable ML Book](https://christophm.github.io/interpretable-ml-book/)