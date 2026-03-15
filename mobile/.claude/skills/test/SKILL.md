---
name: test
description: Написать тесты для экрана, компонента или хука. Используй когда нужно покрыть файл тестами.
argument-hint: [путь к файлу]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

Напиши тесты для: $ARGUMENTS

Существующие тесты рядом с файлом:
!`ls "$(dirname "$ARGUMENTS")" 2>/dev/null | grep test`

1. Прочитай исходный файл полностью
2. Определи тип: экран, компонент, хук, утилита, selector
3. Jest + React Native Testing Library
4. Нативные модули мокай через `jest-expo`
5. Тестируй поведение, не реализацию
6. Симуляция действий через `userEvent`, HTTP-моки через msw
7. Файл теста рядом с исходником: `[name].test.tsx`
