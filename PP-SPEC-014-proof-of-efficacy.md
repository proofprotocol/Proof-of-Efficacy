# PROOF OF EFFICACY
### A Standards Proposal for Adversarially-Verified AI Agent Behavior

**Version:** 0.1 - Public Draft  
**Issued by:** HACKERverse® / Nebulonium, Inc.  
**Author:** Craig Ellrod, Founder & CEO  
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)  
**Categories first published:** September 2025 (Continuous Autonomous Evaluation, 18 September; Proof Economy, 25 September). Independently archived by the Internet Archive, October 2025.  

---

## Abstract

Existing AI governance frameworks - including the Proof of Control Initiative (POCI), the CSA Autonomous Action Runtime Management (AARM) working group, and Gartner's Adversarial Exposure Validation (AEV) category - address whether AI agents acted within authorized boundaries. None of them address whether AI agents actually worked.

This document proposes Proof of Efficacy (PoE) as a formal standard for cryptographically verifiable evidence that an AI agent demonstrated measurable, adversarially-tested effectiveness under real conditions - timestamped before execution, witnessed independently, and sealed against post-hoc fabrication.

The underlying mechanism is the Defensible Knowledge Proof (DKP) protocol. HACKERverse® first published the Continuous Autonomous Evaluation (CAE) category on 18 September 2025 and the Proof Economy category on 25 September 2025. Both were captured by the Internet Archive on 6 October 2025 and are independently verifiable at the URIs cited in Section 8. Gartner released its Adversarial Exposure Validation (AEV) category on 24 March 2026 - six months later. This proposal is offered as an open standard under CC BY 4.0. Certification authority is retained by HACKERverse® under the ProofStamp mark.

The author, Craig Ellrod, brings more than 30 years of offensive security experience to this standard - spanning system and device testing under adversarial conditions, red team operations, and security validation across Cisco, Armor Defense, JupiterOne, and Cequence Security. Craig's work on test environments and test products, including the System Under Test (SUT) methodology, dates back to 2004 and was documented in his book Technical Marketing. DKP is the formalization of that practice into a cryptographically verifiable, independently witnessed protocol.

## 1. Problem Statement

### 1.1 The Control-Efficacy Gap

The AI governance ecosystem has converged on a common architecture: define what an AI agent is authorized to do, log what it did, and verify that the two match. POCI's five domains - Privacy, Portability, Verifiability, Security, and Identity - operationalize this architecture with cryptographic rigor.

This architecture answers one question: did the agent stay in bounds?

It does not answer: did it work?

An AI agent that executes an authorized action and fails adversarially is indistinguishable, under current frameworks, from one that succeeds. Both produce a valid control proof. Neither produces a proof of efficacy.

### 1.2 Why Efficacy Cannot Be Inferred from Control

Control proof establishes procedural compliance. Efficacy requires adversarial validation. These are structurally different claims:

- A penetration test that completes every authorized step but misses the critical vulnerability produces a valid control log and a false assurance.
- An AI agent that executes an authorized remediation action that fails to neutralize a threat produces a valid POCI Verifiability record and a compromised environment.
- A vendor attestation that an AI system performs at benchmark levels under controlled conditions produces a valid compliance artifact and no evidence of real-world adversarial performance.
Without proof of efficacy, AI governance is a well-documented liability, not a verified capability.

### 1.3 Market Conditions

As of mid-2025, no multi-stakeholder standard for AI agent efficacy verification exists. The Linux Foundation, ISO, NIST, IEEE, and CEN/CENELEC have confirmed the gap in the control domain. The efficacy domain is a superset of that gap.

Without a standard, any vendor can claim its AI agents are effective. With a standard, those claims are testable. This is the same structural condition that motivated the Open Source Initiative's definition work in the late 1990s and POCI's formation in 2025.

## 2. Definitions

The following terms are defined for the purposes of this standard:

