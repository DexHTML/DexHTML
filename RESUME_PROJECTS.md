# Проекты для резюме и карьерного профиля

Краткая фактическая сводка проектов. Подробные публичные описания находятся в разделе [Case studies](case-studies/README.md).

## Позиционирование

В свободное от основной работы время применяю инженерный и продуктовый подход к цифровым проектам: от понимания рабочего процесса и пользовательского сценария до тестирования, внедрения, эксплуатации и анализа результата.

Основные направления:

- внутренние web-системы;
- автоматизация рабочих процессов;
- интеграция независимых модулей;
- тестирование и controlled release;
- техническая документация;
- Telegram-продукты;
- WordPress / GitHub Pages / SEO;
- content и media experiments;
- использование AI-инструментов при сохранении ручной проверки и ответственности за результат.

---

# Внутренние системы

## TechRepair

**Рабочая внутренняя production-система учёта техники и ремонтов.**

Основные функции:

- карточки оборудования и стабильная идентификация;
- QR;
- ремонтные циклы и события;
- договоры и акты передачи;
- подменный фонд;
- отчёты и XLSX;
- роли и audit;
- read-only API для интеграций.

Инженерная foundation проекта включает versioned migrations, CI, staging, backup/restore proof, concurrency checks, data integrity guards, immutable historical snapshots, permission matrix и controlled production releases.

Текущий этап: pre-1.0; основной security, reliability и business-logic hardening закрыт permanent regression checks, продолжается финальный audit-driven cleanup.

[Подробный case study](case-studies/TECHREPAIR.md)

---

## FairDesk

**Рабочий внутренний MVP заявочной системы.**

FairDesk отвечает за:

- создание и lifecycle заявок;
- роли заявителя, исполнителя и администратора;
- категории и рабочие группы;
- ручное и автоматическое назначение;
- общую очередь для отдельных сценариев;
- комментарии, историю, архив и audit;
- объяснение логики назначения;
- связь с оборудованием;
- использование внешних данных о доступности сотрудников.

Подтверждён реальный read-only integration path с Duty Schedule через Django-клиент и API v1. TechRepair остаётся отдельным source of truth по оборудованию.

[Подробный case study](case-studies/FAIRDESK.md)

---

## Duty Schedule

**Стабильная внутренняя production-система планирования дежурств и доступности сотрудников.**

Текущий release: **2.0.1 — released / accepted**.

После перехода на V2 реализованы и приняты:

- employee lifecycle;
- effective-dated roster;
- versioned duty queue;
- canonical schedule runtime;
- производственный календарь;
- отпуска, недоступность и больничные;
- дежурства и компенсационные дни;
- Preview и manual overrides;
- Month Check / Today;
- Excel;
- API v1;
- FairDesk integration;
- roles / permissions / CSRF / audit;
- migration/schema integrity;
- backup/recovery.

Финальная проверка релиза 2.0.1: **116 passed / 0 warnings / 0 failed**.

[Подробный case study](case-studies/DUTY_SCHEDULE.md)

---

# Telegram-продукт

## Код полуночи

**Работающий production MVP персонального Telegram-продукта.**

Текущий V2 flow включает:

- бесплатный результат;
- безопасный unavailable-сценарий;
- Telegram Stars;
- persistent entitlement;
- полную расшифровку из пяти глав;
- versioned content packages;
- минимальный runtime state;
- controlled deploy / rollback;
- CI и release checks.

Активный production content package: **0.1.17**, 12 утверждённых golden cases.

На последнем полном hardening-checkpoint: **476 tests — OK** в изолированном Ubuntu-контуре.

[Подробный case study](case-studies/KOD_POLUNOCHI.md)

---

# SEO, content и media projects

## Карта в полночь

Авторский WordPress + Telegram + SEO-проект с подтверждённым поисковым спросом и связанным Telegram-продуктом.

Последний полный checkpoint:

- Яндекс: **1 336 показов / 137 кликов / CTR 10,25%** за месяц;
- Google: 40 кликов / 815 показов за три месяца;
- лидирующая статья дала 116 кликов из Яндекса;
- текущий анонимный form experiment получил первую внешнюю отправку.

