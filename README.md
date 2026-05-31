<!--
SPDX-FileCopyrightText: 2026 KMSEC GmbH
SPDX-License-Identifier: EUPL-1.2
-->

# libenio PROPEL

**P**recompiled · **R**eusable · **O**pen · **P**rofile · **E**ngine · **L**ibrary

A high-performance, profile-agnostic validation engine for HL7® FHIR®. libenio PROPEL
precompiles FHIR profile constraints into a fast, static validation kernel — turning
repeated, interpretation-heavy conformance checks into reusable, ahead-of-time compiled
artifacts. The result is dramatically faster validation that stays open, embeddable and
pluggable into any toolchain.

> **Status:** Early development. This repository is the public home of libenio PROPEL.


## Why

FHIR validation against profiles (StructureDefinitions, constraints, terminology bindings)
is computationally expensive because conventional validators interpret profile rules at
runtime, on every validation. At scale — bulk ingestion, conformance gates in CI, national
exchange platforms — this becomes a real bottleneck.

libenio PROPEL takes a different approach: it **compiles** profile constraints **once** into
an optimized validation kernel that can then be executed repeatedly at a fraction of the cost.
Because the compiler is **profile-agnostic**, the same engine applies to any national or
cross-border FHIR profile set.

## Key properties

- **Fast** — ahead-of-time compilation removes per-validation rule interpretation overhead.
- **Open** — released under the EUPL-1.2, developed in the open.
- **Reusable** — compiled profile kernels are cacheable, shareable artifacts.
- **Pluggable** — designed to embed into existing pipelines, servers and CI gates.
- **Profile-agnostic** — not tied to a single jurisdiction's profile set.

## Profile coverage

The reference profile set used during development is **ISiK** (*Informationstechnische Systeme
in Krankenhäusern*), the FHIR profile family mandated by gematik in Germany. ISiK serves as a
stable, freely available benchmark for constraint coverage.

Because the engine is profile-agnostic, it applies directly to other FHIR profile sets,
including the **European Electronic Health Record Exchange Format (EEHRxF)** under the
**European Health Data Space (EHDS)** — Regulation (EU) 2025/327 — which builds on HL7 FHIR
and will become a mandatory interoperability format for EHR systems on the EU market.

## Getting started

> Detailed build and usage instructions will be published as the public releases mature.

```bash
# Clone
git clone https://github.com/<org>/libenio-propel.git
cd libenio-propel
```

Build and run instructions, supported FHIR versions and integration examples will be
documented in the [`docs/`](docs/) directory.

## Contributing

This repository is published as the public, open-source home of libenio PROPEL. Development
happens primarily on KMSEC GmbH's internal infrastructure and is mirrored here at defined
release points. Issues and questions are welcome via the issue tracker; for substantial
contributions, please open an issue first so we can coordinate how to integrate changes back
into the upstream source.

## License

Licensed under the **EUPL-1.2** (European Union Public Licence v. 1.2).
See the [`LICENSE`](LICENSE) file for the full text.

```
SPDX-License-Identifier: EUPL-1.2
Copyright © 2026 KMSEC GmbH
```

The EUPL is an OSI-approved, copyleft free/open-source licence created and approved by the
European Commission, available in all 23 official EU languages with identical legal value.

## Acknowledgements



---

*HL7® and FHIR® are registered trademarks of Health Level Seven International. Use of these
trademarks does not constitute an endorsement by HL7.*
