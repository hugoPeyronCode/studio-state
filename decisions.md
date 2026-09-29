# Journal des décisions

Seul Hugo écrit ici. Une ligne par décision, la plus récente en haut.

## 2026-09-28

- Tout tourne dans le cloud : GitHub est la source de vérité, les agents tournent en sessions cloud et en tâches planifiées, les builds Unity passent par un service de build cloud.
- Hugo gère lui-même les coûts et les budgets UA. Pas d'agent finance, pas d'alertes de coût.
- Niche décidée par les données, sans exclusion de cible (la cible de Cortex Studio est possible).
- Rendu 2D ou 3D décidé jeu par jeu.
- Capital à risque : environ 50K€, donc payback visé avant J60 à J90.
- Android d'abord pour les tests, iOS au scale.
- Analytics : Adjust (attribution, revenus) + Firebase Analytics avec export BigQuery + Firebase Remote Config.
- Un seul modèle au départ (Claude). Les API d'image (GPT Image 2, Flux) sont des outils.
- Agents : studio-director, market-intel, art-director (+ ASO), game-dev, economy-data (+ ad monetization), growth, ua-manager, qa-playtest.
- Ordre de construction : market-intel, puis game-dev et growth, puis ua-manager et economy-data, puis studio-director.
