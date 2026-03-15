---
name: component
description: Создать React-компонент. Используй когда нужно сгенерировать новый компонент, хук или UI-блок.
argument-hint: [ComponentName] [описание]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай React-компонент: $ARGUMENTS

Существующие компоненты:
!`ls src/components/ 2>/dev/null`

1. Прочитай CLAUDE.md для правил проекта
2. Найди похожие компоненты для соответствия стилю
3. Базовый UI → `src/components/ui/`, остальное → `src/components/[Name]/`
4. TypeScript strict, без `any`, props interface перед компонентом
5. Классы через `cn()`, экспорт через `index.ts`
