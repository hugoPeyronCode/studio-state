# studio-state

La mémoire partagée du studio IA Cortex SASU. Les agents n'ont pas de mémoire entre deux runs : tout ce qu'ils savent est ici.

| Chemin | Contenu | Qui écrit |
|---|---|---|
| `AGENTS.md` | Règles communes à tous les agents | Hugo |
| `CLAUDE.md` | Renvoie vers `AGENTS.md` pour Claude | Hugo |
| `decisions.md` | Journal des décisions | Hugo |
| `agents/` | Instructions de chaque agent, quel que soit le modèle | Hugo |
| `.claude/agents/` | Adaptateurs Claude qui pointent vers `agents/` | Hugo |
| `briefs/` | Demandes entre agents et gates pour Hugo | Agents |
| `reports/<agent>/` | Livrables de chaque agent | L'agent concerné |
| `logs/<agent>/` | Journal de chaque run | L'agent concerné |
| `metrics/` | Données brutes (exports, dumps API) | Hugo, puis agents |

Le code de chaque jeu vit dans son propre repo.
