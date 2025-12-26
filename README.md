# MetaMemoryWorks — Architecture Overview

MetaMemoryWorks is a file-based architecture and method for building LLM-assisted systems that maintain **persistent, user-controlled state** across extended work, analysis, and decision processes. In practical terms, it enables AI-assisted workflows to remain coherent over time instead of resetting with each session.

The architecture addresses a central limitation of current AI assistants: the loss of structured state, decisions, and context between interactions.

This repository provides a **system-level overview** of the method and serves as a stable entry point to the individual MetaMemoryWorks modules.


## The Problem

Most LLM-based assistants rely on:
- transient chat context
- prompt engineering
- retrieval-based augmentation (RAG)

These approaches do not provide:
- persistent functional memory
- explicit state transitions
- auditability over time
- user ownership of long-term state

As a result, complex workflows fragment, decisions get lost, and assistants cannot reliably support extended analytical or operational processes.

---

## Core Idea

MetaMemoryWorks treats **memory as an external system property**, not as an implicit model feature.

The architecture is based on:
- explicit files as state carriers
- append-only logs instead of mutable context
- separation of model, rules, and state
- model-agnostic persistence

The LLM becomes a **stateless reasoning engine** operating over durable, inspectable artifacts.

This enables long-running analytical, planning, and decision-making workflows that remain coherent across sessions and model changes.

---

## Architectural Principles

- **File-based**  
  All state is stored in human-readable files under user control.

- **Append-only**  
  State evolves through explicit additions, preserving history and decisions.

- **Model-independent**  
  The method does not rely on a specific LLM or provider.

- **Explicit over implicit**  
  Rules, roles, memory, and intent are externalized instead of embedded in prompts.

- **Reconstructable state**  
  System state can be rebuilt deterministically from files after restarts or model changes.

---

## Core Architecture

The abstract architecture and method are defined in the following repository:

- **MetaMemoryArchitecture**  
  https://github.com/johannes42x/MetaMemoryArchitecture  
  (method specification, architectural rules, state model)

This repository describes the method independently of any concrete domain or module.

---

## System Structure (Abstract)

At a high level, MetaMemoryWorks separates:

- **State**  
  Persistent files representing decisions, memory, and progress

- **Rules & Method**  
  How state is read, written, and evolved

- **LLM**  
  A replaceable reasoning component without internal memory assumptions

- **Modules**  
  Domain-specific instantiations of the same method

---

## Modules (Selected)

The architecture is operationalized in several modular systems, including:

- **scanOS** — external information capture & structured ingestion  
  https://github.com/johannes42x/scanOS

- **noteOS** — persistent knowledge and note management  
  https://github.com/johannes42x/noteOS

- **trainingOS** — structured training and fitness logging  
  https://github.com/johannes42x/trainingOS

- **nutritionOS** — persistent nutrition, cooking, and intake management based on long-term state
  https://github.com/johannes42x/nutritionOS

Each module applies the same underlying architectural method to a specific domain.

Additional modules following the same pattern exist and are released on a staggered basis.

---

## Usage Status

- Actively used in daily analytical and decision-making workflows
- Developed iteratively through practical application
- Ongoing work; architecture evolves through real-world constraints

The architecture is evaluated through sustained real-world use rather than isolated benchmarks.

---

## Licensing

- **Private / personal use:** free
- **Commercial use:** requires a license

See individual module repositories for specific licensing terms.

For licensing inquiries, please contact:  
- licensing@metamemoryworks.com
- lizenz@metamemoryworks.de

---

## Scope of This Repository

This repository intentionally:
- focuses on architectural explanation
- avoids implementation details
- serves as a stable reference point for the system as a whole

For concrete implementations, see the linked module repositories.

---

## Author

Johannes Glaser  
Architecture & Method Development  
MetaMemoryWorks (since 2025)

---

## Project Links & Contact

- Project website (EN): https://metamemoryworks.com  
- Project website (DE): https://metamemoryworks.de  

For questions regarding the architecture or method  
- contact@metamemoryworks.com  
- kontakt@metamemoryworks.de
