---
title: Core Langauge Ontology
nav_order: 1
parent: Full Modelling Specification
layout: default
---

# Core Language Ontology

> **Scope:** A CAE‑style assurance case with an explicit **Risk** extension. The ontology specifies *what* elements exist and *how* they connect to build an assurance case. It is agnostic to metrics, attributes, and assessment/roll‑up semantics.


## 1) Claim

{: .note-title }
> Definition: Claim
>
> A proposition the assurance case seeks to support (e.g., that a property/requirement holds).

**Link rules & cardinalities**

*   **Outgoing**
    *   `Claim —(is_supported_by)→ Argument (exactly 1)`  
        *(Suppressed if the Claim is marked self‑evident; see §12.)*
    *   `Claim —(has_context)→ Context (0..N)`
    *   `Claim —(has_risk)→ Risk (0..N)`
*   **Incoming**
    *   `Argument —(introduces_subclaim)→ Claim (0..N)` *(i.e., this Claim may be a sub‑claim of a parent Argument).*

**Special constraints**

*   **Immediate support is 1:1:** Each non‑self‑evident Claim must have **exactly one** supporting **Argument**; each **Argument** supports **exactly one** parent **Claim** (see §2).
*   **Self‑evident Claims** terminate the branch and have **no Argument** (see §12).

***

## 2) Argument

{: .note-title }
> Definition: Argument
>
> The reasoning step that warrants a (parent) Claim by invoking sub‑claims and/or evidence.

**Link rules & cardinalities**

*   **Outgoing**
    *   `Argument —(introduces_subclaim)→ Claim (0..N)` *(hierarchical decomposition).*
    *   `Argument —(is_supported_by)→ Evidence (0..N)`
    *   `Argument —(has_assumption)→ Assumption (0..N)`
    *   `Argument —(has_justification)→ Justification (exactly 1)`
    *   `Argument —(has_risk)→ Risk (0..N)`
*   **Incoming**
    *   `Claim —(is_supported_by)→ Argument (exactly 1)` *(the parent Claim)*

**Special constraints**

*   **Immediate support is 1:1:** An **Argument** supports **exactly one** parent **Claim**.
*   Sufficiency of support (how much evidence/sub‑claiming is “enough”) is a modelling decision expressed in the **Justification**.

***

## 3) Evidence

{: .note-title }
> Definition: Evidence
>
> Concrete artefacts that substantiate Arguments and/or Mitigations (e.g., test reports, analyses).

**Link rules & cardinalities**

*   **Incoming**
    *   `Argument —(is_supported_by)→ Evidence (0..N)`
    *   `Mitigation —(is_evidenced_by)→ Evidence (0..N)`
*   **Outgoing**
    *   *(None; Evidence does not point to Claims, Risks, or Contexts directly.)*

**Notes**

*   Evidence may be reused across multiple Arguments and Mitigations (many‑to‑many is permitted).

***

## 4) Context

{: .note-title }
> Definition: Context
>
> Scope/boundary information that clarifies a Claim (conditions, definitions, variants, e.g., multiple ODDs).

**Link rules & cardinalities**

*   **Incoming**
    *   `Claim —(has_context)→ Context (0..N)`
*   **Outgoing**
    *   *(None; Context does not link further.)*

**Special constraints**

*   **Attachment restriction:** Context attaches **only to Claims**.
*   Multiple Contexts can attach to a single Claim (variants allowed).

***

## 5) Justification

{: .note-title }
> Definition: Justification
>
> The rationale for an Argument’s structure — why its decomposition and selected evidence are appropriate.

**Link rules & cardinalities**

*   **Incoming**
    *   `Argument —(has_justification)→ Justification (exactly 1)`
*   **Outgoing**
    *   *(None; Justification does not link further.)*

**Special constraints**

*   **Attachment restriction:** Justification attaches **only to Arguments**; exactly one per Argument.

***

## 6) Assumption

{: .note-title }
> Definition: Assumption
>
> A constraint accepted without proof within an Argument’s reasoning (e.g., simplifying parameter, validity bound).


**Link rules & cardinalities**

*   **Incoming**
    *   `Argument —(has_assumption)→ Assumption (0..N)`
*   **Outgoing**
    *   *(None; Assumptions do not carry Evidence directly.)*

**Special constraints**

*   **Attachment restriction:** Assumptions attach **only to Arguments**.
*   Assumptions are justified within the **Argument/Justification** narrative, not by Evidence links.

***

## 7) Risk

{: .note-title }
> Definition: Risk
>
> A threat to the credibility or validity of a Claim or Argument.

**Link rules & cardinalities**

*   **Incoming (exclusive)**
    *   `Claim —(has_risk)→ Risk (0..N)` **or** `Argument —(has_risk)→ Risk (0..N)`  
        *(Each Risk attaches to exactly one parent, either a Claim or an Argument.)*
*   **Outgoing (owned components)**
    *   `Risk —(has_origin)→ Origin (exactly 1)`
    *   `Risk —(has_hazard)→ Hazard (exactly 1)`
    *   `Risk —(has_impact)→ Impact (exactly 1)`
    *   `Risk —(has_mitigation)→ Mitigation (0..N)`

**Special constraints**

*   Risks do not attach to Evidence.
*   A node (Claim or Argument) may have multiple Risks.
*   Risks are separate nodes that must have an Origin, Hazard, Impact, and Mitigation(s).
***

## 8) Origin

{: .note-title }
> Definition: Origin
>
> The source or causal locus of a Risk (e.g., data, model, operation).

**Link rules & cardinalities**

*   **Incoming**
    *   `Risk —(has_origin)→ Origin (exactly 1)`
*   **Outgoing**
    *   *(None.)*

**Special constraints**

*   **Attachment restriction:** Origin exists **only** as a child of a **Risk**.

***

## 9) Hazard

{: .note-title }
> Definition: Hazard
>
> The hazardous condition/event within a Risk.

**Link rules & cardinalities**

*   **Incoming**
    *   `Risk —(has_hazard)→ Hazard (exactly 1)`
*   **Outgoing**
    *   *(None.)*

**Special constraints**

*   **Attachment restriction:** Hazard exists **only** as a child of a **Risk**.

***

## 10) Impact

{: .note-title }
> Definition: Impact
>
> The consequence if the Hazard manifests.

**Link rules & cardinalities**

*   **Incoming**
    *   `Risk —(has_impact)→ Impact (exactly 1)`
*   **Outgoing**
    *   *(None.)*

**Special constraints**

*   **Attachment restriction:** Impact exists **only** as a child of a **Risk**.

***

## 11) Mitigation

{: .note-title }
> Definition: Mitigation
>
> A treatment/control intended to reduce a Risk.

**Link rules & cardinalities**

*   **Incoming**
    *   `Risk —(has_mitigation)→ Mitigation (0..N)`
*   **Outgoing**
    *   `Mitigation —(is_evidenced_by)→ Evidence (0..N)` *(recommended but not mandatory)*

**Special constraints**

*   Evidence for a Mitigation is **optional** in the ontology.

***

## 12) Self‑evident flag (Claim modifier)

{: .note-title }
> Definition: Self-evident Flag
>
> Marks a Claim as self‑evident/true for the purposes of the case.

**Effect on links**

*   **Forbidden:** `Claim —(is_supported_by)→ Argument`
*   **Allowed:** `Claim —(has_context)→ Context (0..N)`
*   **Allowed:** `Claim —(has_risk)→ Risk (0..N)` 
