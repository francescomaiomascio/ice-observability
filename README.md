# ICE Observability

[![ICE Architecture](https://img.shields.io/badge/ICE-Architecture%20%26%20RFCs-8FB9FF?style=flat)](https://francescomaiomascio.github.io/ice-docs/)
[![Status](https://img.shields.io/badge/status-active%20research-6B7280?style=flat)](#)
[![GitHub Sponsors](https://img.shields.io/badge/support-GitHub%20Sponsors-7A7CFF?style=flat)](https://github.com/sponsors/francescomaiomascio)
[![Buy Me a Coffee](https://img.shields.io/badge/support-Buy%20Me%20a%20Coffee-FFDD00?style=flat&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/francescomaiomascio)

---

## What this repository is

**ICE Observability** is the **system-level observability layer** of the ICE ecosystem.

It provides a **sovereign, runtime-agnostic observation model** for:

- execution events  
- lifecycle transitions  
- audit trails  
- security-relevant actions  

This repository defines **how ICE systems are observed**,  
not how they execute.

Observability is treated as a **first-class architectural concern**,  
not as a logging utility.

---

## What ICE Observability is (and is not)

ICE Observability is **not**:

- a logging framework  
- a metrics-only system  
- a UI or dashboard  
- a debugging tool  

ICE Observability **is**:

- a canonical event model for observation  
- a routing and fan-out layer for observation events  
- a filesystem-backed, audit-safe persistence model  
- a bridge between runtime execution and post-hoc analysis  

The core rule is strict:

> **Execution does not observe itself.  
> Observability observes execution.**

---

## Architectural role in ICE

ICE Observability sits **outside** of the Runtime.

It does **not**:

- influence execution  
- mutate runtime state  
- gate capabilities  
- introduce side effects  

Instead, it consumes **emitted events** and produces:

- structured logs  
- audit records  
- traceable execution histories  

This separation is intentional and non-negotiable.

---

## Design principles

### Runtime-agnostic

ICE Observability can observe:

- ICE Runtime  
- ICE Engine  
- ICE Studio  
- plugins  
- protocols  
- providers  

without requiring them to depend on it.

---

### Event-first observation

All observability data is expressed as **immutable events**.

- no implicit state  
- no hidden mutation  
- no best-effort logging  

Observation events are append-only and serializable.

---

### Filesystem as an audit surface

The filesystem layout is **part of the specification**.

It reflects **causal domains**, not implementation details.

This allows:

- offline analysis  
- reproducible investigations  
- long-term traceability  

---

### Extensible by design

ICE Observability supports multiple outputs via:

- sinks (local consumption)  
- transports (external emission)  

Filesystem, IPC, HTTP, and future transports are treated uniformly.

---

## Repository scope

This repository contains:

- the observation event model  
- routing and fan-out logic  
- filesystem persistence rules  
- minimal debug/test sinks  

It does **not** contain:

- frontend log viewers  
- dashboards  
- runtime execution code  

---

## Documentation

Architectural documentation and RFCs are available at:

https://francescomaiomascio.github.io/ice-docs/

Refer in particular to:

- Observability model  
- Audit and lifecycle semantics  
- Runtime vs Observability boundaries  

---

## Status

ICE Observability is under **active research and development**.

APIs and structures may evolve as invariants are refined,
but architectural boundaries are considered stable.

---

## Support

If you are interested in **system-level observability**,  
runtime accountability, and long-term architectural research:

- GitHub Sponsors  
  https://github.com/sponsors/francescomaiomascio  

- Buy Me a Coffee  
  https://buymeacoffee.com/francescomaiomascio  

Support goes directly into sustained engineering work.
