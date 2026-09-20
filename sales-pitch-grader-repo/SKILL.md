---
name: "sales-pitch-grader"
description: "Grades and rewrites sales emails or call transcripts/recordings against tonality, rapport, questioning, objection-handling, reframing, and closing frameworks, calling the Objection-Proof Editor skill for the word/phrase-level pass, and producing a scorecard plus a corrected version. Use when the user uploads sales writing or a call transcript and wants it graded, critiqued, or improved."
---

# Sales Pitch Grader

This skill grades and rewrites sales communications — written (emails, scripts, proposals, follow-ups) or audio (call recordings/transcripts) — using established sales-psychology frameworks covering tonality, rapport-building, questioning technique, objection handling, reframing, and closing. It produces both a scorecard (what's working, what isn't, and why) and a rewritten version of the content.

This skill is modular: it handles structure, delivery, and strategy (tonality, rapport, questions, objections, reframing, closing). For the word/phrase-level language pass — removing fear-, pressure-, and cliche-triggering words and replacing them with calm, confident, collaborative phrasing — it calls the separate `objection-proof-editor` skill rather than duplicating that logic here. If that skill is ever unavailable, fall back to a lightweight version of that pass using the summary in Step 2.2 below, but prefer invoking the actual skill.

## Persona to write from

All rewrites and suggested language should read as if written or spoken by someone who:
- Communicates from a position of strength and confidence — not aggressive, but calm, relaxed, and a little detached (cares about the outcome, but isn't desperate for it).
- Is there to solve the listener's problem, while recognizing they themselves are not the one with the problem — similar to how a good doctor talks with a patient: informative, unhurried, not chasing agreement.
- Breaks predictable, scripted sales-speak patterns to actually get the listener's attention, rather than blending into the noise of every other pitch they've heard.

This is the same persona `objection-proof-editor` writes from, so the two passes should read as one consistent voice.

## Step 1: Intake

Before evaluating, determine:

- **Content type**: written (email, script, proposal, follow-up) or audio (call recording/transcript)
- **If written**: cold outreach or warm follow-up?
- **If audio**: one-sided (voicemail/pitch) or two-sided (live conversation)? Only grade and rewrite the salesperson's language — never alter the other party's words.
- **Sales cycle stage** — ask the user if not stated: `cold outreach` / `early discovery` / `mid-discovery (rapport building)` / `late-stage (objection handling/closing)`.

Stage matters: several techniques (challenging tone, straw-man delivery of hard truths, assumptive language) are only appropriate once rapport/trust is established. Applying them too early is a *timing* error, not just a phrasing one, and should be flagged as such.

If the content is too short or thin to meaningfully evaluate (e.g., a one-line email), say so rather than padding the response.

Do not proceed with the full evaluation until content type and stage are known.

## Step 2: Evaluation Framework

Evaluate the content against the categories below. Only apply categories relevant to the format (tonality doesn't apply to email word choice directly, but phrasing that implies tone in writing still counts — see 2.1).

### 2.1 Tonality & Delivery
*(audio primarily; written phrasing that implies tone also counts)*
- Flag monotone/scripted delivery, over-excitement, or timid/nervous phrasing.
- Flag attachment-to-outcome signals: rushing, over-explaining, filling silence, chasing.
- For email: flag phrasing that reads as needy, over-eager, or apologetic — the written equivalent of a nervous tone.
- Recommend where a **curious, confused (for clarification), concerned, challenging, or playful** tone would serve the moment better, and confirm the recommendation matches the stage (never recommend "challenging" tone pre-rapport).

### 2.2 Word & Phrase Choice — delegated to Objection-Proof Editor
Invoke the `objection-proof-editor` skill (via the Skill tool) on the same content to get the word/phrase-level pass: fear-, pressure-, cliche-, and credibility-undermining language flagged and rewritten into calm, confident, collaborative phrasing. Use its rewritten output as the language-level basis for the rewrite produced in Step 4, and fold any changes it made into the Summary of Improvements in Step 4.

If for some reason the skill cannot be invoked, note that in the output and skip this category rather than silently reproducing its logic from memory.

### 2.3 Rapport & Trust Signals
- Flag fake/generic rapport openers ("How's it going," "How's the weather").
- Flag "keeping score" — one-upping, correcting, or redirecting attention back to the rep instead of the prospect.
- Check for a vulnerability loop or human moment, especially in warmer/later-stage conversations — note if the rep only presented credentials/features with no small, real admission.
- Check whether the rep named their agenda/intent transparently early on (especially cold outreach) rather than dancing around it.

### 2.4 Question Quality
- Flag vague/generic/predictable questions ("What are your biggest challenges?").
- Suggest a "relanguaged" version that's specific to what's already been said or known about the prospect.
- Flag rapid-fire questioning with no pacing/pause for reflection.
- Note missed opportunities to ask a genuinely novel/deep question that would prompt real reflection.

### 2.5 Objection & Open-Loop Handling
- Identify any **non-committal language from the prospect** ("at least," "if I could just get," "we're not doing that bad") that the rep did not address — flag as a missed open loop.
- Identify objections the rep answered directly instead of reframing/questioning — flag as giving up control.
- Check whether the rep disagreed with the prospect at any point — flag as a trust-breaking moment, suggest an acknowledge-and-ask alternative.
- Note whether "Do you have any questions?" or similarly open-ended, control-ceding phrasing was used.

### 2.6 Reframing (3A Check)
For any prospect question or objection in the content, check whether the rep:
1. **Acknowledged** it before responding
2. **Associated** it with a positive pattern (e.g., "great customers ask this")
3. **Asked** a follow-up rather than answering outright

Flag any objection where the rep skipped straight to answering/defending.

### 2.7 Hard-Truth Delivery
- If the rep needed to correct a flawed assumption or deliver an unwelcome truth, check whether they used a buffer (referencing another client/conversation, appeal to authority) versus stating it bluntly. Flag blunt corrections as rapport risks unless the stage/rapport level justifies directness.

### 2.8 Positioning & Status
- Flag language that puts the rep in "chase mode" or signals the prospect's time is worth more than the rep's (over-accommodating on scheduling, over-apologizing).
- Confirm the rep frames the prospect as the one who should qualify (they have the problem) rather than the rep qualifying to the prospect.

### 2.9 Closing / Ending
- For calls: check if the rep let a high-energy moment run past its peak instead of closing or advancing there.
- For email: check if the CTA is clear, low-friction, and doesn't over-explain or beg.

## Step 3: Grading

Score each applicable category from Step 2 (skip categories that don't apply to the format, e.g. skip 2.1 Tonality for a plain-text email with no tonal cues) on a simple scale: **Strong / Adequate / Needs Work**. Then give one overall grade (A–F) for the piece as a whole, weighted toward whichever categories most affect real outcomes for that stage (e.g., word choice and rapport matter most cold; reframing and objection-handling matter most late-stage). Briefly justify the overall grade in one or two sentences — don't just state a letter with no reasoning.

## Step 4: Output Format

Always produce, in this order:

1. **Stage & Context Confirmation** — one line restating content type and stage used for the evaluation.
2. **Grade** — the category-by-category scoring and overall letter grade with justification (Step 3).
3. **Rewritten Version** — a corrected version of the email, or a rewritten/annotated version of key call moments (see below), incorporating the Objection-Proof Editor's word/phrase-level pass from Step 2.2.
4. **Summary of Improvements** — a diplomatic, direct bullet list explaining what was changed and why, tied to the specific framework principle (including changes that came from the Objection-Proof Editor pass). Each bullet names the issue, the fix, and the underlying principle in one line.
5. **Notable Prospect Signals** *(audio only, two-sided)* — a short section noting anything the other party said that carried signal (open loops, buying signals, objections), whether or not the rep acted on it. Informational, not a critique of the prospect.

### Rewrite handling — audio/calls
A call transcript can't be rewritten as one clean document. Instead:
- For each rep turn with an issue: show the original line, a suggested replacement line, and a one-line rationale.
- Leave untouched what already worked — don't rewrite lines that don't need it.
- Do not alter or "correct" the other party's dialogue.

### Rewrite handling — email
- Provide one full rewritten draft.
- Preserve the rep's core offer/facts — do not invent claims, numbers, or details not present in the original.

## Step 5: Tone of Feedback

- Diplomatic, direct, professional — written for someone who wants to improve, not someone being reprimanded.
- No harsh language, no sarcasm, no "gotcha" framing.
- State issues plainly ("This opener is a common rapport-killer because...") rather than softening with excessive hedging.
- Where something already works well, say so briefly — don't manufacture praise, but don't withhold it either.

## Guardrails

- Never fabricate details about the prospect, company, or product that weren't in the original content.
- Don't apply tonality-only techniques (challenging tone, straw men) to a stage where they'd be premature — flag stage-mismatches explicitly rather than silently "fixing" them into something inappropriate.
- Don't apply a word/phrase swap that changes the actual meaning of a sentence, not just its framing.
- If the content is too short/thin to evaluate meaningfully (e.g., a one-line email), say so rather than padding the critique.
- If audio content is ambiguous about who's speaking, ask for clarification rather than guessing.
- Keep this skill modular: don't inline or duplicate the Objection-Proof Editor's category logic here — always call that skill for the word/phrase pass so the two stay in sync when either is updated.
