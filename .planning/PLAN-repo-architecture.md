# RainbowLight -- Repo Architecture Plan

**Purpose:** Structured analysis of couples therapy sessions to track relationship growth, communication patterns, individual development, and therapist insights over time.

**Operator:** Ethan Baer
**Subjects:** Ethan + Jasmin (+ family sessions: Maya, Tyler)
**Privacy:** MAXIMUM -- no cross-repo automation, no external sync, no Notion, no remote pushes without explicit approval.

---

## Core Principles (Adapted from CharacterProfiles)

### What We Keep
- **Extraction-first pipeline:** Source -> Extract -> Build. No content reaches a profile without a formal extraction.
- **Evidence-based observations:** Ground everything in quotes, specific examples, dates. No speculation without flagging it.
- **ADD, DON'T CONDENSE:** The record grows. Never delete or summarize without approval.
- **ASCII only:** Plain text, no formatting accidents.
- **Save incrementally:** Crash protection.
- **Source tracking:** Know what's been processed and what hasn't.

### What We Change
- **No personality frameworks** (Big Five, TKI, etc.) -- replace with relationship frameworks (Gottman, attachment theory, communication patterns)
- **No business context** -- no CC signals, YouTube KB, client registry, Notion sync, dashboard
- **No multi-subject extraction** -- every session has the same subjects (Ethan + Jasmin, sometimes + family)
- **Simpler pipeline** -- no Gate 1/2/3 ceremony. Trust the operator. Light quality checks.
- **Different tone** -- this is personal. Observations should be compassionate, not clinical.
- **Relationship as the primary "profile"** -- not individual profiles. The relationship IS the entity.

### What We Add
- **Session-over-session tracking** -- trends, not just snapshots
- **Therapist recommendation tracking** -- did we follow through?
- **Selective CP export** -- operator-controlled, manual, one-way staging area for Ethan-specific insights

---

## File Structure

```
RainbowLight/
  CLAUDE.md                              # Repo rules, isolation enforcement, tone guidance
  README.md                              # What this is (private)

  00-templates/
    Session_Extraction_Scaffold.md       # Per-session extraction guide
    Relationship_Profile_Template.md     # The relationship as a living document
    Individual_Growth_Template.md        # Per-person growth tracking
    Family_Session_Scaffold.md           # For sessions with Maya/Tyler

  01-sessions/
    YYYY-MM-DD_Session_NNN.md            # Extracted session analysis (one per session)

  02-profiles/
    Relationship.md                      # THE core document -- relationship patterns, growth, dynamics
    Ethan_Growth.md                      # Ethan's individual journey as observed in sessions
    Jasmin_Growth.md                     # Jasmin's individual journey as observed in sessions

  03-reference/
    Source_Ledger.md                     # Tracking what's been processed
    Session_Timeline.md                 # Chronological milestones and arcs
    Therapist_Recommendations.md        # All recommendations + follow-through status
    Framework_Reference.md              # Relationship frameworks used for analysis

  04-archive/
    sessions/                           # Completed session extractions (after integration)

  05-sources/
    PRIVATE/                            # Raw transcripts (gitignored)

  06-export/
    cp-staging/                         # Ethan insights staged for manual CP export
    EXPORT_LOG.md                       # Record of what was exported when

  .claude/
    settings.json                       # Permissions (strict)
    hooks/                              # Minimal -- no ceremony gate needed
```

---

## Extraction Scaffold (Session_Extraction_Scaffold.md)

Each session transcript gets extracted into these sections:

### Part 1: Session Metadata
- Date, session number, therapist name
- Session type (couples / individual / family)
- Emotional temperature going in (both people, 1-10)
- Emotional temperature coming out (both people, 1-10)
- One-line session summary

### Part 2: Topics Discussed
- Bullet list of major topics with approximate time spent
- Which topics were new vs recurring

### Part 3: Key Exchanges
- Significant dialogue captured with context
- Quote tiering: BREAKTHROUGH (rare, pivotal) / MEANINGFUL (important) / NOTED (worth recording)
- Who said it, how it landed, what it revealed

### Part 4: Communication Observations
- Patterns observed (who initiates, who deflects, who repairs)
- Effective communication moments (what worked)
- Friction points (where communication broke down)
- Therapist interventions during communication breakdowns

### Part 5: Conflict & Repair
- What triggered conflict (if any)
- How it escalated or de-escalated
- Repair attempts (who, when, how, did it work?)
- Unresolved threads carried forward

### Part 6: Breakthroughs & Growth
- Aha moments (specific, with quotes)
- Behavioral shifts observed since last session
- New understanding expressed by either person
- Vulnerability moments (who opened up, about what)

### Part 7: Therapist Insights
- Professional observations made during session
- Frameworks or concepts introduced
- Homework / action items assigned
- Recommendations for between sessions

### Part 8: Individual Observations

