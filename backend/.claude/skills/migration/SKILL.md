---
name: migration
description: Создать Prisma-миграцию и обновить схему. Используй когда нужно изменить структуру базы данных.
argument-hint: [описание изменений]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Создай Prisma-миграцию: $ARGUMENTS

Текущая схема:
!`cat prisma/schema.prisma 2>/dev/null | head -100`

Последние миграции:
!`ls prisma/migrations/ 2>/dev/null | tail -5`

1. Прочитай текущую `prisma/schema.prisma` полностью
2. Внеси изменения в схему согласно заданию
3. Учти связи между моделями и индексы
4. Проверь что типы Prisma соответствуют TypeScript-типам в коде
5. После изменений запусти: `pnpm prisma migrate dev --name [описание]`
