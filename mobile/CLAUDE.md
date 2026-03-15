# Mobile Project

## Стек
React Native 0.76+ (New Architecture), TypeScript 5 (strict), Expo 52+, Redux Toolkit 2 + RTK Query, React Navigation v7, NativeWind v4, React Hook Form + Zod, React Native Reanimated 3, React Native MMKV, Jest + React Native Testing Library, Maestro (E2E), pnpm

## Структура
```
src/
├── app/          # store, навигация, App.tsx
├── screens/      # экраны — только компоновка, без логики
├── components/   # переиспользуемые компоненты
│   └── ui/      # базовые (Button, Input, Modal...)
├── api/          # RTK Query endpoints
├── store/        # Redux slices и selectors
├── types/        # TypeScript типы, Zod-схемы
├── hooks/        # кастомные хуки
└── lib/          # утилиты
```

## Конвенции
- Компоненты — `PascalCase`, хуки — `useX`, утилиты — `camelCase`, папки — `kebab-case`
- Стили через NativeWind (`className`), сложная анимация — Reanimated 3
- Типы выводить из Zod-схем: `type X = z.infer<typeof xSchema>`
- Тесты рядом с файлом: `Component.test.tsx`
- Коммиты — Conventional Commits (`feat:`, `fix:`, `refactor:`)

## Запрещено
- `any` в TypeScript
- Бизнес-логика и обращение к store внутри `components/`
- `StyleSheet.create` если есть NativeWind — только для динамических стилей
- Хардкод URL — только `process.env.EXPO_PUBLIC_*`
- `console.log` в коде — только через logger
