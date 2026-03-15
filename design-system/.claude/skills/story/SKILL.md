---
name: story
description: Создать или дополнить Storybook stories для компонента. Используй когда компонент уже есть, но нужно добавить документацию или варианты.
argument-hint: [путь к компоненту или ComponentName]
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

Создай Storybook story для: $ARGUMENTS

Существующие stories рядом:
!`ls "$(dirname "$ARGUMENTS")" 2>/dev/null | grep stories`

1. Прочитай исходный компонент полностью
2. Определи все props, варианты и состояния
3. Создай `[Name].stories.tsx` рядом с компонентом:
   - `meta` с `title`, `component`, `argTypes` для каждого prop
   - Story `Default` — базовый вид
   - Story на каждый `variant` и `size`
   - Stories для состояний: `Disabled`, `Loading`, `Error`, `Empty` если применимо
   - Story `AllVariants` — все варианты на одном экране
4. Добавь MDX-документацию если компонент сложный
