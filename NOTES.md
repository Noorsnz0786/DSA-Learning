# Teaching Notes & Preferences

## How this learner wants to be taught
- **Little theory, lots of intuition.** Lead with a real-life analogy, then the concept.
- **Interactive animations / learn-by-doing.** Every lesson should have something to
  click, drag, or run — not just read.
- **Always answer: why this concept, when to use it, when NOT to.**
- **Complexity always.** Every problem & structure: state time + space + the reasoning.
- **Verbal-interview framing.** They will be assessed on *thinking out loud*. End lessons
  with "how to say this in an interview" prompts. Drill the talk-track, not just the code.
- Python is the language. Keep code short and idiomatic.

## Format of the deliverable (locked in by learner feedback)
- **One single self-contained HTML file**: `DSA-Interview-Course.html` (inline CSS/JS, no deps).
- **Section-wise navigation** via a sidebar — one section visible at a time, not one long scroll.
- **Checkboxes per section**, progress saved to `localStorage` (key `dsa-course-progress-vN`;
  bump N if checklist ids change so stale state doesn't mislead). Global + per-section progress bars.
- **Practice problems in `<details>` accordions** — statement visible, solution/hint hidden until clicked.
- **Per topic: a LIST of the most-asked interview problems** (aim ~8+), not just 2-3.
- For each problem: **every approach** brute→optimal, mark the *best* one, **heavily commented code**,
  time+space complexity, and an interview "talk-track".
- **Code tracer** (`makeTrace(id, code, steps)` in the file) lets the learner step through code
  line-by-line with live variable chips — used to SHOW how loops / nested loops flow. Reuse it for
  any loop-heavy solution. Learner specifically wants to "see how the loop is running".
- Each new section should follow this exact template before moving on.

## Progress (build status)
- ✅ Section 1 — Foundations: UPER framework, Big-O, slider + binary-search animations, complexity quizzes, 2 practice problems.
- ✅ Section 2 — Arrays/Hash Maps/Strings: 8 most-asked problems, every approach, commented code, talk-tracks. Animations: Big-O slider, array access-vs-search, + 9 step-through tracers (one per solution).
- ✅ Section 3 — Two Pointers: 7 most-asked problems (Valid Palindrome, Two Sum II, Container With Most Water, Remove Duplicates, Move Zeroes, Reverse String, 3Sum), palindrome converging-pointer animation, tracer on every solution.
- ✅ Section 4 — Sliding Window: 6 most-asked problems (Max Sum Subarray of Size K, Longest Substring Without Repeating, Minimum Size Subarray Sum, Find All Anagrams, Longest Repeating Char Replacement, Max Consecutive Ones III), fixed-window sliding animation, tracer on every solution.
- ✅ Section 5 — Stacks & Queues: 6 most-asked problems (Valid Parentheses, Min Stack, Evaluate RPN, Daily Temperatures, Implement Queue using Stacks, Next Greater Element I), bracket-stack animation, tracer on every solution. Introduced monotonic stack.
- ✅ Section 6 — Linked Lists: 6 most-asked problems (Reverse List, Middle of List, Cycle/Floyd's, Merge Two Sorted Lists, Remove Nth From End, Add Two Numbers), pointer-rewiring reverse animation, tracer on every solution. Patterns: pointer rewiring + fast/slow.
- ✅ Section 7 — Recursion: 6 problems (Factorial, Sum of List, Power/fast-exp, Fibonacci+memoization, Reverse String, Subsets/backtracking), call-stack animation, tracer on every solution. Bridges to DP (memoization) and backtracking.
- ✅ Section 8 — Binary Search: 6 problems (Binary Search, Search Insert Position, First Bad Version, Search in Rotated Sorted Array, Find Minimum in Rotated, Sqrt/search-on-answer), lo/mid/hi animation, tracer on every solution. Templates: exact-match (lo<=hi) vs boundary (lo<hi, hi=mid); plus "binary search on the answer".
- ✅ Section 9 — Trees & BSTs: 6 problems (Max Depth, Invert, Inorder, Level Order/BFS, Validate BST, LCA of BST), SVG tree BFS animation, tracer on every solution. Covers DFS recursion + BFS queue + BST property + 4 traversals.
- ✅ Section 10 — Graphs (BFS/DFS): 6 problems (Number of Islands, Flood Fill, Rotting Oranges/multi-source BFS, Clone Graph, Course Schedule/cycle detection, Connected Components), SVG graph BFS animation showing visited-set skip on cycles, tracer on every solution.
- ✅ Section 11 — Sorting: 5 algorithms (Bubble, Selection, Insertion, Merge, Quick) with commented code, comparison table (time/space/stable), bubble-sort bars animation (+ auto-play), "which to use" table, tracer on every algorithm. Framed as a VERBAL-skill section (explain + complexity), since you just use sorted()/Timsort in practice.
- Core course COMPLETE: 11 sections, ~70 problems, 63 tracers, 67 checkboxes.
- ✅ Section 12 — 🎤 MOCK DRILL (Top 50): 20 verbal theory Q&A (accordion show-answer) + 30 coding problems each with optimal commented solution + a step-through tracer (trace-d1..d30). Built from Blind-75 / Preplaced most-asked lists. This section has NO checklist (intentional — doesn't inflate the 67-checkbox progress per user's "don't touch other things").
- 🐛 FIXED: mobile horizontal-overflow scroll bug — wide tables forced page width >viewport. Fix: body{overflow-x:clip} + mobile media query table{display:block;overflow-x:auto} + .content max-width:100%. Verified scrollWidth==clientWidth at 390px.
- File now: 12 sections, 93 trace containers, ~100 problems total (70 in lessons + 30 drill + 20 verbal).
- OPTIONAL remaining (only if user asks): Section 13 Dynamic Programming. Heaps deprioritised by user.
- ALWAYS run `node --check` on the extracted inline script before delivering (a stray apostrophe like `It\\'s` once crashed the whole page). localStorage key is now `dsa-course-progress-v3`; 25 checkboxes total across 4 sections.
- Reusable JS in file: `makeTrace(id, code, steps)` (line-by-line stepper), `Quiz.mountAll()`, section nav, localStorage progress (`dsa-course-progress-v3`).
- When adding a section: unlock its sidebar navitem (set data-go to its DOM index, give it data-mini="N"), add the <section data-sec="N"> with the same template, give EVERY solution a tracer, add a checklist with data-section="N", and wire prev/next buttons.

## Working notes
- Learner is "okay-ish" at coding — comfortable with basic loops/functions, shaky on
  logic-heavy problems. Don't assume DSA vocabulary; define every term on first use.
- Goal: ~50 famous interview problems over 2–4 weeks.
- Keep each lesson SHORT (one win). They want breadth, but working memory is small —
  resist cramming. Sequence > size.
