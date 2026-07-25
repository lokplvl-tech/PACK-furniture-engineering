# PACK-furniture-engineering

Source-of-truth для домена: инженерная методология проектирования и производства корпусной мебели на базе САПР «Базис-Салон».
Структура: SPF/pack-template. Upstream: FPF, SPF.

При работе с этим Pack: читать 00-pack-manifest.md для навигации.

Пока `name_status: provisional` в манифесте: каждое новое различение в `01-domain-contract/01B-distinctions.md` получает заголовок `### {{PACK_ID}}.D.NNN: <Название>` (плейсхолдер `{{PACK_ID}}`, не реальный код Pack'а), а путь `01-domain-contract/01B-distinctions.md` добавляется в `provisional_distinction_files` в `.pfad-decision.md` (если его там ещё нет - не дублировать). Если в `01B-distinctions.md` набралось 3+ различений - предложить пользователю финализацию имени (см. `pack-new/SKILL.md` Шаг 2 «Финализация имени» в FMT-exocortex-template).
