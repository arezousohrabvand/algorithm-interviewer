# Algorithm Interviewer

A Claude Code skill that acts as a personal algorithm tutor and interview coach — not a random coding-question generator. It tracks curriculum progress across sessions, enforces mastery before advancing, mixes in spaced review of old topics, and uses AI-assisted interview drills to test whether you can actually work with (and verify) AI-generated code.

Everything lives under `.claude/skills/algorithm-interviewer/` and loads automatically in Claude Code whenever this repo is open, or can be invoked explicitly.

## How to use it

Just talk to Claude Code in this repo. Typical phrases:

- `Start my daily algorithm training. Begin from my current level.`
- `Continue my daily algorithm training.`
- `Give me today's 45-minute session.`
- `Continue from my weakest topic.`
- `Today I only have 20 minutes.`
- `Run today's session in interview mode.`
- `Grill me on this.` (invokes the `grill-me` plugin directly)

Claude reads `progress.md` first every time, finds the earliest topic that isn't mastered yet, and picks up exactly where you left off.

## Files

| File | Purpose |
|---|---|
| `SKILL.md` | The coach's core behavior: modes, the Daily Learning Rule, mastery checklist, spaced review, session triggers, interview flow, Grill Me / Claude-Mem integration, AlgoMonster integration, adaptive practice, end-of-session summary. |
| `curriculum.md` | The 4-phase topic order (Beginner → Intermediate → Advanced → Engineering Interview), the per-topic progression pipeline, daily session-length breakdown, weekly rhythm, and the Grill Me intensity table. |
| `progress.md` | The single source of truth for curriculum state: current level/topic, completed topics per phase, weak/strong areas, topics that need spaced re-practice, recurring mistakes, and the next recommended topic. Read before every session, updated after every session. |
| `question-bank.md` | Reusable practice/interview questions by difficulty, with rules for adapting wording and avoiding repetition. |
| `patterns.md` | Algorithm pattern-recognition signals and mental models (Binary Search, Hash Map, Two Pointers, Sliding Window, Stack, BFS/DFS, Heap, Backtracking, DP, etc.). |
| `ai-interview.md` | The AI-assisted interview format: candidate reasons first, writes the AI prompt, reviews (sometimes intentionally flawed) AI output, explains and tests the result. |
| `grading-rubric.md` | Scoring rubric (1–5 per category) for traditional and AI-assisted interviews, plus the Strong Hire → No Hire recommendation scale. |
| `sources.md` | Rules for using external study sources (currently AlgoMonster via Playwright) as a live reference without mirroring proprietary course content. |
| `.gitignore` | Excludes Playwright session/auth artifacts (`.playwright/`, `*auth*.json`) from version control. |

## Curriculum

**Phase 1 — Beginner:** Big-O → Arrays → Strings → Hash Map → Hash Set → Sorting → Two Pointers → Binary Search → Stack → Queue

**Phase 2 — Intermediate:** Sliding Window → Prefix Sum → Linked Lists → Fast/Slow Pointers → Intervals → Recursion → Trees → BST → BFS → DFS → Heap

**Phase 3 — Advanced:** Graphs → Topological Sort → Backtracking → Greedy → Trie → Union Find → Monotonic Stack → Advanced Binary Search → Dynamic Programming

**Phase 4 — Engineering Interview:** Streaming problems → Rate-limited APIs → Distributed data → Memory constraints → Search over large data → Real-world debugging → AI-assisted interviews

A topic only advances on demonstrated mastery (solve easy independently, solve medium with minimal hints, explain time/space complexity, identify edge cases, debug a flawed version) — never just because it was shown once.

## Per-topic flow

```
Learn concept → Easy problem → Another easy problem → Real-world example
   → Medium problem → Debug broken solution → AI-assisted review
   → Pattern recognition → Mastered → Next topic
```

## Daily session (45–60 min default)

| Time | Activity |
|---|---|
| 5 min | Previous-topic review |
| 10 min | Learn/review today's pattern |
| 15 min | Easy coding problem |
| 15 min | Medium/interview problem |
| 10 min | AI-generated code review/debugging |
| 5 min | Big-O + feedback + update `progress.md` |

Once fundamentals are solid, sessions shift toward: pattern recognition (5) → medium problem (25) → follow-up requirement (10) → AI-assisted debugging (10) → feedback/weak-area review (10).

## Weekly rhythm

| Day | Focus |
|---|---|
| Mon | Learn new pattern |
| Tue | Practice same pattern |
| Wed | Medium problems |
| Thu | Real-world problem + debugging |
| Fri | AI-assisted interview |
| Sat | Mixed mock interview |
| Sun | Review weak areas only |

Topics are grouped across roughly a week at a time rather than jumping pattern-to-pattern day to day — mastery drives pace, not the calendar.

## Spaced review

Every session includes a recent-topic review, an older mastered topic revisited every few sessions, and current-topic practice. If a mastered topic goes weak again, it moves from `Strong Areas` back into `Needs Practice` in `progress.md`.

## Integrations

- **[grill-me](https://github.com/alirezarezvani/claude-skills)** (`grill-me@claude-code-skills`) — Socratic pressure-testing of reasoning ("why does this work", "prove the bound", "what if the input streams"). Usage scales with level: ~20% beginner, ~40% intermediate, ~70% advanced, 100% mock interview.
- **[claude-mem](https://github.com/thedotmack/claude-mem)** (`claude-mem@thedotmack`) — persistent memory across Claude Code sessions. Used only for long-term behavioral trends (recurring habits, phrasing that works well); `progress.md` remains the authoritative curriculum state and always wins on conflict.
- **AlgoMonster** (via Playwright, optional) — when an authenticated session is available, used as a live study source (lesson content, curriculum sequencing, completion status) without mirroring the full paid course locally.

```
             Algorithm Interviewer
                      │
          ┌───────────┼───────────┐
          ↓           ↓           ↓
     curriculum   question     patterns
         .md       bank.md       .md
          │
          ↓
      progress.md
          │
    ┌─────┴─────┐
    ↓           ↓
Grill Me     Claude-Mem
challenge     history
reasoning
```

## Scheduled daily session

A cloud routine is planned to fire at 8:30 PM (America/Chicago) and kick off the day's session automatically against this repo. It's pending a one-time GitHub connection at [claude.ai/customize/connectors](https://claude.ai/customize/connectors) before it can be created (cloud routines need OAuth access to clone the repo).
