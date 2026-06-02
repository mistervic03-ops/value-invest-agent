# Bear Thesis Construction Skill

## Purpose

Use this optional deep-analysis skill to construct the strongest independent bear thesis against the current investment judgment.

This skill is not for adding more risks. It tests whether the investment thesis breaks under a realistic adverse interpretation of the evidence.

This is not a default workflow stage, a generic risk checklist, or a summary of filing risk factors. Invoke it only when bear-case quality can materially improve investment judgment.

Before invoking, answer:

> What decision could change if the strongest realistic bear thesis is true?

If the answer is unclear, do not invoke the skill.

## Invocation Triggers

Use this skill when one or more of the following is true:

- The company is a `BUY` candidate.
- The thesis feels too smooth or too favorable.
- The investment relies heavily on one decision-dominant expectation.
- The primary uncertainty is material but not fully pressure-tested.
- The business is high quality and the analyst may be underweighting valuation or disruption risk.
- The company appears cheap but could be a value trap.
- The existing thesis challenge is generic or weak.

## Non-Triggers

Do not use this skill when:

- The company is already an obvious `PASS`.
- Business understanding is too weak to construct a fair bear thesis.
- The analyst only wants a generic risk list.
- The bear case would be pure speculation unsupported by evidence.
- The decision would not change even if the bear case were stronger.

## Required Inputs

Use already-completed workflow artifacts. Required inputs include:

- Current investment thesis
- Final or provisional decision
- Key variables in decision-importance order
- `.work/numerical_anchors.md`
- Expectation gap
- Normalized owner earnings estimate
- Primary uncertainty
- Strongest available supporting evidence
- Existing error test or thesis challenge if available

If the source base is too weak to build a fair bear thesis, stop and state the limitation.

## Workflow

1. Restate the current bull or base thesis in one sentence.
2. Identify the assumptions that must be true for the thesis to work.
3. Select the 1-3 assumptions most capable of breaking the investment judgment.
4. For each selected assumption, construct the strongest realistic bear interpretation.
5. Build the causal chain:
   - adverse fact or trend
   - business economics impact
   - owner earnings impact
   - valuation or margin of safety impact
   - decision impact
6. Identify whether the bear evidence already exists, is emerging, or is still speculative.
7. Estimate how owner earnings or intrinsic value would change if the bear thesis is right.
8. Ask whether the current price already compensates for this bear case.
9. Decide whether the current investment judgment should be maintained, downgraded, or deferred.

## Output Format

Keep the output short. Use this format:

```text
## Bear Thesis Construction

Invocation reason:

Current thesis in one sentence:

Strongest bear thesis in one sentence:

Broken assumptions:

Bear causal chain:

Existing supporting evidence:

What would have to happen next:

Owner earnings / valuation impact:

Does price compensate for the bear case?

Decision impact: maintain / downgrade / defer

Updated primary uncertainty:

Updates required:
- Key variables:
- Expectation gap:
- Downside owner earnings:
- Primary uncertainty:
- Final decision:
- What would change my mind:
```

Do not paste the full output into the final memo unless it materially improves clarity. Compress the conclusion into the existing thesis challenge, decision, and what-would-change-my-mind sections.

## Failure Modes

- Listing generic risks.
- Creating a strawman bear case.
- Using speculation without evidence.
- Protecting the original conclusion.
- Ignoring that price may already reflect the risk.
- Failing to connect the bear case to owner earnings.
- Confusing temporary volatility with permanent impairment.
- Treating all risks as equally important.
- Treating a severe scenario as likely without evidence.

## Feedback Into Main Workflow

This skill feeds back into existing workflow artifacts only when it changes judgment.

- Key variables: reorder or revise if the bear thesis reveals a more decision-critical failure mode.
- Expectation gap: revise if the bear case makes the gap smaller, larger, negative, or too uncertain.
- Downside owner earnings: add a downside range if the bear thesis changes normalized cash economics.
- Primary uncertainty: update if the bear thesis identifies a sharper uncertainty than the prior one.
- Final decision: maintain, downgrade, or defer only after considering price and margin of safety.
- What would change my mind: add concrete disconfirming or confirming evidence tied to the bear causal chain.

The skill should improve judgment by making the strongest realistic failure mode explicit. It should not make the memo longer unless it makes the decision harder to fool.
