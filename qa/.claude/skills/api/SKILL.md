---
name: api
description: Создать API тест для эндпоинта. Используй когда нужно протестировать REST API — статус-коды, схему ответа, валидацию.
argument-hint: [resource] [описание]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай API тест: $ARGUMENTS

Существующие API тесты:
!`ls tests/api/ 2>/dev/null`

Swagger/OpenAPI схема:
!`cat docs/openapi.json 2>/dev/null | head -50 || cat swagger.json 2>/dev/null | head -50`

1. Прочитай CLAUDE.md для правил проекта
2. Найди похожий тест для соответствия стилю
3. Создай тест в `tests/api/[resource].spec.ts`
4. Покрой: успешный сценарий, валидационные ошибки, авторизацию
5. Проверяй статус-код, схему ответа и side-effects в БД
6. Аутентификацию выноси в fixture, не дублируй
