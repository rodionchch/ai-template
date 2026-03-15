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

**Критично** — баги, утечки памяти, security-проблемы, неверная типизация (`any`)
**Важно** — нарушение конвенций проекта (CLAUDE.md), дублирование, производительность
**Предложения** — читаемость, упрощение

Формат: `file:line — проблема — решение`
