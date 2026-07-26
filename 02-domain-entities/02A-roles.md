# Roles: Мебельный инжиниринг

> Источник: `06-sota/Эпистемологический стандарт предприятия.md` §2 (внутренний стандарт «Датум Мебель»)

---

## What is a Role?

Per FPF: A **role** is a functional position that an agent occupies when performing certain methods. One person may occupy multiple roles; one role may be occupied by multiple people.

A role is NOT:
- A job title (may map to multiple roles)
- A person (person occupies roles)
- A skill (skills enable role performance)

---

## Roles Index

| ID | Role | Primary Methods | Тип (FPF) |
|----|------|-----------------|-----------|
| FE.R.001 | Дизайнер-конструктор (Designer-Constructor) | FE.M.001 (P2W) | U.Role |
| FE.R.002 | Технолог (Technologist) | контроль-гейт внутри FE.M.001, шаг 8 | U.Role |
| FE.R.003 | Монтажник (Installer) | сборка L1+L2 → L3 (метод не формализован) | U.Role |
| FE.R.004 | Клиент (Client) | согласование, подписание Договора | U.Role |
| FE.R.005 | Фабрика (Factory) | физический конвейер L0 → L1 (метод не формализован) | S.Role |

---

## [FE.R.001] Дизайнер-конструктор (Designer-Constructor)

**Definition**: Агент виртуального пространства. Переводит требования клиента и физические параметры помещения (L4-L6) в цифровую модель гарнитура в САПР «Базис-Салон».

**Key responsibilities**:
- Абсолютный изоморфизм между CAD-моделью и физической реальностью (см. [FE.D.004](../01-domain-contract/01B-distinctions.md#fe-d-004))
- Формирование 3D-эскиза и Спецификации
- Применение расчётных формул полок, зазоров и погонажа

**Methods performed**:
- [FE.M.001](../03-methods/FE.M.001.md) — P2W, все 8 шагов

**Work products owned**:
- Спецификация (FE.WP.001, карточка не создана)
- 3D-эскиз

**Typical failure modes when this role is absent or poorly performed**:
- Коллизии при монтаже (см. [FE.D.001](../01-domain-contract/01B-distinctions.md#fe-d-001) — путаница Объект/Описание)
- Локальные оптимизации в ущерб физике — перехватываются Гвардами на контроле Технолога

**Often confused with**: Технолог — Дизайнер создаёт Описание, Технолог проверяет его истинность относительно физики. Дизайнер не имеет права сам себя проверять (Guard).

---

## [FE.R.002] Технолог (Technologist)

**Definition**: Контролёр эпистемологической точности проекта. Выполняет физический аудит CAD-модели перед конвертацией в G-коды для ЧПУ.

**Key responsibilities**:
- Защита Производства от локальных оптимизаций Дизайнера (принцип-агент конфликт, см. `01A-bounded-context.md` §3 источника)
- Аудит технологических зазоров
- Применение 38-пунктового чек-листа GateProfilization
- Проверка совместимости материалов

**Methods performed**:
- Контроль-гейт на шаге 8 метода [FE.M.001](../03-methods/FE.M.001.md)

**Work products owned**:
- Отчёт DRR
- Заполненный чек-лист GateProfilization

**Typical failure modes when this role is absent or поorly performed**:
- Все 9 конфликтов из Матрицы эпистемологического контроля (Guards, §5 источника) — например, сокрытие газовых магистралей, назначение HPL на фрезерованный фасад

**Often confused with**: Дизайнер-конструктор — см. выше. Технолог не создаёт Описание, только проверяет его.

---

## [FE.R.003] Монтажник (Installer)

**Definition**: Агент физического мира. Выполняет финальную агрегацию холонов L1 и L2 в систему L3 (собранный гарнитур) на объекте клиента.

**Key responsibilities**:
- Абсолютно точное следование меткам Спецификации без самовольных изменений
- Сборка корпусов из ЛДСП, юстировка механизмов
- Подключение к L5 (квартирная разводка)

**Methods performed**: _не формализован как карточка метода — физическая сборка вне CAD-конвейера_

**Work products owned**: Собранный гарнитур (L3)

**Typical failure modes when this role is absent or poorly performed**: Отклонение от меток Спецификации → коллизии на этапе, где их уже нельзя исправить без демонтажа

**Often confused with**: Фабрика — Фабрика производит детали (L0→L1) на станках, Монтажник собирает готовые детали в помещении клиента (L1+L2→L3).

---

## [FE.R.004] Клиент (Client)

**Definition**: Принципал внешней среды. Владелец помещения и плательщик ресурса.

**Key responsibilities**:
- Формирование эстетических требований
- Подготовка помещения (L4) под монтаж
- Согласование 3D-эскиза, выбор техники
- Подписание Договора (деонтическое обязательство)

**Methods performed**: _не метод в CAD-конвейере — роль вне САПР_

**Work products owned**: Подписанный Договор

**Typical failure modes when this role is absent or poorly performed**: Самовольный ремонт помещения после замера аннулирует ответственность предприятия за коллизии при монтаже (см. Claim Scope, [FE.D.003](../01-domain-contract/01B-distinctions.md#fe-d-003))

**Often confused with**: —

---

## [FE.R.005] Фабрика (Factory)

**Definition**: Агент физического конвейера. Конвертирует сырой материал (L0) в детали (L1) на станках по цифровым спецификациям из САПР.

**Key responsibilities**:
- Раскрой форматно-раскроечным станком
- Кромление, сверление (присадка)
- Строгое следование картам кроя без исправления ошибок дизайна

**Methods performed**: _физический конвейер L0→L1 не формализован как карточка метода — см. таблицу «Компонентный уровень L1» в источнике (§1); кандидат на будущую карточку FE.M.002_

**Work products owned**: Набор физических деталей с ПВХ-кромкой и фурнитурой

**Typical failure modes when this role is absent or poorly performed**: Некомплект → остановка монтажа у клиента, срыв сроков

**Often confused with**: Монтажник — см. выше.

---

_Roles per SPF.SPEC.001/003. Pack ID: FE._
