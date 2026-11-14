# Apumia DQG — Public Demo

<p align="center"><img src="assets/logo.svg" alt="logo" width="400"></p>


## За 30 секунд

**Что это:** Data Quality Gate: 29 аксиом (8 CRITICAL) с IFRS-ссылками. Compliance Evidence Pack с детерминированным audit_hash. Ставится до скоринга.

**Кому:** Embedded lending, SME credit fintech, Tier-1 банки — доказать регулятору качество входных данных.

**Что доказано:** 52 passed. Реальный output движка: verdict REJECT, AXIOM_BALANCE_EQUATION, audit_hash sha256.

**Чего не доказано (честно):** 0 клиентов. Пилот €3–5K / 2 мес — не начат. EU AI Act-ready, но не сертифицирован.

---



> **Данные не нарисованы.**
>
> DQG: отчётность + первичка. Проверяем не только, что сходится — но и что не нарисовано.

**Data Quality Gate for SME credit reporting.** EU AI Act Art. 12/14/86-ready. Stateless. p95 < 50ms.

## Что делает

- **29 аксиом** (8 CRITICAL, 19 WARNING, 2 INFO) с IFRS-ссылками — balance, hierarchies, turnover, earnings quality
- **Compliance Evidence Pack** — `/v1/evidence/{request_id}` JSON + printable HTML с детерминированным `audit_hash`
- **Verify-hash** — ре-верификация любого исторического вердикта без хранения PII
- **Batch** — до 500 отчётов за вызов
- **Ingest** — `.xlsx`, `.json`, **`.pdf`** (pdfplumber) для быстрых демо
- **Threshold profiles** — `X-DQG-Profile: strict / balanced / lenient`

## Проблема

EU AI Act Art. 12 (logging) + Art. 14 (oversight) + Art. 86 (right to explanation) требуют от банков документировать качество входных данных для кредитных решений. Moody's / Abrigo / nCino — тяжело и дорого. DQG — слой **до** скоринга, 3-строчная интеграция.

## Кому

| Сегмент | Боль |
|---|---|
| Embedded lending (Froda, Flowpay, Teylor) | Нужен compliance-шлюз, а не Moody's |
| SME credit fintech | Документировать качество данных для регулятора |
| Tier-1 банк (после SOC2) | Art. 12/14/86 evidence pack |

## Что проверено

- `verify.py` — **15/15 offline checks** (verdict logic, determinism, hash recompute)
- `pytest` — **44 passed**
- `python tests/golden/evaluate.py` — **10/10 = 1.000** verdict accuracy
- Deterministic `audit_hash` — SHA256(canonical(input) + flag_codes + thresholds + engine_version + verdict)
- Ре-верификация через `POST /v1/verify-hash` — без хранения PII

## Цена

| Уровень | Цена | Что |
|---|---|---|
| Free | 0 | 10 rps, 100 отчётов/мес |
| Standard | €500/мес | 100 rps, 10k отчётов, audit on |
| Enterprise | €1500/мес | 1000 rps, custom thresholds + profiles, SLA |
| Pilot | €3-5K / 2 мес | Интеграция + golden dataset под ваш домен |

Контакт: apumiaaifund@gmail.com


## Data integrity

**No synthetic data in production.** External sources are documented in `sources.yaml` (Private repo) with official URLs, real verification dates, and status. No fabricated dates. Demo artifacts are clearly marked as examples.

**Никакой синтетики в продакшене.** Внешние источники — в `sources.yaml` (Private репо) с официальными URL, реальными датами, статусом. Ни одной придуманной даты. Demo — помечены как примеры.


## Лицензия

Proprietary. См. LICENSE. Исходный код — по запросу.

## Examples

- `demo/validate_PASS.json` — synthetic input, real PASS output
- `demo/validate_REJECT.json` — broken balance, real REJECT + flags
- `demo/journal_REJECT.json` — journal with empty account, real REJECT

All inputs are marked `_synthetic: true`. Outputs — real engine responses from `/v1/validate` and `/v1/journal/validate`.
