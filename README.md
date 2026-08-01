# Meaning Across Representations

**Semantic modelling for boundary-crossing and AI-native network operations.**

A short discussion deck arguing that the many separate conversations across the IETF and IRTF —
AI-consumable YANG, ontology reconciliation, reference lexicons, NAIM, the ONSEN YANG↔TMF bridge,
multi-vendor normalisation, knowledge-graph annotation — point at one common requirement: a
**semantic model**. That is, a model's *meaning* (its ontology, lexicon and pragmatics), made
explicit and independent of form, built *ad hoc* for each bridge rather than standardised as a
universal artefact.

The deck develops the theory (form / meaning / use; why reconciliation is inherently cross-layer),
looks closely at two cases (NAIM vs. ontology reconciliation; the TMF↔YANG bridge), and frames the
resulting research problem: how to support maximally-automated ad hoc semantic-model creation,
reconciliation across systems, and use — with **thin** standardizable supports and **publishable,
reusable** pieces, not a universal model.

## Slides

- [Meaning Across Representations — slides (PDF)](semantic_model_deck.pdf)
- [Editable source (PPTX)](semantic_model_deck.pptx)

## Related drafts

- `draft-janz-nmrg-ontology-reconciliation` — *Automated Agent-to-Agent Ontology Reconciliation for Cognitive Network Management Systems*
- `draft-janz-nmrg-reference-lexicons` — *Shared Reference Lexicons for Agent-to-Agent Model Reconciliation in Network Management*

## Related work (semantic layer in practice)

Two NMOP drafts build a semantic / knowledge-graph layer over existing models — ad hoc and
federated rather than universal — and are concrete instances of the "complementary layer, not a
replacement for YANG" argument made here:

- [`draft-mackey-nmop-kg-for-netops`](https://datatracker.ietf.org/doc/draft-mackey-nmop-kg-for-netops/) — *A Knowledge Graph Framework for Network Operations*
- [`draft-tailhardat-nmop-incident-management-noria`](https://datatracker.ietf.org/doc/draft-tailhardat-nmop-incident-management-noria/) — *Incident Management for Network Operations* (NORIA)

## Comparative reading

A neutral, side-by-side reading of those two knowledge-graph drafts against this deck's contents —
drawing out where they align (declining the universal model; meaning above form; per-case
reconciliation; standardizing only thin supports) and where they genuinely differ (technology
commitment, the treatment of *use* and provenance, and how each handles dynamics):

- [Knowledge Graphs and the Semantic-Model Perspective — a comparative reading (PDF)](kg_vs_semantic_model_comparison.pdf)
- [Editable source (DOCX)](kg_vs_semantic_model_comparison.docx)

## Background & history

A factual reference map of the IETF/NMOP knowledge-graph and semantic-model effort behind those
drafts — the hackathons (YANG2RDF, RML, SIMAP↔NORIA-O), the cluster of related Internet-Drafts,
the NMOP Knowledge Graph Design Team, and the tools, results and findings generated — with
hyperlinks throughout:

- [Knowledge Graphs for Network Operations in the IETF — history, documents, and results](nmop_kg_history.md)
