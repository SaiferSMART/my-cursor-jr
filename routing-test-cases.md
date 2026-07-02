# CursorJr — матрица маршрутизации

Цель: не путать пользовательского наставника `cursor-jr`, maintainer-субагента `cursor-jr-maintainer` и обычную работу главного Agent.

## Решение за 10 секунд

```mermaid
flowchart TD
    q[Запрос пользователя]
    beginner{Нужно объяснить Cursor новичку?}
    kb{Нужно обслуживать KB/плагин?}
    deep{Это production/debug/code task?}
    jr[Task cursor-jr]
    maint[Task cursor-jr-maintainer]
    main[Главный Agent]

    q --> kb
    kb -->|да| maint
    kb -->|нет| beginner
    beginner -->|да| jr
    beginner -->|нет| deep
    deep -->|да| main
    deep -->|нет| main
```

## Таблица случаев

| Запрос | Кого звать | Почему |
|--------|------------|--------|
| «Я новичок, что нажать?» | `Task(cursor-jr)` | Нужен наставник простым языком |
| «Объясни Ask/Plan/Agent» | `Task(cursor-jr)` | Обучение режимам |
| «Что такое MCP?» | `Task(cursor-jr)` | Обучение концепции |
| «Сделай rule/skill для меня» | Сначала `Task(cursor-jr)`, потом главный Agent | Сначала понять выбор, затем выполнить |
| «Обнови базу знаний CursorJr» | `Task(cursor-jr-maintainer)` | Это обслуживание KB |
| «Запусти sync docs» | `Task(cursor-jr-maintainer)` | Это maintainer workflow |
| «Проверь, почему Canvas не шарится» | `Task(cursor-jr)` | Объяснение UI/условий |
| «Сделай сайт/код/фикс» | Главный Agent | Это выполнение, не обучение Cursor |
| «Production падает, вот логи» | Debug / главный Agent | Нужен дебаг, не наставник |

## Антиошибки

- Не вызывать `cursor-jr`, если пользователь просит «просто сделай без объяснений».
- Не вызывать `cursor-jr-maintainer` для обычных вопросов новичка.
- Не создавать `skills/cursor-jr/SKILL.md`.
- Не копировать maintainer-поведение в `agents/cursor-jr.md`.