**Ethan:**
- Emotional patterns observed
- Growth indicators vs previous sessions
- Triggers identified or confirmed
- Strengths demonstrated
- Areas the therapist highlighted

**Jasmin:**
- Same structure as above

### Part 9: Relationship Health Indicators
- Trust signals (positive and concerning)
- Intimacy / connection moments
- Shared goals discussed or reinforced
- Alignment vs misalignment areas
- Overall trajectory (improving / stable / concerning)

### Part 10: Session Report
- Coverage: what % of session was captured
- Self-check (all topics covered? all participants represented?)
- Carry-forward items for next session

---

## Relationship Profile Structure (Relationship.md)

The living document that grows with every session extraction:

### 1. Relationship Summary
- How long together, when therapy started
- Core strengths of the relationship
- Core growth areas
- Current phase / focus

### 2. Communication Map
- What works (proven patterns)
- What doesn't (known friction patterns)
- Repair strategies that succeed
- Triggers for each person
- Communication evolution over time

### 3. Conflict Patterns
- Recurring themes (with dates of each occurrence)
- Resolution strategies that work
- Escalation patterns to watch for
- Unresolved long-term threads

### 4. Growth Timeline
- Session-by-session trajectory markers
- Major breakthroughs with dates
- Behavioral changes observed over time
- Regression patterns (if any)

### 5. Shared Values & Vision
- Agreed-upon values
- Shared goals (short and long term)
- Areas of alignment
- Areas of productive disagreement

### 6. Attachment & Dynamics
- Attachment patterns observed
- Roles each person tends to play
- Power dynamics
- Dependency / independence balance

### 7. Therapist Arc
- How the therapist's approach has evolved
- Key frameworks introduced and when
- Cumulative recommendations
- What the therapist has praised vs flagged

### 8. Appreciation Log
- Specific moments of gratitude expressed in sessions
- Acts of care noted by therapist or partner
- Positive patterns that should be reinforced

### 9. Version History
- Sources integrated, dates, session counts

---

## CP Export Process (MANUAL, OPERATOR-ONLY)

Some insights about Ethan's personal psychology, triggers, communication style, or growth patterns may be valuable in CharacterProfiles (his business profile). This export is:

1. **Never automated** -- no hooks, no scripts, no scheduled pulls
2. **Operator-initiated** -- Ethan manually selects what to export
3. **Staged first** -- selected insights go to `06-export/cp-staging/` with context stripped
4. **Reviewed** -- operator reads staged content and confirms it's appropriate for the business context
5. **Logged** -- every export is recorded in `EXPORT_LOG.md` with date, what was exported, and why
6. **One-way** -- CP never reads from RainbowLight. Only manually copied text.

**What might be exportable:**
- Ethan's self-awareness about his communication triggers
- Leadership-relevant emotional patterns
- Stress response insights that inform his work style
- Growth patterns that explain behavioral changes noted in business context

**What is NEVER exportable:**
- Anything about Jasmin
- Anything about the relationship dynamics
- Anything about family sessions
- Therapist-specific recommendations
- Session content or quotes from therapy

---

## Pipeline (Simplified from CP)

```
SOURCE (transcript in 05-sources/PRIVATE/)
  |
  v
EXTRACT (create 01-sessions/YYYY-MM-DD_Session_NNN.md using scaffold)
  |
  v
INTEGRATE (merge key observations into 02-profiles/ documents)
  |
  v
ARCHIVE (move extraction to 04-archive/sessions/)
  |
  v
UPDATE (Source_Ledger.md, Session_Timeline.md, Therapist_Recommendations.md)
```

No hard gates. No ASCII police. No CC signals. Just: extract, integrate, archive, update references.

---

## CLAUDE.md Isolation Rules

```markdown
## Sandbox Rules (MANDATORY)

1. NEVER read, write, or access any file outside this repo directory.
   This includes CharacterProfiles, CommandCenter, and all other repos.
2. NEVER reference business context (Rebel, clients, team members, revenue).
3. NEVER automate any export to other repos.
4. Treat ALL content as maximally private. No suggestions to share, publish, or sync.
5. Tone: compassionate, observational, non-judgmental. This is a relationship tool, not a business tool.
```

---

## Next Steps

1. [ ] Build CLAUDE.md with isolation rules
2. [ ] Build Session_Extraction_Scaffold.md
3. [ ] Build Relationship_Profile_Template.md and Individual_Growth_Template.md
4. [ ] Build Source_Ledger.md
5. [ ] Set up .gitignore (05-sources/PRIVATE/ must be gitignored)
6. [ ] Move PRIVATE folder from CharacterProfiles to RainbowLight
7. [ ] Process first session transcript as a pilot
8. [ ] Iterate on scaffold based on what the actual transcripts contain

**Recommendation:** Build steps 1-6 in this session or a dedicated RainbowLight session. Step 7 (first extraction) should be done in a session running from the RainbowLight directory with zero CP context.
