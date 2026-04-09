# chip-codex-tg-public

Совместимый alias-репозиторий для старого public имени Telegram Codex cockpit.

## Статус
Это больше не отдельный competing public center.

После refactor от 2026-04-09 схема такая:
- `telegram-codex-cockpit` = canonical public contract
- `chip-codex-tg-public` = compatibility alias
- `chip-codex-tg` = private live overlay

## Зачем alias сохранён
Чтобы не ломать:
- старые заметки,
- старые ссылки,
- старые промпты,
- привычное имя из прошлых обсуждений.

## Что делать дальше
Для новых public изменений и документации использовать:
- `../telegram-codex-cockpit/`

А этот repo держать тонким и совместимым, без собственной дрейфующей логики.
