# Technical Interview Prep Roadmap

> A checkpoint-based roadmap. No deadlines. Work through each stage at my own pace — tick a checkpoint when I'm confident, or mark it "good enough for now" and move on. The order matters: each stage builds on the last.

---

## How to Use This

- ✅ **Done** — confident, can explain and apply without prompting
- 🔄 **Good enough for now** — functional knowledge, flagged to revisit before applying
- ⬜ **Not started**

**Learning pattern for every checkpoint:**

> **→ Foundation** — the minimum resource to get oriented before touching practice. One thing, not a list. Read it or watch it once.
> **→ Practice** — exactly what to do after. This is where the learning actually happens.

Three tracks: **DSA** (start immediately), **C# / .NET Depth** (start once DSA Stage 2 is underway), **System Design** (start when approaching the application phase).

---

---

# STAGE 0 — C# SYNTAX CRASH COURSE

> Complete this before anything else. The goal is not mastery — it's getting my hands fluent enough that syntax never blocks my thinking when I sit down to solve a problem. Every checkpoint here is practical: read the minimum, then write code immediately.
>
> **Setup:** Install [Visual Studio Code](https://code.visualstudio.com) + the [C# Dev Kit extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit) + the [.NET SDK](https://dotnet.microsoft.com/en-us/download). Create a console app with `dotnet new console -n Practice` and do all of this inside it. Don't use an online compiler — get the real environment working from day one.

---

### Checkpoint 0.1 — Variables, Types & the Type System

- [ ] Declaring variables: `int`, `double`, `bool`, `char`, `string`
- [ ] `var` keyword — type inference, when C# uses it
- [ ] Constants: `const` vs `readonly` — the difference
- [ ] Nullable types: `int?`, `string?` — what the `?` means
- [ ] Type casting: implicit vs explicit, and when casting fails

**→ Foundation:** Read [Microsoft Docs — C# Types](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types) (5 min). It's a reference table — scan it, don't memorise it.

**→ Practice:** In my console app, declare one variable of each primitive type, print them all, then write a method that takes an `int` and returns it as a `double`. Then declare an `int?`, assign it `null`, and write an `if` check that handles the null case. Run it. If it compiles and runs correctly, I'm done.

---

### Checkpoint 0.2 — Control Flow

- [ ] `if` / `else if` / `else`
- [ ] `switch` statement and `switch` expression (C# modern syntax)
- [ ] `for` loop, `while` loop, `do-while` loop
- [ ] `foreach` loop over a collection
- [ ] `break`, `continue`, `return` — when each exits what

**→ Foundation:** Watch [Bro Code — C# Full Course (control flow sections)](https://www.youtube.com/watch?v=wxznTygnRfQ) — jump to the timestamp for if/else (around 30 min in) and watch through to loops (roughly 1 hour in total for these sections). Bro Code is fast, practical, and skips the theory padding.

**→ Practice:** Write a program that:

1. Takes a number and prints "Fizz" if divisible by 3, "Buzz" if by 5, "FizzBuzz" if both — using `if`/`else`
2. Rewrites the same logic using a `switch` expression
3. Uses a `for` loop to run it for every number 1–100 and prints the results

This is the classic FizzBuzz. If I can write it cleanly from scratch with no Googling, control flow is done.

---

### Checkpoint 0.3 — Methods

- [ ] Defining a method: return type, name, parameters
- [ ] `void` methods vs methods that return a value
- [ ] Optional parameters with default values
- [ ] Method overloading: same name, different signatures
- [ ] `static` vs instance methods — the practical difference at this stage

**→ Foundation:** Read [Microsoft Docs — Methods in C#](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods) (10 min).

**→ Practice:** Write four methods in the same file:

1. A `static int Add(int a, int b)` that returns the sum
2. A `static void PrintGreeting(string name = "stranger")` with a default parameter
3. A `static int Add(int a, int b, int c)` — overload of the first
4. A `static bool IsEven(int n)` that returns true/false

Call all four from `Main` and print the results. Then answer: why does the third method compile alongside the first without conflict?

---

### Checkpoint 0.4 — Arrays & Lists

- [ ] Declaring and initialising arrays: `int[] nums = new int[5]` and `int[] nums = {1, 2, 3}`
- [ ] Indexing, iterating, length
- [ ] `List<T>`: declaring, `Add`, `Remove`, `Count`, `Contains`
- [ ] When to use an array vs a `List<T>`
- [ ] Common array methods: `Array.Sort`, `Array.Reverse`, `Array.IndexOf`

**→ Foundation:** Read [Microsoft Docs — Arrays](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/) (5 min) then [Microsoft Docs — List\<T\>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1) (just the methods table, 5 min).

**→ Practice:** Write a program that:

1. Creates an array of 5 integers, sorts it, reverses it, and prints each element using a `for` loop
2. Creates a `List<string>` of five names, removes one, checks if another exists with `Contains`, and iterates with `foreach`
3. Writes a method `static int[] GetEvens(int[] nums)` that takes an array and returns a new array containing only the even numbers

The third one requires me to think about building a result — use a `List<int>` internally then convert with `.ToArray()`.

---

### Checkpoint 0.5 — Strings

- [ ] String as an immutable reference type
- [ ] Common methods: `Length`, `ToUpper`, `ToLower`, `Trim`, `Contains`, `Replace`, `Substring`, `Split`, `IndexOf`
- [ ] String interpolation: `$"Hello {name}"`
- [ ] Comparing strings: `==` vs `.Equals()` vs `string.Compare`
- [ ] Converting between string and other types: `int.Parse`, `ToString`, `Convert.ToInt32`

**→ Foundation:** Read [Microsoft Docs — String methods](https://learn.microsoft.com/en-us/dotnet/api/system.string#methods) (5 min — skim the method list, don't read every entry).

**→ Practice:** Write a program that:

1. Takes a sentence as a hardcoded string, splits it into words, and prints each word on a new line
2. Counts how many words start with a vowel
3. Reverses the entire string character by character using a `for` loop (don't use `Array.Reverse` — build it manually)

The third task is a genuine interview warm-up problem. If I can do it cleanly, my string fundamentals are solid.

---

### Checkpoint 0.6 — Dictionaries & HashSets

- [ ] `Dictionary<TKey, TValue>`: declaring, `Add`, `ContainsKey`, `TryGetValue`, iterating with `foreach`
- [ ] Accessing a value safely: why `dict[key]` throws if key missing, and how `TryGetValue` fixes that
- [ ] `HashSet<T>`: declaring, `Add`, `Contains`, `Remove` — and why lookup is O(1)
- [ ] When to use Dictionary vs HashSet

**→ Foundation:** Read [Microsoft Docs — Dictionary\<TKey, TValue\>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2) (5 min — the examples section is the useful part).

**→ Practice:** Write a program that:

1. Takes a string and uses a `Dictionary<char, int>` to count the frequency of each character — print the results
2. Takes two string arrays and uses a `HashSet<string>` to find which elements appear in both (the intersection)
3. Writes a method `static bool HasDuplicate(int[] nums)` that returns true if any number appears more than once — use a HashSet, not nested loops

The third task is a direct LeetCode pattern. If I can write it fluently, I'm ready for Checkpoint 1.2.

---

### Checkpoint 0.7 — Classes & Objects (Basics Only)

- [ ] Defining a class: fields, properties, constructor
- [ ] `public`, `private`, `protected` — access modifiers and what they control
- [ ] Creating an object with `new`
- [ ] Auto-properties: `public int Age { get; set; }`
- [ ] `this` keyword — when it's needed

_Note: this is basics only. Deep OOP (inheritance, polymorphism, abstract classes) is covered in Track 2 Checkpoint 6.1. I just need enough here to define a simple class and use it._

**→ Foundation:** Watch [Bro Code — C# Classes](https://www.youtube.com/watch?v=wxznTygnRfQ&t=3600s) (jump to the classes section, roughly 1 hour in, watch for ~20 min).

**→ Practice:** Write a `RiskEvent` class with:

- Private fields for `Id` (int), `Description` (string), `Severity` (int)
- A constructor that sets all three
- Public auto-properties for read access
- A `ToString()` override that returns a formatted summary string

Then create three instances in `Main`, put them in a `List<RiskEvent>`, and print each one. If it compiles and the output looks right, I'm done with Stage 0.

---

### Checkpoint 0.8 — The Exit Test

_Before moving to Track 1, Stage 1 — do this from scratch, no Googling, no looking back at previous code._

Write a single C# program that does all of the following:

- [ ] Defines a `Student` class with `Name` (string) and `Score` (int) properties and a constructor
- [ ] Creates a `List<Student>` with at least five students
- [ ] Uses a `for` loop to find the highest score
- [ ] Uses a `foreach` loop to print the name and score of every student who scored above 70
- [ ] Uses a `Dictionary<string, int>` to store name → score pairs and looks one up safely with `TryGetValue`
- [ ] Writes a method `static double GetAverage(List<Student> students)` that calculates and returns the average score

If I can write all of that cleanly and it runs correctly, my syntax is ready for LeetCode. Move to Checkpoint 1.1.

If I get stuck on more than one section, identify which checkpoint it maps back to and revisit just that one.

---

---

# TRACK 1 — DATA STRUCTURES & ALGORITHMS

> All practice in C#. LeetCode is my platform. NeetCode.io is my guide — it organises problems by pattern.
>
> **Core principle:** Learn the pattern first. Then solve. Never grind randomly.

---

## Stage 1 — Foundations

---

### Checkpoint 1.1 — Complexity Analysis

- [ ] Understand Big O notation: O(1), O(log n), O(n), O(n log n), O(n²)
- [ ] Can determine time and space complexity of a given piece of code
- [ ] Understand best case vs worst case vs average case
- [ ] Know why this matters — every solution in an interview needs complexity analysis stated

**→ Foundation:** Watch [NeetCode — Big O Notation](https://www.youtube.com/watch?v=BgLTDT03QtU) (18 min). That's all I need.

**→ Practice:** After watching, open any piece of code I've written at work or on a side project and manually annotate the time and space complexity of each section. Do this for 5–10 snippets until it feels automatic. From this point forward: every LeetCode problem I solve, always state complexity before moving on — make it a non-negotiable habit from day one.

---

### Checkpoint 1.2 — Core C# Data Structures

- [ ] **Array / List\<T\>** — indexing O(1), insertion/deletion O(n), when to prefer over linked list
- [ ] **Dictionary\<K,V\> / HashSet\<T\>** — lookup O(1) average, hash collision basics
- [ ] **Stack\<T\>** — LIFO, O(1) push/pop, when it's the right tool
- [ ] **Queue\<T\>** — FIFO, O(1) enqueue/dequeue, when it's the right tool
- [ ] **LinkedList\<T\>** — O(1) insertion at head/tail, O(n) access, pointer logic
- [ ] **SortedDictionary / SortedSet** — tree-backed, O(log n) operations, when to use

**→ Foundation:** Work through the data structures chapters (Arrays, Linked Lists, Stacks & Queues, Hash Maps) of [NeetCode — DSA for Beginners](https://neetcode.io/courses/dsa-for-beginners/0). These are short and visual. Don't touch the algorithm chapters yet.

**→ Practice:** For each structure, write a short C# console snippet from scratch: create the structure, add items, remove items, look something up. Don't copy-paste — type it. Annotate each operation with its Big O in a comment. Goal: I can do this without looking anything up. One session per structure.

---

### Checkpoint 1.3 — Strings & Arrays

- [ ] String immutability in C# and when to use `StringBuilder`
- [ ] Array traversal: forward, backward, from both ends simultaneously
- [ ] Subarray index arithmetic (start, end, length relationships)
- [ ] Char frequency counting using `Dictionary<char, int>` or `int[26]`
- [ ] Can solve LeetCode Easy array/string problems without hints

**→ Foundation:** Read [C# String vs StringBuilder — C# Corner](https://www.c-sharpcorner.com/article/stringbuilder-in-c-sharp/) (5 min). Then briefly skim the Arrays section from the NeetCode course in 1.2 — I've already partially covered this.

**→ Practice:** Solve these four LeetCode problems in order, in C#. Attempt each for at least 20 minutes before looking at anything:

1. [Two Sum](https://leetcode.com/problems/two-sum/) — array indexing + hashmap
2. [Valid Anagram](https://leetcode.com/problems/valid-anagram/) — char frequency counting
3. [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/) — HashSet usage
4. [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) — array traversal logic

After each: write time and space complexity. If I needed a hint, add it to my mistakes log.

---

## Stage 2 — Core Patterns

_Each checkpoint is a pattern. Foundation gets I oriented. Practice locks it in. Do 3–5 problems per pattern before moving on._

---

### Checkpoint 2.1 — Two Pointers

- [ ] Understand the pattern: two indices moving toward each other or in the same direction
- [ ] Can apply to sorted arrays and string problems
- [ ] Recognise when a problem is a two-pointer candidate

**→ Foundation:** Watch [NeetCode — Two Pointers](https://www.youtube.com/watch?v=jJ4Q0khFAaA) (12 min). Pay attention to the two sub-variants: opposite ends vs same direction.

**→ Practice:** Solve in order:

1. [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) — opposite ends, easy entry point
2. [Two Sum II — Input Array is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) — opposite ends, sorted constraint
3. [3Sum](https://leetcode.com/problems/3sum/) — combines sorting + two pointers, medium
4. [Container With Most Water](https://leetcode.com/problems/container-with-most-water/) — classic two-pointer logic

Rule: attempt each for 20 minutes unaided. If stuck, look at the approach only — not the code. Then implement myselfself.

---

### Checkpoint 2.2 — Sliding Window

- [ ] Understand fixed-size vs variable-size windows
- [ ] Can maintain window state (running sum, char count) as the window moves
- [ ] Know when to expand and when to shrink

**→ Foundation:** Watch [NeetCode — Sliding Window](https://www.youtube.com/watch?v=jSto0O4AJbM) (17 min). The variable-size window shrink logic is the part that trips most people — pay close attention to that section.

**→ Practice:** Solve in order:

1. [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) — revisit as a sliding window to see the pattern
2. [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/) — variable window, classic
3. [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/) — harder window condition
4. [Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/) — hard but important; attempt it even if I need the approach

---

### Checkpoint 2.3 — Binary Search

- [ ] Can implement binary search from scratch without off-by-one errors
- [ ] Understand it as a thinking pattern, not just an algorithm for sorted arrays
- [ ] Can apply it to "search on answer" problems

**→ Foundation:** Watch [NeetCode — Binary Search](https://www.youtube.com/watch?v=s4DPM8ct1pI) (14 min). Then immediately implement binary search in C# from memory before touching LeetCode — this forces the loop/boundary logic to stick.

**→ Practice:** Solve in order:

1. [Binary Search](https://leetcode.com/problems/binary-search/) — get the template clean
2. [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/) — extends the template to 2D
3. [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) — adapts the condition, medium
4. [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/) — "search on answer" pattern; the key insight is non-obvious at first

---

### Checkpoint 2.4 — Stack & Queue Patterns

- [ ] Monotonic stack: what it is and when to reach for it
- [ ] Bracket/parenthesis problems using a stack
- [ ] BFS queue pattern — preview for graphs

**→ Foundation:** Watch [NeetCode — Stack](https://www.youtube.com/watch?v=KInG04mAjO0) (15 min). The monotonic stack concept is the new thing here — everything else I likely have intuition for already.

**→ Practice:** Solve in order:

1. [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) — pure stack, entry point
2. [Min Stack](https://leetcode.com/problems/min-stack/) — designing a stack with auxiliary state
3. [Daily Temperatures](https://leetcode.com/problems/daily-temperatures/) — classic monotonic stack
4. [Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/) — stack + arithmetic logic

---

### Checkpoint 2.5 — Linked Lists

- [ ] Reverse a linked list iteratively and recursively
- [ ] Fast/slow pointer — Floyd's cycle detection
- [ ] Merge two sorted lists
- [ ] Find the middle of a linked list

**→ Foundation:** Watch [NeetCode — Linked Lists](https://www.youtube.com/watch?v=Hj_rA0dhr2I) (20 min). Draw the pointer diagrams on paper as he walks through them — linked list problems are spatial and the visual is essential.

**→ Practice:** Solve in order:

1. [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/) — do both iterative and recursive
2. [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/) — pointer manipulation
3. [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/) — fast/slow pointer
4. [Reorder List](https://leetcode.com/problems/reorder-list/) — combines find-middle + reverse + merge

---

### Checkpoint 2.6 — Trees (Binary Trees)

- [ ] Tree structure: nodes, children, leaves, height, depth
- [ ] DFS traversals: inorder, preorder, postorder — recursive and iterative
- [ ] BFS (level-order traversal) using a queue
- [ ] Recursive thinking: "what do I need from my left and right subtree?" — trust the recursion

**→ Foundation:** Watch [NeetCode — Trees](https://www.youtube.com/watch?v=RBSGKlAvoiM) (15 min). The recursive mindset is the single most important thing here. Internalise it before touching code.

**→ Practice:** Solve in order:

1. [Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/) — simplest recursive tree problem
2. [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/) — recursive depth, entry point
3. [Same Tree](https://leetcode.com/problems/same-tree/) — recursive comparison
4. [Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/) — BFS with a queue
5. [Diameter of Binary Tree](https://leetcode.com/problems/diameter-of-binary-tree/) — requires tracking globally vs returning locally

---

### Checkpoint 2.7 — Binary Search Trees (BST)

- [ ] BST property: left < node < right at every level
- [ ] Inorder traversal of a BST yields sorted output — frequently useful
- [ ] Lowest Common Ancestor

**→ Foundation:** Watch [NeetCode — BST](https://www.youtube.com/watch?v=Gt2yBZAhsGM) (12 min). I already understand trees from 2.6 — this is a short extension. Focus on why inorder = sorted.

**→ Practice:** Solve in order:

1. [Search in a Binary Search Tree](https://leetcode.com/problems/search-in-a-binary-search-tree/) — apply the BST property directly
2. [Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/) — classic trap; the naive approach fails
3. [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/) — inorder traversal insight
4. [Lowest Common Ancestor of a BST](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) — uses BST property cleanly

---

### Checkpoint 2.8 — Hashing Patterns

- [ ] Frequency maps using `Dictionary<T, int>`
- [ ] Two-sum lookup pattern: store complement, not value
- [ ] Grouping with hashmaps

**→ Foundation:** Watch [NeetCode — Hashing](https://www.youtube.com/watch?v=KyUTuwz_b7Q) (13 min). I've used hashmaps in earlier problems — this consolidates the pattern thinking.

**→ Practice:** Solve in order:

1. [Group Anagrams](https://leetcode.com/problems/group-anagrams/) — grouping pattern; key insight is the canonical key
2. [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) — frequency map + sorting
3. [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/) — HashSet-based; the O(n) solution is non-obvious

---

## Stage 3 — Intermediate Patterns

_These take longer to internalise. Spend more time on each before moving on._

---

### Checkpoint 3.1 — Heaps / Priority Queues

- [ ] Min-heap vs max-heap: what each gives I
- [ ] C# `PriorityQueue<TElement, TPriority>` (.NET 6+) — syntax and usage
- [ ] "Top K" pattern: when a heap beats sorting — O(n log k) vs O(n log n)
- [ ] Know when to reach for a heap vs a sort

**→ Foundation:** Watch [NeetCode — Heap / Priority Queue](https://www.youtube.com/watch?v=yCsKJ5yeyyU) (20 min). Knowing how the heap works internally helps I use `PriorityQueue` correctly even though I won't build one from scratch.

**→ Practice:** Solve in order:

1. [Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/) — direct heap application
2. [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) — redo with a heap (I did it with sorting in 2.8)
3. [Task Scheduler](https://leetcode.com/problems/task-scheduler/) — heap + greedy thinking
4. [Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/) — two-heap technique, important pattern

---

### Checkpoint 3.2 — Graphs (BFS & DFS)

- [ ] Represent a graph as adjacency list: `Dictionary<int, List<int>>`
- [ ] BFS: shortest path in unweighted graphs, level-by-level traversal
- [ ] DFS: connected components, cycle detection, path existence
- [ ] Visited set pattern to avoid infinite loops

**→ Foundation:** Watch [NeetCode — Graphs](https://www.youtube.com/watch?v=EgI5nU9etnU) (30 min — watch it in full). Graphs are the most conceptually broad topic. After watching, draw a small graph on paper and manually trace BFS then DFS through it before opening LeetCode.

**→ Practice:** Solve in order:

1. [Number of Islands](https://leetcode.com/problems/number-of-islands/) — DFS/BFS on a grid, entry point
2. [Rotting Oranges](https://leetcode.com/problems/rotting-oranges/) — BFS with multi-source starting points
3. [Clone Graph](https://leetcode.com/problems/clone-graph/) — DFS + hashmap for visited tracking
4. [Course Schedule](https://leetcode.com/problems/course-schedule/) — cycle detection in a directed graph
5. [Pacific Atlantic Water Flow](https://leetcode.com/problems/pacific-atlantic-water-flow/) — multi-source BFS, harder but common

---

### Checkpoint 3.3 — Backtracking

- [ ] Decision tree mental model: at each step, try all choices
- [ ] Build → explore → undo (the backtrack step)
- [ ] Pruning: cut branches early when the current path can't succeed

**→ Foundation:** Watch [NeetCode — Backtracking](https://www.youtube.com/watch?v=A80YzvNwqXA) (14 min). Draw the decision tree on paper for the first problem before coding — backtracking is spatial and the visual is the thing.

**→ Practice:** Solve in order:

1. [Subsets](https://leetcode.com/problems/subsets/) — simplest backtracking structure
2. [Combination Sum](https://leetcode.com/problems/combination-sum/) — adds "can reuse elements" logic
3. [Permutations](https://leetcode.com/problems/permutations/) — all orderings, slightly different structure
4. [Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/) — mapping + backtracking
5. [Word Search](https://leetcode.com/problems/word-search/) — backtracking on a grid

---

### Checkpoint 3.4 — Dynamic Programming — 1D

- [ ] Core idea: overlapping subproblems + optimal substructure
- [ ] Top-down (memoisation) vs bottom-up (tabulation)
- [ ] Define the subproblem before writing code: "dp[i] represents..."

**→ Foundation:** Watch [NeetCode — 1D Dynamic Programming](https://www.youtube.com/watch?v=Y0lT9Fck7qI) (20 min). DP is where most people stall. The critical habit is defining the subproblem precisely before touching code — watch how NeetCode frames that step and copy it exactly.

**→ Practice:** Solve in order — deliberately ordered from most to least intuitive:

1. [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/) — Fibonacci in disguise, entry point
2. [House Robber](https://leetcode.com/problems/house-robber/) — first real DP decision
3. [Min Cost Climbing Stairs](https://leetcode.com/problems/min-cost-climbing-stairs/) — variation to confirm understanding
4. [Coin Change](https://leetcode.com/problems/coin-change/) — classic unbounded knapsack
5. [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/) — O(n²) solution first, then think about O(n log n)

---

### Checkpoint 3.5 — Dynamic Programming — 2D

- [ ] Grid-based DP: dp[i][j] depends on adjacent cells
- [ ] String DP: comparing two sequences
- [ ] Can define the 2D table structure and transition formula before coding

**→ Foundation:** Watch [NeetCode — 2D Dynamic Programming](https://www.youtube.com/watch?v=FLbqgyJ-70I) (22 min). After watching, draw the DP table for Unique Paths on paper before opening LeetCode. The table visualisation is the foundation here.

**→ Practice:** Solve in order:

1. [Unique Paths](https://leetcode.com/problems/unique-paths/) — grid DP, entry point
2. [Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/) — classic 2D string DP
3. [Edit Distance](https://leetcode.com/problems/edit-distance/) — harder string DP, very common in interviews
4. [Maximal Square](https://leetcode.com/problems/maximal-square/) — grid DP with a less obvious transition

---

## Stage 4 — Interview Readiness (DSA)

---

### Checkpoint 4.1 — Speed & Communication

- [ ] Can solve Easy problems in under 10 minutes
- [ ] Can solve Medium problems in 20–25 minutes
- [ ] Narrate approach out loud before typing
- [ ] Always state brute force first, then optimise
- [ ] Always state time and space complexity at the end

**→ Foundation:** None. This is entirely about habit.

**→ Practice:** Start setting a 25-minute timer for every Medium problem. When it goes off and I'm not done, note where I got stuck and push for 5 more minutes before reviewing. The timer introduces pressure, which is the actual condition being practised. If I'm not narrating out loud, I'm not practising the real skill.

---

### Checkpoint 4.2 — Blind 75 Completion

- [ ] Worked through all 75 problems at least once
- [ ] Can revisit any problem after a week and solve it again without hints

**→ Foundation:** None — I've been building toward this since Stage 1.

**→ Practice:** Use [NeetCode.io — Blind 75](https://neetcode.io/practice) as the master tracker. Categorise every problem: solved unaided / solved with hint / needed full solution. Problems in the third category go into my mistakes log and get revisited weekly. Aim for everything in the first two categories before I start applying.

---

### Checkpoint 4.3 — Timed Mock Practice & Mistakes Log

- [ ] Practising with a hard 25-minute timer per problem regularly
- [ ] Maintaining a mistakes log: wrong approach / missed edge case / complexity error
- [ ] Revisiting logged mistakes weekly

**→ Foundation:** None.

**→ Practice:** Keep my mistakes log as a simple running note — problem name, what went wrong, correct approach in one sentence. Review it every week. The log becomes more valuable than the problems themselves over time — it's a personalised list of exactly the patterns I haven't yet internalised.

---

---

# TRACK 2 — C# / .NET DEPTH

> Start this track once DSA Stage 2 is underway. my LeetCode practice in C# is already building language fluency — this track adds the _why_ layer that interviews probe.

---

## Stage 1 — The Runtime & Memory Model

---

### Checkpoint 5.1 — CLR & Compilation

- [ ] What the CLR is and what services it provides
- [ ] CIL (Common Intermediate Language): what it is and why it exists
- [ ] JIT compilation: when it happens and what it does
- [ ] Managed vs unmanaged code: the practical difference
- [ ] What an assembly is; difference between .exe and .dll

**→ Foundation:** Read [Microsoft Docs — Overview of the .NET CLR](https://learn.microsoft.com/en-us/dotnet/standard/clr) (10 min). After reading, close it and write a bullet-point explanation of the compilation pipeline in my own words: C# → CIL → JIT → machine code. If I can't, re-read the relevant section.

**→ Practice:** The practice for conceptual checkpoints is explanation-based. Answer these three questions out loud, as if to another engineer, without notes:

- "What does the CLR actually do at runtime?"
- "Why does .NET compile to CIL instead of directly to machine code?"
- "What's the practical difference between managed and unmanaged code?"

If my answers feel vague, the foundation wasn't enough — re-read and repeat. Interviews ask these conversationally, so practice must be conversational.

---

### Checkpoint 5.2 — Memory: Stack vs Heap

- [ ] What lives on the stack vs the heap, and why
- [ ] Value types vs reference types — where each is stored
- [ ] What happens to memory when I pass each to a method
- [ ] `ref` and `out` keywords and what they change

**→ Foundation:** Watch [Tim Corey — Stack vs Heap in C#](https://www.youtube.com/watch?v=clOUdVDDzIM) (20 min). Tim Corey is one of the best C# educators available — clear, practical, no filler.

**→ Practice:** Write a short C# console app that demonstrates the difference concretely: pass a struct (value type) to a method and modify it — observe nothing changes in the caller. Do the same with a class (reference type) — observe it does change. Add a `ref` version of the struct example. Run all three, confirm the behaviour, and be able to explain _why_ each outcome happens in memory terms.

---

### Checkpoint 5.3 — Garbage Collection

- [ ] How the GC works: mark, sweep, compact cycle
- [ ] Generational GC: Gen 0, Gen 1, Gen 2 — what they mean and why generations exist
- [ ] Large Object Heap (LOH): what goes there and why it's treated differently
- [ ] `IDisposable` and the Dispose pattern — when and why
- [ ] What the `using` statement compiles to
- [ ] Finalisers: what they are and when to avoid them

**→ Foundation:** Read [Microsoft Docs — Fundamentals of Garbage Collection](https://learn.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals) (15 min). Focus particularly on the generations section — that's what interviewers probe most.

**→ Practice:** Write a C# class that holds an unmanaged resource (simulate with a `bool _isOpen` flag representing a file handle). Implement `IDisposable` correctly — the full `Dispose(bool disposing)` pattern plus a finaliser. Use it with a `using` statement. After writing it, explain out loud why I wrote each part and what problem it solves. The act of implementing IDisposable correctly from scratch is the test.

---

### Checkpoint 5.4 — Boxing & Unboxing

- [ ] What boxing is and when it happens implicitly
- [ ] The performance cost: heap allocation, extra GC pressure
- [ ] How to identify unnecessary boxing in code
- [ ] Why generics solve the boxing problem for collections

**→ Foundation:** Read [Microsoft Docs — Boxing and Unboxing](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing) (5 min). Short and sufficient.

**→ Practice:** Write three C# snippets side by side:

1. An `ArrayList` storing integers — boxing happening implicitly
2. A `List<int>` storing the same integers — no boxing
3. A method taking an `object` parameter called with an `int` argument

Annotate in comments exactly where boxing/unboxing occurs and why. Then write one sentence: "Why should I prefer `List<T>` over `ArrayList` from a memory perspective?" If I can't write it without referring back to the code, I'm not there yet.

---

## Stage 2 — Language Fundamentals (Interview Depth)

---

### Checkpoint 6.1 — OOP in C#

- [ ] Classes vs structs: value semantics, stack vs heap, when each is appropriate
- [ ] Abstract classes vs interfaces — including default interface implementations in C# 8+
- [ ] `virtual` / `override` vs `new` (hiding) — subtle but commonly probed
- [ ] Sealed classes: what they prevent and why I'd use them

**→ Foundation:** Watch [Tim Corey — OOP in C#](https://www.youtube.com/watch?v=wrFoFTMC_9I) (35 min). If I'm comfortable with basic OOP, skip to the abstract class vs interface section — that's the part most likely to surface in interviews.

**→ Practice:** Write a small class hierarchy from scratch using a domain I know well — e.g. financial instruments: `Instrument` (abstract base) → `Equity`, `Bond`, `Derivative`. Include: an abstract method, an interface, a sealed class, and a `virtual` method that gets overridden. Don't use a tutorial example. Then answer from memory: "When would I use an abstract class over an interface?"

---

### Checkpoint 6.2 — SOLID Principles

- [ ] **S** — Single Responsibility: one reason to change
- [ ] **O** — Open/Closed: open for extension, closed for modification
- [ ] **L** — Liskov Substitution: subtypes must be fully substitutable
- [ ] **I** — Interface Segregation: many specific interfaces beat one fat one
- [ ] **D** — Dependency Inversion: depend on abstractions, not concretions

**→ Foundation:** Read [Milan Jovanović — SOLID Principles in C#](https://www.milanjovanovic.tech/blog/solid-principles) (20 min). Milan's blog is one of the best .NET resources available — practical and production-oriented.

**→ Practice:** For each principle, identify a real example from the codebases I've worked on or risk-event-tracker where the principle was either followed or violated. Write one sentence per principle: "In [context], we [did/didn't] follow this because...". Anchoring principles to real experience is exactly what distinguishes strong interview answers from textbook recitation.

---

### Checkpoint 6.3 — Generics

- [ ] Generic classes, methods, and interfaces — syntax and purpose
- [ ] Constraints: `where T : class`, `where T : new()`, `where T : IComparable<T>`
- [ ] Why generics eliminate boxing for collections
- [ ] Covariance (`out`) and contravariance (`in`) — conceptual level is sufficient

**→ Foundation:** Read [Microsoft Docs — Generics in C#](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/generics) (10 min), including the linked constraints page.

**→ Practice:** Write a generic `Repository<T>` class with `Add(T item)`, `GetById(int id)`, and `GetAll()` methods — include an `IEntity` constraint (define the interface myselfself). Then implement a `Stack<T>` from scratch without using the built-in one. Implementing a generic data structure myselfself is the fastest way to internalise how generics behave.

---

### Checkpoint 6.4 — Delegates, Events & Lambdas

- [ ] What a delegate is: a type-safe reference to a method
- [ ] `Func<>`, `Action<>`, `Predicate<>` — what each represents
- [ ] How lambda expressions compile to delegates
- [ ] Events: the publisher/subscriber pattern using the `event` keyword
- [ ] Multicast delegates: one delegate, multiple subscribers

**→ Foundation:** Watch [Tim Corey — Delegates in C#](https://www.youtube.com/watch?v=R8Blt5c-Vi4) (25 min). Delegates and events don't land from reading alone — I need to see the wiring.

**→ Practice:** Build a small C# event system from scratch: a `PriceUpdater` class that fires a `PriceChanged` event (using a custom delegate) whenever a price changes, with two subscriber classes that each log the change differently. No tutorials. Then refactor it to use `Action<decimal>` instead of the custom delegate. Understanding why the refactor works is the goal.

---

### Checkpoint 6.5 — LINQ

- [ ] Query syntax vs method syntax — comfortable with both
- [ ] Deferred execution: the query doesn't run until I iterate it
- [ ] Core operators: `Where`, `Select`, `OrderBy`, `GroupBy`, `Join`, `Aggregate`, `First`/`FirstOrDefault`, `Any`/`All`, `Distinct`, `Take`/`Skip`
- [ ] When LINQ is the wrong tool: performance-critical tight loops
- [ ] How LINQ to EF translates to SQL — the mental model

**→ Foundation:** Read [Microsoft Docs — LINQ Overview](https://learn.microsoft.com/en-us/dotnet/csharp/linq/) (10 min), focusing on the deferred execution section. That's what interview questions probe.

**→ Practice:** Take my risk-event-tracker project (or any dataset) and write 5–10 queries covering different operators. Then deliberately demonstrate deferred execution: enumerate a query twice and observe it runs twice — add a side-effect to make this visible. Write a comment explaining why. Finally, write the same query in both query syntax and method syntax side by side.

---

## Stage 3 — Asynchronous Programming

---

### Checkpoint 7.1 — async / await Internals

- [ ] What `async`/`await` compiles to (a state machine — understand the concept, not the IL)
- [ ] Why `await Task.Delay(5)` doesn't block the thread but `Thread.Sleep(5)` does
- [ ] `Task` vs `Thread`: why Tasks are almost always the right choice
- [ ] `ConfigureAwait(false)`: what it does and when it matters

**→ Foundation:** Watch [Nick Chapsas — async/await in C# — how it actually works](https://www.youtube.com/watch?v=il9gl8MH17s) (20 min). Nick Chapsas is the go-to channel for deep .NET content. This is the clearest explanation of the state machine model available — exactly the depth senior interviewers want.

**→ Practice:** Write a C# console program that:

1. Makes three async HTTP calls sequentially (await each one)
2. Makes the same three calls concurrently with `Task.WhenAll`
3. Prints elapsed time for each approach

Observe the timing difference and comment on why it occurs. Then add `ConfigureAwait(false)` to the inner methods and write a comment explaining what changes and why I would or wouldn't use it in a library vs application context.

---

### Checkpoint 7.2 — Common async Pitfalls

- [ ] `async void`: why it's dangerous (exceptions vanish, can't be awaited)
- [ ] Deadlocks from `.Result` / `.Wait()` — how they happen and why
- [ ] `Task.WhenAll` vs `Task.WhenAny` — when I want all vs first
- [ ] `CancellationToken`: pattern for cooperative cancellation

**→ Foundation:** Read [Stephen Cleary — Async Best Practices](https://learn.microsoft.com/en-us/archive/msdn-magazine/2013/march/async-await-best-practices-in-asynchronous-programming) (15 min). Stephen Cleary is the authority on async in .NET. This article covers all four points precisely.

**→ Practice:** Write code that deliberately triggers an async deadlock using `.Result` in a synchronous context calling an async method. Watch it hang. Then fix it. Once I've caused a deadlock myselfself, I'll never forget why `.Result` is dangerous. Then implement a method that accepts a `CancellationToken` and cancels a long-running loop cleanly when triggered.

---

### Checkpoint 7.3 — Concurrency & Thread Safety

- [ ] Race conditions: what they are, how to construct one deliberately
- [ ] `lock` keyword and `Monitor` — what they protect and what they cost
- [ ] `Interlocked.Increment` — atomic operations without locking
- [ ] `SemaphoreSlim` — async-compatible locking
- [ ] `ConcurrentDictionary` — when it's appropriate vs `Dictionary` + `lock`

**→ Foundation:** Watch [Nick Chapsas — Threading in C#](https://www.youtube.com/watch?v=d3Wl82QBzQE) (25 min). Race conditions are hard to understand from text alone — the demonstration is what makes it click.

**→ Practice:** Write a program that increments a shared counter from 10 concurrent threads — first without any synchronisation (observe the wrong result), then with `lock`, then with `Interlocked.Increment`. Measure and note all three results. This minimal demo forces you to confront what thread safety actually protects and costs.

---

## Stage 4 — Architecture & .NET Ecosystem

---

### Checkpoint 8.1 — Dependency Injection

- [ ] What DI is and why: testability, loose coupling, inversion of control
- [ ] Constructor injection as the primary pattern
- [ ] Service lifetimes: **Singleton** (one instance ever), **Scoped** (one per request), **Transient** (new every time)
- [ ] The captive dependency problem: scoped service injected into singleton — what breaks and why
- [ ] Can register services in `Program.cs` from memory

**→ Foundation:** Read [Milan Jovanović — Dependency Injection in .NET](https://www.milanjovanovic.tech/blog/dependency-injection-in-asp-net-core) (15 min). The best practical explanation of DI lifetimes and the captive dependency trap available.

**→ Practice:** Build a minimal ASP.NET Core Web API that registers one service of each lifetime — Singleton, Scoped, Transient — and logs a new GUID per instance in each. Call the endpoint twice and observe which GUIDs change and which don't. Seeing lifetime behaviour myself is the only way to really internalise the difference. Then deliberately inject a Scoped service into a Singleton and observe what happens (with and without `ValidateScopes`).

---

### Checkpoint 8.2 — Design Patterns (Code-Level)

- [ ] **Repository Pattern** — abstracts data access; why it aids testability
- [ ] **Unit of Work** — coordinates writes across multiple repositories
- [ ] **Factory Pattern** — object creation without exposing instantiation logic
- [ ] **Singleton Pattern** — one instance (and why the DI container is usually the better answer)
- [ ] **Strategy Pattern** — swap algorithms behind an interface at runtime
- [ ] **Decorator Pattern** — add behaviour without modifying a class
- [ ] **Observer Pattern** — event-driven notification (connects to delegates/events)

**→ Foundation:** Read [Refactoring.Guru — Design Patterns in C#](https://refactoring.guru/design-patterns/csharp) — only the seven patterns listed above. Each page follows a clean structure: intent → problem → solution → C# code. That's exactly the format needed here.

**→ Practice:** Implement each pattern in a small, self-contained C# file. Use a domain that makes sense to me — financial instruments, risk events, trading operations. Don't use tutorial examples like "pizza factory". Making the domain mine forces deeper thinking. For each pattern, write one comment at the top: "I'd use this pattern when...".

---

### Checkpoint 8.3 — ASP.NET Core Fundamentals

- [ ] The middleware pipeline: how requests flow through it and why order matters
- [ ] Routing: attribute routing vs convention-based
- [ ] Controller actions: HTTP verbs, `IActionResult` return types
- [ ] Model binding: `[FromBody]`, `[FromQuery]`, `[FromRoute]`
- [ ] Authentication vs authorisation: conceptual difference + JWT basics

**→ Foundation:** Watch [Nick Chapsas — ASP.NET Core fundamentals](https://www.youtube.com/watch?v=dsXwkGHSb_Y) (30 min). The middleware pipeline section is the most commonly misunderstood and most commonly asked about — pay particular attention to it.

**→ Practice:** Build or extend my risk-event-tracker API to include: a custom middleware that logs request duration, attribute routing on all controllers, a validated `[FromBody]` DTO with DataAnnotations, and one JWT-protected endpoint. Building rather than reading is the only way these concepts stick.

---

### Checkpoint 8.4 — Entity Framework Core

- [ ] Code-first approach: defining the model, generating migrations
- [ ] `DbContext` and `DbSet<T>`: what they represent
- [ ] Migrations: what they track and how to apply them
- [ ] Eager vs lazy vs explicit loading — and the N+1 problem lazy loading causes
- [ ] `.AsNoTracking()`: what it does and when to use it for performance

**→ Foundation:** Follow [Microsoft Docs — Getting Started with EF Core](https://learn.microsoft.com/en-us/ef/core/get-started/overview/first-app) (20 min, code along). The key things to lock in: how migrations work, and what change tracking does.

**→ Practice:** Add EF Core to my risk-event-tracker project if it doesn't have it. Write a query that causes an N+1 problem — load entities, then access a navigation property in a loop. Observe the generated queries in the debug output. Fix it with `Include()`. Then run the same query with `.AsNoTracking()` and write a comment on when I would and wouldn't use it.

---

### Checkpoint 8.5 — Testing

- [ ] Unit tests with xUnit: `[Fact]` and `[Theory]`
- [ ] Mocking with Moq: replacing real dependencies with controllable fakes
- [ ] What makes code testable: DI + single responsibility are the prerequisites
- [ ] Arrange / Act / Assert structure
- [ ] Integration tests vs unit tests: what each covers and why I need both

**→ Foundation:** Watch [Tim Corey — Unit Testing in C# with xUnit](https://www.youtube.com/watch?v=2Wp8en1I9oQ) (45 min — code along with it). Longer but it's a practical walkthrough, not a lecture. The Moq section is the most valuable part.

**→ Practice:** Write unit tests for my risk-event-tracker's service layer using xUnit + Moq. Aim for at least 10 tests covering happy paths and edge cases. If my service layer isn't testable (creates its own dependencies internally), refactor it to use constructor injection first — that refactor is itself the most valuable part of this exercise.

---

---

# TRACK 3 — SYSTEM DESIGN

> Start this track when approaching the application phase. DSA and C# foundations first — system design is about reasoning through trade-offs, which requires knowing what the components actually do.

---

## Stage 1 — Core Concepts

_Each concept is a tool. The practice is understanding it well enough to reach for it instinctively when designing._

---

### Checkpoint 9.1 — Scalability Fundamentals

- [ ] Vertical vs horizontal scaling: what each is and the core trade-offs
- [ ] Stateless vs stateful services: why statelessness enables horizontal scaling
- [ ] Load balancing: round-robin, least connections, consistent hashing
- [ ] What a reverse proxy is and why it's used

**→ Foundation:** Watch [ByteByteGo — System Design Fundamentals](https://www.youtube.com/watch?v=lX4CrbXMsNQ) (10 min). ByteByteGo's short videos are the best entry point for system design concepts — dense, visual, and accurate.

**→ Practice:** After watching, draw a simple 3-tier web app on paper: client → load balancer → app servers → database. Annotate each component: "what breaks if this fails?" and "how does this scale?". This is the mental model underlying every system design interview.

---

### Checkpoint 9.2 — Caching

- [ ] Why caching exists: latency reduction, database offload
- [ ] Cache strategies: cache-aside, write-through, write-back, read-through
- [ ] Cache invalidation: why it's genuinely hard
- [ ] Redis: what it is and common use cases (sessions, rate limiting, pub/sub)
- [ ] CDN: what it caches and when it's relevant

**→ Foundation:** Watch [ByteByteGo — Top Caching Strategies](https://www.youtube.com/watch?v=a9__D53WsMs) (8 min).

**→ Practice:** For each cache strategy, write one sentence describing a scenario where it's the right choice. Then answer out loud: "In a system where users frequently read their own profile data but rarely update it, which caching strategy would I use and why?" Write or speak a 3–4 sentence answer as if in an interview.

---

### Checkpoint 9.3 — Databases

- [ ] SQL vs NoSQL: when each is appropriate — it's about access patterns, not "modern vs legacy"
- [ ] ACID properties: what each letter means and why they matter together
- [ ] Database indexing: speeds reads, adds write overhead — understand the trade-off
- [ ] Replication: primary-replica pattern, read replicas, replication lag
- [ ] Sharding: horizontal partitioning strategies and their trade-offs
- [ ] CAP theorem: I can only have two of three — know what each choice gives up

**→ Foundation:** Watch [ByteByteGo — CAP theorem explained](https://www.youtube.com/watch?v=BHqjEjzAicA) (8 min) as a starting point. If I want to go deeper (recommended), read chapters 1 and 6 of _Designing Data-Intensive Applications_ by Martin Kleppmann — it's the definitive resource for this topic.

**→ Practice:** Write a one-paragraph comparison of when I'd choose Cassandra vs PostgreSQL for a given use case. Forcing myself to articulate this with concrete reasoning is the test. Then draw replication and sharding concepts on paper, labelling where failures can occur in each.

---

### Checkpoint 9.4 — APIs & Communication

- [ ] REST: stateless, resource-based, standard HTTP verbs — I already know this
- [ ] REST vs RPC vs GraphQL: when the trade-off matters
- [ ] Synchronous vs asynchronous communication: latency vs resilience
- [ ] Message queues (Kafka, RabbitMQ): decoupling producers from consumers
- [ ] Webhooks vs polling vs WebSockets: push vs pull models

**→ Foundation:** Watch [ByteByteGo — REST vs RPC vs GraphQL](https://www.youtube.com/watch?v=yGtpkSXGZDQ) (10 min). For the Kafka/messaging section, lean on my existing experience rather than re-learning it abstractly.

**→ Practice:** Answer out loud: "In the risk pipeline, why does it use Kafka rather than direct API calls between services?" I've worked in that system — be able to articulate the specific trade-offs: decoupling, backpressure handling, message replay. This is directly usable interview material.

---

### Checkpoint 9.5 — Reliability & Fault Tolerance

- [ ] High availability: what it means, how redundancy achieves it
- [ ] Single points of failure: how to identify and eliminate them
- [ ] Circuit breaker pattern: stops calling a failing service repeatedly
- [ ] Retries with exponential backoff and jitter — why jitter matters
- [ ] Rate limiting: token bucket and leaky bucket algorithms
- [ ] Health checks and basic observability

**→ Foundation:** Read [Microsoft — Cloud Design Patterns: Reliability](https://learn.microsoft.com/en-us/azure/architecture/framework/resiliency/reliability-patterns) (15 min, skim the pattern summaries). Focus on circuit breaker, retry, and rate limiting.

**→ Practice:** For each of the five bullet points above, describe one scenario where that concept would have prevented a production incident. These can be hypothetical. Connecting abstract concepts to concrete failure modes is exactly how system design interviews probe understanding — and I already have real production context to draw on.

---

## Stage 2 — Design Practice

---

### Checkpoint 10.1 — A Framework for Answering Design Questions

- [ ] Repeatable structure: requirements → scale estimation → API design → data model → high-level design → deep dive → trade-offs
- [ ] Clarify functional vs non-functional requirements before designing anything
- [ ] Estimate scale before choosing components: "how many users, reads/writes per second?"
- [ ] The answer is the reasoning, not the diagram

**→ Foundation:** Read chapter 1 of _System Design Interview_ by Alex Xu. Short, practical, and gives me the exact repeatable framework to use on every problem. Get the book — it's the single most valuable resource for this track.

**→ Practice:** Before attempting any design problem, write the framework steps on a card and keep it visible. For the first 3–4 problems, follow it mechanically even if it feels slow. The goal is to make the structure automatic so I don't freeze when an interviewer gives me an open-ended prompt.

---

### Checkpoint 10.2 — Core Practice Problems

_Work through each one out loud, following the framework from 10.1. Time myself — aim for 35–45 minutes per design._

- [ ] **URL Shortener** — hashing, redirects, storage, read-heavy design
- [ ] **Rate Limiter** — token bucket, Redis, distributed environments
- [ ] **Notification System** — push/email/SMS, fan-out, queue-based architecture
- [ ] **Chat Application** — WebSockets, message storage, delivery guarantees
- [ ] **News Feed / Timeline** — fan-out on write vs fan-out on read trade-off
- [ ] **File Storage System** — chunking, CDN, metadata vs blob storage
- [ ] **Distributed Cache** — eviction policies (LRU), consistency, Redis internals

**→ Foundation:** Each problem has a dedicated chapter in _System Design Interview_ by Alex Xu. Read the chapter first, then close the book and design the system from scratch myself. The read gives me enough foundation to get started — which is exactly the learning style that works for me.

**→ Practice:** After each design, write three things: one thing I got right, one thing I missed, one trade-off I didn't consider. That debrief is more valuable than the design itself.

---

### Checkpoint 10.3 — Communication Under Pressure

- [ ] Can articulate trade-offs clearly: "I chose X over Y because..."
- [ ] Narrates thinking even when uncertain — never goes silent
- [ ] Handles interviewer pushback without collapsing
- [ ] Knows when to go deep vs stay high-level from interviewer cues

**→ Foundation:** None — this is a performance skill, not a knowledge skill.

**→ Practice:** Use [Pramp](https://www.pramp.com) for free peer mock interviews (system design and coding both available). Do at least 3–4 before my first real interview. A cheaper alternative: explain a design to someone non-technical — if I can't make it clear to them, I don't understand the trade-offs well enough yet. Teaching forces clarity.

---

---

# RESOURCES SUMMARY

| Area                                | Resource                                                                                                                                                                  | Format               |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| DSA patterns & problems             | [NeetCode.io](https://neetcode.io)                                                                                                                                        | Video + problem sets |
| DSA practice platform               | [LeetCode](https://leetcode.com) — in C#                                                                                                                                  | Problems             |
| CLR, memory, GC                     | [Microsoft Learn — .NET docs](https://learn.microsoft.com/en-us/dotnet/)                                                                                                  | Documentation        |
| Stack/heap, OOP, delegates, testing | [Tim Corey — YouTube](https://www.youtube.com/@IAmTimCorey)                                                                                                               | Videos               |
| async/await, threading, ASP.NET     | [Nick Chapsas — YouTube](https://www.youtube.com/@nickchapsas)                                                                                                            | Videos               |
| SOLID, DI, architecture             | [Milan Jovanović blog](https://www.milanjovanovic.tech/blog)                                                                                                              | Articles             |
| Design patterns                     | [Refactoring.Guru — C#](https://refactoring.guru/design-patterns/csharp)                                                                                                  | Articles + code      |
| async best practices                | [Stephen Cleary — Async best practices (MSDN)](https://learn.microsoft.com/en-us/archive/msdn-magazine/2013/march/async-await-best-practices-in-asynchronous-programming) | Article              |
| System design concepts              | [ByteByteGo — YouTube](https://www.youtube.com/@ByteByteGo)                                                                                                               | Videos               |
| System design practice              | _System Design Interview_ — Alex Xu (Vol. 1)                                                                                                                              | Book                 |
| System design depth                 | _Designing Data-Intensive Applications_ — Kleppmann                                                                                                                       | Book                 |
| Mock interviews                     | [Pramp](https://www.pramp.com)                                                                                                                                            | Live peer practice   |

---

_Last updated: April 2026_
