# 📋 Template US ServiceNow — Digital Bench L'Oréal

Template HTML pour les champs **Description** et **Critères d'acceptance** des User Stories dans ServiceNow.

**Objectif :** Forcer la rédaction des tests fonctionnels dès l'écriture de l'US et tracer leur exécution par les développeurs et le PO/PPO.

---

## 📁 Structure du repo

```
snow-us-template/
├── template_US_complet.html   ← fichier source à copier dans ServiceNow
├── CHANGELOG.md               ← historique des versions
└── README.md                  ← ce fichier
```

---

## 🚀 Comment utiliser ce template

### Étape 1 — Copier le HTML dans ServiceNow
1. Ouvrir `template_US_complet.html` dans un éditeur de texte
2. Sélectionner tout le contenu (`Ctrl+A`)
3. Dans ServiceNow, ouvrir l'US concernée
4. Basculer le champ **Description** en mode HTML (icône `<>`)
5. Coller le contenu — **Bloc 1 uniquement** (jusqu'à `<!-- FIN BLOC 1 -->`)
6. Répéter pour le champ **Critères d'acceptance** avec le **Bloc 2**

### Étape 2 — Remplir le Bloc 1 (Description) — *PO avant le sprint*
| Section | Obligatoire |
|---|---|
| Format US (En tant que…) | ✅ |
| Persona(s) concerné(s) | ✅ |
| Problème à résoudre | ✅ |
| Pourquoi maintenant | ⬜ Optionnel |
| Documentation préexistante | ⬜ Optionnel |
| Scope IN / OUT | ✅ |
| Dépendances | ⬜ Optionnel |
| Ressources (Figma, Confluence) | ⬜ Optionnel |
| Attendu fonctionnel | ✅ |

### Étape 3 — Remplir le Bloc 2 (Critères d'acceptance) — *PO avant le sprint*
- Renseigner les colonnes **Code → Message ANG** et **Liste des tests** pour chaque critère
- Numéroter les critères : CA1, CA2, CA3…
- Pour chaque critère, lister les cas de test en 3 catégories : 🚫 Bloquants / ✅ Nominaux / ⚠️ Aux limites

### Étape 4 — Validation Dev — *pendant le développement*
- Mettre à jour la colonne **Statut Dev** avec les emojis RAG :
  - ⚪ À tester (valeur par défaut)
  - 🟢 OK — test passant
  - 🟡 En cours / Doute
  - 🔴 KO — test échoué
- Ajouter un commentaire si statut 🟡 ou 🔴

### Étape 5 — Validation PO/PPO — *avant passage en Done*
- Renseigner la colonne **Statut PO** selon les mêmes codes RAG
- L'US ne peut pas passer en **Done** si un statut PO est ⚪ ou 🔴

---

## 🏷️ Badges Type de message

À utiliser dans la colonne "Type message" du tableau CA :

```html
<!-- ✅ Bonne exécution -->
<span style="background: #f0fff4; color: #276749; border: 1px solid #c6f6d5; border-radius: 4px; padding: 2px 6px; font-size: 10px; font-weight: 700;">✅ Succès</span>

<!-- ℹ️ Information -->
<span style="background: #ebf8ff; color: #2c5282; border: 1px solid #bee3f8; border-radius: 4px; padding: 2px 6px; font-size: 10px; font-weight: 700;">ℹ️ Info</span>

<!-- ⚠️ Avertissement -->
<span style="background: #fffbeb; color: #b7791f; border: 1px solid #fef08a; border-radius: 4px; padding: 2px 6px; font-size: 10px; font-weight: 700;">⚠️ Avertissement</span>

<!-- 🚫 Bloquant -->
<span style="background: #fff5f5; color: #c53030; border: 1px solid #fed7d7; border-radius: 4px; padding: 2px 6px; font-size: 10px; font-weight: 700;">🚫 Bloquant</span>
```

---

## ⚠️ Contraintes techniques ServiceNow

- **Pas de JavaScript** — les cases à cocher ne persistent pas en HTML statique dans ServiceNow
- **Pas de CSS externe ni de classes** — tout le style est en `style=""` inline
- **Pas de flexbox/grid** — utiliser des `<table>` imbriqués uniquement
- **Tester sur sandbox** avant déploiement — certaines versions de ServiceNow strippent les `border-radius` et `linear-gradient`

---

## 🔄 Processus de modification

1. Modifier `template_US_complet.html` en local
2. Tester le rendu dans un navigateur
3. Tester sur l'instance sandbox ServiceNow
4. Mettre à jour `CHANGELOG.md`
5. Commit avec message conventionnel : `fix:`, `feat:`, `chore:`
6. Tagger la release stable : `git tag v1.x`

---

## 👤 Ownership

| Rôle | Responsabilité |
|---|---|
| **Naban TUO (Thiga)** | Auteur — maintenance et évolutions du template |
| **PO/PPO Digital Bench** | Remplissage Bloc 1 + Bloc 2 avant sprint |
| **Développeurs (CapGemini)** | Remplissage colonne Statut Dev pendant le sprint |
