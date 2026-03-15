---
name: component
description: Создать компонент дизайн-системы со Story. Используй когда нужно добавить новый UI-примитив или составной компонент.
argument-hint: [ComponentName] [описание и варианты]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай компонент дизайн-системы: $ARGUMENTS

Существующие компоненты:
!`ls src/components/ 2>/dev/null`

Доступные токены:
!`ls src/tokens/ 2>/dev/null`

1. Прочитай CLAUDE.md для правил проекта
2. Найди похожий компонент для соответствия стилю
3. Создай `src/components/[Name]/[Name].tsx`:
   - Radix UI Primitive как основа если есть подходящий
   - Варианты через `cva()`, стили через `cn()`
   - JSDoc на props для Storybook autodocs
4. Создай `src/components/[Name]/[Name].stories.tsx`:
   - Story на каждый вариант + состояния (Disabled, Loading, Error)
   - `argTypes` для интерактивного контроля
5. Экспорт через `src/components/[Name]/index.ts`
