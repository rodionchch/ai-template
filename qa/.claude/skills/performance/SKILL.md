---
name: performance
description: Создать k6 нагрузочный тест. Используй когда нужно проверить производительность эндпоинта или сценария под нагрузкой.
argument-hint: [scenario] [описание]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай нагрузочный тест: $ARGUMENTS

Существующие performance тесты:
!`ls tests/performance/ 2>/dev/null`

1. Прочитай CLAUDE.md для правил проекта
2. Создай тест в `tests/performance/[scenario].js`
3. Определи thresholds: `http_req_duration p(95) < 500`, `http_req_failed < 0.01`
4. Используй stages: ramp-up → sustained load → ramp-down
5. URL и credentials через переменные окружения (`__ENV.BASE_URL`)
6. Добавь проверки (`check`) на статус-код и тело ответа
