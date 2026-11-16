# Gastrobot Core: Deterministic LLM Guardrail & Multi-Tenant Order Engine

[![Production Tested](https://img.shields.io/badge/Production_Orders-500%2B-emerald?style=flat-square)]()
[![Architecture](https://img.shields.io/badge/Architecture-Deterministic_FSM-amber?style=flat-square)]()
[![Multi-Tenant](https://img.shields.io/badge/Scale-Multi--Tenant_Ready-blue?style=flat-square)]()

**Gastrobot Core** is a production-grade conversational AI framework engineered to eliminate LLM hallucinations, pricing corruption, and context leakage in high-stakes commercial environments. 

Originally battle-tested in the hospitality and restaurant sector with **over 500 real customer orders processed**, this modular architecture separates natural language understanding from deterministic business logic, allowing small and medium businesses (SMBs) to deploy reliable AI agents across any industry vertical.

---

## 🎯 The Problem Solved

Standard Large Language Models (LLMs) fail in transactional retail and hospitality environments due to three critical vulnerabilities:
1. **Hallucinated Inventory & Pricing:** Models inventing menu items, miscalculating split/half-and-half items, or corrupting totals.
2. **State Drift:** Losing track of cart mutations when users edit quantities mid-conversation.
3. **Logistical Ambiguity:** Accepting unstructured text addresses that break last-mile delivery routing.

**The Golden Rule of Gastrobot:** *The LLM handles human conversation; deterministic Python state machines handle the cart, pricing, idempotency, and logistics.*

---

## 🏗️ Core Architecture

```text
┌───────────────────┐     ┌──────────────────────────────────────────┐
│  WhatsApp / Web   │────▶│           Gastrobot Engine (FSM)         │
│  Customer Input   │     │  GREETING → BROWSING → CART → CONFIRMING │
└───────────────────┘     └────────────────────┬─────────────────────┘
                                               │
                    ┌──────────────────────────┼──────────────────────────┐
                    ▼                          ▼                          ▼
      ┌──────────────────────────┐ ┌───────────────────────┐ ┌─────────────────────────┐
      │   Deterministic Cart     │ │  Multi-Model Router   │ │  Logistical Guardrails  │
      │ • Python Source-of-Truth │ │ • OpenAI / Anthropic  │ │ • Mandatory GPS Parsing │
      │ • Idempotency Guards     │ │ • Keyword Fallback    │ │ • Per-Tenant Timezones  │
      │ • Fuzzy/Prefix Matching  │ │ • Token/Cost Cap      │ │ • Live Fleet Telemetry  │
      └──────────────────────────┘ └───────────────────────┘ └─────────────────────────┘


Key Technical Features
Finite State Machine (FSM) & Hard-Blocked Cart Mutations: The LLM is strictly blocked from directly mutating prices or totals. All cart additions, removals, and half-and-half combinations are validated through deterministic Python dataclasses.

4-Layer Order Idempotency: Prevents duplicate order submissions, validates store operating hours per tenant timezone, and ensures cart integrity prior to checkout.

Mandatory Geolocation Enforcement: Regex and coordinate parsers automatically extract and validate GPS pins from WhatsApp and web inputs, rejecting unroutable text addresses.

Resilient Multi-Model & Degraded Fallback: Built-in cost tracking (per-tenant daily caps) and an automatic keyword-based fallback engine that keeps order intake alive even during upstream LLM API outages.

Multi-Tenant Command Center: Real-time Next.js 16 operational dashboard featuring Kanban order management, live driver fleet telemetry, human-in-the-loop takeover, and FSM funnel analytics.

📊 Production Traction & Validation
500+ Real-World Orders: Validated in live commercial operations with real customers, complex order edits, split items, and payment verification.

33+ Automated Pytest Suites & E2E Smoke Checks: Continuous regression testing covering edge cases, adversarial prompts, and cart state transitions.

Horizontal Scalability: Currently expanding from single-store validation into a multi-tenant SaaS architecture with real-time fleet tracking (Gastrobot-Fleet).

🔒 Repository Notice
This public repository hosts the architectural documentation, core system specifications, and public interfaces of the Gastrobot framework. The proprietary production engine, tenant configurations, and adversarial guardrail suites are maintained in a private repository to protect commercial deployments and API security while preparing for open-source modular release.


Con más de **500 pedidos reales procesados**, ya dejaste atrás la etapa de "proyecto en pruebas" y tienes **tracción comprobada en producción**. Para los evaluadores de programas de créditos de IA (GitHub, OpenAI, Anthropic, Meta), pasar de "tengo una idea" a "tengo un sistema determinista con +500 transacciones reales en producción y arquitectura multi-tenant lista para escalar" cambia completamente las reglas del juego.

Aquí tienes el `README.md` profesional (en inglés, listo para subir a tu repositorio público de GitHub como carta de presentación) y el texto actualizado para tu postulación:

---

### 1. Archivo `README.md` para tu Repositorio Público en GitHub

Crea un repositorio público limpio (por ejemplo: `gastrobot-deterministic-engine`) y pega este contenido en el `README.md`. **No expone tus prompts secretos ni credenciales**, pero demuestra una ingeniería de nivel empresarial y tracción real:

```markdown
# Gastrobot Core: Deterministic LLM Guardrail & Multi-Tenant Order Engine

[![Production Tested](https://img.shields.io/badge/Production_Orders-500%2B-emerald?style=flat-square)]()
[![Architecture](https://img.shields.io/badge/Architecture-Deterministic_FSM-amber?style=flat-square)]()
[![Multi-Tenant](https://img.shields.io/badge/Scale-Multi--Tenant_Ready-blue?style=flat-square)]()

**Gastrobot Core** is a production-grade conversational AI framework engineered to eliminate LLM hallucinations, pricing corruption, and context leakage in high-stakes commercial environments. 

Originally battle-tested in the hospitality and restaurant sector with **over 500 real customer orders processed**, this modular architecture separates natural language understanding from deterministic business logic, allowing small and medium businesses (SMBs) to deploy reliable AI agents across any industry vertical.

---

## 🎯 The Problem Solved

Standard Large Language Models (LLMs) fail in transactional retail and hospitality environments due to three critical vulnerabilities:
1. **Hallucinated Inventory & Pricing:** Models inventing menu items, miscalculating split/half-and-half items, or corrupting totals.
2. **State Drift:** Losing track of cart mutations when users edit quantities mid-conversation.
3. **Logistical Ambiguity:** Accepting unstructured text addresses that break last-mile delivery routing.

**The Golden Rule of Gastrobot:** *The LLM handles human conversation; deterministic Python state machines handle the cart, pricing, idempotency, and logistics.*

---

## 🏗️ Core Architecture

```text
┌───────────────────┐     ┌──────────────────────────────────────────┐
│  WhatsApp / Web   │────▶│           Gastrobot Engine (FSM)         │
│  Customer Input   │     │  GREETING → BROWSING → CART → CONFIRMING │
└───────────────────┘     └────────────────────┬─────────────────────┘
                                               │
                    ┌──────────────────────────┼──────────────────────────┐
                    ▼                          ▼                          ▼
      ┌──────────────────────────┐ ┌───────────────────────┐ ┌─────────────────────────┐
      │   Deterministic Cart     │ │  Multi-Model Router   │ │  Logistical Guardrails  │
      │ • Python Source-of-Truth │ │ • OpenAI / Anthropic  │ │ • Mandatory GPS Parsing │
      │ • Idempotency Guards     │ │ • Keyword Fallback    │ │ • Per-Tenant Timezones  │
      │ • Fuzzy/Prefix Matching  │ │ • Token/Cost Cap      │ │ • Live Fleet Telemetry  │
      └──────────────────────────┘ └───────────────────────┘ └─────────────────────────┘

```

### Key Technical Features

* **Finite State Machine (FSM) & Hard-Blocked Cart Mutations:** The LLM is strictly blocked from directly mutating prices or totals. All cart additions, removals, and half-and-half combinations are validated through deterministic Python dataclasses.
* **4-Layer Order Idempotency:** Prevents duplicate order submissions, validates store operating hours per tenant timezone, and ensures cart integrity prior to checkout.
* **Mandatory Geolocation Enforcement:** Regex and coordinate parsers automatically extract and validate GPS pins from WhatsApp and web inputs, rejecting unroutable text addresses.
* **Resilient Multi-Model & Degraded Fallback:** Built-in cost tracking (per-tenant daily caps) and an automatic keyword-based fallback engine that keeps order intake alive even during upstream LLM API outages.
* **Multi-Tenant Command Center:** Real-time Next.js 16 operational dashboard featuring Kanban order management, live driver fleet telemetry, human-in-the-loop takeover, and FSM funnel analytics.

---

## 📊 Production Traction & Validation

* **500+ Real-World Orders:** Validated in live commercial operations with real customers, complex order edits, split items, and payment verification.
* **33+ Automated Pytest Suites & E2E Smoke Checks:** Continuous regression testing covering edge cases, adversarial prompts, and cart state transitions.
* **Horizontal Scalability:** Currently expanding from single-store validation into a multi-tenant SaaS architecture with real-time fleet tracking (`Gastrobot-Fleet`).

---

## 🔒 Repository Notice

*This public repository hosts the architectural documentation, core system specifications, and public interfaces of the Gastrobot framework. The proprietary production engine, tenant configurations, and adversarial guardrail suites are maintained in a private repository to protect commercial deployments and API security while preparing for open-source modular release.*

```

---

### 2. Respuestas Actualizadas para el Formulario de Créditos (Con los +500 pedidos)

Si todavía no enviaste el formulario (o si vas a aplicar a otro programa de OpenAI / Anthropic / Meta), actualiza estos dos campos con tus cifras reales:

* **En "Tell us about the project's reach and impact":**
> **Proven Production Traction (500+ Real Orders):**
> Unlike theoretical chatbot wrappers, this framework has already been battle-tested in live commercial operations, successfully processing **over 500 real customer orders** in the hospitality sector. 
>
> **The Gap in the Ecosystem:**
> Small and medium businesses (SMBs) struggle to adopt generative AI because standard LLMs hallucinate prices, corrupt cart totals, and fail at strict operational boundaries. This project solves that gap through a deterministic Finite State Machine (FSM) architecture where the LLM manages natural conversation while strict Python code governs cart state, idempotency, per-tenant timezones, and mandatory GPS logistics—backed by 33+ automated regression test suites.
>
> **Next Phase (Multi-Tenant & Fleet Scale):**
> Having validated the core engine with 500+ live transactions, I am now generalizing this framework into a multi-tenant platform capable of serving hundreds of SMBs across any retail/service vertical, alongside a real-time delivery fleet telemetry system.

* **En "Other info":**
> This project is already live and processing real commercial volume (500+ completed orders). The public repository on this account provides the architectural overview and system specifications, while the production codebase remains private to protect active business operations and API keys while I finalize the multi-tenant open-source template. As a solo bootstrapped developer, these 6 months of AI infrastructure credits will directly fund the multi-model benchmarking (Anthropic, OpenAI, Meta) and stress-testing required to scale from our initial production deployments to a generalized industry standard.

---

