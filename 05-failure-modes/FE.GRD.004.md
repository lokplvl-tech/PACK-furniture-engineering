## YAML Frontmatter

```yaml
---
id: FE.GRD.004
name: Tip-ON на глубокие выдвижные ящики
category: method-failure
severity: major
status: active
summary: "Дизайнер назначает пружинную систему Tip-ON на тандембоксы ради «стиля без ручек», хотя пружина не преодолеет нагруженный ящик"
created: 2026-07-26
last_updated: 2026-07-26
related:
  affects_method: [FE.M.001]
  affects_wp: [FE.WP.001]
  confused_distinction: []
tags: [guard, фурнитура, технолог]
---
```

---

## [FE.GRD.004] Tip-ON на глубокие выдвижные ящики

### Definition

Дизайнер назначает фурнитуру Tip-ON (открывание нажатием, без ручки) на глубокие выдвижные ящики (тандембоксы), хотя механизм рассчитан на распашные двери, а не на преодоление массы нагруженного ящика.

### Category

**This failure mode is**: `method-failure` — нарушение на шаге 8 метода [FE.M.001](../03-methods/FE.M.001.md), при добавлении платной фурнитуры после продажи.

### Observable Symptoms

- [ ] В заказе Tip-ON назначен на модуль с ящиками, а не с распашной дверью
- [ ] Клиенту продан «стиль без ручек» без уточнения ограничения по типу фасада

### Root Causes

| Cause | Description |
|-------|-------------|
| Эстетическая мода | Клиенты хотят единый безручечный фасад по всей кухне, включая ящики |
| Неявная граница применимости | В интерфейсе Базис-Салон Tip-ON не блокируется автоматически для ящиков |

### Consequences

- Ящик не открывается или открывается с большим усилием, рекламация клиента

### Related Items

| Type | Item | Relationship |
|------|------|--------------|
| Method | [FE.M.001](../03-methods/FE.M.001.md) | нарушается на шаге 8 |
| Role | [FE.R.002](../02-domain-entities/02A-roles.md#fe-r-002) Технолог | проверяет спецификацию фурнитуры |

### Guard (блокирующий инвариант)

Механизм Tip-ON разрешён исключительно для распашных дверей. Роль-контролёр: Технолог. Артефакт-доказательство: спецификация фурнитуры.

### Detection Methods

| Detection Method | When to Apply |
|--------------------|----------------|
| Проверка типа фасада перед назначением Tip-ON | Шаг 8 FE.M.001 |

### Notes

**Кросс-валидировано** источником ONEON Kitchen дословно: «На ящики TipOn НЕ ставим» (`06-sota/oneon-kitchen-tehchast.md` §3), плюс отдельное уточнение: врезной Tip-ON несовместим с газлифтом.

---

## Checklist Before Committing

- [x] ID follows pattern `FE.GRD.NNN`
- [x] Category specified
- [x] Observable symptoms are specific
- [x] Related items are linked
- [ ] Added to `07-map/`
