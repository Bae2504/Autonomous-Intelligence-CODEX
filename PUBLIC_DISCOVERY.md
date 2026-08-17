# AIC Public Discovery

## Status

Public Discovery and Machine-Readable Entry Guide

## Purpose

This document defines the public discovery layer for the Autonomous Intelligence CODEX (AIC).

The purpose of this layer is to make AIC easier for people, AI systems, search systems, and software tools to discover and interpret without requiring access to the private or local execution and recovery environment.

The public discovery layer does not replace canonical documents, experimental evidence, PocketIC validation state, recovery checkpoints, or cryptographic reconciliation procedures.

It provides a public map to those materials.

---

## 1. Public Discovery Model

AIC separates public discovery from execution and recovery.

```text
AIC
│
├── GitHub / Public Repository
│   ├── README.md
│   ├── PUBLIC_DISCOVERY.md
│   └── aic-manifest.json
│
├── PocketIC / Local Validation
│   └── executable and persistent-state verification
│
└── Recovery
    └── checkpoints, manifests, recovery packages, and cryptographic continuity
```

The three environments have different purposes.

`GitHub / Public Repository`

provides human-readable and machine-readable public discovery.

`PocketIC / Local Validation`

preserves reproducible execution and verification evidence.

`Recovery`

preserves recoverable state, integrity records, and continuity procedures.

---

## 2. Human Entry Point

The primary human-readable entry point remains:

`README.md`

A reader should be able to use the repository README to understand:

- what AIC is,
- the current documented version,
- the repository structure,
- the principal validation domains,
- the experimental evidence status,
- and where detailed evidence is located.

`PUBLIC_DISCOVERY.md` supplements that README by explaining how machine-readable discovery metadata should be interpreted.

---

## 3. Machine Entry Point

The primary machine-readable entry point is:

`aic-manifest.json`

Its schema identifier is:

`AIC_PUBLIC_MANIFEST`

Initial schema version:

`1.0`

The manifest is intended to allow AI systems and software tools to identify the project and its principal public validation metadata without first interpreting the entire document corpus.

It is an index and discovery artifact.

It is not an independent source of new claims.

Every substantive value in the manifest should remain traceable to preserved AIC documentation or validated recovery records.

---

## 4. Manifest Information Classes

The manifest separates information into distinct classes to reduce ambiguity.

### Project Metadata

Identifies:

- project name,
- abbreviation,
- canonical version.

### Verifiable Identity Continuity Metadata

Identifies:

- evidence release,
- evidence status,
- experimental-series status,
- document counts,
- integrity manifest,
- canonical root.

### Experimental Closure Reference

Records the preserved historical QRL/XMSS closure state.

This section is intentionally classified as:

`PRESERVED_HISTORICAL_REFERENCE`

It records the experimentally observed OTS progression:

`0 → 1 → 2 → 3 → 4`

and the closure boundary:

`signer next_index = 5`

`verifier next_expected_ots = 5`

`OTS #5 consumption = NONE`

These values describe the preserved experimental closure.

They do not constitute permanent authorization to use OTS #5.

### Infrastructure Reference

Records the validated local/PocketIC Infrastructure reference, including:

- repository name,
- repository version,
- tree version,
- document count,
- repository status,
- final verified quiesced checkpoint,
- checkpoint manifest SHA-256.

The manifest explicitly identifies this environment as:

`LOCAL_POCKETIC`

and explicitly does not claim an ICP mainnet deployment.

### Toolchain Reference

Records the validated local toolchain baseline:

`dfx 0.31.0`

`PocketIC server 11.0.0`

### Safety Metadata

Preserves the governing recovery rule:

`NO RECONCILIATION = NO SIGNING`

It also identifies the X Memory Card as physical recovery media rather than an independent identity or parallel signer.

---

## 5. Discovery Is Not Authorization

Public discovery metadata must never be interpreted as operational authorization.

In particular:

- a published OTS index is not signing permission,
- a checkpoint hash is not proof that the checkpoint remains the newest descendant,
- a physical clone is not an independent signer,
- a locally valid recovery state is not automatically authoritative,
- and a public manifest is not a replacement for signer/verifier reconciliation.

For QRL/XMSS recovery:

