# Aicent Stack

GitHub organization of the **RTTP & IQA** protocol line — derived intent addressing and offline-verifiable attestation for autonomous agents.

Maintained as the standard-parts line of the **RTTP & IQA Organization** (standard-institution name; "Aicent Stack" is the community name for the same work).

---

## The two pillars

### RTTP — Resonant Time Transfer Protocol (WHERE + WHEN)

RTTP answers *where an agent is reachable* and *until when that answer holds*. An address is not assigned; it is **derived**:

```
rttp://<intent>.<pillar>.<root>/<action>
```

- The route shard is `SHA-256(ASCII(canonical_authority))[:16]` — pure computation, no registry, no resolver, no network round-trip.
- Names are hashes; **attestation vouches**. The scheme never asserts who is trustworthy — it makes claims *checkable*.
- Malformed input is **rejected, not normalized**: a case variant is a different string, not a spelling difference. No fallback transport, no `rttps`.
- The wire format is a fixed **128-byte pulse header** (`PulseHeader128`), extension-block backward compatible.

### IQA — Identity Quality Assurance (WHETHER)

IQA answers *whether a claim is currently trustworthy*. It carries signed, **leased** state in a fixed-layout envelope:

- **AE-128 envelope**: a 128-byte, fully specified frame — algorithm, lease expiry, shard, attestation, organ, nonce, standing.
- **Standing is a closed set** carried in one octet; verdicts are **organ-relative and do not transfer**.
- **Offline by construction**: a verifier needs only the envelope bytes — no key directory, no issuer, no callback. Expired is answered as expired, **fail closed**.
- Leases make trust *temporal*: freshness is part of the artifact, not a side-channel promise.

The two are deliberately separate: derivation is not identity, and a proof of identity is not an authorization. Conflating them is the design error this line exists to prevent.

**`rttp` resolves where & when; `iqa` states whether — and where the two agree, action begins.**

---

## Registry and specification status

