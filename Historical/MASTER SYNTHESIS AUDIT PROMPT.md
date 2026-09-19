MASTER SYNTHESIS AUDIT

Critical Re-evaluation, Synthesis & Prioritization

You are an independent expert reviewer responsible for producing a Master Synthesis Audit of the provided product design and prototype.

You have been given the following evidence package:

1. Original Prototype / Prototype Files
   - All available prototype files, or a ZIP archive containing them if supported.
2. Original Prototype Screenshots
   - All available screenshots showing the current prototype.
3. 9 Unified Audits
   - Nine independent audit reports evaluating the design and prototype.
4. Any original design-system, requirements, or technical information included within the provided materials.

---

CORE OBJECTIVE

Do NOT simply summarize the nine audits.

Do NOT combine recommendations mechanically.

Do NOT use majority voting.

Instead, independently evaluate all provided evidence and produce a single, rigorous Master Synthesis Audit that determines:

- What should be changed.
- What should be preserved.
- What should be rejected.
- What should be validated before making a final decision.
- What should be prioritized.
- Why each decision is justified.

Your conclusions must be based on evidence from the provided materials.

When the evidence is insufficient, explicitly mark the issue as:

"NEEDS VALIDATION"

Do not invent missing requirements, screens, functionality, technical constraints, or product decisions.

If any file cannot be opened, inspected, or understood, explicitly identify it as unavailable and do not claim to have evaluated its contents.

---

1. SOURCE PRIORITY

Evaluate decisions against the original materials first.

Use the following priority order:

1. Original Design / Product Intent
2. Original Requirements
3. Existing Prototype and Screens
4. Technical Constraints and existing functionality
5. The 9 Unified Audits

The 9 audits are evidence and expert opinions, not unquestionable truth.

A recommendation appearing in multiple audits is NOT automatically correct.

A recommendation appearing in only one audit may still be correct if its evidence and reasoning are stronger.

---

2. DECISION CRITERIA

Evaluate every important issue or recommendation using:

Evidence

What concrete evidence supports the conclusion?

User Impact

How does the issue affect usability, clarity, efficiency, trust, accessibility, or task completion?

Product Intent

Does the proposed change support the original purpose and goals of the product?

Design Consistency

Does the decision strengthen or weaken the existing design system and visual language?

Technical Feasibility

Can the change realistically be implemented within the existing prototype and technical constraints?

Cost

How much implementation effort or complexity is likely to be required?

Risk

Could the change introduce new usability, design, technical, or consistency problems?

---

3. IMPORTANT RULES

Follow these rules strictly:

- Do not redesign the product from scratch.
- Do not change the product's fundamental identity without strong evidence.
- Do not change Information Architecture without clear justification.
- Do not add new functionality without evidence or clearly labeling it as an assumption.
- Do not recommend changes simply because they are newer, more modern, more fashionable, or visually attractive.
- Separate confirmed problems from subjective preferences.
- Separate evidence from opinion.
- Preserve successful parts of the design.
- When audits disagree, explain the disagreement and make a reasoned decision.
- If the evidence cannot justify a final decision, use "NEEDS VALIDATION".
- Do not increase the number of changes just to make the audit appear more comprehensive.
- Prioritize the highest-value improvements with the lowest reasonable risk.
- Every significant recommendation must be specific and actionable.
- Avoid vague recommendations such as "improve the UX" or "make it more modern."
- Do not assume that a repeated recommendation is correct simply because it appears frequently.
- Do not ignore evidence from the screenshots or prototype files in favor of audit commentary.
- Base conclusions on the complete evidence package, not on the 9 audits alone.

---

4. DECISION CLASSIFICATION

Classify every important decision using exactly one of these categories:

MUST FIX

A clear, high-impact problem that should be corrected.

SHOULD FIX

A strong and well-supported improvement that is important but not critical.

COULD IMPROVE

An optional lower-priority improvement.

PRESERVE

A successful element that should remain substantially unchanged.

REJECT

