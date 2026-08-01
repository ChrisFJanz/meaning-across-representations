# Knowledge Graphs for Network Operations in the IETF
### History, key documents, and results — a reference summary

*Compiled for discussion. All links are public IETF Datatracker, mail-archive, or project pages.*

This note traces the IETF/NMOP work on **knowledge graphs and semantic models for network
operations and incident management**: how it developed across several IETF hackathons, the
Internet-Drafts it produced, the design team that was chartered to shape it, and the tools,
results and findings generated along the way. It is intended as a factual map for anyone picking
up the topic — including the two drafts most often cited, `draft-mackey-nmop-kg-for-netops` and
`draft-tailhardat-nmop-incident-management-noria`.

---

## 1. In brief

Beginning around IETF 119 (2024), several NMOP participants converged on the idea of building a
**semantic / knowledge-graph layer over existing network data** — lifting YANG (and IPFIX, BMP,
syslog, TMF and other sources) into RDF/OWL so that relationships and meaning across silos can be
expressed, queried and reasoned over. The common posture, stated repeatedly, is that this is a
**complementary layer, not a replacement for YANG**, built ad hoc and federated rather than as a
universal model. The effort ran through a sequence of hackathons, produced a cluster of
Internet-Drafts, and in mid-2025 was formalised as an **NMOP Knowledge Graph Design Team**. The
team demonstrated proofs-of-concept (notably fusing the SIMAP topology work with the NORIA-O
incident ontology), agreed that the individual drafts would proceed **independently but
complementarily**, and — per current word from participants — has since wound down its regular
meetings.

## 2. Timeline

