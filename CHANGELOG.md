# Changelog

All notable changes to the GoSum Persona Schema are documented here.
Versioning follows [Semantic Versioning](https://semver.org).
A change is *breaking* (major bump) if it removes or renames a required field,
changes a field type, or alters the content-hash computation.

---

## [0.2.0] — 2026-05-01

### Added
- `memory` block: typed autobiographical memory atoms with salience, decay,
  and privacy classification
- `memoryPolicy` block: retention policies, redaction semantics, GDPR
  right-to-erasure SLA, confabulation policy
- Decay model: Ebbinghaus-derived forgetting curve with rehearsal boost and
  valence-protection floor
- Privacy classes: `non-pii`, `aggregate`, `guest-pii`, `staff-pii`,
  `sensitive-pii`, `commercial-confidential`
- v0.2 JSON-LD context as a strict superset of v0.1

### Unchanged
- All v0.1 blocks and fields remain unchanged. A v0.1 persona is a valid
  v0.2 persona with empty memory.

---

## [0.1.0] — 2026-04-01

### Added
- Initial schema: ten required blocks (`identity`, `brand`, `personality`,
  `voice`, `knowledge`, `guardrails`, `behavior`, `telemetry`, `bindings`,
  `provenance`)
- JSON-LD context at `https://schema.gosum.eu/persona/v0.1.jsonld`
- JSON Schema validator
- `narrativeSpine` in `personality`: `origin`, `definingEvents`, `themes`
- W3C DID cryptographic identity and content-hash versioning
- Six-pass validation pipeline
- Safety tier enum (A / B / C) with tier-C enforcement
- EU AI Act Article 50 compliance flag and disclosure text
- Hardware adapter bindings: Pudu, Bear Robotics, Keenon, Figure, Apptronik,
  Unitree, Agility, simulator, generic-MQTT
- TTS provider bindings: ElevenLabs, Cartesia, Azure TTS, Google TTS, Coqui,
  on-device
- Example persona: Eliza, hospitality concierge
