---
name: review
description: Code review тестов. Используй когда нужно проверить качество тест-кода перед мержем.
argument-hint: [путь к файлу или пусто для всех изменений]
context: fork
allowed-tools: Read, Glob, Grep, Bash
---

Проведи code review тестов: $ARGUMENTS

Изменения:
!`git diff HEAD -- $ARGUMENTS 2>/dev/null || git diff -- $ARGUMENTS 2>/dev/null || git diff HEAD 2>/dev/null`

Проверь по приоритетам:

**Критично** — тесты без assertions, зависимости между тестами, хардкод credentials, `any` в TypeScript
**Важно** — нарушение Page Object Model, `waitForTimeout`, хардкод тест-данных, дублирование
**Предложения** — читаемость, покрытие edge-cases, оптимизация скорости

Формат: `file:line — проблема — решение`
