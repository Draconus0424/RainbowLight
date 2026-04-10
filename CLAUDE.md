# CLAUDE.md -- RainbowLight

## Sandbox Rules (MANDATORY -- NO EXCEPTIONS)

**Hard boundary: `~/Desktop/Dev/00 - GitHub/RainbowLight/`**

1. **NEVER read, write, or access any file outside this repo.** This includes CharacterProfiles, CommandCenter, and all other repos. No exceptions, no cross-repo reads, no "just checking."
2. **NEVER reference business context.** No Rebel, no clients, no team members, no revenue, no CC signals. This repo has zero relationship to any business.
3. **NEVER automate any export.** The cp-staging folder in 06-export/ is manually populated by the operator ONLY.
4. **ALL content is maximally private.** Never suggest sharing, publishing, syncing, or pushing to any external system.
5. **Tone: compassionate, observational, non-judgmental.** This is a relationship growth tool. Not clinical, not business, not evaluative.

---

## Project Overview

Structured analysis of couples therapy sessions to track relationship growth, communication patterns, individual development, and therapist insights over time.

**Subjects:** Ethan + Jasmin (+ family sessions: Maya, Tyler)
**Source material:** Weekly therapy session transcripts
**Goal:** Digestible insights, pattern tracking, and growth documentation for the couple

---

## Core Rules

| Rule | Description |
|------|-------------|
| **EXTRACTION FIRST** | No content reaches a profile without a session extraction on record |
| **EVIDENCE-BASED** | Ground observations in quotes, specific examples, dates. Flag interpretation. |
| **ADD, DON'T CONDENSE** | The record grows. Never delete or summarize without explicit approval. |
| **SAVE INCREMENTALLY** | Save after every major section. |
| **BOTH PERSPECTIVES** | Always capture both Ethan's and Jasmin's experience. Never one-sided. |
| **COMPASSIONATE TONE** | Observations are compassionate. No blame language, no scorekeeping, no judgment. |
| **ASCII ONLY** | Plain ASCII characters only. Straight quotes, double-dash, three dots. |

---

## Identity Notes

- "Ethan" in this repo = Ethan Baer (the operator)
- "Jasmin" = Ethan's partner
- "Maya" and "Tyler" = family members appearing in family sessions
- Therapist name should be captured but observations attributed to "the therapist" in profiles

---

## File Structure

```
00-templates/          Extraction scaffold, profile templates
01-sessions/           Per-session extractions (YYYY-MM-DD_Session_NNN.md)
02-profiles/
  Relationship.md      Core relationship profile (the living document)
  Ethan_Growth.md      Ethan's individual journey
  Jasmin_Growth.md     Jasmin's individual journey
03-reference/
  Source_Ledger.md     Processing status of all transcripts
  Session_Timeline.md  Chronological milestones
  Therapist_Recs.md    Recommendations + follow-through tracking
  Framework_Ref.md     Relationship frameworks reference
04-archive/sessions/   Completed extractions after integration
05-sources/PRIVATE/    Raw transcripts (GITIGNORED)
06-export/
  cp-staging/          Manual staging for CP export (operator only)
  EXPORT_LOG.md        Record of all exports
Config/
  council_roster.json  Therapy modality council members
```

---

## Pipeline

```
SOURCE (transcript) -> EXTRACT (session file) -> INTEGRATE (profiles) -> ARCHIVE -> UPDATE REFERENCES
```

No hard gates. Light quality checks. Trust the operator.

---

## Therapy Council

The council system reviews session extractions through multiple therapeutic lenses. Each member represents a major therapy modality and flags what others miss. Council members are defined in `Config/council_roster.json`.

Modes:
- **review**: Analyze a session extraction through all lenses
- **pattern**: Identify recurring patterns across multiple sessions
- **growth**: Assess growth trajectory and highlight progress
- **concern**: Flag potential issues that need attention

---

## CP Export Rules (MANUAL ONLY)

Some Ethan-specific insights may be valuable for his CharacterProfiles business profile. This export is:

1. **Never automated** -- operator manually selects and copies
2. **Staged first** -- goes to 06-export/cp-staging/ with relationship context stripped
3. **Logged** -- every export recorded in EXPORT_LOG.md
4. **One-way** -- CP never reads from this repo
5. **NEVER export:** anything about Jasmin, relationship dynamics, family sessions, therapist recommendations, or session quotes