A recommendation that is unsupported, inappropriate, contradictory, unnecessarily risky, or inconsistent with the product.

NEEDS VALIDATION

A decision that requires user testing, technical validation, prototype testing, or additional evidence before being finalized.

---

5. AREAS TO EVALUATE

Evaluate the product across all relevant levels:

Design System Foundations

- Colors
- Typography
- Spacing
- Grid
- Borders
- Radius
- Shadows
- Icons
- Design tokens
- Visual consistency

Components

- Buttons
- Inputs
- Forms
- Cards
- Tables
- Navigation
- Dialogs
- Alerts
- Feedback components
- Other reusable UI components

Layout and Hierarchy

- Content hierarchy
- Information density
- Alignment
- Grouping
- Visual priority
- Scannability
- Balance

UX Flows

- Task flow
- Navigation
- Clarity
- Friction
- Number of steps
- User understanding
- Error prevention

Interaction and States

Evaluate relevant states such as:

- Default
- Hover
- Focus
- Active
- Disabled
- Loading
- Empty
- Error
- Success

Responsive Behavior

Evaluate:

- Desktop
- Tablet
- Mobile
- Breakpoints
- Layout adaptation
- Content prioritization
- Component behavior

Accessibility

Evaluate relevant issues including:

- Contrast
- Typography/readability
- Keyboard interaction
- Focus visibility
- Semantic clarity
- Touch target size
- State visibility
- Accessibility-related interaction problems

Technical Implementation

Evaluate whether proposed changes can realistically coexist with the existing implementation and functionality.

---

6. REQUIRED ANALYSIS PROCESS

Perform the following analysis before producing the final report:

1. Extract the core product intent and constraints from the original materials.
2. Inspect the prototype and screenshots carefully.
3. Review all 9 Unified Audits.
4. Identify:
   - Repeated findings
   - Conflicting findings
   - Unique findings
   - Unsupported recommendations
   - Important issues missed by the audits
5. Separate evidence from opinions.
6. Determine what should be preserved.
7. Evaluate each significant recommendation against the original materials.
8. Prioritize decisions using:

"Impact × Confidence × Feasibility"

9. Also assess:
   - Cost: Low / Medium / High
   - Risk: Low / Medium / High
10. Convert accepted decisions into actionable guidance at:

- Component level
- Screen level
- State level

11. Record rejected recommendations and explain why they were rejected.
12. Identify all decisions that require validation.

---

7. REQUIRED REPORT STRUCTURE

Produce the final Master Synthesis Audit using exactly this structure.

A. Executive Decision

Provide a concise executive summary.

Choose one overall direction:

- "Preserve and Refine"
- "Partial Rework"
- "Limited Rebuild"

Explain the reasoning and identify the three most important decisions.

---

B. Product and Design Principles to Preserve

Identify the strongest parts of the existing product and design.

For each, explain:

- What should be preserved.
- Why it is successful.
- What types of modification are acceptable.
- What should not be changed.

---

C. Critical Problems

Use this table:

ID| Problem| Evidence| User / Product Impact| Severity| Decision

Focus on genuine high-impact problems.

---

D. Master Decision Matrix

Use this table:

ID| Area| Specific Decision| Classification| Evidence| User Impact| Design Consistency| Technical Feasibility| Impact| Confidence| Cost| Risk| Source

Use only the six approved classifications:

"MUST FIX"
"SHOULD FIX"
"COULD IMPROVE"
"PRESERVE"
"REJECT"
"NEEDS VALIDATION"

---

E. Required Changes by Priority

Organize accepted changes into:

P0 — Blocking / Must Fix

Changes required before approving the enhanced prototype.

P1 — High-Value Improvements

High-value improvements that should follow P0.

P2 — Optional / Later Improvements

Lower-priority improvements that can be deferred.

For every change specify:

- Objective
- Current problem
- Exact change
- What must remain unchanged
- Reason
- Dependencies
- Risks
- Priority

---

F. Component-Level Specifications

For every affected component, describe:

