# Design System Project

## Стек
React 19, TypeScript 5 (strict), Storybook 8+, Style Dictionary 4, Tailwind CSS v4, Radix UI Primitives, shadcn/ui, Chromatic (visual regression), Figma Tokens (Variables), pnpm

## Структура
```
src/
├── tokens/       # дизайн-токены
│   ├── colors.ts
│   ├── spacing.ts
│   ├── typography.ts
│   └── index.ts
├── components/   # компоненты дизайн-системы
│   └── [Name]/
│       ├── [Name].tsx
│       ├── [Name].stories.tsx
│       └── index.ts
├── docs/         # MDX документация и гайдлайны
└── .storybook/   # конфиг Storybook
```

## Конвенции
- Все значения (цвет, отступ, шрифт) — только через токены, не хардкод
- Компоненты строятся на Radix UI Primitives для доступности (a11y)
- Каждый компонент — обязательно `.stories.tsx` со всеми вариантами
- Стили через Tailwind `className` + `cn()` (clsx + tailwind-merge)
- Токены синхронизированы с Figma Variables
- Коммиты — Conventional Commits (`feat:`, `fix:`, `refactor:`)

## Запрещено
- `any` в TypeScript
- Хардкод цветов, отступов, размеров — только токены
- Стили через `style={{}}` если есть токен в Tailwind
- Компонент без Story в Storybook
- Нарушение a11y: интерактивные элементы без `aria-*` и keyboard support
