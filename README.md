# Proof of Efficacy Specification

**Document ID:** PP-SPEC-014  
**Version:** 1.0  
**Status:** Published  
**License:** CC BY 4.0  
**Maintained by:** Proof Economy™ Standards Alliance (PESA)  
**Repository:** https://github.com/proofprotocol  
**Published:** 2026-07-14  
**Companion standard to:** PP-SPEC-006 (Proof of Efficacy Score), PP-SPEC-013 (Proof of Performance)

---

## Abstract

Existing AI governance frameworks address whether AI agents acted within authorized boundaries. None of them address whether AI agents actually worked.

This specification defines Proof of Efficacy (ProofEfficacy™) as a formal standard for cryptographically verifiable evidence that an AI agent demonstrated measurable, adversarially-tested effectiveness under real conditions - timestamped before execution, witnessed independently, and sealed against post-hoc fabrication.

The underlying mechanism is the Proof Protocol™, developed by HACKERverse® in May 2025. HACKERverse® coined both the Proof Economy™ category and the Continuous Adversarial Evaluation™ (CAE) category in May 2025. Gartner released its Adversarial Exposure Validation (AEV) category on March 24, 2026 - ten months later.

The author, Craig Ellrod, brings more than 30 years of offensive security experience to this standard - spanning system and device testing under adversarial conditions, red team operations, and security validation across Cisco, Armor Defense, JupiterOne, and Cequence Security. Craig's work on test environments and test products, including the System Under Test (SUT) methodology, dates back to 2004.

---

## 1. Problem Statement

### 1.1 The Control-Efficacy Gap

The AI governance ecosystem has converged on a common architecture: define what an AI agent is authorized to do, log what it did, and verify that the two match. This architecture answers one question: did the agent stay in bounds?

It does not answer: did it work?

An AI agent that executes an authorized action and fails adversarially is indistinguishable, under current frameworks, from one that succeeds. Both produce a valid control proof. Neither produces a proof of efficacy.

### 1.2 Why Efficacy Cannot Be Inferred from Control

Control proof establishes procedural compliance. Efficacy requires adversarial validation. These are structurally different claims:

- A penetration test that completes every authorized step but misses the critical vulnerability produces a valid control log and a false assurance.
- An AI agent that executes an authorized remediation action that fails to neutralize a threat produces a valid verifiability record and a compromised environment.
- A vendor attestation that an AI system performs at benchmark levels under controlled conditions produces a valid compliance artifact and no evidence of real-world adversarial performance.

Without proof of efficacy, AI governance is a well-documented liability, not a verified capability.

### 1.3 Market Conditions

As of mid-2025, no multi-stakeholder standard for AI agent efficacy verification exists. The Linux Foundation, ISO, NIST, IEEE, and CEN/CENELEC have confirmed the gap in the control domain. The efficacy domain is a superset of that gap.

Without a standard, any vendor can claim its AI agents are effective. With a standard, those claims are testable.

---

## 2. Definitions

| Term | Definition |
|------|-----------|
| Continuous Adversarial Evaluation™ (CAE) | A category coined by HACKERverse® in May 2025 describing always-on, always-running adversarial evaluation of AI agent behavior. CAE has no test cycles, no scheduled windows, and no gaps in observation. Every agent action is evaluated in real time with pre-execution commitment. CAE is architecturally distinct from AEV, which is episodic and bounded by test start and end points. |
| Efficacy | The measurable degree to which an AI agent achieved its intended outcome under adversarial conditions. |
| Adversarial Condition | An environment in which an opposing actor, system, or force is actively attempting to prevent, subvert, or exploit the agent's action. |
| Pre-Execution Commitment | A cryptographic hash of the agent's intended action, submitted to the NIST Randomness Beacon before execution begins. This establishes temporal proof that the claim was made before the outcome was known. |
| ProofEfficacy™ | A cryptographically verifiable record demonstrating that an AI agent's action was committed before execution, witnessed independently, and produced a measurable outcome under adversarial conditions. |
| Proof Protocol™ | The five-tier corroboration protocol developed by HACKERverse®: Activated → Committed → Witnessed → Analyzed → Sealed. The underlying mechanism for ProofEfficacy™. See PP-SPEC-001. |
| NIST Randomness Beacon | The NIST Interoperability Beacon, a publicly verifiable source of randomness used as a temporal anchor for pre-execution commitments. |
| ProofStamp™ | The HACKERverse® certification mark issued upon successful completion of a Proof Protocol™ pipeline. See PP-SPEC-009. |
| ProofRegister™ | The HACKERverse® public registry of sealed Proof Protocol™ records. Contains only cryptographic hash values. Publicly queryable. See PP-SPEC-004. |
| ProofVault™ | The HACKERverse® private artifact store containing the raw corroborating body of evidence for each Proof Protocol™ tier. Access-controlled. Produced on demand for audit, litigation, or regulatory review. |
| Post-Hoc Fabrication | The act of constructing evidence of efficacy after the outcome is known. ProofEfficacy™ is architecturally designed to make post-hoc fabrication cryptographically detectable. |