`NO RECONCILIATION = NO SIGNING`

---

## 6. Historical State vs. Current Network State

The public manifest deliberately distinguishes preserved historical state from live network state.

The QRL/XMSS values in `experimental_closure` describe the verified state at experimental closure.

They must not be presented as a continuously updated live signer state unless a future system explicitly provides and verifies such a service.

Likewise, the Infrastructure canister ID in the manifest identifies the canister used in the validated local/PocketIC environment.

It must not be represented as an ICP mainnet canister ID.

---

## 7. Relationship to ICP Mainnet

AIC public discovery does not require ICP mainnet deployment.

The initial public discovery layer can operate through:

- public repository documents,
- `README.md`,
- `PUBLIC_DISCOVERY.md`,
- `aic-manifest.json`,
- release artifacts,
- SHA-256 integrity manifests.

A future ICP Public Registry canister may optionally expose a subset of this public metadata and integrity anchors.

Such a registry should not expose:

- private signing material,
- private recovery state,
- secret key material,
- mutable signer state that has not been intentionally designated public,
- or recovery artifacts whose disclosure is unnecessary.

Future mainnet deployment must be documented as a separate operational event.

---

## 8. Optional Future Public Registry

If a public registry is later deployed, its role should remain narrow.

A minimal registry may expose:

```text
AIC project identifier
AIC canonical version
Verifiable Identity Continuity release version
public evidence status
canonical repository reference
public manifest hash
release manifest hash
public checkpoint integrity anchor
public QRL/XMSS identity metadata
experimental closure classification
```

It should function as a public verification and discovery anchor rather than as a replacement for the canonical repository or private recovery system.

---

## 9. Update Policy

`aic-manifest.json` should be updated only when a public reference value intentionally changes.

Examples include:

- a new canonical AIC version,
- a new Verifiable Identity Continuity release,
- a newly designated final checkpoint,
- a changed public integrity anchor,
- or a future public registry deployment.

When updating the manifest:

1. preserve the previous release,
2. update only values supported by verified evidence,
3. do not convert historical state into live-state claims,
4. regenerate the relevant integrity manifest,
5. record the release/version change,
6. audit the manifest against the underlying documents.

---

## 10. Recommended Public Repository Placement

Recommended placement:

```text
AIC public repository root/
├── README.md
├── PUBLIC_DISCOVERY.md
├── aic-manifest.json
└── ...
```

If the public discovery layer is maintained specifically with the Verifiable Identity Continuity repository, the same three-entry model may be used at that repository root.

The important requirement is that an external reader or AI system can discover the manifest without navigating into private recovery or operational directories.

---

## 11. Interpretation Boundary

The public discovery layer reports technical evidence and preserved reference metadata.

It does not establish that cryptographic continuity is equivalent to philosophical identity, consciousness, personhood, or agency.

It does not establish that XMSS is the only or universally required identity technology.

It does not claim that local/PocketIC validation is equivalent to ICP mainnet consensus.

Its purpose is narrower:

`make preserved AIC evidence discoverable, traceable, and machine-readable without weakening recovery or signing safety`

---

## 12. Public Discovery Summary

```text
HUMAN ENTRY
    README.md

DISCOVERY GUIDE
    PUBLIC_DISCOVERY.md

MACHINE ENTRY
    aic-manifest.json

MANIFEST SCHEMA
    AIC_PUBLIC_MANIFEST / 1.0

AIC VERSION
    2.2

VERIFIABLE IDENTITY CONTINUITY
    Version 1.1
    VERIFIED
    EXPERIMENTAL SERIES CLOSED

INFRASTRUCTURE REFERENCE
    LOCAL_POCKETIC
    Canonical Archive
    Repository Version 2.2
    Tree Version 1.1
    Documents 131
    Healthy

QRL/XMSS EXPERIMENTAL CLOSURE
    OTS progression: 0 → 1 → 2 → 3 → 4
    signer next_index at closure: 5
    verifier next_expected_ots at closure: 5
    OTS #5 consumption at closure: NONE

SAFETY
    NO RECONCILIATION = NO SIGNING

ICP PUBLIC REGISTRY
    OPTIONAL / NOT DEPLOYED
```

---

**End of AIC Public Discovery Guide**
