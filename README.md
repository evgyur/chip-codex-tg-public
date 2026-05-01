# chip-codex-tg-public

Совместимый alias-репозиторий для старого public имени Telegram Codex cockpit.

## Статус
Это больше не отдельный competing public center.

Канонический public центр правды:
- `telegram-codex-cockpit`

Этот repo нужен, чтобы не ломать:
- старые заметки
- старые ссылки
- старые промпты
- привычное старое имя

## Что должно оставаться тем же
Alias должен сохранять тот же public contract:
- отдельный Telegram-чат под Codex
- topics вместо одной шумной ленты
- отдельный agent
- `/cas_*` как control surface
- **один topic = один workstream**
- progress heartbeat для длинных run
- visible stall notice + nudge при тишине
- после bind можно писать обычным текстом
- voice notes идут в Codex как transcript
- inbound files идут в Codex как local path/context

## Важно
Этот alias не должен снова обрастать собственной competing логикой.

Новые public правки сначала вносить в:
- `telegram-codex-cockpit`

А здесь держать:
- совместимость по имени
- тонкий public wrapper
- те же reference docs и проверки, если они нужны для self-contained публикации

## References
- `SKILL.md`
- `references/onboarding-ru.md`
- `references/runbook.md`
- `references/public-private-split.md`
- `references/media-ingress-contract.md`
- `references/refactor-topology-2026-04-09.md`
