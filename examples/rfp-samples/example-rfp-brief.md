# Example RFP Brief — для тестирования MVP

**Это пример входных данных для прогона полного flow.**
**Все имена и цифры — синтетические.**

---

## RFP: SAP S/4HANA Transformation
**Client**: NordicRetail Group (fictional)
**Industry**: Retail (Fashion + Lifestyle), Omnichannel
**Geography**: 5 стран EU (Nordics + Germany)
**Issued**: 2026-XX-XX
**Response deadline**: 6 weeks

---

## 1. About Us

NordicRetail Group — крупный ритейлер модной одежды и lifestyle товаров в скандинавском регионе. Основан в 1998 году.

- **Магазины**: 240 физических точек продаж
- **Online**: 5 интернет-магазинов (по странам)
- **Бренды**: 4 собственных бренда + 200 partner brands
- **Сотрудники**: 8,500 (включая retail staff)
- **Revenue (2025)**: EUR 1.2 млрд
- **Growth**: +8% YoY за последние 3 года

## 2. Current State

### Текущий landscape:
- **ERP**: SAP ECC 6.0 EHP 8 (с 2014 года)
- **POS**: SAP Retail Store (legacy)
- **E-commerce**: Custom-built на Spryker (5 instances)
- **Warehouse**: Standalone WMS (Manhattan)
- **BI**: SAP BW 7.5 + custom Tableau
- **HCM**: SAP HCM on-prem

### Кастомизация ECC:
- ~400 Z-программ
- ~150 user-exits
- Heavy modification в SD и MM

### Pain points:
1. **Slow closing**: финансовое закрытие занимает 12-15 рабочих дней
2. **Inventory visibility**: real-time данных по складам нет, только дневные сводки
3. **Pricing flexibility**: изменение цен в кампаниях занимает 2-3 дня
4. **Omnichannel disconnect**: online и offline cart нельзя объединить
5. **Reporting lag**: BI обновляется ночью, нет real-time KPI
6. **End-of-life ECC**: SAP заканчивает поддержку ECC в 2027

## 3. Strategic Drivers

- Переход на S/4HANA до конца поддержки ECC (2027)
- Real-time view across operations (omnichannel)
- Снижение TCO IT-ландшафта на 20% за 3 года
- Подготовка к expansion в 2 новые страны (планируется 2027-2028)
- ESG reporting requirements (CSRD compliance)

## 4. Scope (Initial)

### In Scope (наше видение, открыто для обсуждения):
- S/4HANA как core ERP (модули: FI, CO, MM, SD, PP, Retail-specific)
- BTP для integration + extensions
- SAP Datasphere + SAC замена BW + Tableau
- Migration с ECC (Brownfield предпочтительно, но open to Greenfield)
- Integration с Spryker e-commerce
- Integration с Manhattan WMS (минимум 3 года)
- Data migration: 5 лет исторических данных

### Out of Scope (на этот RFP):
- POS replacement (отдельный stream)
- E-commerce migration (Spryker остаётся)
- HCM/SuccessFactors (отдельно)
- Ariba (не сейчас)

## 5. Non-Functional

- **Users**: 2,500 concurrent (peak)
- **Languages**: 6 (EN, SE, NO, DK, FI, DE)
- **Availability**: 99.9% during business hours, planned maintenance windows OK
- **Disaster recovery**: RPO 4h, RTO 8h
- **Compliance**: GDPR (data residency EU), CSRD reporting
- **Hosting preference**: Private cloud (preferably SAP RISE)

## 6. Timeline

- **RFP response**: 6 weeks from issue
- **Vendor selection**: by [date + 12 weeks]
- **Target go-live**: Q4 2027 (Phase 1)
- **Full transformation complete**: Q2 2028

## 7. Budget

Бюджет не указан явно ("competitive pricing").

Внутренний benchmark (не упоминается в RFP): EUR 8-15 млн на трансформацию.

## 8. Evaluation Criteria

| Critierion | Weight |
|---|---|
| Domain expertise in EU retail | 25% |
| Methodology and approach | 20% |
| Team strength | 15% |
| Pricing | 20% |
| References | 10% |
| Cultural fit | 10% |

## 9. Stakeholders

- **CIO** (decision maker): Ms. Anna [LastName]
- **CFO** (financial influencer): Mr. Lars [LastName]
- **COO** (operational influencer): Mr. Mikael [LastName]
- **IT Director** (project owner): Mr. Henrik [LastName]
- **Head of Retail Operations** (end user): Ms. Sofia [LastName]

## 10. Questions Process

- Q&A round 1: 2 weeks after RFP issue
- Vendor presentations: in person, 4 weeks after RFP issue
- Site visits: optional, 5 weeks after RFP issue

---

# КАК ИСПОЛЬЗОВАТЬ ДЛЯ ТЕСТА MVP

1. Открой VS Code в папке SAPAIPRESALE
2. Открой Copilot Chat (Ctrl+Alt+I / Cmd+Alt+I)
3. Выбери mode **Director**
4. Скажи: "У меня RFP от клиента, файл `examples/rfp-samples/example-rfp-brief.md`. Что делать?"
5. Director должен выдать план шагов
6. Переключайся на **Discovery Lead** по плану от Director
7. Передавай ему RFP
8. Получай `working/2026-XX-XX/discovery.md`
9. Продолжай по цепочке

Если каждый агент выдаёт что-то осмысленное в своей роли — MVP работает.
Если кто-то путается / выдумывает / лезет в чужую роль — правь его chatmode.