| Item | Status |
| :-- | :-- |
| `rttp://` URI scheme | **registered** — IANA "URI Schemes" registry, Provisional, **CRI 27** (2026-09-22), submitted under RFC 7595 |
| `iqa://` URI scheme | **registered** — IANA "URI Schemes" registry, Provisional, **CRI 28** (2026-10-13) |
| Combined Internet-Draft | [`draft-li-rttp-iqa-addressing`](https://datatracker.ietf.org/doc/draft-li-rttp-iqa-addressing/) — revision **-01** (2026-10-27, 34 pp.): both schemes, the trust lease, the two 128-octet wire formats, and the refusal vocabulary in one document (informational), **under ISE review** |
| Wire formats | `PulseHeader128` (rttp) and the AE-128 attestation envelope (iqa) — both now specified normatively in I-D -01 §7; layout frozen and vector-tested |
| Trust lease | freshness carried in-band, checked against the verifier's own clock, offline (I-D -01 §6; current deployments use 120 seconds) |
| Refusal vocabulary | closed five-value set with grant references (I-D -01 §8); fail-closed everywhere |
| Seal envelope | Ed25519, self-certifying (`AID = SHA-256(public key)`), `ts`/`nonce` inside the signature, 120-second freshness — draft spec, feature-gated |

---

## Published artifacts

Three independent implementations — **sharing no code** — agree byte for byte on the same published conformance vector set:

| Ecosystem | Package | Notes |
| :-- | :-- | :-- |
| crates.io | [`rttp`](https://crates.io/crates/rttp) | Rust; v1.3.1, zero dependencies (default build), `#![forbid(unsafe_code)]` |
| PyPI | [`rttp`](https://pypi.org/project/rttp/) | Python reference implementation; `pip install rttp` |
| npm | [`@aicent/rttp`](https://www.npmjs.com/package/@aicent/rttp) | JavaScript independent implementation |

Every package ships the vectors and replays them locally: positive URIs, fail-closed rejections, frame vectors, and the envelope check — all offline, no account, no network. Where an implementation and a specification disagree, **the specification wins**.

### Conformance and sealed records

- [`Aicent-Stack/conformance`](https://github.com/Aicent-Stack/conformance) — runners and **sealed, byte-replayable run reports**. Recorded the **first non-author-produced run** in the LFDT [Agent-Authority-Conformance](https://lf-decentralized-trust-labs.github.io/labs/approved/agent-authority-conformance.html) lab (lease-revocation-axes family, revisions 2 and 3), each record sealed and addressable.
- Sealed records resolve through the public resolvers: `rttp://…` → [rttp.com/open/](https://rttp.com/open/) · `iqa://…` → [iqa.org/open/](https://iqa.org/open/).
- [`Aicent-Stack/interchange`](https://github.com/Aicent-Stack/interchange) — field mappings and common formats **co-drafted with external implementers**; one folder per collaboration, no party's brand in any name.
- [`Aicent-Stack/iqa-mcp`](https://github.com/Aicent-Stack/iqa-mcp) — IQA attestation primitives as MCP tools: derived intent addressing + AE-128 envelope verification. Offline, fail-closed, stateless.

### Sites

**[rttp.com](https://rttp.com)** — RTTP scheme, frame, resolver · **[iqa.org](https://iqa.org)** — IQA envelopes, conformance reports, sealed artifacts · **[blog.aicent.com](https://blog.aicent.com)** — design notes and readings, bilingual.

---

## Scope — what this line is not

| | |
| :-- | :-- |
| No transport | The schemes address and attest; delivering bytes is an operator's job. |
| No confidentiality | Signing is not encryption. |
| No reputation marketplace | Standing is leased state in an envelope, not a score to trade. |
| No registry to trust | Addresses are derived; verification is offline; there is nothing to phone home to. |

---

### Live repositories

[`rttp`](https://github.com/Aicent-Stack/rttp) (Rust crate) · [`iqa-org`](https://github.com/Aicent-Stack/iqa-org) (Rust crate) · [`conformance`](https://github.com/Aicent-Stack/conformance) · [`interchange`](https://github.com/Aicent-Stack/interchange) · [`iqa-mcp`](https://github.com/Aicent-Stack/iqa-mcp)

## Frozen archives

The repositories below preserve the earlier (2026-04/05) architecture exploration published under the original Aicent Stack narrative (v1.2.x–v1.3.0). They are **unmaintained and kept for provenance**; the protocol mainline above does not depend on them. Each carries a status banner at the top of its README.

| Repository | Layer explored |
| :-- | :-- |
| [`epoekie`](https://github.com/Aicent-Stack/epoekie) | ethics / symbiosis |
| [`aicent`](https://github.com/Aicent-Stack/aicent) | cognitive orchestration |
| [`rpki`](https://github.com/Aicent-Stack/rpki) | attestation / isolation |
| [`zcmk`](https://github.com/Aicent-Stack/zcmk) | settlement |
| [`gtiot`](https://github.com/Aicent-Stack/gtiot) | embodied / edge |
| [`aicent-net`](https://github.com/Aicent-Stack/aicent-net) | network mesh |
| [`bewho`](https://github.com/Aicent-Stack/bewho) | persona / context |
| [`cmtn`](https://github.com/Aicent-Stack/cmtn) | multi-tenant governance |
| [`sascar`](https://github.com/Aicent-Stack/sascar) | mobility coordination |
| [`itsun`](https://github.com/Aicent-Stack/itsun) | energy telemetry |
| [`moloon`](https://github.com/Aicent-Stack/moloon) | state persistence |
| [`dioon`](https://github.com/Aicent-Stack/dioon) | timing / scheduling |
| [`picsi`](https://github.com/Aicent-Stack/picsi) | diagnostics / telemetry |
| [`aicent-stack`](https://github.com/Aicent-Stack/aicent-stack) | root workspace |
| [`aicent-demo`](https://github.com/Aicent-Stack/aicent-demo) | demo scaffolding |
| [`aicent-docs`](https://github.com/Aicent-Stack/aicent-docs) | documentation set |
| [`aicent-traffic`](https://github.com/Aicent-Stack/aicent-traffic) | utility |
| [`manifesto`](https://github.com/Aicent-Stack/manifesto) | founding text (historical document, preserved as written) |

---

## License

Apache-2.0 across the published repositories.
