# Methods Index: Мебельный инжиниринг

This file provides a navigable index of all methods in the pack.

---

## What is a Method?

Per FPF: A **method** (or practice) is a repeatable way of doing something that produces a predictable kind of result. Methods are performed by roles and produce work products.

A method is NOT:
- A tool (tools enable methods)
- A step-by-step scenario (that's an instance/application of a method)
- A work product (that's what the method produces)

---

## Methods by Category

### Категория 1: Проектирование (Дизайнер-конструктор)

| ID | Method Name | Produces | Status |
|----|-------------|----------|--------|
| [FE.M.001](../03-methods/FE.M.001.md) | P2W — Принципы в работу | FE.WP.001 | active |

### Категория 2: Физический конвейер (Фабрика)

| ID | Method Name | Produces | Status |
|----|-------------|----------|--------|
| [FE.M.002](../03-methods/FE.M.002.md) | Физическая сборка L0→L1 (Раскрой→Кромление→Присадка→ПВХ-плёнка→Комплектование) | Набор деталей (без карточки WP) | active |

### Категория 3: Коммерческий расчёт (роль не формализована)

| ID | Method Name | Produces | Status |
|----|-------------|----------|--------|
| [FE.M.003](../03-methods/FE.M.003.md) | Расчёт погонажа кухонного гарнитура | строка в FE.WP.001 | active |

### Категория 4: Интерфейс «Базис-Салон» — не формализован

| ID | Method Name | Produces | Status |
|----|-------------|----------|--------|
| _FE.M.004 (кандидат)_ | Процедурный уровень P2W: создание заказа/клиента/помещения в интерфейсе (см. `06-sota/oneon-kitchen-tehchast.md` §10) | — | не создан |

---

## Full Methods List (Alphabetical)

| ID | Method Name | Category | Produces | SoTA |
|----|-------------|----------|----------|------|
| FE.M.001 | P2W — Принципы в работу | Проектирование | FE.WP.001 | current |
| FE.M.002 | Физическая сборка L0→L1 | Физический конвейер | Набор деталей | current |
| FE.M.003 | Расчёт погонажа кухонного гарнитура | Коммерческий расчёт | строка в FE.WP.001 | current |

---

## Methods by Work Product Produced

| Work Product | Produced By Methods |
|--------------|---------------------|
| [FE.WP.001](../04-work-products/FE.WP.001.md) (Спецификация) | FE.M.001 (создаёт), FE.M.003 (дополняет строкой погонажа) |

---

## Adding a New Method

1. Create file: `../03-methods/DOMAIN.M.<NNN>.md` using template
2. Add entry to this index
3. Update `07-map/` navigation
4. Verify pre-commit checklist
