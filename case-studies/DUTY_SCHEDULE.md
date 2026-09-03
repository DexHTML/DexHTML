# Duty Schedule

## Внутренняя система планирования дежурств и доступности сотрудников

**Статус:** стабильный внутренний production-релиз  
**Текущая версия:** 2.0.1  
**Release status:** released / accepted  
**Исходный код:** закрыт

Duty Schedule — внутренняя система, которая формирует рабочий календарь, управляет очередью дежурств и предоставляет другим модулям данные о фактической доступности сотрудников.

После переработки версии 2.0 V2 стал единственным каноническим runtime системы.

---

## Что реализовано

- жизненный цикл сотрудников;
- effective-dated состав групп;
- versioned duty queue;
- отдельный display order;
- производственный календарь;
- отпуска;
- ручная недоступность;
- больничные;
- дежурства;
- компенсационные дни;
- ручные overrides;
- Preview;
- Month Check;
- Today;
- Excel-экспорт;
- API v1;
- интеграционная страница;
- роли и permissions;
- audit;
- migration/schema integrity;
- backup и recovery.

---

## Версия 2.0

Основная переработка 2.0 заменила раннюю модель каноническим V2 runtime.

Ключевые изменения:

- employee lifecycle отделён от внутренних периодов назначения;
- состав групп стал effective-dated;
- очередь дежурств стала версионируемой;
- расчёт дня централизован через единый runtime;
- browser surfaces, API и Excel используют одну и ту же каноническую модель;
- legacy runtime paths выведены из эксплуатации;
- миграция production-данных прошла отдельную проверку;
- release принят после полного System Check и backup/recovery gates.

---

## Версия 2.0.1

2.0.1 — узкий эксплуатационный maintenance release без redesign основной модели.

В нём были приняты:

- корректное различение общего периода работы сотрудника и внутренних границ назначений;
- отдельное отображение будущего начала дежурств;
- применение больничных в каноническом runtime;
- отдельное отображение больничного в Preview;
- согласованное отражение больничных в обоих вариантах Excel;
- постоянные regression contracts для runtime, Preview и Excel.

---

## Проверяемость

Финальная production-проверка релиза 2.0.1:

**116 passed · 0 warnings · 0 failed**

`SYSTEM_CHECK_OK=1`

Permanent checks покрывают:

- migration/schema integrity;
- отсутствие legacy runtime;
- browser mutation security;
- API и integration health;
- roster/day/runtime contracts;
- duty queue и month-boundary semantics;
- Preview;
- Month Check;
- Excel;
- schedule overrides;
- роли, CSRF, audit и permissions.

---

## API и интеграция с FairDesk

Duty Schedule предоставляет read-only API v1 для внутренних потребителей.

Подтверждён реальный integration path через production Django-клиент FairDesk. FairDesk получает:

- health;
- календарный день;
- дежурство;
- статус сотрудника;
- availability.

Acceptance-проверка подтвердила, что API работает через канонический V2 runtime, база и schedule runtime healthy, а агрегированные количества доступных сотрудников согласованы с фактическими флагами в ответах.

FairDesk использует эти данные в assignment logic, но не изменяет расписание.

---

## Безопасность и эксплуатация

В проекте приняты:

- разграничение ролей;
- CSRF-защита изменяющих действий;
- аудит операций;
- отсутствие credential values в audit-событиях;
- контроль browser mutations;
- проверка privacy/hardcode boundary;
- backup проекта и базы;
- isolated restore proof;
- tagged production releases.

---

## Технологии

- PHP;
- PDO;
- MySQL / MariaDB;
- JavaScript;
- Bootstrap;
- PhpSpreadsheet;
- cron;
- shell;
- Git / GitHub;
- backup tooling.

---

## Моя роль

В проекте я занимаюсь:

- постановкой требований;
- описанием правил графика;
- проектированием lifecycle сотрудников;
- проверкой сложных календарных сценариев;
- release-планированием;
- regression testing;
- production acceptance;
- backup/recovery проверками;
- интеграцией с FairDesk;
- документацией.

AI-инструменты используются как технический помощник; каждое изменение проходит проверку перед включением в рабочий runtime.

---

## Ограничения

- система предназначена для внутреннего использования;
- исходный код и реальные данные закрыты;
- архитектура рассчитана на конкретный организационный процесс;
- публичный case study намеренно не содержит персональных данных и внутренней инфраструктуры.