nails on Deck
A multi‑layer, multi‑language architecture for non‑linear state management using the STS v2 token engine.  
This repository contains three fully isolated layers:

- Core Engine (Rust) — canonical STS v2 implementation  
- Interface Layer (Python / TypeScript) — adapters, mobile logic, and client wrappers  
- Deck DSL (YAML/TOML) — declarative stance and token definitions  
- STS v1 (Legacy) — preserved for historical and comparative reference

Snails on Deck provides a stable, deterministic foundation for environments where sequence is non‑linear, discontinuous, or externally disrupted.

---

1. Architecture Overview
Snails on Deck is built around the STS v2 model:

- $ — State Anchor  
  The stable, immutable snapshot of system state.

- T — Token  
  A discrete unit of transition. Tokens represent events, updates, or temporal shifts.

- S — System / Sequence / Security  
  The transition logic that applies tokens to state.

This forms a deterministic Turing‑style router:

`
δ(state, token) → new_state
`

The engine is intentionally minimal, portable, and non‑linear‑safe.

---

2. Repository Structure

`
snails-on-deck/
│
├── core-engine-rust/          # STS v2 canonical engine
├── interface-python/          # Python adapters + STS-Mobile v1.2
├── interface-typescript/      # Optional TS interface for web/mobile
├── deck-dsl/                  # Declarative stance + token definitions
├── sts-v1/                    # Legacy survival architecture (isolated)
└── docs/                      # Architecture, diagrams, specs
`

Each layer is fully isolated to prevent cross‑contamination of logic or assumptions.

---

3. Core Engine (Rust)
The Rust engine is the authoritative implementation of STS v2.

Responsibilities:
- Define $ (state)
- Define T (token)
- Define reducers (transition functions)
- Route tokens deterministically
- Preserve state integrity across non‑linear sequences

Key Modules:
- state.rs  
- token.rs  
- reducer.rs  
- router.rs  

---

4. Interface Layer (Python / TypeScript)
These layers wrap the Rust engine and provide:

- Mobile adapters  
- Storage adapters  
- API‑friendly interfaces  
- Developer‑friendly tooling  

They do not implement STS logic — they only orchestrate it.

---

5. Deck DSL
The Deck is a declarative layer defining:

- Stances  
- Token schemas  
- Reducer configurations  
- System modes  

This allows behavior to be modified without touching engine code.

Example:
`
stances/
  operator.yaml
  mobile.yaml
tokens/
  init.yaml
  update.yaml
reducers/
  default.yaml
`

---

6. STS v1 (Legacy)
Preserved for reference and comparison.  
Contains:

- Drift‑prevention logic  
- Continuity patches  
- Survival‑mode sequence handling  

STS v1 is not used by STS v2 and remains fully isolated.

---

7. Goals
Snails on Deck aims to:

- Provide a deterministic state engine for non‑linear environments  
- Maintain strict separation between versions and layers  
- Support mobile, distributed, and unstable contexts  
- Offer a minimal, token‑based temporal model  
- Enable declarative configuration through the Deck DSL  

---

8. Status
Active development.  
Core engine scaffolding complete.  
Interface and DSL layers in progress.

---

9. License
MIT (modifiable as needed).

---
