---
name: chip-codex-tg-public
description: "Compatibility alias for the public Telegram Codex cockpit skill. Use when older prompts, notes, or links mention chip-codex-tg-public; preserve the same public contract as telegram-codex-cockpit without creating a second competing source of truth."
---

# chip-codex-tg-public

Совместимый public alias для старого имени Telegram Codex cockpit skill.

## Когда использовать
Используй этот скилл, если:
- в старых заметках, ссылках или промптах уже фигурирует `chip-codex-tg-public`
- нужно сохранить совместимость без второго competing public skill
- нужен тот же public contract, что и у `telegram-codex-cockpit`

## Канонический источник
Source of truth для public workflow:
- `telegram-codex-cockpit`

Если активирован этот alias:
1. Считать `telegram-codex-cockpit` каноническим public contract
2. Сохранять тот же `/cas_*` workflow
3. Сохранять тот же heartbeat / stall-recovery contract
4. Сохранять тот же media ingress contract
5. Не добавлять сюда отдельную competing логику

## Что обязательно должно сохраниться
- отдельный Telegram supergroup под Codex
- topics / forum workflow
- **один topic = один workstream**
- `Codex Control` как bind/status/control surface
- после `/cas_resume` можно писать обычным текстом
- `/cas_*` команды работают внутри topics
- inline-кнопки работают не только в DM, но и в topics
- progress heartbeat примерно раз в 150 секунд на длинных run
- если следующее окно тоже пустое, появляется visible stall notice и automatic nudge
- финал, blocker и вопрос к пользователю сразу relay-ятся обратно в topic
- voice notes доходят до Codex как transcript
- inbound files доходят до Codex как local path/context
- при правках конфига помнить, что массивы вроде `bindings` могут перезаписываться целиком

## Быстрый сценарий для пользователя
1. Зайти в `Codex Control`
2. Отправить `/cas_resume`
3. Выбрать existing thread или `New`
4. После bind писать уже обычным текстом
5. Для новой независимой задачи уходить в отдельный topic

## References
- [Публичный онбординг на русском](references/onboarding-ru.md)
- [Публичный runbook](references/runbook.md)
- [Quick test checklist](references/quick-test-checklist.md)
- [Manual review checklist](references/manual-review-checklist.md)
- [Public/private split notes](references/public-private-split.md)
- [Media ingress contract](references/media-ingress-contract.md)
- [Refactor topology note](references/refactor-topology-2026-04-09.md)

## Quick Test Checklist
- [ ] Alias по-прежнему триггерится по старому имени `chip-codex-tg-public`
- [ ] Alias не содержит competing public contract
- [ ] Alias явно указывает на `telegram-codex-cockpit` как canonical source
- [ ] Topic-per-workstream contract не потерян
- [ ] `/cas_*` workflow и heartbeat/stall-recovery expectations не потеряны
- [ ] Config footgun по массивам назван явно
- [ ] Старые ссылки и заметки не ломаются концептуально

## Done Criteria
- [ ] Сохранена обратная совместимость по старому имени
- [ ] Убран drift между двумя public skills
- [ ] Alias не стал вторым центром правды
- [ ] Canonical public source указан явно
- [ ] Public/private split не размыт

## Output contract
Вернуть то же, что и canonical public skill:
1. структура cockpit
2. как пользователь начинает работу
3. какие `/cas_*` команды нужны ежедневно
4. как устроен heartbeat / stall-recovery contract
5. какие конфиг-риски есть
6. что осталось operator-specific и не должно утекать в public
