# Frontend Project

## Стек
React 19, TypeScript 5 (strict), Vite 6, Redux Toolkit 2 + RTK Query, Tailwind CSS v4, shadcn/ui, React Hook Form + Zod, React Router v7, Vitest + RTL, Prettier, pnpm

## Структура
```
src/
├── app/          # store, router, App.tsx
├── pages/        # страницы — только компоновка, без логики
├── components/   # переиспользуемые компоненты
│   └── ui/      # базовые UI (Button, Input, Modal...)
├── api/          # RTK Query endpoints
├── store/        # Redux slices и selectors
├── types/        # TypeScript типы, Zod-схемы
├── hooks/        # кастомные хуки
└── lib/          # утилиты
```

## Конвенции
- Компоненты — `PascalCase`, хуки — `useX`, утилиты — `camelCase`, папки — `kebab-case`
- Tailwind-классы через `cn()` (clsx + tailwind-merge)
- Типы выводить из Zod-схем: `type X = z.infer<typeof xSchema>`
- Тесты рядом с файлом: `Component.test.tsx`
- Коммиты — Conventional Commits (`feat:`, `fix:`, `refactor:`)

## Запрещено
- `any` в TypeScript
- Бизнес-логика и обращение к store внутри `components/`
- Прямые мутации state вне createSlice
- Хардкод URL — только `import.meta.env.VITE_*`
- `console.log` в коде — только через logger
