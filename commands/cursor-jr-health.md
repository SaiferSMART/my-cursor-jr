# Проверить CursorJr

Запусти полный health-check:

```powershell
.\scripts\health-check.ps1
```

Он проверит:

- `cursor-jr` установлен как readonly-субагент;
- `cursor-jr-maintainer` установлен как maintainer-субагент;
- старый конфликтующий skill `cursor-jr` отсутствует;
- coverage базы знаний без пропусков;
- тестовые сценарии поведения проходят;
- `manifest.json` не устарел.

Итоговый отчёт: `knowledge-base/HEALTH-REPORT.md`.