| Term | Definition |
|------|------------|
| Continuous Adversarial Evaluation (CAE) | A category first published by HACKERverse® on 18 September 2025 as Continuous Autonomous Evaluation and refined to Continuous Adversarial Evaluation in the 2026 specifications, as the adversarial condition requirement became explicit. Describes always-on, always-running adversarial evaluation of AI agent behavior. CAE has no test cycles, no scheduled windows, and no gaps in observation. Every agent action is evaluated in real time with pre-execution commitment. CAE is architecturally distinct from AEV, which is episodic and bounded by test start and end points. |
| Efficacy | The measurable degree to which an AI agent achieved its intended outcome under adversarial conditions. |
| Adversarial Condition | An environment in which an opposing actor, system, or force is actively attempting to prevent, subvert, or exploit the agent's action. |
| Pre-Execution Commitment | A cryptographic hash of the agent's intended action, submitted to a publicly verifiable randomness beacon before execution begins. This establishes temporal proof that the claim was made before the outcome was known. |
| Proof of Efficacy (PoE) | A cryptographically verifiable record demonstrating that an AI agent's action was committed before execution, witnessed independently, and produced a measurable outcome under adversarial conditions. |
| Defensible Knowledge Proof (DKP) | The five-tier corroboration protocol developed by HACKERverse® that implements PoE: Activated, Committed, Witnessed, Analyzed, Sealed. |
| NIST Randomness Beacon | The NIST Interoperability Beacon, a publicly verifiable source of randomness used as a temporal anchor for pre-execution commitments. |
| ProofStamp | The HACKERverse® certification mark issued upon successful completion of a DKP pipeline, functioning as a verifiable credential anchored in ProofRegister. |
| ProofRegister | The HACKERverse® public registry of sealed DKP records. Contains only cryptographic hash values for each tier - no raw evidence. Publicly queryable. Provides independent verification of issued ProofStamps without exposing corroborating artifacts. |
| ProofVault | The HACKERverse® private artifact store containing the raw corroborating body of evidence for each DKP tier - execution logs, witness signatures, analyst reports, NIST Beacon pulse records, interface capture artifacts, and all supporting documentation. Access-controlled and not publicly exposed. Contents produced on demand for audit, litigation, regulatory review, or certification. |
| Post-Hoc Fabrication | The act of constructing evidence of efficacy after the outcome is known. PoE is architecturally designed to make post-hoc fabrication cryptographically detectable. |

## 3. The Proof of Efficacy Standard

### 3.1 Scope

This standard applies to any AI agent, automated system, or autonomous process that makes claims about its effectiveness in an adversarial environment. This includes but is not limited to:

- AI-powered cybersecurity tools (penetration testing, threat detection, vulnerability assessment)
- Autonomous AI agents executing decisions on behalf of enterprises
- Agentic AI systems operating within AARM-conformant authorization frameworks
- AI vendors making benchmark or performance claims to enterprise buyers
- AI systems operating under regulatory oversight requiring demonstrated capability
### 3.2 Requirements

#### 3.2.1 MUST Requirements

A conformant PoE implementation MUST:

- Submit a cryptographic hash of the intended agent action to the NIST Randomness Beacon or equivalent publicly verifiable randomness source before execution begins (Pre-Execution Commitment).
- Record the beacon pulse value and timestamp at the moment of commitment.
- Execute the action in an environment that includes at least one adversarial condition as defined in Section 2.
- Produce a measurable outcome record that can be independently evaluated against the pre-execution commitment.
- Submit the complete record - commitment, beacon value, execution log, and outcome - to an independent witness for verification.
- Seal the record with a cryptographic hash chain that renders post-hoc modification detectable.
- Publish the sealed record to a publicly queryable registry.
#### 3.2.2 SHOULD Requirements

A conformant PoE implementation SHOULD:

