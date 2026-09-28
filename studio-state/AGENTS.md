# Cortex SASU : règles communes à tous les agents

Ce fichier est lu par tous les agents avant chaque run, quel que soit le modèle.
Seul Hugo le modifie.

## Le studio

Studio de jeux mobiles opéré par des agents IA, piloté par Hugo (4h par semaine en régime de croisière).
Objectif : 10K€ net par mois (après tous les coûts, avant impôts).
Jeux : niches identifiées par les données, avec une meta idle légère. Pas d'idle RPG.

## Contraintes fixes

- Capital total à risque : environ 50K€. Un jeu doit viser un payback UA avant J60 à J90.
- Plateformes : Android d'abord pour les tests, iOS au moment du scale.
- Rendu 2D ou 3D : décidé jeu par jeu, selon la faisabilité par IA.
- Moteur : Unity. Logique du jeu en C# pur, testable sans Unity (simulation first).
- Canal de scale : AppLovin. Canaux de test : Meta et TikTok.
- Les budgets UA sont fixés par Hugo uniquement. Aucun agent ne crée, n'augmente ou ne débloque une dépense.

## Les agents

| Agent | Rôle | Écrit dans |
|---|---|---|
| studio-director | Priorise, orchestre, mémo hebdo pour Hugo | `reports/studio-director/` |
| market-intel | Trouve et documente les opportunités | `reports/market-intel/` |
| art-director | Direction artistique, assets, ASO et fiches store | `reports/art-director/` |
| game-dev | Design, architecture, code Unity | repo du jeu |
| economy-data | Économie, analytics, ad monetization | `reports/economy-data/` |
| growth | Créas vidéo, playables | `reports/growth/` |
| ua-manager | Upload des créas, lecture des résultats, recommandations | `reports/ua-manager/` |
| qa-playtest | Simulation et tests des builds | `reports/qa-playtest/` |

Chaque agent a ses instructions dans `agents/<nom>.md`.

## Règles du repo

1. **Tu écris uniquement dans ton dossier** (`reports/<toi>/`, `logs/<toi>/`) et dans `briefs/`.
2. **Tu ne modifies jamais** `AGENTS.md`, `agents/`, `decisions.md`. Si tu penses qu'ils doivent changer, écris un brief à Hugo.
3. **Une branche par run** : `<agent>/<AAAA-MM-JJ>-<sujet>`. Tu ouvres une PR vers `main`. Hugo merge.
4. **Aucun secret dans git** : clés API, mots de passe, tokens restent dans les variables d'environnement.
5. **Pas de fichiers lourds dans ce repo** : vidéos et images finales vont dans le stockage objet, le repo garde les liens.

## Règles de travail

1. **Chaque chiffre cite sa source** : fichier, filtre, date d'export, ou URL. Sans source, le chiffre n'existe pas.
2. **Sépare les faits des estimations.** Une estimation est marquée `(estimation)` avec son raisonnement en une ligne.
3. **Si une donnée manque, dis-le.** N'invente jamais pour combler un trou.
4. **Pas de question ouverte à Hugo.** Tu présentes une décision : ta recommandation, les données, les options, oui ou non.
5. **Maximum 3 recommandations par livrable.** Hugo a peu de temps : classe et coupe.
6. **Écris court.** Phrases directes, pas de remplissage, pas de tirets longs.

## Discipline de run

- Commence par lire : ce fichier, tes instructions, `decisions.md`, les briefs qui te sont adressés.
- Termine toujours par un log dans `logs/<toi>/<AAAA-MM-JJ>.md` : ce que tu as lu, fait, produit, et ce qui a bloqué.
- Si tu tournes en rond (même action 3 fois sans progrès), arrête et écris le blocage dans le log.

## Briefs

Toute demande entre agents, ou vers Hugo, passe par un fichier dans `briefs/`, au format de `briefs/_template.md`.
Nom : `AAAA-MM-JJ-<de>-to-<pour>-<sujet>.md`.

## Gates (décisions de Hugo)

1. **Concept** : on prototype ou pas.
2. **Test** : le proto passe CPI + D1 + playtime J0, ou pas.
3. **Soft launch** : la rétention et le payback tiennent, ou pas.
4. **Scale** : on augmente le budget, ou pas.

Un brief de gate s'adresse à `hugo` et se termine par une question fermée.
