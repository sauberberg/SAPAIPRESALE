# Solution Blueprint: [Client Name]

**Prepared by**: Solution Architect, EPAM
**Date**: YYYY-MM-DD
**Базис**: discovery.md от YYYY-MM-DD

---

## 1. Transformation Approach

**Выбран**: [Greenfield / Brownfield / Selective Data Transition]

**Обоснование**:
- [Почему именно этот подход — 2-3 ключевых аргумента из discovery]

**Альтернативы рассмотрены**:
- [Подход 2] — отклонён, потому что ...

---

## 2. Target Architecture

### 2.1 SAP Core
- **S/4HANA**: версия [2023 / 2022], deployment [Cloud Private / Cloud Public / On-Premise]
- **Database**: HANA 2.0 SPS [версия]
- **Fiori**: standard apps + custom apps

### 2.2 Module Map
| Domain | Module | Purpose | Notes |
|---|---|---|---|
| Finance | FI / CO | General Ledger, Cost Accounting | + Group Reporting |
| Finance | Treasury | Cash management | Optional |
| Logistics | MM | Materials Management | |
| Logistics | SD | Sales & Distribution | |
| Logistics | PP | Production Planning | Если manufacturing |
| Logistics | EWM | Extended Warehouse Mgmt | Optional |
| HR | SuccessFactors | HCM | Если в scope |
| Procurement | Ariba | Source-to-Pay | Если в scope |
| Analytics | Datasphere + SAC | BI + Planning | |
| Platform | BTP — Integration Suite | Integration | |
| Platform | BTP — Build Apps | Custom apps | |

### 2.3 Landscape Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                    [Client] Landscape                       │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌──────────────┐    ┌──────────────┐   ┌───────────────┐  │
│  │  Source      │    │   BTP        │   │   Target      │  │
│  │  Systems     │◄──►│  Integration │◄─►│   S/4HANA     │  │
│  │  (ECC, etc.) │    │   Suite      │   │               │  │
│  └──────────────┘    └──────────────┘   └───────────────┘  │
│                              │                              │
│                              ▼                              │
│                      ┌──────────────┐                       │
│                      │  Datasphere  │                       │
│                      │  + SAC       │                       │
│                      └──────────────┘                       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 3. In Scope vs Out of Scope

### ✅ In Scope
- [Module / process 1]
- [Module / process 2]
- Data migration: [исторических данных Х лет]
- Integrations: [названия систем]
- Training: [роли]

### ❌ Out of Scope
- [Что НЕ включено — критично для защиты от scope creep]
- Hardware procurement
- Network setup
- Business process redesign (выделяется отдельно)

---

## 4. Integration Architecture

### 4.1 Integration Patterns
- **Real-time** (REST/OData): для ...
- **Batch** (IDoc, file-based): для ...
- **Event-driven** (BTP Event Mesh): для ...

### 4.2 Integration List
| Source | Target | Pattern | Frequency | Volume |
|---|---|---|---|---|

---

## 5. Data Migration

### 5.1 Approach
- **Tool**: SAP Migration Cockpit / SDI / custom
- **Scope**: [master data + transactional]
- **Historical**: [сколько лет переносим]

### 5.2 Data domains
| Domain | Volume | Complexity | Cleansing required |
|---|---|---|---|
| Customers | XXX records | Medium | Yes |
| Vendors | XXX | Low | Partial |
| Materials | XXX | High | Yes |
| Open POs / SOs | XXX | Medium | No |

---

## 6. Non-Functional Requirements

### Performance
- Concurrent users: XXX
- Peak TPS: XXX
- Reporting SLA: ...

### Availability
- HA: active-active / active-passive
- DR: RPO < X hours, RTO < X hours
- Maintenance window: ...

### Security
- IAM: SAML / OIDC через [Azure AD / Okta]
- Encryption: at-rest, in-transit
- Audit: SAP UAL / external SIEM

### Compliance
- GDPR: data residency, consent management
- SOX (если US-listed): controls automation
- Industry-specific: ...

---

## 7. Phasing

### Phase 0: Preparation (X months)
**Goal**: Foundation, data assessment, environments setup.
**Deliverables**:
- Detailed design
- Cleansed data sample
- Dev/Test environments
- Team onboarded

### Phase 1: Foundation + Finance (X months)
**Goal**: S/4HANA core + Finance live.
**Deliverables**:
- Финансовый go-live
- Master data migrated
- Key integrations live

### Phase 2: Logistics (X months)
**Goal**: MM/SD/PP/EWM live.
**Deliverables**:
- Full operational coverage
- Production go-live

### Phase 3: Analytics + Extensions (X months)
**Goal**: BI, custom apps, optimization.
**Deliverables**:
- Datasphere + SAC
- Custom BTP apps
- Hypercare complete

---

## 8. Assumptions

- Client provides business owners по каждому процессу
- Client team available [X FTE] на весь проект
- No regulatory changes требующих re-scoping
- SAP licensing acquired клиентом отдельно
- [Other key assumptions]

---

## 9. Architectural Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Legacy data quality | High | High | Phase 0 cleansing sprint |
| Custom code dependencies | Medium | High | Code analysis in Phase 0 |
| Integration with legacy [system X] | Medium | Medium | PoC в Phase 0 |
| Performance под peak | Low | High | Performance test в Phase 2 |

---

## 10. Dependencies (от клиента)

- [ ] Готовность infrastructure (если on-prem или private cloud)
- [ ] SAP licenses закуплены
- [ ] Business владельцы выделены и доступны
- [ ] Готовность к Decision Making в течение [N] дней
- [ ] Доступ к source systems для миграции

---

## 11. What requires further design

- [Что-то, что требует workshop'ов в Phase 0 для точного scoping]
- ...