- Use the DKP five-tier corroboration model (Activated, Committed, Witnessed, Analyzed, Sealed) as the implementation framework.
- Anchor sealed records to a public blockchain or distributed ledger for independent verification.
- Include adversarial frameworks, such as MITRE ATT&CK and ATLAS, TTP identifiers for adversarial conditions where applicable.
- Provide machine-readable output compatible with threat intelligence interchanges, such as STIX and TAXII, for threat intelligence integration.
- Align with POCI Verifiability domain requirements where control proof and efficacy proof overlap.
#### 3.2.3 MAY Requirements

A conformant PoE implementation MAY:

- Use ProofStamp as the certification mark upon successful completion.
- Register sealed records in ProofRegister for public query.
- Align with AARM Attested tier requirements for agentic AI authorization contexts.
### 3.3 The DKP Five-Tier Corroboration Model

The Defensible Knowledge Proof protocol implements the PoE standard through five sequential tiers. Each tier is a necessary condition for the next. No tier may be skipped.

> *Note: Sequence markers T0 through T4 are relative indicators of ordering only. They imply no specific timing, duration, or interval between tiers.*

| Tier | Name | Description | ProofRegister (Public Hash Values) | ProofVault (Private Corroborating Evidence) |
|------|------|-------------|-------------------------------------|---------------------------------------------|
| 1 | Activated | The agent is initialized, the adversarial environment is confirmed active, and the intended action is defined. | Session ID hash, environment state hash, agent identity hash. | Agent initialization logs, environment scan artifacts, adversarial condition confirmation. |
| 2 | Committed | A cryptographic hash of the intended action is submitted to the NIST Randomness Beacon before execution. This is the architectural moat: no competitor can replicate this step without having called the shot before execution. | Pre-execution commitment hash, NIST Beacon pulse value and timestamp. | Full intended action specification, Beacon API response record, PCID. |
| 3 | Witnessed | An independent party observes execution in real time and signs the witness record. Witness records are hash-chained to the commitment record. | Witness signature hash, hash-chain link to Tier 2 commitment. | Signed witness record, real-time execution log, interface capture artifacts. |
| 4 | Analyzed | The outcome is evaluated against the pre-execution commitment. Measurable efficacy criteria are applied. The analysis record is signed by an independent analyst. | Analyst signature hash, efficacy verdict hash, hash-chain link to Tier 3. | Signed analyst report, outcome evidence, efficacy measurement data, adversarial condition documentation. |
| 5 | Sealed | The complete record - Activated through Analyzed - is hash-sealed and published to ProofRegister. The seal is publicly verifiable and tamper-evident. | Final sealed hash of the complete Tier 1-4 chain. Publicly queryable. ProofStamp issued. | Complete corroborating artifact bundle for Tiers 1-4. Access-controlled. Produced on demand for audit, litigation, or regulatory review. |

### 3.4 Illustrative Example: Interface Capture Analogy

Security practitioners understand packet capture. The DKP five-tier model maps directly to a wire or wireless packet capture session. Each tier is a frame on the wire. The sequence cannot be spoofed because the NIST Randomness Beacon is an external clock that neither the agent operator nor the vendor controls.

> *Note: Sequence markers T0 through T4 are relative indicators of ordering only. They imply no specific timing, duration, or interval between tiers.*

The critical distinction from a standard behavioral log: a wire or wireless capture records what happened on the medium. DKP T1 proves the intent was declared and externally timestamped before the first frame was captured. A standard compliance log is T2 and T4 only - capture and seal. Without T1, you have a record. With T1, you have proof. A cryptographic hash only seals the misread.

## 4. Agent Class Taxonomy and the Dual Proof Requirement

### 4.1 Two Classes of Agent

Current AI governance frameworks - POCI, AARM, AEV, and every AI security startup building policy engines and guardrails - operate on an implicit assumption: there is one class of agent, the application agent, and the question is whether it behaved according to policy.

This assumption is wrong. There are two distinct agent classes operating simultaneously in any governed AI environment, and they require separate proof regimes.

