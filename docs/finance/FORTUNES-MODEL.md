# Modèle financier — fortunes progressives

Version : 1.1.0  
Unité : EUR. Les montants ci-dessous sont des **cibles de planification**, pas des résultats constatés.

## Principe

Trois couches de fortune, jamais mélangées dans un même compteur :

1. **Fortune boutique** — marge contributive Shopify / print-on-demand.
2. **Fortune jeu** — Gold et Credits émis / détruits (hors cash, hors promesse de rachat).
3. **Fortune studio** — trésorerie réelle après coûts fixes, taxes et outils.

Confondre CA, marge brute et bénéfice net est une erreur de pilotage.

## Unit economics produit physique (cible)

| Poste | Hypothèse de travail |
|---|---|
| Prix T-shirt | 29–39 EUR TTC selon drop |
| Coût impression + logistique | 12–18 EUR |
| Frais plateforme + paiement | 3–5 % |
| Marge contributive cible | ≥ 40 % du HT |
| Bundle (tee + sticker + poster) | AOV +25 à +40 % |

Règle : aucun SKU en dessous de la marge contributive cible, sauf drop d’acquisition plafonné en volume et dans le temps.

## Paliers de fortune studio (12 mois, scénarios)

| Palier | Commandes / mois | CA TTC indicatif | Usage de la tréso |
|---|---|---|---|
| F0 Survivre | 10–25 | tester photos, copy, livraison | outillage minimal |
| F1 Stabiliser | 40–80 | couvrir POD + Shopify + une campagne |
| F2 Amplifier | 120–200 | second drop + budget créa |
| F3 Atelier | 250+ | stock sélectif, collab audio, agent Spring |

Ces paliers sont des *seuils de décision*, pas des prévisions marketing à publier comme faits.

## Économie de jeu (non monétisable comme cash)

| Flux | Règle |
|---|---|
| Source | XP et Gold uniquement après validation serveur |
| Sink | réparations `Bleeding`, crafts, cosmétiques, reset de faille |
| Ratio | sinks avant d’augmenter les récompenses |
| Interdit | conversion Gold → EUR sans cadre légal et comptable |
| Ledger | append-only ; correction = nouvelle écriture |

## Tableau de bord kvnbbg.fr

Afficher séparément :

- sessions et CVR boutique ;
- marge contributive par SKU ;
- Gold émis / Gold détruit ;
- coûts outils (Shopify, hébergement, LLM) ;
- trésorerie nette du mois.

## Garde-fous

- Le prompt IA peut suggérer un *hint* de récompense ; il n’écrit jamais le ledger.
- Un webhook Shopify crée un `correlation_id` ; le bonus de jeu est idempotent.
- Pas de promesse de rendement, de « fortune garantie » ni de token spéculatif dans les pages publiques.
