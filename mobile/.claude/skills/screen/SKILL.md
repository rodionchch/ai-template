---
name: screen
description: Создать экран или компонент React Native. Используй когда нужно добавить новый экран, UI-блок или хук.
argument-hint: [ScreenName] [описание]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай экран или компонент: $ARGUMENTS

Существующие экраны:
!`ls src/screens/ 2>/dev/null`

Существующие компоненты:
!`ls src/components/ 2>/dev/null`

1. Прочитай CLAUDE.md для правил проекта
2. Найди похожий экран/компонент для соответствия стилю
3. Экран → `src/screens/[Name]/`, базовый UI → `src/components/ui/`, остальное → `src/components/[Name]/`
4. Зарегистрируй экран в навигаторе если нужно
5. TypeScript strict, без `any`, props interface перед компонентом
6. Стили через NativeWind `className`, экспорт через `index.ts`