| Agent Class | Definition | Proof Question |
|-------------|------------|----------------|
| Application Agent | Built to execute a business task. Operates within a defined policy boundary. Subject to authorization, guardrails, and behavioral logging. | Did the application agent behave according to policy? Did it act nefariously, or was it targeted and compromised? |
| Security Agent | Built to protect and govern the application agent. Monitors for nefarious behavior originating from within the application agent and adversarial targeting from without. | Did the security agent actually stop the application agent from going rogue? Did it detect and block external adversarial targeting? How do you know? |

### 4.2 The Gap No One Has Addressed

Every AI governance framework published to date - POCI, AARM, AEV, and the policy engine and guardrail products built around them - addresses the application agent. None of them address the security agent.

The policy engine governs the application agent. The guardrail constrains it. The behavioral log records what it did. None of these mechanisms produce verifiable proof that a security agent was present, activated, and effective before the application agent ran.

This is not a minor gap. It is a categorical omission. Without security agent proof, the entire application agent governance stack rests on an unverified assumption: that the thing protecting the application agent worked. None of them can prove the thing worked.

### 4.3 The Timing Problem

In AI execution time, the interval between agent activation and action completion is measured in nanoseconds. By the time a behavioral log is written and cryptographically stamped, the application agent has already acted. The log tells you what happened. It cannot tell you whether the security agent stopped something from happening.

Post-hoc behavioral logs are forensic artifacts. They are useful for investigation. They are not proof of protection. A cryptographic hash only seals the misread.

The only architecture that answers the security agent question is pre-execution commitment. The security agent must be provably activated and committed - with a NIST Beacon-anchored timestamp - before the application agent runs. Not after. Before.

This is the DKP Committed tier. It is the mechanism no other framework has implemented. It is the reason DKP produces proof of protection rather than proof of what happened after protection may or may not have occurred.

### 4.4 The Dual Proof Requirement

A complete Proof of Efficacy record for any governed AI environment addresses two independent proof chains with different conformance levels:

- Security Agent PoE (MUST): cryptographic proof that the security agent was activated before the application agent ran, detected adversarial conditions, and demonstrably stopped or permitted agent actions under those conditions. This is a mandatory requirement. Without it, no PoE claim is valid.
- Application Agent PoE (MAY): cryptographic proof that the application agent behaved according to policy, was not acting nefariously, and was not successfully targeted by an adversary. This is an optional extension that strengthens the overall proof record.
Neither proof chain substitutes for the other. An application agent that behaved correctly provides no evidence that the security agent worked - the application agent may have behaved correctly because no attack occurred, or because the attack succeeded and the agent was operating under adversary control. A security agent that produced a clean log provides no evidence of what the application agent actually did.

Both chains must be present, independently witnessed, and temporally anchored before execution. This is the Dual Proof Requirement. No current standard imposes it. PoE does.

## 5. Relationship to Existing Frameworks

### 5.1 POCI (Proof of Control Initiative)

POCI establishes cryptographic evidence that AI agents acted within authorized boundaries across five domains: Privacy, Portability, Verifiability, Security, and Identity. PoE is complementary to POCI, not competitive.

The POCI Verifiability domain establishes what an agent did. PoE establishes whether it worked. PoE is a complementary standard that sits above the POCI stack - control without efficacy is a well-documented liability, not a verified capability.

POCI defines three conformance levels:

- Level 1: Self-Declared - the organization documents its cryptographic evidence capabilities and publishes a PoC Conformance Statement.
- Level 2: Third-Party Assessed - an independent qualified assessor validates that the cryptographic mechanisms work as claimed.
- Level 3: Continuously Monitored - cryptographic evidence is generated and validated on an ongoing basis, not assessed at a point in time.

### 5.2 CSA AARM (Autonomous Action Runtime Management)

AARM defines authorization and receipt mechanisms for agentic AI systems. The AARM Attested tier - the highest conformance tier, above Core and Extended - requires independent third-party verification. PoE provides the efficacy verification layer that satisfies Attested tier requirements for demonstrated capability.

