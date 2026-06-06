# AIPS-1 Reference Verifier Implementations

Reference implementations of the AIPS-1 Policy Certificate verification flow specified in §7 of the specification.

## Status

**Deferred to v0.2 (Q3 2026).**

## Planned modules

| Module | Description |
|--------|-------------|
| `aips1-verifier-js/` | JavaScript / TypeScript client library. Runnable in browser, Node.js, and Deno. Composes with AIS-1 resolution, AES-1 enclave checks, and AAS-1 record emission. |
| `aips1-verifier-solidity/` | On-chain Solidity verifier contract. Permits a smart contract to verify an AIPS-1 Policy Certificate before accepting a transaction from an Insured Agent. |
| `aips1-mcp-server-module/` | Server-side MCP module. Verifies the AIPS-1 cover of any agent invoking a covered-action MCP tool; declines invocations from uncovered agents. |
| `aips1-conformance/` | Conformance harness and test vectors (v0.5). |

## Design principles

- Composable with AIS-1 resolution and verification.
- Composable with AES-1 enclave currency checks where `aesConditional` is set.
- Emits AAS-1 Class A records on every verification outcome.
- Pure functions over Certificate inputs where possible; side-effects clearly factored.
- Deterministic given the inputs at evaluation time — Status freshness is the only non-determinism.

## DID method

A `did:aips1` DID method specification will accompany the verifier modules in v0.2, conforming to the W3C DID Core specification. Provisional format:

```
did:aips1:{chain}:{address}:{seq}
```

## Comment

Input on the verifier design and the `did:aips1` method is invited via GitHub issues during the v0.1 public comment period.
