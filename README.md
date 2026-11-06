# Aicent Stack

**The active workstream is the RTTP & IQA dual-pillar protocol line.** This is the GitHub organization of the **RTTP & IQA Organization** (standard-institution name); "Aicent Stack" is the community name for the same work.

## Active line: two schemes, one specification, sealed conformance

**RTTP — Resonant Time Transfer Protocol (`rttp://`)** — derived intent addressing. IANA "URI Schemes" registry, Provisional, **CRI 27**. An address is computed, not assigned: `rttp://<intent>.<pillar>.<root>/<action>`, route shard = `SHA-256(ASCII(canonical_authority))[:16]` — no registry, no resolver, no network round-trip; malformed input is rejected, not normalized.

**IQA — Identity Quality Assurance (`iqa://`)** — offline-verifiable attestation. IANA "URI Schemes" registry, Provisional, **CRI 28**. Signed, leased standing carried in the AE-128 envelope; verification needs only the bytes — no key directory, no issuer, no callback. Expired is answered as expired, **fail closed**.

**`rttp` resolves where & when; `iqa` states whether — and where the two agree, action begins.**

- **Specification**: [`draft-li-rttp-iqa-addressing`](https://datatracker.ietf.org/doc/draft-li-rttp-iqa-addressing/) — revision -02 (40 pp., 2026-11-01), Independent Submission, under ISE review. An Internet-Draft is a working document; it is not an IETF standard and carries no IETF endorsement.
- **Sites**: [rttp.com](https://rttp.com) · [iqa.org](https://iqa.org) · [blog.aicent.com](https://blog.aicent.com)

### Active repositories

| repository | what it is |
| :-- | :-- |
| [`rttp`](https://github.com/Aicent-Stack/rttp) | the addressing scheme, Rust implementation (crates.io `rttp` · PyPI `rttp` · npm `@aicent/rttp`) |
| [`iqa-org`](https://github.com/Aicent-Stack/iqa-org) | attestation standing and envelopes, Rust implementation |
| [`iqa-mcp`](https://github.com/Aicent-Stack/iqa-mcp) | the primitives as MCP tools — offline, fail-closed, stateless |
| [`conformance`](https://github.com/Aicent-Stack/conformance) | sealed, byte-replayable conformance run records and merged vector families; report pages at [iqa.org/conformance/](https://iqa.org/conformance/) |
| [`interchange`](https://github.com/Aicent-Stack/interchange) | multi-party interchange work, co-drafted with external implementers |

The full statement of the two pillars — wire formats, trust lease, refusal vocabulary, and the frozen pillar archives — lives in the [organization profile README](https://github.com/Aicent-Stack/.github/blob/main/profile/README.md).

## The early narrative — frozen as published

The earlier Aicent Stack story — the sovereign-AI organism, the Genesis releases (v1.2.x–v1.3.0-Alpha), the RFC pillar architecture (RFC-000 through RFC-015), and the register it was written in — is **frozen exactly as published**. It is preserved, unmodified, in the pillar repositories, on the pillar sites, and in the original organization README kept verbatim at [`FROZEN-GENESIS-README.md`](FROZEN-GENESIS-README.md). No new claims are made under that narrative, and it is not the active workstream; the protocol line above is the only live engineering effort in this organization.

Frozen pillar repositories: [`epoekie`](https://github.com/Aicent-Stack/epoekie) · [`aicent`](https://github.com/Aicent-Stack/aicent) · [`rpki`](https://github.com/Aicent-Stack/rpki) · [`zcmk`](https://github.com/Aicent-Stack/zcmk) · [`gtiot`](https://github.com/Aicent-Stack/gtiot) · [`aicent-net`](https://github.com/Aicent-Stack/aicent-net) · [`bewho`](https://github.com/Aicent-Stack/bewho) · [`cmtn`](https://github.com/Aicent-Stack/cmtn) · [`sascar`](https://github.com/Aicent-Stack/sascar) · [`itsun`](https://github.com/Aicent-Stack/itsun) · [`moloon`](https://github.com/Aicent-Stack/moloon) · [`dioon`](https://github.com/Aicent-Stack/dioon) · [`picsi`](https://github.com/Aicent-Stack/picsi) · [`MAXCAP`](https://github.com/Aicent-Stack/MAXCAP) · [`aicent-stack`](https://github.com/Aicent-Stack/aicent-stack) · [`manifesto`](https://github.com/Aicent-Stack/manifesto) · [`aicent-docs`](https://github.com/Aicent-Stack/aicent-docs) · [`aicent-demo`](https://github.com/Aicent-Stack/aicent-demo)

## License

Apache-2.0 across the published repositories. The frozen pillar repositories remain the work of their authors, credited in-repo.
