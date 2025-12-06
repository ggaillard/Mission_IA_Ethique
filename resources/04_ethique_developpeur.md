# 🧭 Éthique du Développeur

## 🎯 Principe fondamental

> "Le développeur n'est pas un simple exécutant. Il est le dernier rempart avant qu'un système potentiellement nuisible n'arrive en production."

---

## 🤔 La question clé

Avant de coder, posez-vous ces questions :

```
┌─────────────────────────────────────────┐
│  1. Qu'est-ce que ce système va         │
│     décider ?                           │
│                                         │
│  2. Pour qui ? Contre qui ?             │
│                                         │
│  3. Comment peut-il échouer ?           │
│                                         │
│  4. Qui subit les erreurs ?             │
│                                         │
│  5. Suis-je à l'aise si c'est public ?  │
└─────────────────────────────────────────┘
```

---

## 🛑 Le droit de refuser

### Situations légitimes de refus

| Situation | Exemple | Action |
|-----------|---------|--------|
| **Illégalité** | Système violant RGPD | Refuser, documenter |
| **Discrimination** | IA biaisée contre groupe | Alerter, proposer alternative |
| **Danger** | Système mal testé critique | Escalader, ne pas déployer |
| **Éthique personnelle** | Surveillance de masse | Discuter, possiblement refuser |

### Comment refuser professionnellement

1. **Documenter** les risques techniques et éthiques
2. **Proposer des alternatives** (pas juste dire non)
3. **Escalader** au niveau approprié
4. **Formaliser** par écrit (mail, ticket)

---

## 📢 Le devoir d'alerte

### Quand alerter ?

- Biais détecté dans un système en production
- Violation de données potentielle
- Système déployé sans tests suffisants
- Non-conformité réglementaire

### Comment alerter ?

```
Niveau 1 : Manager direct
    ↓ (si pas d'action)
Niveau 2 : Direction technique (CTO)
    ↓ (si pas d'action)
Niveau 3 : Direction générale / Compliance
    ↓ (si pas d'action)
Niveau 4 : Whistleblowing externe (CNIL, presse)
```

---

## 🛡️ Protection du lanceur d'alerte

### Loi Sapin II (France, 2016)

Le lanceur d'alerte est protégé s'il signale :
- De bonne foi
- De manière désintéressée
- Des faits graves (crime, délit, violation grave)

**Protections :**
- Interdiction de licenciement
- Confidentialité de l'identité
- Accompagnement juridique possible

---

## 📝 Fiche éthique pré-développement

À remplir AVANT de commencer à coder :

| Question | Réponse |
|----------|---------|
| Quel problème ce système résout-il ? | |
| Qui sont les utilisateurs ? | |
| Qui sont les personnes impactées ? | |
| Quelles données sont utilisées ? | |
| Comment les décisions sont-elles prises ? | |
| Existe-t-il un recours humain ? | |
| Quels biais potentiels ? | |
| Conformité RGPD/AI Act ? | |

---

## ✅ Principes à adopter

1. 🤔 **Je questionne** la pertinence de ce que je code
2. 🛑 **J'ai le droit** de refuser un système discriminant
3. 📢 **J'ai le devoir** d'alerter si problème éthique
4. 📝 **Je documente** les risques et décisions
5. 🧑 **Je garde l'humain** dans la boucle
6. 📚 **Je me forme** aux enjeux éthiques

---

## 📚 Ressources
- [ACM Code of Ethics](https://www.acm.org/code-of-ethics)
- [IEEE Ethically Aligned Design](https://ethicsinaction.ieee.org/)
- [Défenseur des droits - Algorithmes](https://www.defenseurdesdroits.fr/)
