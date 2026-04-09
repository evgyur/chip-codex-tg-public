---
name: chip-codex-tg-public
description: "Compatibility alias for the public Telegram Codex cockpit skill. Use when older prompts, notes, or links mention chip-codex-tg-public; route to the canonical telegram-codex-cockpit contract while preserving the same public behavior, including /cas_* workflow and heartbeat/stall-recovery expectations."
---

# chip-codex-tg-public

Совместимый public alias для старого имени Telegram Codex cockpit skill.

## Когда использовать
Используй этот скилл, если:
- в старых заметках, ссылках или промптах уже фигурирует `chip-codex-tg-public`
- нужно сохранить совместимость без второго competing public skill
- нужно то же public поведение cockpit, что и в `telegram-codex-cockpit`

## Правило
Канонический public contract теперь живёт в:
- `/opt/clawd-workspace/skills/public/telegram-codex-cockpit/SKILL.md`

Если активирован этот alias:
1. Считать `telegram-codex-cockpit` source of truth для public workflow
2. Сохранять тот же `/cas_*` contract
3. Сохранять тот же heartbeat / stall-recovery contract
4. Не добавлять сюда отдельную competing логику

## Что именно должно сохраниться
- topic-per-workstream модель
- `Codex Control` как bind/status/control surface
- progress heartbeat примерно раз в 150 секунд на длинных run
- visible stall notice + automatic nudge при тишине
- немедленный relay финала, blocker и вопроса пользователя обратно в topic
- media ingress contract для voice notes и inbound files

## References
- [Canonical public skill](../telegram-codex-cockpit/SKILL.md)
- [Canonical public runbook](../telegram-codex-cockpit/references/runbook.md)
- [Canonical public quick tests](../telegram-codex-cockpit/references/quick-test-checklist.md)

## Quick Test Checklist
- [ ] Alias по-прежнему триггерится по старому имени `chip-codex-tg-public`
- [ ] Alias не содержит competing public contract
- [ ] Alias явно указывает на `telegram-codex-cockpit` как canonical source
- [ ] `/cas_*` workflow и heartbeat/stall-recovery expectations не потеряны
- [ ] Старые ссылки и заметки не ломаются концептуально

## Done Criteria
- [ ] Сохранена обратная совместимость по старому имени
- [ ] Убран drift между двумя public skills
- [ ] Alias не стал вторым центром правды
- [ ] Canonical public source указан явно

## Output contract
Вернуть то же, что и canonical public skill:
1. структура cockpit
2. как пользователь начинает работу
3. какие `/cas_*` команды нужны ежедневно
4. как устроен heartbeat / stall-recovery contract
5. какие конфиг-риски есть
6. что осталось operator-specific и не должно утекать в public
