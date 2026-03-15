---
name: review
description: Code review изменений. Используй когда нужно проверить качество кода перед мержем или после написания.
argument-hint: [путь к файлу или пусто для всех изменений]
context: fork
allowed-tools: Read, Glob, Grep, Bash
---

Проведи code review: $ARGUMENTS

Изменения:
!`git diff HEAD -- $ARGUMENTS 2>/dev/null || git diff -- $ARGUMENTS 2>/dev/null || git diff HEAD 2>/dev/null`

Проверь по приоритетам:

**Критично** — баги, утечки, security-проблемы, неверная типизация (`any`), незащищённые эндпоинты, SQL-инъекции
**Важно** — нарушение конвенций проекта (CLAUDE.md), логика в контроллерах, дублирование, N+1 запросы
**Предложения** — читаемость, упрощение, производительность

Формат: `file:line — проблема — решение`