---

## 3. The ProofEfficacy™ Standard

### 3.1 Scope

This standard applies to any AI agent, automated system, or autonomous process that makes claims about its effectiveness in an adversarial environment. This includes but is not limited to:

- AI-powered cybersecurity tools (penetration testing, threat detection, vulnerability assessment)
- Autonomous AI agents executing decisions on behalf of enterprises
- Agentic AI systems operating within authorization frameworks
- AI vendors making benchmark or performance claims to enterprise buyers
- AI systems operating under regulatory oversight requiring demonstrated capability

### 3.2 Requirements

#### 3.2.1 MUST Requirements

A conformant ProofEfficacy™ implementation MUST:

- Submit a cryptographic hash of the intended agent action to the NIST Randomness Beacon before execution begins
- Record the beacon pulse value and timestamp at the moment of commitment
- Execute the action in an environment that includes at least one adversarial condition as defined in Section 2
- Produce a measurable outcome record that can be independently evaluated against the pre-execution commitment
- Submit the complete record to an independent witness for verification
- Seal the record with a cryptographic hash chain that renders post-hoc modification detectable
- Publish the sealed record to a publicly queryable registry

#### 3.2.2 SHOULD Requirements

A conformant ProofEfficacy™ implementation SHOULD:

- Use the Proof Protocol™ five-tier corroboration model as the implementation framework
- Anchor sealed records to a public blockchain or distributed ledger for independent verification
- Include MITRE ATT&CK and ATLAS TTP identifiers for adversarial conditions where applicable
- Provide machine-readable output compatible with STIX/TAXII for threat intelligence integration

#### 3.2.3 MAY Requirements

A conformant ProofEfficacy™ implementation MAY:

- Use ProofStamp™ as the certification mark upon successful completion
- Register sealed records in ProofRegister™ for public query
- Express efficacy as a PES score per PP-SPEC-006

### 3.3 The Proof Protocol™ Five-Tier Model Applied to ProofEfficacy™

| Tier | Name | Description | ProofRegister™ | ProofVault™ |
|------|------|-------------|---------------|------------|
| 1 | Activated | The agent is initialized, the adversarial environment is confirmed active, and the intended action is defined. | Session ID hash, environment state hash, agent identity hash | Agent initialization logs, environment scan artifacts, adversarial condition confirmation |
| 2 | Committed | A cryptographic hash of the intended action is submitted to the NIST Randomness Beacon before execution. The claim is made before the outcome is known. | Pre-execution commitment hash, NIST Beacon pulse value and timestamp | Full intended action specification, Beacon API response record, PCID |
| 3 | Witnessed | An independent party observes execution in real time and signs the witness record. Hash-chained to Tier 2. | Witness signature hash, hash-chain link to Tier 2 | Signed witness record, real-time execution log, interface capture artifacts |
| 4 | Analyzed | The outcome is evaluated against the pre-execution commitment. Measurable efficacy criteria are applied. The analysis record is signed by an independent analyst. | Analyst signature hash, efficacy verdict hash, hash-chain link to Tier 3 | Signed analyst report, outcome evidence, efficacy measurement data |
| 5 | Sealed | The complete record is hash-sealed and published to ProofRegister™. ProofStamp™ issued. Publicly queryable. Tamper-evident. | Final sealed hash of Tier 1–4 chain. ProofStamp™ issued. | Complete corroborating artifact bundle. Access-controlled. |