HACKERverse® holds a CSA AARM working group seat and has contributed to witness class definitions, chain of custody standards, and hash-chaining requirements within the AARM specification.

### 5.3 Gartner AEV (Adversarial Exposure Validation) and CAE (Continuous Adversarial Evaluation)

Gartner's AEV category, released March 24, 2026, consolidates Breach and Attack Simulation (BAS) and automated penetration testing into a single market category. Gartner explicitly states that AEV replaces both prior categories. AEV is, in practice, a red team penetration test with automation and a new label - episodic, scheduled, and bounded by a start and an end. It is not continuous.

Gartner uses the word 'continuous' in the AEV definition to mean continuously available, not continuously running. There is a meaningful architectural difference between those two claims. An AEV tool that runs on a schedule, completes a validation cycle, and stops is not observing the environment between cycles. The gap between tests is unobserved. Adversarial conditions that arise and resolve in that gap leave no record.

HACKERverse® first published the CAE category on 18 September 2025 - six months before Gartner released AEV, and independently archived three weeks after publication. CAE means always on. Always running. No start, no stop, no gap. The security agent evaluates every action the application agent takes in real time, with pre-execution commitment anchoring each evaluation to the NIST Randomness Beacon before the action occurs. There is no window between tests because there are no tests. There is only continuous runtime observation.

The proof gap in AEV compounds the episodic problem. AEV validates that an attack can succeed or fail during a test window. It does not prove that the security agent governing the application agent was active and committed before the attempt. A clean AEV result proves nothing was exploited during the test. It does not prove the security agent worked. Under DKP, the security agent's pre-execution commitment is anchored before every application agent action, continuously, with no gaps. That is the distinction between a test and a proof.

The Proof Economy category, which DKP implements, was first published by HACKERverse® on 25 September 2025, six months prior to Gartner's 24 March 2026 AEV release.

### 5.4 Zero-Knowledge Proofs

Zero-knowledge proofs (ZKPs) demonstrate that a computation was performed correctly without revealing inputs. DKP demonstrates that a real-world action was performed under adversarial conditions at a specific point in time. These are complementary, not equivalent claims.

ZKP proves computation. DKP proves temporal reality. ZKP cannot establish that an action occurred in the physical world at a specific moment under adversarial conditions. DKP is specifically designed to do this.

## 6. Certification

### 6.1 Standard vs. Certification

This standard is published under Creative Commons Attribution 4.0 International (CC BY 4.0). Any party may implement, reference, or build upon it without restriction, provided attribution is given to HACKERverse® / Nebulonium, Inc.

Certification against this standard - the right to carry the ProofStamp mark - is a separate function retained by HACKERverse®. The standard is open. The stamp is not.

### 6.2 ProofStamp

ProofStamp is the HACKERverse® certification mark issued upon successful completion of a DKP pipeline. ProofStamp functions as both a visual badge and a verifiable credential anchored in ProofRegister. Enterprises, AI vendors, and regulators can independently verify any ProofStamp by querying ProofRegister with the associated record hash.

### 6.3 ProofRegister

ProofRegister is the public registry of sealed DKP records. It is currently live at ProofRegister.com on AWS EC2 with SSL, Python backend, and custom blockchain anchoring node. ProofRegister exposes five tools via MCP: proof_commit, proof_query, proof_verify, coverage_score, and chain_status.

### 6.4 ProofVault

ProofVault is the private, offline storage of corroborating evidence for each DKP tier. ProofVault is not publicly accessible. It contains the raw artifact bundle that supports every sealed hash published in ProofRegister - execution logs, witness signatures, analyst reports, NIST Beacon pulse records, interface capture artifacts, and all supporting documentation generated during the DKP pipeline.

ProofVault contents are produced on demand for audit, litigation, regulatory review, or certification purposes. The separation of public hash records in ProofRegister from private corroborating evidence in ProofVault is the architecture that enables independent public verification without exposing sensitive operational data.

