# AIPS-1 Schemas

JSON Schema 2020-12 definitions for the AIPS-1 Policy Certificate and supporting structures.

## Planned for v0.2 (Q3 2026)

| File | Description |
|------|-------------|
| `aips1-policy-certificate.schema.json` | The top-level Policy Certificate schema |
| `aips1-coverage-schema.schema.json` | Coverage Scope schema — perils, exclusions, limits, deductibles, named insureds, period of cover |
| `aips1-trigger-predicate.schema.json` | Trigger predicate schema (oracle, attestation, time, balance, manual, composite) — patterned on ARS-1 §3.3 |
| `aips1-settlement-path.schema.json` | Settlement Path schema — endpoint, notification protocol, response timeline, payout instrument, fallback dispute mechanism |
| `aips1-status-transition.schema.json` | Status transition schema — Active / Suspended / Claimed / Exhausted / Lapsed |

## Conventions

- Schemas conform to **JSON Schema 2020-12**.
- All schemas use **JCS (RFC 8785)** for canonicalisation, matching AIS-1 §6.2 and AAS-1 §6.2.
- Default hash algorithm: **SHA-256**.
- Signature objects follow the AIS-1 / AAS-1 shared format.
- Field naming follows lowerCamelCase.

## Cross-references

- Policy Certificate `issuerDid`, `policyholderDid`, and `insuredAgents[]` reference AIS-1 DIDs.
- `aesConditional` (where present) references an AES-1 Enclave Certificate identifier.
- Trigger Evidence Sources MAY reference AAS-1 Class A record IDs.

See the v0.1 specification (`docs/AIPS-1_Specification_v0_1.pdf`) for the normative field descriptions until the schemas land.
