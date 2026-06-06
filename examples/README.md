# AIPS-1 Worked Examples

Worked Policy Certificate examples covering each tier and a range of agent activity types.

## Status

**Deferred to v0.2 (Q3 2026).** The v0.1 specification includes one worked example in Appendix A — a Bermuda captive issuing a Tier II Policy Certificate covering an AI agent executing automated treasury operations on behalf of a multinational corporate Policyholder, with cover conditional on operation within an AES-1 enclave.

## Planned for v0.2

| File | Tier | Use case |
|------|------|----------|
| `tier-i-payments-agent.json` | I | Standard commercial cover for an agent making low-value automated payments — payment failure, fraud, basic cyber |
| `tier-i-customer-ops.json` | I | E&O / professional indemnity cover for an agent in a customer operations context |
| `tier-ii-agentic-treasury.json` | II | Bermuda captive covering an AI agent executing automated treasury operations (the Appendix A example, broken out as a standalone artefact) |
| `tier-ii-trade-finance.json` | II | Cayman / Bermuda captive covering an agent executing trade-finance facility drawdowns |
| `tier-iii-settlement-infrastructure.json` | III | Sovereign-backed cover for an agent operating as part of national settlement infrastructure |
| `tier-iii-critical-utility.json` | III | Sovereign-backed cover for an agent in critical-infrastructure deployment |

Each example will include:

- A complete signed Policy Certificate.
- A worked verification flow showing the relevant AIS-1 resolution, authorisation credential checks, P1–P5 evaluation, and Status check.
- Annotated commentary on the drafting choices.

## Contributing examples

If you would like to contribute a worked example for v0.2 — particularly an example covering an agent activity type not represented above — open an issue at [github.com/Kadikoy1/aips-1/issues](https://github.com/Kadikoy1/aips-1/issues) with a sketch of the use case.
