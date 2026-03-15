---
name: feature
description: Создать Redux slice + RTK Query endpoint для новой фичи. Используй когда нужно добавить новую бизнес-логику с состоянием и API.
argument-hint: [название фичи] [описание]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай Redux slice и RTK Query endpoint для фичи: $ARGUMENTS

Текущая структура store:
!`ls src/store/ 2>/dev/null`

Текущие API endpoints:
!`ls src/api/ 2>/dev/null`

1. Прочитай CLAUDE.md для правил проекта
2. Создай `src/store/[name].slice.ts` — slice с actions и selectors
3. Создай `src/api/[name].api.ts` — RTK Query endpoints
4. Добавь reducer и api в `src/app/store.ts`
5. Типы вынеси в `src/types/[name].ts`