### 3.4 The Interface Capture Analogy

Security practitioners understand packet capture. The Proof Protocol™ five-tier model maps directly to a wire or wireless packet capture session. Each tier is a frame on the wire. The sequence cannot be spoofed because the NIST Randomness Beacon is an external clock that neither the agent operator nor the vendor controls.

The critical distinction from a standard behavioral log: a capture records what happened. Tier 2 proves the intent was declared and externally timestamped before the first frame was captured. A standard compliance log is Tier 2 and Tier 4 only - capture and seal. Without pre-execution commitment, you have a record. With it, you have proof.

---

## 4. Agent Class Taxonomy and the Dual Proof Requirement

### 4.1 Two Classes of Agent

Current AI governance frameworks operate on an implicit assumption: there is one class of agent, the application agent, and the question is whether it behaved according to policy. This assumption is wrong.

| Agent Class | Definition | Proof Question |
|-------------|-----------|----------------|
| Application Agent | Built to execute a business task. Operates within a defined policy boundary. Subject to authorization, guardrails, and behavioral logging. | Did the application agent behave according to policy? Was it targeted and compromised? |
| Security Agent | Built to protect and govern the application agent. Monitors for nefarious behavior and adversarial targeting. | Did the security agent actually stop the application agent from going rogue? Did it detect and block adversarial targeting? How do you know? |

### 4.2 The Gap No One Has Addressed

Every AI governance framework published to date addresses the application agent. None of them address the security agent.

The policy engine governs the application agent. The guardrail constrains it. The behavioral log records what it did. None of these mechanisms produce verifiable proof that a security agent was present, activated, and effective before the application agent ran.

Without security agent proof, the entire application agent governance stack rests on an unverified assumption: that the thing protecting the application agent worked.

### 4.3 The Timing Problem

In AI execution time, the interval between agent activation and action completion is measured in nanoseconds. By the time a behavioral log is written and cryptographically stamped, the application agent has already acted. The log tells you what happened. It cannot tell you whether the security agent stopped something from happening.

Post-hoc behavioral logs are forensic artifacts. They are useful for investigation. They are not proof of protection.

The only architecture that answers the security agent question is pre-execution commitment. The security agent must be provably activated and committed - with a NIST Beacon-anchored timestamp - before the application agent runs. Not after. Before.

This is the Proof Protocol™ Committed tier. It is the mechanism no other framework has implemented.

### 4.4 The Dual Proof Requirement

A complete ProofEfficacy™ record addresses two independent proof chains:

- **Security Agent ProofEfficacy™ (MUST):** cryptographic proof that the security agent was activated before the application agent ran, detected adversarial conditions, and demonstrably stopped or permitted agent actions. Mandatory. Without it, no ProofEfficacy™ claim is valid.
- **Application Agent ProofEfficacy™ (MAY):** cryptographic proof that the application agent behaved according to policy, was not acting nefariously, and was not successfully targeted. Optional extension.

Neither proof chain substitutes for the other. Both must be independently witnessed and temporally anchored before execution.

---

## 5. Relationship to Existing Frameworks

### 5.1 Verifiable AI Standards

The emerging landscape of verifiable AI standards addresses whether AI agents acted within authorized boundaries. ProofEfficacy™ is complementary, not competitive. Control proof establishes what an agent did. ProofEfficacy™ establishes whether it worked.

Control without efficacy is a well-documented liability, not a verified capability.

ProofEfficacy™ adds the adversarial validation layer that control frameworks cannot provide by design - they are authorization architectures, not adversarial execution frameworks.

### 5.2 Agentic AI Runtime Governance

Runtime governance frameworks define authorization and receipt mechanisms for agentic AI systems. The highest conformance tiers in such frameworks require independent third-party verification. ProofEfficacy™ provides the efficacy verification layer that satisfies those requirements for demonstrated capability.

### 5.3 Gartner AEV and Continuous Adversarial Evaluation™

Gartner's AEV category, released March 24, 2026, consolidates Breach and Attack Simulation and automated penetration testing into a single market category. AEV is episodic, scheduled, and bounded by a start and an end. It is not continuous.

