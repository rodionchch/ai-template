---
name: test
description: Написать тесты для сервиса, контроллера или утилиты. Используй когда нужно покрыть файл тестами.
argument-hint: [путь к файлу]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Напиши тесты для: $ARGUMENTS

Существующие тесты рядом с файлом:
!`ls "$(dirname "$ARGUMENTS")" 2>/dev/null | grep spec`

1. Прочитай исходный файл полностью
2. Определи тип: service, controller, guard, pipe, interceptor
3. Для сервисов — unit-тесты с моком Prisma и зависимостей
4. Для контроллеров — e2e через Supertest или unit с моком сервиса
5. Тестируй поведение, не реализацию
6. Файл теста рядом с исходником: `[name].spec.ts`
