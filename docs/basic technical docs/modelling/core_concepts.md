---
title: Core Concepts
nav_order: 2
parent: Basics of Modelling
layout: default
---

# Composition of an Assurance Case

An assurance case is not simply lines and boxes on a page; it is a structured argument. This concept is vital - every element that you add has to build your argument. 

The four fundamental components of how you build an assurance case using our Aegis framework are claims, arguments, evidence, and risk. 

| Key Element 	| Definition 	| Visual Representation 	|
|-------------	|------------	|-----------------------	|
| Claim       	|A proposition the assurance case seeks to support (e.g., that a property/requirement holds).    | ![claim](..\..\..\assets\platform_screenshots\claim_clip.png)                |
| Argument    	| The reasoning step that warrants a (parent) Claim by invoking sub‑claims and/or evidence.     | ![argument](..\..\..\assets\platform_screenshots\argument_clip.png)             |
| Evidence    	| Concrete artefacts that substantiate Arguments and/or Mitigations (e.g., test reports, analyses).    |  ![evidence](..\..\..\assets\platform_screenshots\evidence_clip.png)   	      |
| Risk        	| A threat to the credibility or validity of a Claim or Argument.                       | ![risk](..\..\..\assets\platform_screenshots\risk_clip.png)                 |

[Full defintions of the elements and their ontology can be found here](https://docs.synoptix.co.uk/assurance/docs/advanced%20technical%20docs/full_specification/core_ontology.html){: .btn .btn-purple }


## Core Linkage

Claims are the foundation of an assurance case. These are the statements that we are aiming to justify - the core tenets or characteristics of the system of interest that we are trying to convince others that are true. 
The top-level claims that we want to make about a system (e.g. trustworthiness) are large, and have a lot of different aspects. In order to be able to provide meaningful evidence, we have to undertake a structured reasoning process, as we build our argument. To do this, we decompose our claims. 

The only route to decompose a claim is by an Argument. We can think of arguments as a rule that provides the bridge between what we know or are assuming  and the claim we are investigating. From the argument, we can construct a set of sub-claims, assumptions, evidence, or risks that together substantiate the logical step within the argument. 

Evidence is establishes facts against a claim. This can be thought of as the support or rebuttal against the claim. These evidence artefacts should be sufficiently decomposed themselves to make it obvious how the evidence links against the claim. This may require further decomposition of the main argument, until the claims are sufficiently bounded that evidence can be clearly linked against them.
Some claims may be self-evident - meaning that the claim is simply and obviously proven, and no further decomposition is necessary to justify their adequacy.

The final component of the core set of elements is risk. Risks are defeaters or threats to the validity of the justification of the claims - where there is a chance that the claims may not be true. It's important to note that - in any sufficient complex system - there will always be residual risk, even after you've tried to mitigate in. The objective of the assurance case is primarily to surface and quantify these risks, ensure that those approving deployment of the system understand what they are deploying.

![1 stage argument](..\..\..\assets\platform_screenshots\generic_1stage_argument.png)

## Additional elements

Alongside the main elements, there are a number of other allowable elements. 

| Key Element 	| Definition 	| Visual Representation 	|
|-------------	|------------	|-----------------------	|
| Context       	|Scope/boundary information that clarifies a Claim (conditions, definitions, variants, e.g., multiple ODDs).    | ![context](..\..\..\assets\platform_screenshots\context_clip.png) |
| Justification    	| The rationale for an Argument’s structure — why its decomposition and selected evidence are appropriate.     | ![justification](..\..\..\assets\platform_screenshots\justification_clip.png)  |
| Assumption    	| A constraint accepted without proof within an Argument’s reasoning (e.g., simplifying parameter, validity bound).    |  ![assumption](..\..\..\assets\platform_screenshots\assumption_clip.png) |
| Origin        	| The source or causal locus of a Risk (e.g., data, model, operation) - subcomponent of a Risk.          | ![origin](..\..\..\assets\platform_screenshots\origin_clip.png)  |
| Hazard        	| The hazardous condition/event within a Risk - subcomponent of a Risk.  | ![hazard](..\..\..\assets\platform_screenshots\hazard_clip.png)              |
| Impact        	| The consequence if the Hazard manifests - subcomponent of a Risk.          | ![impact](..\..\..\assets\platform_screenshots\impact_clip.png)           |
| Mitigation        	| A treatment/control intended to reduce a Risk - subcomponent of a Risk.   | ![mitigation](..\..\..\assets\platform_screenshots\mitigation_clip.png) |

## Links to Industry Standards

The Aegis framework described here is a variation of the "CAE approach" - more information can be found on https://claimsargumentsevidence.org/. The key variation is the addition of risk elements, which not only allows an AI assurance case to link closely with wider organisational risk management approaches, but also helps with representing "softer" aspects of an AI-specific assurance argument - like ethics, fairness, or legality. 

[Continue to understand how to manage evidence within the model](https://docs.synoptix.co.uk/assurance/docs/basic%20technical%20docs/modelling/managing_evidence.html){: .btn .btn-purple }

[Consider modelling best practice and advice](https://docs.synoptix.co.uk/assurance/docs/basic%20technical%20docs/modelling/modelling_guidance.html){: .btn .btn-purple }