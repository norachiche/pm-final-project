# AI Synthesis, Product Health & Insights Summary (Module 2)

## Responses
- **Assumption to validate #1:** Consumers with variable income struggle to assess affordability, leading to abandoned journeys or repayment agreements they cannot sustain.
- **Assumption to validate #2:** Unclear repayment conditions, inconsistent claim information and insufficient explanations reduce consumer trust and discourage digital self-service.
- **Assumption to validate #3:** Fragmented journeys, technical failures and missing information between the portal and agent systems drive avoidable contact and increase collection costs.
- **Moment of misery / red flag #1 (e.g., “user gave up after 3 tries”):** A shift worker abandons the affordability assessment because she cannot determine which income figure to provide (N-01). Another consumer selects the shortest repayment plan and subsequently misses a payment (N-02). This suggests that unclear affordability guidance can contribute to both abandonment and unsustainable agreements.
- **Moment of misery / red flag #2:** A consumer discovers that the outstanding balance in the portal differs from the amount stated in their letter and refuses to agree to a repayment plan without an explanation (N-07, T-203). Missing explanations about income data and late-payment consequences further undermine trust, potentially pushing consumers towards agent-assisted resolution.
- **Moment of misery / red flag #3:** When a consumer abandons the digital journey and calls an agent, the agent cannot access the information already submitted online and must repeat identity and affordability checks (N-08, T-205). Agents also lack visibility into why repayment plans were offered (N-09), creating duplicated work, longer interactions and limited decision transparency.
- **Product Health & Insights Summary (Claude's output):** Product Health & Insights Summary
Executive Summary

The platform is technically functional at its core, but a cluster of defects and data inconsistencies is eroding the experience at the exact moments where consumers make financial commitments. Consumers abandon or mis-commit because the product asks for sensitive information without context, offers plans without explaining consequences, and shows amounts that contradict official letters. These failures flow downstream into agent workload, client complaint reporting, and compliance exposure, so stability issues and UX issues are compounding one another rather than sitting separately.

Thematic Synthesis
1. Technical Stability

Several defects interrupt the journey mid-flow and force consumers to restart or abandon. The most material is the mobile document upload failure, which affects a large share of journeys. Smaller state-handling and notification bugs add friction at the plan-setup and first-payment stages, where a single failure can lead directly to a missed instalment.

Income document upload timeouts on mobile (large photos): 853 journeys in the sample month requested a document that never arrived. Severity: Critical
Pre-instalment reminder sent after the due date in some cases: removes the safety net ahead of the first payment and compounds missed-payment risk. Severity: High
Back button on the plan review screen clears affordability answers: forces re-entry of sensitive data and risks abandonment. Severity: Medium
2. Onboarding and Plan Setup UX

Consumers are making consequential decisions with ambiguous prompts and incomplete views of their situation. Questions about income lack a defined reference period, plan choice is steered by surface cues (such as the shortest term) rather than affordability, and the portal’s claim-by-claim structure leaves multi-claim consumers unable to see or manage their position as a whole. The result is abandonment, unaffordable plan selection, and missed payments.

Ambiguous income question (current month vs. typical month): observed abandonment among shift workers with variable income. Severity: High
Plan selection based on the lowest term rather than affordability: led to an unaffordable instalment and a missed second payment. Severity: High
No way to set up a single plan across multiple claims (separate claim views only): consumers with two or three open claims cannot see the total picture or understand how paying one affects the other. Severity: High
3. Trust and Clarity

Trust is the most pervasive theme. Consumers hesitate to disclose financial information when they do not know why it is needed, how long it is retained, or whether it could be used against them. Mismatches between portal amounts and letters are especially damaging because they undermine confidence in the digital channel itself, and the effect is concentrated in purchased portfolios. Consumers also receive incomplete information about consequences, including from the chat assistant.

Portal amounts differ from letter amounts: 531 journeys in the sample month, 343 of them purchased portfolio cases (roughly 65%). Consumers withhold agreement until a person explains the discrepancy. Severity: Critical
Chat assistant confirms plans without explaining missed-payment consequences: consumers commit without understanding the risk of paying late. Severity: High
No help text on why income is requested or how long it is retained: fear of misuse of data discourages completion, particularly among consumers in financial hardship. Severity: High
Uncertainty about whether paying one claim stops contact on another: unresolved ambiguity about the effect of payment on collection activity. Severity: Medium
4. Support Load and Operational Visibility

The digital journey is not reducing agent effort as intended, and in places it is adding to it. Agents cannot see what consumers entered online or the rationale behind an offered plan, so they re-collect information and cannot diagnose failures. Some consumers also default to phone contact because they trust a human to explain cost implications, which sustains call volume that the portal was meant to absorb.

Agent screen shows neither consumer-entered data nor plan-offer rationale: repeated data collection on calls and no ability to explain why a plan failed. Severity: High
Preference for phone contact driven by need for cost reassurance: digital deflection is limited by the trust and clarity gaps above. Severity: Medium
5. Commercial, Compliance and Data Context

External stakeholders add constraints that raise the stakes of the issues above. The client evaluates complaints alongside recovery, so broken plans surface directly in client reporting. Compliance requires that any decision be explainable to both consumers and agents, which the current absence of plan-offer rationale does not support. Variable data quality across acquired portfolios also limits how consistently the product can behave.

Broken plans visible in client complaint reporting: reputational and contractual exposure. Severity: High
Decisions must be explainable to consumers and agents (compliance expectation): current lack of visible rationale is a gap. Severity: High
Inconsistent data across acquired portfolios (e.g., unreliable phone and address history): constrains consistency and the reliability of any automated logic. Severity: Medium
Minor Technical Debt

Isolated UI state and messaging inconsistencies, such as input-retention edge cases and minor copy gaps, which individually carry low impact but should be tracked for cumulative effect. Severity: Low

Cross-Cutting Observation

The highest-severity issues share a common pattern: they occur at points of financial commitment or disclosure, where consumers are most sensitive to ambiguity. The two largest quantified problems, upload failures (853 journeys) and amount mismatches (531 journeys), both break the path to a completed, agreed plan, while the qualitative evidence shows that even consumers who complete the journey often do so without confidence in the outcome.
- **Did the AI catch the specific moment of misery / pain point you found in Step 1?:** Yes. Claude identified all three critical pain points: affordability uncertainty leading to abandonment or unsustainable plans, trust breakdown caused by unclear or inconsistent information, and fragmented digital-to-agent handoffs creating duplicated work. It also connected these issues to recovery performance, consumer confidence and operational efficiency.
- **Did it smooth over a critical frustration into a generic bullet point?:** Partially. Claude recognised affordability issues but underemphasised the emotional consequences of financial vulnerability. Consumers fear providing incorrect information or accepting agreements they cannot afford. It also grouped failed repayment plans under UX friction without fully exploring the strategic tension between increasing agreement creation and ensuring sustainable repayment.
- **Did the AI try to suggest features or a roadmap despite the constraints?:** No. Claude respected the constraints and focused on synthesising evidence, identifying recurring problems and assessing severity. It did not introduce feature recommendations or a roadmap.
- **Logic leak / hallucination #1 (e.g., “AI suggested a new search bar feature, roadmap leak”):** Claude introduced a “Minor Technical Debt” category containing unspecified UI and messaging inconsistencies. The source data does not establish these additional low-severity issues. It also describes input-retention problems as minor despite separately identifying the loss of affordability answers as a medium-severity defect.
- **Logic leak / hallucination #2:** Claude classified mobile upload failures and balance discrepancies as Critical without an explicit severity framework or evidence of their full business impact. It also inferred that these issues directly cause abandonment and missed payments, although the data establishes their occurrence rather than their precise causal effects. These conclusions require further validation.
