# Politique anti-biais — NUMERIA / Division by Zero

Version : 1.0.0  
Statut : norme de conception  
Dépôts liés : `Kvnbbg/GDD`, `Kvnbbg/Division-by-Zero`

## Objectif

Empêcher que le lore, les prompts IA, le marketing ou le GDD présentent une **métaphore de jeu** comme une **preuve scientifique**. La division par zéro est une opération non définie dans l’arithmétique usuelle. Elle n’établit pas l’existence de réalités multiples.

## Séparation des registres

| Registre | Autorisé | Interdit |
|---|---|---|
| Mathématique | « indéfini », « indéterminé », domaine de validité | « Infinity est la vraie réponse », « 1/0 = autre univers » |
| Physique | Citer la mécanique quantique comme domaine distinct | Déduire des mondes multiples d’un dénominateur nul |
| Gameplay | Faille `NULL_RIFT`, branches de quête, XP de raisonnement | Présenter une branche comme preuve empirique |
| Marketing | Rétro-futurisme spatial original | Marques, personnages ou assets protégés sans licence |
| Économie | Ledger append-only, règles serveur | Laisser un LLM attribuer de l’or ou des crédits |

## Biais à contrôler

1. **Biais de confirmation** : ne pas chercher des citations qui « prouvent » une lecture mystique de `a / 0`.
2. **Biais d’autorité** : un texte généré par IA n’est jamais la source de vérité du calcul.
3. **Biais de cadrage** : « réalités multiples » désigne des *branches de gameplay*, pas une ontologie physique.
4. **Biais de représentation** : exercices, lore et récompenses doivent rester accessibles sans stéréotype de genre, d’origine ou de capacité.
5. **Biais financier** : ne pas confondre chiffre d’affaires, marge brute et bénéfice net dans les dashboards.

## Règle de validation joueur

- `a / 0` avec `a ≠ 0` → réponse attendue : **UNDEFINED**.
- `0 / 0` → réponse attendue : **INDETERMINATE**, avec justification : plusieurs valeurs satisfont `0 × x = 0`.
- Jamais `Infinity` comme réponse mathématique du jeu.
- Le serveur recalcule toujours ; le prompt ne décide pas de l’économie.

## Revue

Toute modification de lore, de prompt ou de GDD qui mélange physique et arithmétique doit être relue contre ce document avant fusion.
