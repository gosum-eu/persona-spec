# GoSum Persona Schema

**Spec URL:** `https://schema.gosum.eu/persona/v0.1.jsonld`  
**Status:** v0.1 frozen · v0.2 (memory extension) in RFC  
**License:** CC0 (schema and vocabulary) · Apache-2.0 (validators, tooling)

An open JSON-LD specification for defining, versioning, and governing synthetic AI personas deployed on customer-facing robots and conversational interfaces.

The schema is the open standard. The runtime that executes against it is a separate commercial product. This repository holds the standard.

## What a GoSum persona is

A persona document is a single JSON-LD file with ten required blocks: `identity`, `brand`, `personality`, `voice`, `knowledge`, `guardrails`, `behavior`, `telemetry`, `bindings`, and `provenance`. Each block is validated structurally (JSON Schema) and semantically (SHACL). Every persona has a cryptographic W3C DID and a SHA-256 content hash that together guarantee tamper-evidence and version-chain integrity.

## Repository structure

```
persona-spec/
├── schema/
│   ├── v0.1/
│   │   ├── persona.jsonld        # JSON-LD context (normative)
│   │   └── persona.schema.json   # JSON Schema validator
│   └── v0.2/
│       └── persona.jsonld        # v0.2 context: adds memory and memoryPolicy blocks
└── examples/
    └── eliza-lighthouse-cafe.jsonld   # Worked example: hospitality concierge persona
```

## Quick start

```json
{
  "@context": "https://schema.gosum.eu/persona/v0.1.jsonld",
  "@type":    "Persona",
  "@id":      "did:gosum:yourorg:your-persona:v1.0.0",
  "identity": { ... }, "brand": { ... }, "personality": { ... },
  "voice": { ... }, "knowledge": { ... }, "guardrails": { ... },
  "behavior": { ... }, "telemetry": { ... }, "bindings": { ... },
  "provenance": { ... }
}
```

All ten blocks are required.

**Validate locally:**

```bash
npx ajv validate -s schema/v0.1/persona.schema.json -d your-persona.jsonld
```

## Citation

```bibtex
@article{pop2026governed,
  title   = {Governed Synthetic Personas: A Schema-Based Framework for
             Coherent, Persistent, and Auditable {AI} Agent Personality},
  author  = {Pop, Liviu},
  journal = {Journal of Artificial Intelligence Research},
  year    = {2026},
  note    = {Submitted}
}
```

## Contact

Liviu Pop · liviu@gosum.eu · [gosum.eu](https://gosum.eu)
