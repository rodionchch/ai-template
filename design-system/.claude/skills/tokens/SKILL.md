---
name: tokens
description: Добавить или обновить дизайн-токены. Используй когда нужно синхронизировать токены с Figma или добавить новые значения в систему.
argument-hint: [категория токенов] [описание изменений]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Обнови дизайн-токены: $ARGUMENTS

Текущие токены:
!`cat src/tokens/index.ts 2>/dev/null`

Tailwind конфиг:
!`cat tailwind.config.ts 2>/dev/null`

1. Прочитай CLAUDE.md и все файлы в `src/tokens/`
2. Внеси изменения в нужный файл (`colors.ts`, `spacing.ts`, `typography.ts`)
3. Обнови `src/tokens/index.ts` если добавлены новые экспорты
4. Синхронизируй с `tailwind.config.ts` — токены должны быть доступны как Tailwind-классы
5. Проверь: нет ли компонентов с захардкоженными значениями которые стоит заменить
