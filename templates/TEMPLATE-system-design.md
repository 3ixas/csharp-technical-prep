# System Design: [Problem Name]

> **Date attempted:**  
> **Time taken:**  
> **Reference:** Alex Xu — Chapter [X]

---

## Step 1 — Requirements

### Functional Requirements
*What must the system do? (core features only)*

-
-
-

### Non-Functional Requirements
*Scale, latency, availability, consistency expectations.*

-
-
-

### Out of Scope
*What am I explicitly not designing?*

-

---

## Step 2 — Scale Estimation

*Rough numbers — order of magnitude is fine.*

- **Daily active users:**
- **Reads per second:**
- **Writes per second:**
- **Storage needed (per year):**
- **Bandwidth:**

---

## Step 3 — API Design

*The key endpoints or interfaces the system exposes.*

```
POST   /[resource]        — [what it does]
GET    /[resource]/{id}   — [what it does]
```

---

## Step 4 — Data Model

*Key entities and their relationships. What gets stored where.*

| Entity | Fields | Storage |
|---|---|---|
| | | |

---

## Step 5 — High-Level Design

*Draw this on paper first, then describe it in text.*

```
[Client] → [Load Balancer] → [App Servers] → [Database]
                                           ↘ [Cache]
```

*Describe each component and why it's there:*

-
-
-

---

## Step 6 — Deep Dive

*Pick 1–2 components and go deeper. What are the hard parts?*

### [Component 1]

### [Component 2]

---

## Step 7 — Trade-offs & Decisions

*For each major decision, state what I chose and why.*

| Decision | Chose | Over | Because |
|---|---|---|---|
| | | | |

---

## Debrief

### What I got right
-

### What I missed
-

### Trade-off I didn't consider
-