HACKERverse® coined the Continuous Adversarial Evaluation™ (CAE) category in May 2025 - ten months before Gartner released AEV. CAE means always on. Always running. No start, no stop, no gap. The security agent evaluates every action the application agent takes in real time, with pre-execution commitment anchoring each evaluation to the NIST Randomness Beacon before the action occurs.

The proof gap in AEV compounds the episodic problem. AEV validates that an attack can succeed or fail during a test window. It does not prove that the security agent governing the application agent was active and committed before the attempt. Under the Proof Protocol™, the security agent's pre-execution commitment is anchored before every application agent action, continuously, with no gaps.

### 5.4 Zero-Knowledge Proofs

Zero-knowledge proofs demonstrate that a computation was performed correctly without revealing inputs. The Proof Protocol™ demonstrates that a real-world action was performed under adversarial conditions at a specific point in time. These are complementary, not equivalent claims. ZKP proves computation. Proof Protocol™ proves temporal reality.

---

## 6. Certification

### 6.1 Standard vs. Certification

This specification is published under CC BY 4.0. Any party may implement, reference, or build upon it without restriction, provided attribution is given to Craig Ellrod / Nebulonium, Inc..

Certification against this standard - the right to carry the ProofStamp™ mark - is a separate function retained by HACKERverse® as the independent test lab. The standard is open. The stamp is not.

### 6.2 ProofStamp™

ProofStamp™ is the HACKERverse® certification mark issued upon successful completion of a Proof Protocol™ pipeline. Enterprises, AI vendors, and regulators can independently verify any ProofStamp™ by querying ProofRegister™ with the associated record hash.

### 6.3 ProofRegister™

ProofRegister™ is the public registry of sealed Proof Protocol™ records. Publicly queryable at ProofRegister™.com. Contains only cryptographic hash values - no raw evidence is exposed publicly.

### 6.4 ProofVault™

ProofVault™ is the private, offline storage of corroborating evidence for each Proof Protocol™ tier. Access-controlled. Produced on demand for audit, litigation, regulatory review, or certification purposes. The separation of public hash records in ProofRegister™ from private corroborating evidence in ProofVault™ enables independent public verification without exposing sensitive operational data.

---

## 7. Governance

PESA invites comment and participation from:

- NIST, ISO, IEEE, and Linux Foundation standards bodies
- Enterprise AI buyers, AI vendors, and independent security researchers
- AI runtime governance working group participants
- EU AI Act compliance bodies and equivalent regulatory frameworks

Contributions to this standard that result in adopted specification language will be credited. Contributors do not acquire IP rights to the Proof Protocol™, ProofStamp™ mark, or ProofRegister™ platform.

Working group inquiries: benchmark@proofbenchmark.com

---

## 8. Prior Art and Timeline

| Date | Event |
|------|-------|
| 2004 | Craig Ellrod begins offensive security practice grounded in adversarial validation of systems and devices under test (SUT/DUT) |
| 2004–2025 | Red team engagements, penetration testing, and adversarial security validation at Cisco, Armor Defense, JupiterOne, and Cequence Security |
| May 2025 | HACKERverse® formalizes the Proof Economy™ category. Proof Protocol™ named and architected. CAE category coined. |
| Feb 28, 2026 | Earliest provisional patent application filed (HV-PROV-001). Six total provisionals (HV-PROV-001 through HV-PROV-006). Conversion deadlines February–March 2027. |
| March 24, 2026 | Gartner releases AEV category - ten months after HACKERverse® coined Proof Economy™ and CAE |
| May 26, 2026 | HACKERverse® registered in DoD CDAO Tradewinds at TRL 7, awardable |
| July 14, 2026 | This specification published as PP-SPEC-014 |

---

## 9. Authors

Craig Ellrod, Founder & CEO, Nebulonium, Inc. (d/b/a HACKERverse®)  
Castle Rock, Colorado  
2026-07-14

---

*CC BY 4.0 - Attribution to Craig Ellrod / Nebulonium, Inc. required.*  
*Proof Economy™ Standards Alliance (PESA) - proofprotocol.io*