- Current state
- Problem
- Decision
- Layout
- Spacing
- Typography
- Color
- Dimensions
- Interaction behavior
- Responsive behavior
- Relevant states
- Accessibility requirements
- What to preserve
- What to reject

Be specific enough that a designer or developer could implement the decision without guessing.

---

G. Screen and Flow Changes

Evaluate each affected screen and flow.

For every relevant screen or flow specify:

- Current issue
- Decision
- Hierarchy changes
- Layout changes
- Content priority
- Interaction changes
- Navigation changes
- Flow changes
- Responsive considerations

Do not invent new screens or flows unless supported by evidence.

When assumptions are unavoidable, explicitly label them:

"ASSUMPTION"

---

H. Responsive, Accessibility, and State Requirements

Define actionable and testable requirements for:

- Desktop
- Tablet
- Mobile
- Interaction states
- Loading
- Empty
- Error
- Success
- Accessibility

Requirements should be concrete and testable rather than general advice.

---

I. Explicit Rejection List

List important recommendations that should NOT be implemented.

Use this table:

ID| Rejected Recommendation| Source| Reason for Rejection| Future Validation Needed?

Include recommendations that are:

- Unsupported
- Contradictory
- Excessive
- Unnecessarily risky
- Technically impractical
- Inconsistent with the product
- Purely subjective without sufficient evidence

---

J. Validation Plan

Identify decisions that require validation.

For each validation item specify:

- Decision being tested
- Objective
- Validation method
- What should be measured
- Success criteria
- What result would change the current recommendation

Possible validation methods include:

- Prototype testing
- User testing
- Comparative testing
- Technical validation
- Accessibility validation
- Responsive testing

---

K. Implementation Handoff

Provide direct implementation guidance.

The implementation team should:

- Implement approved decisions only.
- Preserve the original product intent.
- Preserve successful design patterns.
- Preserve required functionality.
- Avoid introducing unrelated redesigns.
- Avoid adding new ideas that were not approved.
- Treat unresolved conflicts as issues to document and validate rather than inventing solutions.

Instructions must be concrete and actionable.

---

L. Open Questions and Assumptions

List every unresolved issue.

For each one specify:

- Question / Assumption
- Why it matters
- Which decisions it affects
- What information or validation is needed

---

M. Final Recommendation

End with a clear decision covering:

Implement

What should definitely be changed.

Preserve

What should remain.

Defer

What should be postponed.

Reject

What should not be implemented.

Validate

What requires additional evidence or testing.

Also state whether the current evidence is sufficient to proceed to the next design-review stage or whether important gaps remain.

---

8. FINAL QUALITY CHECK

Before delivering the audit, verify all of the following:

- You evaluated the original prototype and screenshots, not just the audits.
- You considered all 9 Unified Audits.
- You identified important agreements and disagreements between audits.
- You did not use majority voting.
- Every "MUST FIX" has a clear reason and evidence.
- You clearly identified what should be preserved.
- You recorded important rejected recommendations.
- You separated confirmed decisions from validation decisions.
- Recommendations are specific and actionable.
- Component, screen, state, responsive, and accessibility implications are addressed where relevant.
- You did not invent unsupported functionality or requirements.
- You considered technical feasibility and existing functionality.
- You avoided unnecessary redesign.
- You prioritized impact, confidence, feasibility, cost, and risk.
- The report is independently reasoned and does not merely summarize the nine audits.
- You explicitly identified any file that could not be opened, inspected, or understood, and did not claim to have evaluated unavailable content.

---

FINAL INSTRUCTION

Produce one comprehensive, independent Master Synthesis Audit based on the complete evidence package.

Do not merely summarize the nine audits.

Do not vote between them.

Do not blindly accept their recommendations.

Critically evaluate the original materials and the nine audits together, resolve conflicts through evidence and reasoning, preserve what works, identify what must change, reject what should not change, and clearly identify what requires validation.

The final result must be a practical, evidence-based decision document that can directly guide the next stage of design refinement and prototype improvement.