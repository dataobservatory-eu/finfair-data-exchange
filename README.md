<!-- badges: start -->

<!-- badges: end -->

# FinFAIR Data Exchange

**Worked examples, RDF projections and interoperability tests for operational Heritage Digital Twins.**

This repository supports the development of interoperable, rights-aware Heritage Digital Twins in the **Finno-Ugric Data Sharing Space (FUDSS)**, with particular attention to alignment with the **ECHOES Heritage Digital Twins Ontology (HDT-O)**, CIDOC CRM and related semantic standards.

The repository provides reproducible examples of how knowledge maintained in Wikibase and reviewed through Betwixt can be represented and exchanged using domain ontologies. It will also host test datasets, validation cases and conformance reports as the interoperability workflow develops.

## Approach

The Finno-Ugric Data Sharing Space uses Wikibase for collaborative knowledge maintenance, Betwixt for provenance-aware knowledge production and review, Apache Jena Fuseki for semantic querying, and Sampo-UI for exploration.

These applications are not themselves Heritage Digital Twins. They provide the operational environment through which knowledge about heritage entities is created, maintained, investigated and governed.

Our approach separates **operational knowledge maintenance** from **ontology-aligned semantic exchange**. Curators can work with familiar Wikibase items and properties, while documented RDF projections make explicit the distinctions required by HDT-O and CIDOC CRM.

The objective is to preserve persistent identities, relevant semantic relationships and provenance without requiring all participating institutions to adopt the same database or application architecture.

## Worked example: Dēliņi farmhouse

The initial example concerns the Dēliņi farmhouse at the Latvian Ethnographic Open-Air Museum and its relationship to the wider farmstead, photographic documentation and the Livonian cultural community.

The example uses persistent Reprexbase identifiers:

| Resource | Wikibase identifier |
|----|----|
| Dēliņi farmhouse digital twin | [Q7328](https://reprexbase.eu/fu/Item:Q7328) |
| Dēliņi farmstead digital twin | [Q5582](https://reprexbase.eu/fu/Item:Q5582) |
| Physical farmhouse (`HC1`) | [Q7376](https://reprexbase.eu/fu/Item:Q7376) |
| Physical farmstead (`HC1`) | [Q7379](https://reprexbase.eu/fu/Item:Q7379) |
| Frontal photograph digital twin | [Q7362](https://reprexbase.eu/fu/Item:Q7362) |
| Oblique photograph digital twin | [Q7363](https://reprexbase.eu/fu/Item:Q7363) |
| Livonians | [Q46](https://reprexbase.eu/fu/Item:Q46) |

### RDF representations

The `ttl/` directory contains three complementary representations:

| File | Purpose |
|----|----|
| [wikibase-Q7328.ttl](ttl/wikibase-Q7328.ttl) | Native Wikibase RDF representation, preserving operational identifiers, properties and statements. |
| [intermediate-Q7328.ttl](ttl/intermediate-Q7328.ttl) | Intermediate representation combining Wikibase statements with ontology annotations and mappings. |
| [hdt-Q7328.ttl](ttl/hdt-Q7328.ttl) | Semantic projection into HDT-O and CIDOC CRM. |

Together, these files illustrate how operational Wikibase knowledge can be projected into an ontology-aligned representation without requiring curators to maintain the complete HDT-O structure directly.

The examples address the distinction between physical heritage entities (`HC1`) and their digital twins (`HC2`), independently identifiable photographic works and their digital representations (`HC5`/`HC7`), and persistent heritage proposition sets (`HC16`).

The examples also demonstrate that semantic projection can involve more than replacing property identifiers. For instance, a heritage relationship maintained operationally on a Wikibase digital twin may need to be expressed as a relationship concerning its represented physical heritage entity.

## Knowledge production and provenance

Betwixt supports the examination, correction and review of candidate propositions before their acceptance into the maintained knowledge graph.

Our proposed workflow distinguishes:

- Candidate propositions and supporting evidence.

- Review activities, decisions and provenance.

- Accepted propositions published as Wikibase statements.

- Persistent `HC16` proposition sets associated with digital twins.

- Former proposition sets and historical review records.

PROV-O provides a basis for describing the agents, activities and resources involved in knowledge production. The exact interoperable representation of proposition-set membership, versioning and review provenance remains an area for further alignment with HDT-O.

## Interoperability testing

This repository is intended to support reproducible testing of RDF projections and exchange representations.

Future materials may include:

- **Test dumps:** controlled Wikibase and Betwixt datasets for reproducing mapping and review scenarios.

- **SHACL validation:** shapes and reports for checking structural and semantic constraints.

- **Positive and negative test cases:** examples with documented expected outcomes.

- **EARL reports:** machine-readable records of interoperability and conformance test results.

- **Exchange packages:** examples combining digital twins, proposition sets, representations, provenance and rights information.

These materials will distinguish between the validity of RDF syntax, consistency with declared ontology semantics, and conformance with any agreed ECHOES exchange profile.

## Status and limitations

**This repository is a development and interoperability-testing resource, not a claim of formal ECHOES conformance.**

The initial Turtle examples illustrate proposed modelling patterns. Some relationships use application-specific predicates, and the HDT-O namespace and class definitions must be aligned with an authoritative, versioned ontology release.

In particular, the classification of contemporary photographic works as `HC1 Heritage Entity` is a temporary modelling accommodation. We propose investigating a more general `Digital Twin` class, with `HC2 Heritage Digital Twin` as a heritage-specific subclass, so that independently governed cultural works do not require prior recognition as heritage.

The repository will distinguish demonstrated implementations from modelling proposals and unresolved interoperability questions.

## Related work

- [Finno-Ugric Data Sharing Space](https://finnougric.net/)

- [Reprexbase Wikibase](https://reprexbase.eu/fu/)

- [Betwixt Vocabulary](https://usebetwixt.com/articles/betwixt-vocabulary.html)

- [CIDOC CRM](https://cidoc-crm.org/)

- [W3C PROV-O](https://www.w3.org/TR/prov-o/)

- [W3C SHACL](https://www.w3.org/TR/shacl/)

- [W3C EARL](https://www.w3.org/TR/EARL10-Schema/)

## Development and contributions

The repository is maintained as part of FinFAIR-related interoperability work by Reprex. Contributions concerning semantic mappings, ontology alignment, reproducible tests and validation are welcome through GitHub issues and pull requests.

The immediate objective is to establish a small, testable reference implementation that can support technical collaboration with ECHOES and other cultural heritage data infrastructures.
