# Vakthund v0.1 Software Requirements Specification

Vakthund is a Bitcoin full node. This document specifies Vakthund v0.1. It follows the Software Requirements Specification
(SRS) outline of ISO/IEC/IEEE 29148:2018, one file per section.

| Section                        | File                                                                             |
|--------------------------------|----------------------------------------------------------------------------------|
| 1 Introduction                 | [1-introduction.md](1-introduction.md)                                           |
| 2 References                   | [2-references.md](2-references.md)                                               |
| 3 Requirements                 | [3-requirements/README.md](3-requirements/README.md)                             |
| 3.1 External interfaces        | [3.1-external-interfaces.md](3-requirements/3.1-external-interfaces.md)          |
| 3.2.1 Functions: net           | [3.2.1-net.md](3-requirements/3.2.1-net.md)                                      |
| 3.2.2 Functions: chain         | [3.2.2-chain.md](3-requirements/3.2.2-chain.md)                                  |
| 3.2.3 Functions: block-sync    | [3.2.3-block-sync.md](3-requirements/3.2.3-block-sync.md)                        |
| 3.3 Usability                  | not applicable                                                                   |
| 3.4 Performance                | no requirements in v0.1                                                          |
| 3.5 Logical database           | [3.5-logical-database.md](3-requirements/3.5-logical-database.md)                |
| 3.6 Design constraints         | [3.6-design-constraints.md](3-requirements/3.6-design-constraints.md)            |
| 3.7 Software system attributes | [3.7-system-attributes.md](3-requirements/3.7-system-attributes.md)              |
| 3.8 Supporting information     | [3.8-supporting-information.md](3-requirements/3.8-supporting-information.md)    |
| 4 Verification                 | [4-verification.md](4-verification.md)                                           |
| 5 Appendices                   | [5-appendices.md](5-appendices.md)                                               |

## Conventions

### Requirements

A requirement is a paragraph that begins with a bold identifier, for example `NET-01` in bold. Identifiers are a prefix and a
number:

| Prefix | Section                        |
|--------|--------------------------------|
| EXT    | 3.1 External interfaces        |
| NET    | 3.2.1 Functions: net           |
| CHN    | 3.2.2 Functions: chain         |
| BSY    | 3.2.3 Functions: block-sync    |
| STO    | 3.5 Logical database           |
| DES    | 3.6 Design constraints         |
| ATT    | 3.7 Software system attributes |

Identifiers are stable. A retired identifier is not reused; a new requirement takes the next free number of its prefix.

A table, list or code block that a requirement names is part of that requirement. Text without an identifier is
descriptive and carries no requirement of its own.

### Keywords

MUST, MUST NOT, SHOULD, SHOULD NOT and MAY are used as defined in RFC 2119 and clarified by RFC 8174: only the
uppercase forms are keywords. MUST is used in the sense of "shall" in ISO/IEC/IEEE 29148. SHALL is not used.

### Unresolved items

`[TBD-n]` marks an unresolved item. Every item is listed in [Appendix C](5-appendices.md#c-tbd-register).

### Bitcoin Core

Where a requirement names a Bitcoin Core function, constant or reject reason, the behaviour is that of the Bitcoin Core
version listed in [2 References](2-references.md). BIPs are cited by number.

### Diagrams

Mermaid sequence diagrams are supporting information. In them `->>` is a direct call, `-->>` is its result, and `-)` is
a push to a queue or a P2P message.
