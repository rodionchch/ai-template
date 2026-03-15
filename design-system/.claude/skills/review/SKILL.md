---
name: review
description: Code review компонентов дизайн-системы. Используй когда нужно проверить качество и соответствие гайдлайнам перед мержем.
argument-hint: [путь к файлу или пусто для всех изменений]
context: fork
allowed-tools: Read, Glob, Grep, Bash
---

Проведи code review: $ARGUMENTS

Изменения:
!`git diff HEAD -- $ARGUMENTS 2>/dev/null || git diff -- $ARGUMENTS 2>/dev/null || git diff HEAD 2>/dev/null`

Проверь по приоритетам:

**Критично** — хардкод цветов/отступов вместо токенов, отсутствие a11y (aria-*, keyboard nav), `any` в TypeScript, компонент без Story
**Важно** — нарушение конвенций (CLAUDE.md), `style={{}}` вместо Tailwind, отсутствие вариантов в Story, не используется Radix UI там где нужно
**Предложения** — полнота документации, покрытие edge-cases в Stories, читаемость

Формат: `file:line — проблема — решение`