| When | Event | Materials |
|---|---|---|
| IETF 119 — Mar 2024, Brisbane | Hackathon: semantic metadata annotation + anomaly detection ("Antagonist") | [ietf119 project presentations](https://github.com/IETF-Hackathon/ietf119-project-presentations) |
| IETF 120 — Jul 2024, Vancouver | Hackathon: "Antagonist" (anomaly tagging on historical data) | [slides](https://datatracker.ietf.org/meeting/120/materials/slides-120-hackathon-sessd-antagonist-anomaly-tagging-on-historical-data) |
| IETF 121 — Nov 2024, Dublin | Hackathon: **YANG2RDF** (YANG → RDF transformer) | [slides](https://datatracker.ietf.org/meeting/121/materials/slides-121-hackathon-sessd-yang-2-rdf-01) · [code](https://github.com/Huawei-IOAM/yang2rdf) |
| IETF 122 — Mar 2025, Bangkok | Hackathon: **Transforming Network Data to RDF using RML** | [slides](https://datatracker.ietf.org/meeting/122/materials/slides-122-hackathon-sessd-transforming-network-data-to-rdf-using-rml-rdf-mapping-language-00) |
| 21 May 2025 | **NMOP interim on Knowledge Graphs** — KG tutorial (R. Troncy), business case (B. Claise), three drafts, next-steps brainstorming | [agenda](https://datatracker.ietf.org/doc/agenda-interim-2025-nmop-03-nmop-01/) |
| 1–2 Jul 2025 | **Knowledge Graph Design Team** chartered by NMOP chair (R. Rahman); kickoff 1 Jul | [announcement](https://mailarchive.ietf.org/arch/msg/nmop/7s4Y6pbFtVrdjvtlwsPm95jUSVc/) |
| IETF 123 — Jul 2025, Madrid | Design-team consensus: build an initial SIMAP + NORIA-O PoC; identify value-demonstrating use cases | (reported in the IETF 124 update) |
| IETF 124 — Nov 2025, Montreal | Hackathon PoCs (SIMAP path computation; SIMAP + NORIA-O fusion); **design-team update** to the WG | [DT update](https://datatracker.ietf.org/meeting/124/materials/slides-124-nmop-sessb-5-knowledge-graphs-design-team-update-00) · [SIMAP hackathon](https://datatracker.ietf.org/meeting/124/materials/slides-124-nmop-simap-hackathon-result-00) · [WG minutes](https://datatracker.ietf.org/meeting/124/materials/minutes-124-nmop-202511051930-00) |
| After IETF 124 | Design team resolves drafts proceed independently; regular meetings wind down | — |

## 3. Internet-Drafts (the cluster)

The effort produced, or drew together, several related drafts. The first two are the ones most
often referenced; the others show the breadth of the KG work in NMOP.

- [`draft-mackey-nmop-kg-for-netops`](https://datatracker.ietf.org/doc/draft-mackey-nmop-kg-for-netops/) — *A Knowledge Graph Framework for Network Operations* (M. Mackey, Huawei). An RDF layer connecting data across management/control/data planes; "a complementary layer," not a replacement for YANG.
- [`draft-tailhardat-nmop-incident-management-noria`](https://datatracker.ietf.org/doc/draft-tailhardat-nmop-incident-management-noria/) — *Knowledge Graphs for Enhanced Cross-Operator Incident Management and Network Design* (L. Tailhardat, Orange / Eurecom). The NORIA-O incident ontology; YANG lifted to RDF/OWL and reconciled by alignment.
- [`draft-marcas-nmop-kg-construct`](https://datatracker.ietf.org/doc/draft-marcas-nmop-kg-construct/) — *Knowledge Graph Construction from Network Data Sources* (N. Dominguez et al.).
- [`draft-marcas-nmop-knowledge-graph-yang`](https://datatracker.ietf.org/doc/draft-marcas-nmop-knowledge-graph-yang/) — *Knowledge Graphs for YANG-based Network Management*.
- [`draft-pang-nmop-kg-for-traffic-monitoring-analysis`](https://datatracker.ietf.org/doc/draft-pang-nmop-kg-for-traffic-monitoring-analysis/) — *Knowledge Graph for Network Traffic Monitoring and Analysis*.

## 4. Hackathon projects and results

- **YANG2RDF** (IETF 121). A transformer converting YANG models to RDF triples via an Eclipse
  Modeling Framework (EMF) intermediate representation, an RDF serializer, and SPARQL
  normalisation rules, with deterministic IRI translation based on XPATH and full YANG-grammar
  coverage. Reported result: a Huawei ne40e-x8x16 device configuration produced **277,329
  triples**. Participants: M. Mackey, A. Pererva, B. Claise (Huawei).
  [slides](https://datatracker.ietf.org/meeting/121/materials/slides-121-hackathon-sessd-yang-2-rdf-01) ·
  [code: Huawei-IOAM/yang2rdf](https://github.com/Huawei-IOAM/yang2rdf)

- **Transforming Network Data to RDF using RML** (IETF 122). Using the RDF Mapping Language (RML)
  to map network configuration/state data into RDF, as an alternative/complement to the
  code-based YANG2RDF path.
  [slides](https://datatracker.ietf.org/meeting/122/materials/slides-122-hackathon-sessd-transforming-network-data-to-rdf-using-rml-rdf-mapping-language-00)

- **SIMAP + NORIA-O fusion** (IETF 124, design team). A proof-of-concept fusing the SIMAP
  (Service & Infrastructure Map) work with the NORIA-O incident ontology — model mappings showing
  concept alignments and example queries linking IETF YANG-derived data with an external incident
  application ontology.
  [design-team update](https://datatracker.ietf.org/meeting/124/materials/slides-124-nmop-sessb-5-knowledge-graphs-design-team-update-00)

- **SIMAP physical-path computation** (IETF 124). A related hackathon result: an algorithm
  computing SRv6 physical packet paths over an RFC 8345 topology graph (MicroSID support;
  link enable/disable), run across Swisscom and Telefónica labs; identified RFC 8345 extensions
  (order, preference, weight). Presented by O. Havel et al.
  [slides](https://datatracker.ietf.org/meeting/124/materials/slides-124-nmop-simap-hackathon-result-00)

- **Antagonist** (ANomaly TAGging ON hISTorical data) — IETF 119/120/121. Semantic metadata
  annotation and anomaly detection/tagging over historical operational data; adjacent to, and
  feeding, the KG work.
  [ietf119 presentations](https://github.com/IETF-Hackathon/ietf119-project-presentations)

An index of NMOP-related hackathons is maintained on the WG wiki:
[NMOP-related Hackathons](https://github.com/ietf-wg-nmop/Misc/wiki/NMOP%E2%80%90related-Hackathons).

## 5. The Knowledge Graph Design Team

Chartered by NMOP chair **Reshad Rahman** on 1–2 July 2025 "to propose a realistic plan for what
the deliverables should be," against the usual tests (a demonstrated problem, critical mass,
well-defined scope, agreed deliverables, reasonable probability of success). Initial appointees
(alphabetically): **Benoit Claise, Nacho Dominguez, Pauline Folz, Thomas Graf, Michael Mackey,
Brad Peters, Lionel Tailhardat, Dan Voyer** — later broadening to roughly a dozen participants
across Huawei, Cisco, Orange, Telefónica, Swisscom, Eurecom and Adapt.

- Formation announcement:
  [\[NMOP\] Knowledge Graph Design Team](https://mailarchive.ietf.org/arch/msg/nmop/7s4Y6pbFtVrdjvtlwsPm95jUSVc/)
- Team's own summary of progress and position (IETF 124):
  [Knowledge Graphs Design Team update](https://datatracker.ietf.org/meeting/124/materials/slides-124-nmop-sessb-5-knowledge-graphs-design-team-update-00)

**Agreed position.** The design team's conclusion — consistent with what participants report — is
that the individual drafts (`kg-for-netops`, `kg-construct`, `noria`) proceed as **independent but
complementary** efforts rather than being merged, with a possible shared output being "a core set
of properties and relationship definitions" to support agreed use cases. As of the IETF 124
update the team was still meeting, with open questions on scope, concrete deliverables, and the
probability of timely charter completion; regular meetings have since wound down.

## 6. Tools and artefacts generated

- **`yang2rdf`** — open-source YANG→RDF transformer (EMF + RDF serializer + SPARQL rules;
  deterministic XPATH-based IRIs). [github.com/Huawei-IOAM/yang2rdf](https://github.com/Huawei-IOAM/yang2rdf)
- **RML mappings** — declarative RDF Mapping Language mappings for network data → RDF (IETF 122).
- **NORIA-O** — the NORIA incident-management ontology (RDFS/OWL) and associated `YANG2OWL` /
  `JSON2RDF` tooling from the NORIA line of work (Orange / Eurecom).
  [NORIA-O project pages](https://genears.github.io/)
- **SIMAP ↔ NORIA-O mappings and example SPARQL queries** — the IETF 124 fusion PoC linking IETF
  YANG-derived data to the incident ontology.
- **Antagonist** — anomaly tagging/annotation tooling over historical data.

## 7. Key findings and recurring themes

- **Complementary, not a replacement.** Across the drafts and the team, the knowledge graph is
  positioned as a layer that *connects* existing models and recovers meaning from the connections
  — not a new or universal model. Reconciliation is done per-case, by alignment, "without
  requiring a priori universal consensus."
- **Scale is real but manageable.** Concrete figures were reported: a single device dump yielded
  hundreds of thousands to millions of triples (277k triples for one ne40e config; ~7M triples for
  a raw lab dump), with **storage/cost** flagged as the primary concern over raw ingestion rate.
  Event-stream work reported ~5k events/min bursts with roughly a x10 event-to-triples ratio.
  [performance discussion (mail thread)](https://mailarchive.ietf.org/arch/msg/nmop/tOwZ5xFxQtF5JkLFg8i10bNyuyM/)
- **Standardize thin, connect the rest.** The standardizable targets discussed are connective
  supports — import/mapping formats (YANG/IPFIX/BMP → RDF), deterministic IRIs, alignment and
  provenance conventions — rather than a master schema.
- **Use cases.** The team's value-demonstrating use cases include anomaly management, API data
  tracking, and change coordination, plus cross-operator incident-signature sharing (NORIA).
- **Governance is the open question.** Who maintains the shared ontologies and mappings is
  explicitly noted as unresolved.

## 8. Meeting records and further reading

- NMOP interim — Knowledge Graphs (21 May 2025):
  [agenda](https://datatracker.ietf.org/doc/agenda-interim-2025-nmop-03-nmop-01/)
- IETF 124 NMOP session minutes:
  [minutes](https://datatracker.ietf.org/meeting/124/materials/minutes-124-nmop-202511051930-00)
- NMOP mailing-list archive: [mailarchive.ietf.org/arch/browse/nmop/](https://mailarchive.ietf.org/arch/browse/nmop/)
- NMOP hackathons index (wiki):
  [NMOP-related Hackathons](https://github.com/ietf-wg-nmop/Misc/wiki/NMOP%E2%80%90related-Hackathons)
- External NORIA references: [KG4DI 2024 (DMOps)](https://genears.github.io/pubs/KG4DI-2024-DMOps.pdf) ·
  [CEUR Vol-3471 paper 3](https://ceur-ws.org/Vol-3471/paper3.pdf)

## 9. Caveats on sourcing

Formal, per-meeting **minutes of the design team's own calls** do not appear to be published
separately; the documented public record is the May 2025 interim session, the IETF 124
design-team update deck, and the NMOP working-group minutes. Dates and locations above follow the
standard IETF meeting calendar; where a specific claim rests on a single slide or email it is
linked inline so it can be checked. If per-call design-team notes or a shared working document
exist, they are most likely in the nmop list archive or a team-private document.
