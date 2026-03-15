# QA Project

## Стек
Playwright 1.50+, TypeScript 5 (strict), Jest 29, Supertest, k6, Allure Report, Faker.js, Docker Compose, pnpm

## Структура
```
tests/
├── e2e/          # Playwright E2E сценарии
│   └── [feature]/
│       └── [scenario].spec.ts
├── api/          # API-тесты (Jest + Supertest или Playwright API)
│   └── [resource].spec.ts
├── performance/  # k6 нагрузочные тесты
│   └── [scenario].js
├── fixtures/     # тестовые данные, фабрики
├── helpers/      # Page Objects, утилиты, кастомные матчеры
└── reports/      # Allure-отчёты (gitignore)
```

## Конвенции
- Page Object Model для E2E: один класс — одна страница
- Тест-данные через Faker.js, не хардкод
- Независимые тесты — каждый тест не зависит от другого
- Группировка: `describe` по фиче, `test` по сценарию
- Теги: `@smoke`, `@regression`, `@critical` через `test.describe`
- Коммиты — Conventional Commits (`test:`, `fix:`, `refactor:`)

## Запрещено
- `any` в TypeScript
- Зависимости между тестами (общий state, порядок запуска)
- Хардкод URL и credentials — только через `.env`
- `waitForTimeout` (sleep) — только явные ожидания Playwright
- Тесты без assertions