## 7. Governance and Working Group

HACKERverse® invites comment and participation from:

- POCI founding members and the Advanced AI Society
- CSA AARM working group participants
- NIST, ISO, IEEE, and Linux Foundation standards bodies
- Enterprise AI buyers, AI vendors, and independent security researchers
Contributions to this standard that result in adopted specification language will be credited. Contributors do not acquire IP rights to the DKP protocol, ProofStamp mark, or ProofRegister platform.

Working group inquiries: HACKERverse®.ai

## 8. Prior Art and Timeline

Craig Ellrod has been proving efficacy under adversarial conditions since 2004. The foundational concepts behind DKP - System Under Test (SUT), Device Under Test (DUT), and red team adversarial validation - are the product of more than two decades of offensive security practice at Cisco, Armor Defense, JupiterOne, and Cequence. DKP is not a new idea. It is the formalization of that practice into a cryptographically verifiable, independently witnessed, tamper-evident standard.

The following timeline establishes proof of the Proof Economy category and the DKP Protocol:

- 2004: Craig Ellrod begins offensive security practice grounded in adversarial validation of systems and devices under test (SUT/DUT). This constitutes the foundational prior art from which DKP emerges.
- 2004–2025: Twenty-plus years of red team engagements, penetration testing, and adversarial security validation at Cisco, Armor Defense, JupiterOne, and Cequence Security. Each engagement produces informal efficacy proof. DKP formalizes this practice.
- 18 September 2025: Continuous Autonomous Evaluation (CAE) published as a category definition. Archived by the Internet Archive 6 October 2025: https://web.archive.org/web/20251006175845/https://blog.hackerverse.ai/2025/09/18/continuous-autonomous-evaluation-cae-the-next-category-in-cybersecurity/
- 25 September 2025: Proof Economy published as a category definition. Archived 6 October 2025: https://web.archive.org/web/20251006161031/https://blog.hackerverse.ai/2025/09/25/the-proof-economy-proof-is-the-new-currency-hackerverse-at-techcrunch-disrupt/
- 9 October 2025: The CAE Manifesto published. Archived 9 November 2025: https://web.archive.org/web/20251109060700/https://blog.hackerverse.ai/2025/10/09/the-cae-manifesto-welcome-to-the-proof-economy/
- 23 October 2025: The Proof Economy Manifesto published. Archived 9 November 2025: https://web.archive.org/web/20251109065612/https://blog.hackerverse.ai/2025/10/23/the-proof-economy-manifesto/
- 1 January 2026: First independent temporal anchor recorded against NIST Randomness Beacon pulse 1595005, verifiable at https://beacon.nist.gov/beacon/2.0/chain/2/pulse/1595005
- February 28, 2026: Earliest provisional patent application filed (HV-PROV-001). Six total provisional applications filed (HV-PROV-001 through HV-PROV-006), covering the DKP Protocol, Proof Exchange, AgentTwin, and Proof Correlation ID (PCID) architecture. Patent conversion deadlines: February–March 2027.
- March 24, 2026: Gartner releases the Adversarial Exposure Validation (AEV) category - ten months after HACKERverse® coined the Proof Economy and Continuous Adversarial Evaluation (CAE) categories.
- 2025–2026: HACKERverse® holds CSA AARM working group seat and contributes specification language including witness class definitions, chain of custody standards, and hash-chaining requirements.
- May 26, 2026: HACKERverse® registered in DoD CDAO Tradewinds at TRL 7, awardable.
- July 2026: This standards proposal published.
## 9. Contact

Craig Ellrod

Founder and CEO, Nebulonium, Inc. (HACKERverse® / World Hacker Games™)

HACKERverse®.ai | ProofRegister.com

License: Creative Commons Attribution 4.0 International (CC BY 4.0)

> *This document may be freely shared, referenced, and built upon with attribution. Certification rights are retained by HACKERverse®.*
