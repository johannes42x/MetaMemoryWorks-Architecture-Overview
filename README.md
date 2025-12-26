# MetaMemoryWorks — Architecture Overview

**A file-based architecture for building LLM-assisted systems with explicit, persistent memory.**

MetaMemoryWorks is a file-based architecture and method for building
LLM-assisted systems that maintain **persistent, user-controlled state ("memory")**
across extended work, analysis, and decision processes.

In practical terms, it enables AI-assisted workflows to remain coherent
over time instead of resetting with each session, by preserving relevant
information and working instructions so an assistant can resume in a
predefined role rather than starting from scratch.

The architecture addresses a central limitation of current AI assistants:
the loss of structured state, decisions, and context between interactions.

This repository provides a **system-level overview** of the method and
serves as a stable entry point to the individual MetaMemoryWorks modules.

---

## The Problem

Most LLM-based assistants are built around mechanisms such as
transient chat context, prompt engineering, or retrieval-based augmentation (including RAG).

While effective for short interactions, these approaches do not provide
durable system-level properties such as persistent memory, explicit state
transitions, or long-term auditability under user control.

As a consequence, complex workflows fragment over time.
Decisions are lost between sessions, prior reasoning cannot be reliably
reconstructed, and assistants struggle to support extended analytical
or operational processes.

---

## Core Idea

MetaMemoryWorks treats memory as an explicit system property that is
represented directly within the assistant’s working environment,
rather than as an implicit or opaque feature of a language model.

Relevant state — including information, instructions, roles, routing,
and other contextual constraints — is stored in human-readable files
that the LLM can access as part of its normal working context, without
requiring retrieval systems, embeddings, or external tooling.

State is made explicit and inspectable.
Different kinds of state follow different structural conventions,
but are treated uniformly as durable artifacts that shape the
assistant’s behavior over time.

Within this setup, the LLM does not carry long-term state internally.
Instead, it reconstructs its working state from the available files
and operates based on the instructions and context they provide.

This approach makes it possible to support long-running analytical,
planning, and decision-making workflows that remain coherent across
sessions, restarts, and even model changes.

At the same time, it keeps control close to the user.
Assistants and their memory can be configured, adjusted, corrected, or
discarded directly by working with the underlying files.
Users manage their own data, decide what is kept or removed, and can
adapt instructions and context as their needs change — without requiring
programming skills or specialized tooling.

The architecture is shaped and refined through sustained real-world use,
rather than through isolated benchmarks or synthetic demonstrations.

---

## System Structure (Abstract)

At a high level, MetaMemoryWorks separates the system into four
conceptual components:

- **State**  
  Persistent files that represent accumulated information, decisions,
  and progress over time.

- **Rules and Method**  
  The conventions that govern how state is interpreted, updated,
  and evolved.

- **LLM**  
  A replaceable reasoning component that operates on the available
  state without relying on hidden internal memory.

- **Modules**  
  Domain-specific applications that instantiate the same method
  for different problem areas.

---

## Architectural Principles

MetaMemoryWorks follows a small set of architectural principles that
govern how state, instructions, and reasoning are represented and evolved.

All relevant state is stored in human-readable files under user control,
making memory inspectable, portable, and independent of proprietary
storage mechanisms.

State changes are expressed explicitly.
In many cases this takes the form of append-only logs, but the core
principle is that state evolution remains visible, traceable, and
correctable over time.

The architecture is model-independent.
It does not rely on a specific LLM, provider, or runtime environment, and
can be reconstructed across restarts or model changes from the available
artifacts.

Rules, roles, memory, and intent are treated explicitly rather than being
embedded implicitly in prompts or transient context.

As a result, system state can be rebuilt in a deterministic manner from
its files, allowing workflows to remain stable even when components
change.


---

## Core Architecture

The abstract architecture and underlying method are specified separately
in the following repository:

**MetaMemoryArchitecture**  
https://github.com/johannes42x/MetaMemoryArchitecture

That repository defines the architectural rules, state model, and method
independently of any concrete domain or application.

This repository focuses on explaining the architecture at a system level
and situating it within the broader MetaMemoryWorks ecosystem.

---

## Modules

The MetaMemoryWorks architecture is operationalized through a set of
modular systems that apply the same method to different domains.

Each module represents a concrete, working instantiation of the
architecture, using persistent state to support a specific kind of
long-running workflow.

Selected modules include:

- **scanOS** — structured ingestion of external information  
  https://github.com/johannes42x/scanOS

- **noteOS** — persistent knowledge and note management  
  https://github.com/johannes42x/noteOS

- **trainingOS** — long-term training and fitness state  
  https://github.com/johannes42x/trainingOS

- **nutritionOS** — persistent nutrition and cooking workflows  
  https://github.com/johannes42x/nutritionOS

All modules follow the same architectural principles.
They differ only in domain focus, structure, and conventions.

Additional modules based on the same method exist and are released
incrementally.

---

## Licensing

MetaMemoryWorks is available under different terms depending on usage
context:

- **Private / personal use**  
  Free of charge.

- **Commercial or organizational use**  
  Requires a license.

Specific licensing terms are defined in the individual module
repositories.

For licensing inquiries:
- licensing@metamemoryworks.com  
- lizenz@metamemoryworks.de


---

## Scope of This Repository

This repository is intentionally limited in scope.
It focuses on explaining the MetaMemoryWorks architecture at a system
level and serves as a stable reference point for the overall method.

Concrete implementations, domain-specific structures, and practical
workflows are documented in the individual module repositories linked
above.


## Author

Johannes Glaser  
Architecture and Method Development  
MetaMemoryWorks (since 2025)

---

## Project Links and Contact

Project websites:
- https://metamemoryworks.com  
- https://metamemoryworks.de  

For questions regarding the architecture or method:
- contact@metamemoryworks.com  
- kontakt@metamemoryworks.de
