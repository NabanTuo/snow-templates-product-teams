# Changelog — Template US ServiceNow
> Toutes les modifications notables sont documentées ici.
> Format : [version] — date — description

---

## [v1.0] — 2026-05-20

### Ajouté
- **Bloc Description** : 6 sections (Format US, Contexte & Problème, Scope, Dépendances, Ressources, Attendu Fonctionnel)
- **Bloc Critères d'acceptance** : tableau 10 colonnes avec double validation Dev / PO
- Légende RAG (🟢🟡🔴⚪) pour les statuts de tests
- Badges "Type message" : ✅ Succès, ℹ️ Info, ⚠️ Avertissement, 🚫 Bloquant
- Structure des cas de test en 3 catégories : Bloquants / Nominaux / Aux limites
- CSS 100% inline pour compatibilité ServiceNow
- Séparateurs visuels bleu (zone Dev) et orange (zone PO/PPO)

### Décisions d'architecture
- HTML statique uniquement — pas de JavaScript, pas de CSS externe
- Tableaux HTML classiques (pas de flexbox/grid) pour compatibilité maximale ServiceNow
- Statuts de test en emoji texte (⚪🟢🟡🔴) — pas de cases à cocher (non persistantes en HTML statique)
- Commentaires Dev et PO fusionnés avec leur cellule statut respective

---

## [À venir]

### Prévu
- Intégration des modifications issues des retours terrain (sprint de test)
- Ajout d'une section "Hypothèses techniques" co-rédigée avec le Tech Lead
- Évaluation du passage à un widget ServiceNow natif si le HTML statique atteint ses limites
