# SAPAIPRESALE

Мульти-агентная система для пре-сейлс активностей по SAP проектам.
Один **супер-агент** (Director) оркестрирует **8 специализированных агентов** —
от Discovery до Demo Prep.

## Структура

```
SAPAIPRESALE/
├── director.md          ← супер-агент (главный инструктаж + правила делегирования)
│
├── docs/                ← документация проекта (методология, how-to, глоссарий)
├── flows/               ← готовые сценарии (full-presale, rfp-only, demo-prep)
│
├── agents/              ← агенты + их личные скиллы
│   ├── discovery-lead/        — квалификация, стейкхолдеры, BANT
│   ├── solution-architect/    — solution blueprint, выбор модулей
│   ├── industry-expert/       — отраслевая специфика (Retail, Bank, Manuf.)
│   ├── effort-estimator/      — оценка трудозатрат, T-shirt sizing
│   ├── proposal-writer/       — коммерческое предложение, RFP-ответ
│   ├── pricing-specialist/    — модели ценообразования, T&M vs Fixed
│   ├── demo-engineer/         — demo скрипты, sandbox prep
│   └── compliance-reviewer/   — review, риски, compliance
│
├── skills/              ← общие скиллы (доступны любому агенту)
│                          parse-rfp, search-knowledge, translate, format-doc
│
├── templates/           ← шаблоны (RFP-ответ, blueprint, estimation, demo-script)
├── knowledge/           ← база знаний (SAP-доки, кейсы, прайсы, отрасли)
├── examples/            ← реальные примеры прошлых сделок (анонимизированные)
│
├── connectors/          ← MCP-интеграции
│   ├── confluence-kb/         — EPAM Confluence KB
│   ├── jira/
│   └── sharepoint/
│
└── working/             ← рабочая папка (output агентов, .gitignored)
```

## Как читать структуру

| Папка | Кто использует | Когда заполнять |
|---|---|---|
| `docs/` | Ты сам | По мере появления вопросов |
| `flows/` | Director | После того, как агенты готовы |
| `agents/{role}/agent.md` | Конкретный агент | **В первую очередь** |
| `agents/{role}/skills/` | Этот же агент | По мере выявления повторяющихся задач |
| `skills/` | Любой агент | Когда видишь, что один скилл нужен 3+ агентам |
| `templates/` | Writer / Estimator | Из реальной практики EPAM |
| `knowledge/` | RAG / поиск | Постепенно — топ-10 материалов сначала |
| `examples/` | Few-shot для агентов | По 2-3 анонимизированных кейса на тип |
| `connectors/` | MCP | Не на первой неделе |
| `working/` | Все агенты | Автоматически (output) |

## Статус

Skeleton — структура папок готова. Контент агентов, скиллов и шаблонов
заполняется итеративно.

## Стек

- **Workspace**: VS Code (открываешь корень репо)
- **Оркестратор**: TBD — либо Director-chatmode в Copilot, либо Claude Code CLI
- **MCP коннекторы**: на втором этапе (Confluence KB первым приоритетом)
