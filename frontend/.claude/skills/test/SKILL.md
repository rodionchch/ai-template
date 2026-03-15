---
name: test
description: Написать тесты для компонента, хука или утилиты. Используй когда нужно покрыть файл тестами.
argument-hint: [путь к файлу]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Напиши тесты для: $ARGUMENTS

Существующие тесты рядом с файлом:
!`ls "$(dirname "$ARGUMENTS")" 2>/dev/null | grep test`

1. Прочитай исходный файл полностью
2. Определи тип: компонент, хук, утилита, selector
3. Напиши тесты на Vitest + React Testing Library
4. Тестируй поведение, не реализацию
5. Симуляция действий через `userEvent`, HTTP-моки через msw
6. Файл теста рядом с исходником: `[name].test.tsx`
