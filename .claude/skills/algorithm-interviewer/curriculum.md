# Learning Order

## Phase 1 — Beginner

1. Big-O
2. Arrays
3. Strings
4. Hash Map
5. Hash Set
6. Sorting basics
7. Two Pointers
8. Binary Search
9. Stack
10. Queue

Do not move to Phase 2 until the candidate can:
- recognize the main pattern
- solve easy questions with little help
- explain time complexity
- test basic edge cases

---

## Phase 2 — Intermediate

11. Sliding Window
12. Prefix Sum
13. Linked Lists
14. Fast/Slow Pointers
15. Intervals
16. Recursion
17. Trees
18. BST
19. BFS
20. DFS
21. Heap

---

## Phase 3 — Advanced

22. Graphs
23. Topological Sort
24. Backtracking
25. Greedy
26. Trie
27. Union Find
28. Monotonic Stack
29. Advanced Binary Search
30. Dynamic Programming

---

## Phase 4 — Engineering Interview

31. Streaming problems
32. Rate-limited APIs
33. Distributed data
34. Memory constraints
35. Search over large data
36. Real-world debugging
37. AI-assisted interviews

---

# Per-Topic Progression Flow

Every topic moves through this pipeline before it counts as mastered:

```
Learn concept
     ↓
Easy problem
     ↓
Another easy problem
     ↓
Real-world example
     ↓
Medium problem
     ↓
Debug broken solution
     ↓
AI-assisted review
     ↓
Pattern recognition
     ↓
Mastered
     ↓
Next topic
```

Do not skip stages just because one problem went well. A single solved question is not mastery — see the mastery checklist in `SKILL.md`.

---

# Daily Session Structure

Default session length: 45–60 minutes.

| Time | Activity |
|---|---|
| 5 min | Previous-topic review |
| 10 min | Learn/review today's pattern |
| 15 min | Easy coding problem |
| 15 min | Medium/interview problem |
| 10 min | AI-generated code review/debugging |
| 5 min | Big-O + feedback + update `progress.md` |

Once the candidate is stronger on fundamentals, shift to:

| Time | Activity |
|---|---|
| 5 min | Pattern recognition |
| 25 min | Medium problem |
| 10 min | Follow-up requirement |
| 10 min | AI-assisted debugging |
| 10 min | Feedback + weak-area review |

If the candidate states a shorter time budget (e.g. "I only have 20 minutes"), compress proportionally — always keep the warm-up review and the final `progress.md` update, drop AI-review or the second problem first.

---

# Weekly Rhythm

Use this default weekly shape unless the candidate overrides it:

| Day | Focus |
|---|---|
| Monday | Learn new pattern |
| Tuesday | Practice same pattern |
| Wednesday | Medium problems |
| Thursday | Real-world problem + debugging |
| Friday | AI-assisted interview |
| Saturday | Mixed mock interview |
| Sunday | Review weak areas only |

This exists to prevent fragmented learning like:

```
Monday: Binary Search
Tuesday: Graphs
Wednesday: DP
Thursday: Arrays
```

Instead, group topics across a rough weekly cadence, e.g.:

```
Week 1  Big-O + Arrays
Week 2  Strings + Hash Maps
Week 3  Two Pointers
Week 4  Binary Search
Week 5  Stack + Queue
Week 6  Sliding Window
...
```

This is a guideline, not a hard schedule — advancement is driven by mastery (see `SKILL.md`), not by calendar day. A candidate may stay on one topic for two weeks or clear two topics in one week.

---

# Grill Me Intensity by Level

`grill-me` should be used increasingly as the candidate advances, not applied uniformly:

| Level | Grill Me usage | Example question |
|---|---|---|
| Beginner | ~20% | "Why did you use a Hash Map?" |
| Intermediate | ~40% | "Why does shrinking the window here work?" |
| Advanced | ~70% | "Prove every element is processed at most twice." |
| Mock Interview | 100% | "What if the input is streaming? What if memory is capped at 10 MB? Would this still work with duplicates? AI generated a different solution — which is better and why?" |

Do not use Grill Me to make every beginner question brutally difficult — it should scale with level, not front-load pressure on someone just learning a pattern.
