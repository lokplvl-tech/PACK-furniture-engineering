---
id: FE.MAP.001
name: Pack Navigation Map
scope: full-pack
created: 2026-07-26
last_updated: 2026-07-26
generated: false
---

# [FE.MAP.001] Pack Navigation Map

> Собрана вручную 2026-07-26. Автогенератор (`SPF/scripts/generate-map.py`) не используется — он ожидает YAML-разметку буквально первыми символами файла, а собственный эталонный шаблон карточки метода SPF (`pack-template/03-methods/_method-card-template.md`) оборачивает её в заголовок «## YAML Frontmatter» и блок кода. Несовпадение подтверждено проверкой регулярного выражения генератора на самом шаблоне SPF — это системная нестыковка внутри SPF, не ошибка этого Pack'а. Обновлять вручную при добавлении/изменении карточек.

---

## Statistics

| Kind | Count |
|------|-------|
| Distinctions (D) | 8 |
| Roles (R) | 6 |
| Methods (M) | 2 (+2 кандидата, не созданы) |
| Work Products (WP) | 1 |
| Guards (GRD, extended kind) | 10 |
| SoTA Sources | 2 |
| **Total (реально существующих карточек)** | **29** |

---

## Distinctions (D)

> Все восемь — подсекции одного файла `01-domain-contract/01B-distinctions.md`, отдельных файлов с собственной YAML-разметкой нет.

| ID | Name |
|----|------|
| FE.D.001 | Объект vs Описание |
| FE.D.002 | Описание vs Спецификация |
| FE.D.003 | Work Scope vs Claim Scope |
| FE.D.004 | Изоморфизм vs Сходство |
| FE.D.005 | Гвард (Guard) vs Рекомендация |
| FE.D.006 | Инвариант vs Настраиваемый параметр |
| FE.D.007 | Тандембокс vs ПВШ |
| FE.D.008 | Холон vs Модуль |

## Roles (R)

> Все шесть — подсекции одного файла `02-domain-entities/02A-roles.md`, отдельных файлов с собственной YAML-разметкой нет.

| ID | Name | Источник | Status |
|----|------|----------|--------|
| FE.R.001 | Дизайнер-конструктор (Designer-Constructor) | Датум Мебель | active |
| FE.R.002 | Технолог (Technologist) | Датум Мебель | active |
| FE.R.003 | Монтажник (Installer) | Датум Мебель | active |
| FE.R.004 | Клиент (Client) | Датум Мебель | active |
| FE.R.005 | Фабрика (Factory) | Датум Мебель | active |
| FE.R.006 | Менеджер (Manager) | ONEON Kitchen — отсутствовал у Датум Мебель | active |

## Methods (M)

| ID | Name | Produces | SoTA | Status |
|----|------|----------|------|--------|
| [FE.M.001](../03-methods/FE.M.001.md) | P2W — Принципы в работу | FE.WP.001 | current, кросс-валидирован | active |
| [FE.M.003](../03-methods/FE.M.003.md) | Расчёт погонажа кухонного гарнитура | строка в FE.WP.001 | current, кросс-валидирован | active |

**Кандидаты, не созданы:** FE.M.002 (физическая сборка L0→L1, роль Фабрика), FE.M.004 (процедурный уровень P2W в интерфейсе «Базис-Салон»).

## Work Products (WP)

| ID | Name | Produced By | Status |
|----|------|-------------|--------|
| [FE.WP.001](../04-work-products/FE.WP.001.md) | Спецификация (эскиз + размеры + метки) | FE.M.001, FE.M.003 | active |

## Guards (GRD, extended kind)

| ID | Name | Severity | Кросс-валидирован ONEON |
|----|------|----------|----------------------------|
| [FE.GRD.001](../05-failure-modes/FE.GRD.001.md) | Игнорирование технических зазоров ради симметрии | critical | ✅ дословно |
| [FE.GRD.002](../05-failure-modes/FE.GRD.002.md) | Сокрытие газовых коммуникаций за несъёмными панелями | critical | ✅ дословно |
| [FE.GRD.003](../05-failure-modes/FE.GRD.003.md) | Назначение HPL-пластика на фрезерованный фасад | major | косвенно |
| [FE.GRD.004](../05-failure-modes/FE.GRD.004.md) | Tip-ON на глубокие выдвижные ящики | major | ✅ дословно |
| [FE.GRD.005](../05-failure-modes/FE.GRD.005.md) | ПММ дальше 1200 мм от мойки | critical | ✅ принцип идентичен |
| [FE.GRD.006](../05-failure-modes/FE.GRD.006.md) | Расчёт встроенной техники «на глаз» без артикула | major | ✅ принцип идентичен |
| [FE.GRD.007](../05-failure-modes/FE.GRD.007.md) | Отдельно стоящая СМ за профилем GOLA | major | ✅ дословно |
| [FE.GRD.008](../05-failure-modes/FE.GRD.008.md) | Врезка мойки в зону стыка столешниц | critical | ✅ принцип идентичен, числа расходятся |
| [FE.GRD.009](../05-failure-modes/FE.GRD.009.md) | Расхождение метража при заказе полотен | major | ✅ дословно |
| [FE.GRD.010](../05-failure-modes/FE.GRD.010.md) | Пропуск обязательных меток при передаче в производство | critical | ✅ концептуально |

Индекс с полным описанием кросс-валидации: [`05-failure-modes/00-guards-index.md`](../05-failure-modes/00-guards-index.md).

## SoTA Sources

| Источник | Компания | Файл |
|----------|----------|------|
| 1 | Датум Мебель | [`06-sota/Эпистемологический стандарт предприятия.md`](../06-sota/Эпистемологический%20стандарт%20предприятия.md) |
| 2 | ONEON Kitchen | [`06-sota/oneon-kitchen-tehchast.md`](../06-sota/oneon-kitchen-tehchast.md) |

Сводная карточка сравнения обоих источников: [`06-sota/furniture-engineering-sota-sheet.md`](../06-sota/furniture-engineering-sota-sheet.md).

## Decisions

| Дата | Решение | Файл |
|------|---------|------|
| 2026-07-26 | Разбить шаги 2 и 3 метода P2W на подшаги 2a/2b, 3a/3b | [`decisions/2026-07-26-p2w-step-split.md`](../decisions/2026-07-26-p2w-step-split.md) |

## Domain-Specific Entities (не оформлены как карточки)

| Kind | Что это | Где сейчас |
|------|---------|------------|
| HOL (Холон) | Узлы холархии L0-L6 | Только прозой в `06-sota/`, не разбито на отдельные карточки |
| Tools | Инструменты (Базис-Салон, Раскрой, ЧПУ, Смета, Склад, Салон, Упаковка) | `02-domain-entities/02D-tools-index.md`, не base-kind генератора |

## Warnings

- `02-domain-entities/02B-objects-of-attention.md` и `02-domain-entities/02E-characteristics-registry.md` — не заполнены, содержат только текст шаблона (в т.ч. плейсхолдеры `(link)`, это не битые ссылки на реальные файлы)
- Распределение по отдельным файлам («один файл — одна карточка») выдержано только для Methods, Work Products и Guards; Distinctions и Roles остаются подсекциями общих файлов — при будущей автогенерации это потребует либо разбивки на файлы, либо доработки генератора под мультикарточные файлы

---

*Собрана вручную, не сгенерирована. Обновить при следующем значимом изменении состава карточек.*
