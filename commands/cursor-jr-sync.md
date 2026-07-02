# Обновить базу знаний CursorJr

Запусти синхронизацию официальной документации Cursor:

```powershell
.\scripts\sync-docs.ps1
```

Затем:

1. Открой `knowledge-base/UPDATE-QUEUE.md`
2. Запусти `.\scripts\audit-coverage.ps1`
3. Обработай пункты со статусом `new` или `changed`
4. Упрости язык для новичков (контракт: `shared/knowledge-update-contract.md`)
5. Запиши в `knowledge-base/CHANGELOG.md`
6. Выполни `.\scripts\install-plugin.ps1`
7. Выполни `.\scripts\verify-install.ps1`

Следуй rule `cursor-jr-knowledge-refresh`.

Если работа большая — делегируй `Task(cursor-jr-maintainer)`.
