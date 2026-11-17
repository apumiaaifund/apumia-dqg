[![CI Verification](https://github.com/apumiaaifund/apumia-dqg-demo/actions/workflows/ci.yml/badge.svg)](https://github.com/apumiaaifund/apumia-dqg-demo/actions/workflows/ci.yml)

<p align="center"><img src="assets/logo.svg" alt="logo" width="400"></p>

![PROVEN](https://img.shields.io/badge/PROVEN-52%20passed-brightgreen)

# Apumia DQG

**Data Quality Gate для SME-кредитования. Регулятор проверяет хеш — и видит, что данные не нарисованы.**

---

## За 30 секунд

**Что это:** Слой до скоринга — 29 аксиом с IFRS-ссылками (8 CRITICAL), Compliance Evidence Pack с детерминированным audit_hash (SHA-256).

**Кому:** Head of Risk / CISO в банке или embedded lending финтехе.

**Почему сейчас:** MAS Guidelines (7 октября 2027) требуют независимой проверки AI-систем. Self-attestation не считается. DQG даёт артефакт, который регулятор проверяет без доступа к системе банка.

**Что доказано:** 52 passed. Реальный output: verdict REJECT, AXIOM_BALANCE_EQUATION, IFRS IAS 1.54. verified: true. apumia prove → PROVEN.

**Чего не доказано (честно):** 0 клиентов, пилот не начат. EU AI Act-ready, но не сертифицирован.

---

## Оффер

Пилот €3–5K / 2 месяца. Критерий: экономия за 12 мес ≥ цены лицензии. Если меньше — клиент не платит.

**Следующий шаг:** 20-минутный звонок — покажу apumia prove вживую, без слайдов.

---

## GitHub

- **Private code:** apumiaaifund/apumia-dqg
- **Public demo:** apumiaaifund/apumia-dqg-demo

## License

MIT


---

### 🚀 Что мы можем реализовать для партнёров на основе этого решения (Ниши и сценарии)

- **Enterprise RAG и обучение LLM:** санитарный фильтр данных на входе (защита от «отравления» датасетов и битых записей).
- **Финтех и телеком:** потоковая валидация транзакций и телеметрии перед загрузкой в DWH и аналитические витрины.

> **Формат сотрудничества:** запуск пилотного стенда (PoC) за 2–4 недели, лицензирование модуля (On-Premise) или кастомная интеграция под стек заказчика.  
> 📬 **Запросить демонстрацию и расчёт пилота:** [apumiaaifund@gmail.com](mailto:apumiaaifund@gmail.com)

---

### 🛡️ Верификация качества и безопасности (Apumia DevSecOps Gate)

> **Статус:** `VERIFIED & PROVEN` • **Дата аудита:** `16.11.2026`  
> **Контроль архитектуры (`Apumia Blueprint`):** `CLEAN` (`0` циклических зависимостей, контроль сложности McCabe)  
> **Анализ безопасности (`Bandit / Zero-Trust`):** `0` критических уязвимостей  
> **Протокол достоверности (`Apumia Hub`):** `_synthetic: false` | `preservation: 100.0%` | `verified: true`
