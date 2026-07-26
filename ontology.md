# Ontology: Мебельный инжиниринг (Furniture Engineering)

> Domain ontology per SPF.SPEC.002.
> Complete registry of entity types, key terms, and relationships for this Pack.
> Each concept MUST link to a parent concept from SPF base ontology (SPF.SPEC.002, Section 2).

---

## 1. Entity Types

> All entity types used in this Pack: base (from SPF) + extended (defined by this Pack).
> **Mandatory column "FPF/SPF Concept"** — parent concept from SPF base ontology.

| Code | Type | FPF/SPF Concept | Definition | ≠ (what it is NOT) | Source |
|------|------|-----------------|------------|---------------------|--------|
| `M` | Method | U.Method | _TBD_ | ≠ scenario, ≠ tool | SPF (base) |
| `WP` | Work Product | U.Work + U.Episteme | _TBD_ | ≠ method description | SPF (base) |
| `FM` | Failure Mode | — (SPF-specific) | _TBD_ | ≠ code bug | SPF (base) |
| `D` | Distinction | A.7 Strict Distinction | _TBD_ | ≠ fact, ≠ definition | SPF (base) |
| `R` | Role | U.RoleAssignment | _TBD_ | ≠ person, ≠ job title | SPF (base) |
| `CHR` | Characteristic | U.Characteristic | _TBD_ | ≠ metric, ≠ indicator | SPF (base) |
| `SOTA` | SoTA Annotation | — (SPF-specific) | _TBD_ | ≠ literature review | SPF (base) |
| `MAP` | Map | U.Episteme | _TBD_ | ≠ content | SPF (base) |
| `HOL` | Holon (Холон) | U.System | Узел холархии - одновременно целое на своём уровне и часть системы выше | ≠ произвольная деталь, ≠ сборка вне холархии | Pack (extended) |
| `GRD` | Guard (Гвард) | — (SPF-specific, аналог FM) | Эпистемологический барьер, блокирующий переход на следующую стадию при нарушении инварианта | ≠ рекомендация, ≠ soft warning | Pack (extended) |

---

## 2. Domain Glossary

> Key domain terms with definitions. Only terms essential for understanding this domain.
> **Mandatory columns:** "Term (RU)" + "Term (EN)" per DDD Ubiquitous Language (SPF.SPEC.002, Rule 11).
> **Mandatory column "Parent Concept (SPF)"** — which universal concept from SPF base ontology this term belongs to.

| Term (RU) | Term (EN) | Definition | Parent Concept (SPF) | Related entity |
|-----------|-----------|-----------|---------------------|----------------|
| Изоморфизм | Isomorphism | Строгое, однозначное структурное подобие между узлами CAD-модели и атомарными деталями физического гарнитура | U.Characteristic | — |
| Спецификация | Specification | Исчерпывающее перечисление свойств объекта - нормативный документ, обязательный для производства | U.Work + U.Episteme (= WP) | — |
| Инвариант | Invariant | Физическая величина или геометрическое препятствие, неизменное при любых проектных трансформациях | U.Characteristic | — |
| Коллизия | Collision | Пространственное пересечение физических объектов - проявление информационной ошибки в CAD-модели | — (= FM) | — |
| Топология | Topology | Пространственная конфигурация и взаимосвязь физических объектов в целевой среде | U.Characteristic | — |
| Строгое различение | Strict Distinction | Жёсткое разделение Объекта, Описания и Спецификации - смешение уровней ведёт к ошибкам проектирования | A.7 Strict Distinction (FPF) | — |
| Деонтика | Deontics | Алгоритмические обязательства (MUST/MUST NOT), нарушение которых - производственный брак | — (SPF-specific) | — |
| Холон | Holon | Объект, одновременно автономное целое на своём уровне холархии и зависимая деталь системы выше | U.System | HOL |
| Гвард | Guard | Жёсткий эпистемологический барьер против локальной оптимизации в ущерб физике | — (SPF-specific) | GRD |

---

## 3. Relationships Between Types

> How entity types relate to each other in this domain.

| Subject | Relationship | Object | Example |
|---------|-------------|--------|---------|
| Method | produces → | Work Product | FE.M.001 (P2W) → FE.WP.001 (Спецификация) |
| Failure Mode | violates ← | Method | FE.GRD.001 ← FE.M.001 |
| Holon (L2) | composes → | Holon (L3) | Модуль → Собранный гарнитур |
| Role | verifies → | Work Product | Технолог → Отчёт DRR |

---

## 4. Type Hierarchy (optional)

> If types have subtypes or specializations, document here.

```
Holon (HOL)
├── L6 Инфраструктура здания
├── L5 Квартирная разводка
├── L4 Помещение
├── L3 Собранный гарнитур (целевой холон)
├── L2 Модули (подсистемы)
├── L1 Атомарные детали
└── L0 Физико-химический субстрат
```

---

## 5. Cross-Pack Terms (optional)

> Terms shared with or borrowed from other Packs.

| This Pack's term | Related Pack | Term there |
|-----------------|-------------|------------|
| _none_ | | |

---

## 6. Abbreviations

> Abbreviations used in this Pack. Inherited abbreviations from upstream (SPF, FPF) are marked accordingly.

| Abbreviation | Full form (RU) | Full form (EN) | Level |
|-------------|---------------|----------------|-------|
| Datum | Кодовое имя компании «Датум Мебель» в идентификаторах ролей (`UTS.Datum.Role.*`) - латиница, техническое ограничение на кириллицу в кодах | Company code for «Датум Мебель» in role IDs | Pack |
| P2W | Принципы в работу | Principles to Work | Pack |
| ЛДСП | Ламинированная древесно-стружечная плита | Laminated chipboard | Pack |
| МДФ | Мелкодисперсная фракция (плита) | Medium Density Fibreboard | Pack |
| ХДФ | Плита высокой плотности | High Density Fibreboard | Pack |
| ПВХ | Поливинилхлорид | PVC | Pack |
| ПВШ | Полно-выкатные шариковые (направляющие) | Full-extension ball-bearing runners | Pack |
| HPL | Ламинат высокого давления | High Pressure Laminate | Pack |
| ПММ | Посудомоечная машина | Dishwasher | Pack |
| СМ | Стиральная машина | Washing machine | Pack |
| ДШ | Духовой шкаф | Oven | Pack |

---

_Ontology per SPF.SPEC.002. Pack ID: FE_
