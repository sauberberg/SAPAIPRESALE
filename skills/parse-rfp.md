# Skill: Parse RFP

**Используется**: Discovery Lead, Proposal Writer, Compliance Reviewer
**Когда**: Получен текст RFP от клиента (PDF / DOCX / email body)

## Что делает

Извлекает структурированную информацию из неструктурированного RFP-документа.

## Алгоритм

### 1. Идентификация секций
Найди и помечай следующие блоки в исходнике:

| Секция | Признаки |
|---|---|
| **Business context** | "About us", "Our company", "Background" |
| **Scope / Requirements** | "Requirements", "Scope of work", "Deliverables" |
| **Functional requirements** | "Functional", "Features", "Capabilities" |
| **Non-functional** | "Performance", "Security", "Availability", "SLA" |
| **Timeline** | "Schedule", "Milestones", "Go-live date" |
| **Budget** | "Budget", "Pricing", "Investment", "Cost" |
| **Evaluation criteria** | "Evaluation", "Selection", "Decision criteria" |
| **Q&A process** | "Questions", "Clarifications" |
| **Contacts** | "Contact", "Point of contact" |

### 2. Извлечение ключевых данных

**Структурированный output**:

```yaml
client:
  name: ...
  industry: ...
  geography: ...
  scale: [revenue / employees / etc.]

current_state:
  current_erp: ...
  pain_points:
    - ...
  business_drivers:
    - ...

target_state:
  modules_explicit: [перечисленные в RFP]
  modules_implicit: [упомянутые в контексте]
  outcomes_expected:
    - outcome: ...
      metric: ...

constraints:
  timeline: ...
  budget_range: ...
  geographic: [страны / locations]
  language_requirements: ...

stakeholders_mentioned:
  - role: ...
    name: ...

evaluation_criteria:
  - criterion: ...
    weight: ...

red_flags:  # вещи, требующие осторожности
  - ...

ambiguities:  # что НЕ ясно из RFP
  - ...
```

### 3. Выявление gaps

Список того, что в RFP НЕ упомянуто, но критично знать:
- BANT (Budget — если не указан, Authority, Need детали, Timeline уточнения)
- Подход (предпочтение Greenfield / Brownfield)
- Текущие интеграции
- Compliance требования (GDPR, SOX)
- Multi-language / multi-currency
- Hosting preference (on-prem, private cloud, public cloud)

### 4. Red flags

Помечай как warning, если в RFP:
- Нереалистичные сроки ("S/4HANA за 6 месяцев")
- Отсутствие бюджета вообще ("competitive pricing")
- Очень много кастомных требований
- Требование fixed price на untested scope
- Reverse auction процесс
- Жёсткие IP requirements (всё передаётся клиенту)
- Penalty clauses без upside

## Output

Файл `working/{дата}/rfp-parsed.md` с заполненной структурой выше.

Используй это как вход для Discovery Lead для последующего deep-dive.
