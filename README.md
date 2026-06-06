# AIPS-1 — Agent Insurance Policy Standard

**An open standard for the issuance, identification and verification of insurance policies covering AI agent activity.**

Working Paper · v0.1 · Draft for Public Comment
Published by Kadikoy Limited, Bermuda
Creative Commons CC0 — no rights reserved · free to implement.

Website: [aips-1.org](https://aips-1.org)
Specification: [`docs/AIPS-1_Specification_v0_1.pdf`](docs/AIPS-1_Specification_v0_1.pdf)

---

## What AIPS-1 is

AIPS-1 defines a common, jurisdiction-agnostic framework for the issuance, identification and verification of insurance policies covering the activity of autonomous and semi-autonomous AI agents. It addresses the **Illegible Insurance Problem**: cover may exist, but it is not legible to machines in a form an agent or counterparty can act on at the moment of reliance.

The standard introduces the **Policy Certificate** — a structured, signed, on-chain artefact issued by a regulated insurer that any relying party can verify in real time. The Certificate represents an underlying regulated insurance policy; it does not replace, modify or interpret insurance regulation in any jurisdiction.

AIPS-1 sits alongside AIS-1, AES-1 and AAS-1 as the fourth element of the open agent infrastructure stack.

## Five core properties

| Property | What it requires |
|----------|------------------|
| **P1 — Issuer Authority** | Regulated insurer in a Recognised Jurisdiction, with a verifiable regulator-issued authorisation credential |
| **P2 — Coverage Specificity** | Machine-parseable Coverage Scope: perils, exclusions, limits, deductibles, named insureds, period of cover |
| **P3 — Trigger Determinism** | Objectively-evaluable trigger predicates referencing declared Evidence Sources |
| **P4 — Settlement Path** | Claims-handling endpoint, response timeline, payout instrument, fallback dispute mechanism |
| **P5 — On-Chain Verifiability** | Current Status retrievable from public chain data without Issuer disclosure |

The five properties roll up to one question: *is this policy credibly enforceable?*

## Three tiers

| Tier | Issuer category | Reinsurance |
|------|-----------------|-------------|
| **I — Standard Commercial** | Licensed commercial insurer in a Recognised Jurisdiction | Discretionary |
| **II — Captive and Specialised** | Captive, mutual, protected cell, segregated account company, or specialised insurance vehicle | Typically present |
| **III — Sovereign-Backed** | Tier II issuer with sovereign or quasi-sovereign reinsurance backstop or guarantee fund participation | Required |

The tier hierarchy is structural, not qualitative. It signals the resilience of the standing-behind, not the quality of the underwriting.

## Composition with the agent infrastructure stack

| Standard | Subject | Cross-reference with AIPS-1 |
|----------|---------|------------------------------|
| [AIS-1](https://ais-1.org) | Agent identity | Issuer, Policyholder and Insured Agents are all identified by AIS-1 DIDs |
| [AES-1](https://aes-1.org) | Execution environment | Coverage Scope MAY be conditioned on the Insured Agent operating within an AES-1 certified enclave |
| [AAS-1](https://aas-1.org) | Records of agent activity | AAS-1 Class A records are admissible as Evidence Sources under P3; claim notifications under P4 SHOULD emit a Class A record |
| **AIPS-1** *(this standard)* | Insurance policy covering AI agents | First open standard for portable, machine-verifiable agent insurance |

## What AIPS-1 is *not*

AIPS-1 is a **representation standard**, not a regulatory framework.

- It is **not** a new legal instrument. The underlying Policy remains governed by the law of the Issuer's jurisdiction.
- It does **not** replace, modify or interpret insurance regulation in any jurisdiction.
- It does **not** create insurance coverage where none has been written under the underlying Policy.
- It does **not** modify the rights or obligations of any party under the Policy.
- It does **not** privilege or prefer any particular jurisdiction's insurance regulation.

The Certificate sits on top of existing insurance regulation; it does not displace it.

## Repository layout

```
aips-1/
├── README.md                                   — this file
├── LICENSE                                     — Creative Commons CC0
├── docs/
│   └── AIPS-1_Specification_v0_1.pdf           — v0.1 specification
├── schemas/                                    — JSON Schema 2020-12 (v0.2)
│   └── README.md
├── jurisdiction-list/                          — Recognised Jurisdiction List governance (v0.2)
│   └── README.md
├── reference/                                  — Reference verifier implementations (v0.2)
│   └── README.md
└── examples/                                   — Worked examples by tier (v0.2)
    └── README.md
```

## Roadmap

| Version | Target | Key additions |
|---------|--------|---------------|
| **v0.1** | Jun 2026 | This release — specification, P1–P5, three tiers, Policy Certificate schema, worked example |
| v0.2 | Q3 2026 | `did:aips1` DID method, reference verifier (JavaScript + smart contract + MCP), Coverage Schema v1, first Tier I and II Certificate issuances |
| v0.3 | Q4 2026 | On-chain reinsurance attestation framework, Tier III sovereign-backed framework, syndicated coverage structures, first Tier III Certificate |
| v0.4 | Q1 2027 | Captive market integration profiles (Bermuda, Cayman, Vermont, Guernsey, Singapore); regulator dashboard specification |
| v0.5 | Q2 2027 | Conformance suite, test vectors |
| v1.0 | Q3 2027 | Standardisation track — ISO TC 68 / SC 8 liaison and IAIS observer engagement; stable schemas |

## Public comment

AIPS-1 v0.1 is open for public comment until **30 November 2026**. Comments are invited from insurance supervisors (IAIS members, national regulators); commercial insurers and reinsurers; captive insurance markets and managers (Bermuda BMA, Cayman CIMA, Vermont DFR, Guernsey GFSC, Singapore MAS); insurance brokers and risk advisers; AI agent developers; legal, regulatory and compliance professionals; standards organisations (ISO TC 68, IAIS, IFRS Foundation); and the wider AI-agent developer community.

**Channels:**

- GitHub Issues — [github.com/Kadikoy1/aips-1/issues](https://github.com/Kadikoy1/aips-1/issues)
- Email — [info@aiagentsservices.net](mailto:info@aiagentsservices.net)
- Web form — [aips-1.org/#feedback](https://aips-1.org/#feedback)

A revised v0.2 will be published incorporating substantive feedback.

### Open questions for comment

- Should P3 permit Issuer-discretionary triggers at Tier I while retaining the hard determinism requirement at Tier II and Tier III?
- Should the Recognised Jurisdiction List be governed by AIPS-1's own governance body, or delegated to an existing standards organisation (e.g. IAIS)?
- Should Trigger predicates be expressed in a defined predicate language (e.g. JSONLogic, Rego) or remain Issuer-defined within a structural envelope?
- What is the appropriate on-chain home for Policy Certificates: a dedicated registry, the Issuer's own contract space, or a multi-chain identifier scheme?
- Should reinsurance attestations be on-chain artefacts in their own right (suggesting an AIPS-2 reinsurance standard) or remain fields within the Policy Certificate?
- How should Certificate Status changes notify subscribed Relying Parties without exposing the Insured Agent's transaction graph?

## License

Creative Commons CC0 — no rights reserved. Free to implement, distribute, modify, and build on. See [`LICENSE`](LICENSE).

## Citation

> Kadikoy Limited (2026). *AIPS-1: Agent Insurance Policy Standard, v0.1.* Working Paper, June 2026. Available at https://aips-1.org.

## Authors and contact

- **Author:** Kadikoy Limited, Bermuda (Reg. 202302362)
- **Affiliation:** BDA Law · BDA AI Agent Services
- **Contact:** [info@aiagentsservices.net](mailto:info@aiagentsservices.net)
- **Website:** [aips-1.org](https://aips-1.org)
- **Repository:** [github.com/Kadikoy1/aips-1](https://github.com/Kadikoy1/aips-1)

---

*Companion standards: [AIS-1](https://ais-1.org) · [AES-1](https://aes-1.org) · [AAS-1](https://aas-1.org) · [ARS-1](https://ars-1.org)*
