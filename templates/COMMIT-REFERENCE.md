# Commit Message Reference

> Keep commit messages short, specific, and consistent.  
> Format: `type: description`  
> Description should complete the sentence: *"This commit will..."*

---

## Types & Examples

### `solve` — A LeetCode problem attempt
```
solve: Valid Palindrome (two pointers) — unaided
solve: 3Sum (two pointers) — needed approach hint
solve: Coin Change (dp-1d) — needed full solution
solve: Binary Search — unaided, clean template
```
Always include: problem name, pattern in brackets, and outcome (unaided / approach hint / full solution).

---

### `retry` — Revisiting a problem from the mistakes log
```
retry: Valid Palindrome — solved unaided this time ✅
retry: 3Sum — still needed hint on duplicate handling
```

---

### `add` — New practice code (Stage 0 or C# depth)
```
add: 0.3 methods — overloading and static vs instance demo
add: 0.6 dictionaries — TryGetValue and HashSet intersection
add: 5.2 stack vs heap — value vs reference type comparison
add: 7.1 async — sequential vs concurrent Task.WhenAll demo
```
Always include: checkpoint number, topic, and what the code demonstrates.

---

### `notes` — A concept notes file
```
notes: 1.1 complexity analysis — Big O summary
notes: 5.1 CLR — compilation pipeline in own words
notes: 6.2 SOLID — principles mapped to BNP codebase examples
notes: 9.2 caching — cache strategies comparison
```

---

### `design` — A system design practice attempt
```
design: url shortener — first attempt
design: rate limiter — second attempt, improved trade-offs section
design: chat application — first attempt, missed WebSocket scaling
```

---

### `log` — Mistakes log update
```
log: 3Sum — missed duplicate skip logic at outer loop
log: weekly review — 3 entries revisited, 2 resolved
log: async deadlock — .Result anti-pattern, noted fix
```

---

### `progress` — README checkpoint update
```
progress: mark 0.1 and 0.2 complete
progress: mark 2.1 done — 2.2 in progress
progress: mark checkpoint 5.3 good-enough-for-now
```

---

### `init` — One-off setup commits
```
init: repo structure and gitignore
init: add templates and README
init: add roadmap
```

---

## Quick Reference

| What I did | Type to use |
|---|---|
| Solved a LeetCode problem | `solve` |
| Revisited a problem from mistakes log | `retry` |
| Wrote practice code | `add` |
| Wrote a concept notes file | `notes` |
| Did a system design attempt | `design` |
| Updated the mistakes log | `log` |
| Ticked a checkpoint in README | `progress` |
| First-time repo setup | `init` |

---

## Rules

- **One commit per thing done** — don't bundle a solution, notes, and a progress update into one commit
- **Always include the checkpoint number or problem name** — vague messages like `add practice code` are useless in three months
- **Commit at the end of every session** — even if all you did was write notes, commit it
- **Never leave a session without at least one commit**
