# Atomic Flow

**Build reliable workflows. Make failures predictable.**

Atomic Flow is an open-source project focused on reliable execution, explicit failure handling, and predictable recovery in application workflows.
Its goal is quite simple: **help developers build systems where failures do not silently leave application state inconsistent.**
Atomic Flow aims to provide a consistent set of concepts, behavioral specifications, and testing principles across multiple programming languages.

> **Project status:** Early development. The specifications and public APIs are evolving. No stable release is available **yet**.

## Why Atomic Flow?

Real-world operations rarely happen in isolation.
A workflow might update a database, reserve inventory, process a payment, and notify an external service. What happens when one of those operations fails halfway through?
Traditional database transactions cannot necessarily cover every component or external system involved.
Atomic Flow wants to provide an application-level approach to managing these situations through explicit execution boundaries, failure semantics, recovery mechanisms, and verifiable consistency requirements.
The objective is **not** to eliminate failures. It is to make their consequences understandable, manageable, and testable.

## Design principles

- **Consistency first :** Define the invariants that must remain true, including when operations fail.
- **Explicit failure semantics :** Make failures, partial execution, and recovery outcomes visible.
- **Predictable recovery :** Provide well-defined mechanisms for handling interrupted or failed workflows.
- **Testable by design :** Validate failure scenarios, not just successful execution.
- **Language-independent foundations :** Maintain shared concepts and behavioral expectations across implementations.
- **Honest guarantees :** Document the limits of each implementation rather than claiming universal transaction atomicity.

## Project structure

Atomic Flow is organized into independent language implementations, guided by shared specifications.

| Repository | Purpose | Status |
|---|---|---|
| [atomic-flow](https://github.com/atomic-flow-dev/atomic-flow) | Project specifications, architecture, and coordination | Early development |
| [atomic-flow-ts](https://github.com/atomic-flow-dev/atomic-flow-ts) | TypeScript / JavaScript implementation | Early development |

Additional language implementations may be introduced as the project matures.

## Core components

### Atomic Flow Core

The runtime component responsible for executing workflows according to explicit failure-handling and recovery rules.
The exact execution model, API, and supported guarantees are being defined as part of the initial implementation.

### Atomic Flow Failure Lab

A testing-focused component intended to help developers validate how workflows behave under failure conditions.
Its planned capabilities include controlled failure injection, recovery testing, and verification of application-level consistency invariants.
The Failure Lab is designed for testing and validation, **not** as a required production runtime dependency.

## Specifications and compatibility

This repository is intended to become the central reference for Atomic Flow's language-independent behavior.
Implementations may use different internal architectures and language-specific APIs, but should clearly document which common guarantees they support.
Future shared specifications and conformance tests will help prevent unexpected behavioral differences between implementations.

## Non-goals

Atomic Flow is not intended to:

- Replace native database transactions.
- Promise that arbitrary external side effects can always be rolled back.
- Guarantee global ACID transactions across unrelated systems.
- Hide unrecoverable failures or inconsistent states from developers.

## Roadmap

The initial development priorities are:

1. Establish the shared vocabulary and execution model.
2. Define the initial TypeScript Core contracts.
3. Implement and validate fundamental execution and failure scenarios.
4. Develop the Failure Lab and its first test scenarios.
5. Document the supported guarantees and limitations.
6. Prepare an initial public alpha release.
7. Evaluate additional language implementations.

## Security

Please do not publish potentially exploitable security vulnerabilities in public issues.
**A dedicated vulnerability reporting process will be documented before the first public release.**

## License

Atomic Flow is licensed under the **Apache License, Version 2.0**.

See the [LICENSE](LICENSE) file for the full license terms.

> **Contributions are temporarily restricted.**
>
> Atomic Flow is currently in its early architectural development phase. External contributions are not yet accepted while the foundational contracts and APIs are being established.
>
> Contributions will be welcomed as the project matures. Thank you for your interest!
