# Effort Estimation: [Client Name]

**Prepared by**: Effort Estimator, EPAM
**Date**: YYYY-MM-DD
**Базис**: blueprint от YYYY-MM-DD

---

## 1. T-shirt Size

**Размер**: **[XS / S / M / L / XL]**

**Обоснование**:
- [почему именно этот размер]
- [ключевые факторы]

---

## 2. Total Effort (Range)

| Сценарий | Man-Days |
|---|---|
| **Low** (optimistic) | XXX |
| **Expected** | **XXX** |
| **High** (с буферами) | XXX |

**Spread**: ±XX% от expected.

---

## 3. Breakdown by Phase

### Phase 0: Preparation

| Workstream | Role | MD low | MD exp | MD high |
|---|---|---|---|---|
| PMO | PM Senior | | | |
| Architecture | Solution Architect | | | |
| Architecture | Integration Architect | | | |
| Data | Data Migration Lead | | | |
| Functional | Functional Lead | | | |
| **Phase 0 total** | | **XXX** | **XXX** | **XXX** |

### Phase 1: Foundation + Finance

| Workstream | Role | MD low | MD exp | MD high |
|---|---|---|---|---|
| PMO | PM | | | |
| Functional | Finance Lead | | | |
| Functional | Finance Consultant Sr | | | |
| Functional | Finance Consultant Mid | | | |
| Development | ABAP Developer Sr | | | |
| Development | BTP Developer | | | |
| Data | Data Migration Specialist | | | |
| Integration | Integration Consultant | | | |
| Test | Test Lead | | | |
| Test | Tester | | | |
| Training | Trainer | | | |
| **Phase 1 total** | | **XXX** | **XXX** | **XXX** |

### Phase 2: Logistics
(аналогичная разбивка)

### Phase 3: Analytics + Hypercare
(аналогичная разбивка)

---

## 4. Risk Multipliers Applied

| Risk Factor | Source | Adjustment |
|---|---|---|
| Tight timeline (18 мес) | discovery | +15% |
| Multi-country (3 countries) | discovery | +25% |
| Legacy customization (ECC heavy) | blueprint | +30% |
| Weak client team availability | discovery | +20% |
| Non-standard processes | discovery | +20% |
| **Combined effect** | | **+XX%** (применён к expected) |

---

## 5. Assumptions

- Стандартные SAP-процессы, минимум кастома
- Клиент предоставляет business owners полностью
- 1 язык интерфейса (если несколько — +10%)
- 1 country / legal entity (если несколько — +20% на каждый дополнительный)
- Нет M&A в течение проекта
- SAP licenses готовы к началу Phase 1
- Standard SLA для hypercare (8x5, не 24x7)

---

## 6. NOT Included

- Hardware / infrastructure procurement
- SAP license costs
- Third-party software (если необходимо)
- Business process redesign (отдельная активность)
- Change management beyond training
- Long-tail support после hypercare (managed service отдельно)

---

## 7. What requires precise estimation (Phase 0)

- Точный объём кастомизаций (зависит от code analysis)
- Точный scope миграции (зависит от data assessment)
- Точное количество integrations (зависит от source landscape audit)
- Точные performance SLAs (зависит от volumetrics)

---

## 8. Validation Notes

- [ ] Сверено с similar past projects в knowledge/case-studies/
- [ ] Bottoms-up расчёт и top-down sanity check сходятся ±15%
- [ ] Все workstreams покрыты
- [ ] Hypercare заложен (3-6 мес)
- [ ] PM/PMO заложены явно (не "включены в роли")
