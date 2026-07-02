# CursorJr — реестр Task-субагентов

| Task name | Файл | Роль |
|-----------|------|------|
| `cursor-jr` | `agents/cursor-jr.md` | Русскоязычный наставник для новичков (readonly) |
| `cursor-jr-maintainer` | `agents/cursor-jr-maintainer.md` | Обслуживание KB, sync, coverage, install/verify |

Вызов: `Task(cursor-jr)`

Обслуживание: `Task(cursor-jr-maintainer)`

Fallback: `Task(generalPurpose)` + `agents/cursor-jr.md`