Проект развивается через измеримые гипотезы и чистые окна наблюдения.

[Подробный case study](case-studies/KARTA_V_POLNOCH.md)

---

## Проверь перед действием

Публичный SEO-MVP на GitHub Pages.

- 24 публичных URL;
- интерактивные проверки;
- sitemap / robots / canonical;
- Яндекс Метрика;
- Search Console / Вебмастер;
- автоматизированный site audit;
- первые тематические показы и органические клики.

Продуктовые цели на последнем checkpoint пока не подтверждены, что зафиксировано как часть результата эксперимента.

[Подробный case study](case-studies/CHECK_BEFORE_ACTION.md)

---

## АРХИВ 03:17

Экспериментальный YouTube Shorts-проект с серийным production workflow и data-driven анализом удержания.

Последний документированный checkpoint:

- 9 469 просмотров;
- 46,2 часа просмотра;
- 26 подписчиков;
- 61,7% продолжили смотреть;
- 98,1% трафика из Shorts feed.

Проект использует реестр сюжетов, единый визуальный/звуковой стандарт и сравнительный анализ выпусков через 24/48 часов.

[Подробный case study](case-studies/ARHIV_0317.md)

---

## НейроПомощник

Контентный проект на Дзене и в Telegram.

Стратегия эволюционировала от «нейросеть в обычной жизни» к конкретным пользовательским проблемам, где AI используется как инструмент решения.

Проект тестирует:

- темы;
- заголовки;
- обложки;
- CTR;
- дочитывания;
- нативный Telegram-контент;
- повторяемость результата между сериями материалов.

[Подробный case study](case-studies/NEIROPOMOSHNIK.md)

---

## Текст и точка

Контентно-сервисный MVP о понятных текстах.

- WordPress.com;
- Telegram;
- работающая форма;
- Google Search Console;
- Яндекс Вебмастер;
- 21 страница в индексе Google на последнем checkpoint.

Устойчивый спрос и реальные обращения пока не подтверждены. Следующий этап — ручная продуктовая валидация на реальных задачах, а не массовое расширение SEO-контента.

[Подробный case study](case-studies/TEKST_I_TOCHKA.md)

---

# Frontend-демонстрации

- [AutoService Demo](https://github.com/DexHTML/AutoService-Demo) — многостраничный адаптивный сайт сферы услуг;
- [Gym Landing](https://github.com/DexHTML/gym-landing-dexhtml) — адаптивный лендинг с анимациями;
- [Crypto Landing Demo](https://github.com/DexHTML/crypto-landing-demo) — статический адаптивный лендинг;
- [NFT Landing Demo](https://github.com/DexHTML/nft-landing-demo) — адаптивная сетка, карточки и JavaScript-анимации.

---

# Технологии проектов

В разных проектах используются:

- PHP / PDO;
- Python / Django;
- MariaDB / MySQL / SQLite;
- HTML / CSS / JavaScript;
- Bootstrap;
- Linux / Nginx / systemd;
- Telegram Bot API;
- WordPress.com;
- Git / GitHub / GitHub Actions;
- GitHub Pages;
- CI / regression testing;
- database migrations;
- backup / restore;
- Google Search Console;
- Яндекс Вебмастер / Метрика;
- YouTube Studio analytics;
- системная документация;
- AI-assisted analysis, implementation и content workflow.

Этот список описывает стек проектов, а не заявляет одинаковый уровень самостоятельного владения каждым инструментом.

---

# Краткая формулировка для карьерного профиля

В свободное от основной работы время развиваю цифровые проекты для реальных рабочих и пользовательских задач: внутренние системы учёта и заявок, планирование доступности сотрудников, Telegram-продукт, SEO-MVP, WordPress-проекты и медиа-эксперименты. В проектах занимаюсь постановкой задач, описанием процессов, пользовательскими сценариями, проверкой логики, тестированием, внедрением изменений, аналитикой и документацией. AI-инструменты использую как помощник, сохраняя ручную проверку и ответственность за итоговое решение.
