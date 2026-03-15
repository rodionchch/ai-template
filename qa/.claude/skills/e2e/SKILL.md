---
name: e2e
description: Создать Playwright E2E тест и Page Object. Используй когда нужно покрыть пользовательский сценарий или фичу.
argument-hint: [feature/scenario] [описание сценария]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай E2E тест: $ARGUMENTS

Существующие тесты:
!`ls tests/e2e/ 2>/dev/null`

Существующие Page Objects:
!`ls tests/helpers/pages/ 2>/dev/null`

1. Прочитай CLAUDE.md для правил проекта
2. Найди похожий тест для соответствия стилю
3. Создай или дополни Page Object в `tests/helpers/pages/[Page].ts`
4. Создай тест в `tests/e2e/[feature]/[scenario].spec.ts`
5. Только `getByRole`, `getByLabel`, `getByTestId` — без CSS-селекторов
6. Без `waitForTimeout`, данные через Faker.js
