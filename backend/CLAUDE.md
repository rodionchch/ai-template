# Backend Project

## Стек
NestJS 11, TypeScript 5 (strict), PostgreSQL 16, Prisma 6, Redis (ioredis), BullMQ, Passport + JWT, class-validator + class-transformer, Swagger (@nestjs/swagger), Zod (@nestjs/config), Jest + Supertest, pnpm

## Структура
```
src/
├── app/          # AppModule, main.ts, конфигурация
├── modules/      # фиче-модули
│   └── [name]/
│       ├── dto/           # DTO с class-validator
│       ├── entities/      # Prisma-модели или доп. типы
│       ├── [name].controller.ts
│       ├── [name].service.ts
│       └── [name].module.ts
├── common/       # guards, interceptors, decorators, pipes, filters
├── config/       # конфиги (@nestjs/config + Zod-валидация)
├── database/     # Prisma schema, migrations, seeds
└── types/        # общие TypeScript типы
```

## Конвенции
- Модули — `PascalCase`, файлы — `kebab-case.type.ts`
- DTO — `CreateXDto`, `UpdateXDto`, `XResponseDto`
- Валидация входных данных через `class-validator` в DTO
- Конфиг через `@nestjs/config` + Zod-схема валидации
- Тесты рядом с файлом: `[name].service.spec.ts`
- Коммиты — Conventional Commits (`feat:`, `fix:`, `refactor:`)

## Запрещено
- `any` в TypeScript
- Бизнес-логика в контроллерах — только в сервисах
- Прямые SQL-запросы вне Prisma/Repository
- Хардкод секретов — только через `process.env` + ConfigService
- `console.log` — только через NestJS Logger
