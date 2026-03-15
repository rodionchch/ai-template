---
name: module
description: Создать NestJS модуль с контроллером, сервисом и DTO. Используй когда нужно добавить новую фичу или ресурс.
argument-hint: [ModuleName] [описание]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай NestJS модуль: $ARGUMENTS

Существующие модули:
!`ls src/modules/ 2>/dev/null`

1. Прочитай CLAUDE.md для правил проекта
2. Найди похожий модуль для соответствия стилю
3. Создай структуру `src/modules/[name]/`:
   - `[name].module.ts` — NestJS модуль
   - `[name].controller.ts` — эндпоинты, Swagger-декораторы
   - `[name].service.ts` — бизнес-логика
   - `dto/create-[name].dto.ts` — DTO с class-validator
   - `dto/update-[name].dto.ts` — DTO для обновления
4. TypeScript strict, без `any`
5. Зарегистрируй модуль в `src/app/app.module.ts`
