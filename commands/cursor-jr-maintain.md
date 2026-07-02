# CursorJr Maintainer

Вызови maintainer-субагента:

```text
Task(cursor-jr-maintainer)
```

Передай задачу:

- проверить `knowledge-base/UPDATE-QUEUE.md`;
- обновить недостающие карточки;
- запустить `scripts/audit-coverage.ps1`;
- обновить `CHANGELOG.md`;
- выполнить `scripts/install-plugin.ps1` и `scripts/verify-install.ps1`.

Не используй этот сценарий для ответов новичкам. Для этого есть `Task(cursor-jr)`.
