# 📊 Biais Algorithmiques - Comprendre et Prévenir

## 🎯 Définition

Un **biais algorithmique** est une erreur systématique dans un système d'IA qui produit des résultats injustes envers certains groupes.

> "Un algorithme n'est jamais neutre : il reflète les biais de ses données et de ses concepteurs."

---

## 🔍 Types de biais

### Biais de données
| Type | Description | Exemple |
|------|-------------|---------|
| **Historique** | Données reflétant discriminations passées | Recrutement : 80% hommes → IA favorise hommes |
| **Représentation** | Groupes sous/sur-représentés | Reconnaissance faciale moins précise peaux foncées |
| **Mesure** | Données ne mesurent pas ce qu'elles prétendent | "Productivité" = heures présence → défavorise temps partiel |

### Biais de modèle
| Type | Description | Exemple |
|------|-------------|---------|
| **Proxy** | Variable "neutre" encode caractéristique protégée | Code postal → prédit origine ethnique |
| **Feedback** | Modèle renforce ses erreurs | Police prédictive → plus patrouilles → plus arrestations |

---

## 📦 Cas emblématiques

### Amazon (2018)
- IA de tri CV pénalisait "women's" dans les CV
- Cause : 10 ans d'embauches masculines
- **Projet abandonné**

### COMPAS (2016)
- Score récidive : faux positifs 2x plus élevés Afro-Américains
- **Toujours utilisé malgré contestation**

---

## 🛠️ Détection avec Fairlearn

```python
from fairlearn.metrics import demographic_parity_difference

dpd = demographic_parity_difference(
    y_true=labels,
    y_pred=predictions,
    sensitive_features=gender
)
# dpd > 0.1 → biais significatif
```

---

## ✅ Bonnes pratiques

1. **Auditer les données** avant entraînement
2. **Identifier les proxies** (prénom, code postal...)
3. **Mesurer l'équité** sur groupes protégés
4. **Documenter** les décisions et limites

---

## 📚 Ressources
- [Fairlearn Documentation](https://fairlearn.org/)
- [AI Fairness 360 (IBM)](https://aif360.mybluemix.net/)
- [Google What-If Tool](https://pair-code.github.io/what-if-tool/)