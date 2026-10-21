# Criterion A — Review notes for document-a.md

> **What this file is:** feedback and a revision checklist for the draft in `document-a.md`.
> It is **not** text to paste into the IA. Rewrite your Criterion A in your own words.
> Basis: *IB Computer Science Guide, first assessment 2027* — Criterion A descriptors,
> printed pp. 55–56 (PDF pp. 61–62); documentation rules, printed p. 55 (PDF p. 61).
> Provisional teacher-support feedback only — no mark is given here.

---

## 1. What the 2027 Criterion A asks for

Criterion A is **"Problem specification" (4 marks)**, recommended about **300 words**.
The top band (3–4) asks you to:

1. **describe** the problem scenario in terms of its **measurable solution requirements**;
2. **state appropriate success criteria** (measurable outcomes derived from those requirements);
3. **explain** why you chose this **computational context** for the solution.

The success criteria you write here are reused in Criterion B (planning), D (development)
and E (evaluation), so every SC must be something you can later test and evaluate.

The whole documentation must not exceed **2,000 words** (code excerpts, comments and diagrams excluded).

---

## 2. Current state of the draft

| Check | What the draft shows | Location in `document-a.md` |
|---|---|---|
| Heading | Titled "Criteria A: Planning" — in the 2027 guide, Planning is Criterion **B**; A is **Problem specification** | line 1 |
| Length | ~1,789 words (raw count, includes notes-to-self) — about 6× the recommended 300 | whole file |
| Problem scenario | Written **twice** (lines 4–6 and again 32–35, plus 37–38) | 4–6, 32–38 |
| Computational context | Explained **twice** with different technologies (FastAPI + PostgreSQL vs "Java, Python or Node.js") | 9–12, 15 |
| Success criteria | **Three** separate lists: unlabelled bullets, three "should" statements, and SC-1…SC-10 | 17–29, 42–44, 60–69 |
| Limitations / scope | Present | 48–57 |
| Notes-to-self in Mongolian | Still in the draft | 55, 59 |

---

## 3. Issues to resolve (you decide how)

**A. Choose one version of each part.** Decide which scenario, which technology stack and
which success-criteria list is final, and remove the rest. Right now an examiner cannot tell
which one you will test against in Criterion E.

**B. Inconsistencies between versions** — check which is true for your product:

- Club status: "open / closed" (lines 6, 23) vs "open / full / closed" (lines 37, 65).
- Who edits club information: the **coordinator** (line 29) vs **club administrators** (line 38, SC-7).
- Client's role name: "activities coordinator" (line 4) vs "Club Activity Manager" (lines 38, 54).
- Technology: line 11 lists "Python for functionality" alongside HTML/CSS/JS, and line 15 says the
  server language could be Java, Python or Node.js. Which one have you actually chosen?
- Line 42 says an account is required to submit requests; lines 25 and 28 (older list) do not mention accounts.

**C. Requirements described in the scenario but missing from SC-1…SC-10.**
If these matter to your client, decide whether they need an SC; if not, consider whether they belong in the scenario:

- page loads within five seconds (line 44)
- at least six pieces of information on each club page (line 43)
- data persists after a server restart (line 27)
- incomplete submissions are rejected with an error message (line 28)
- works on school computers and student devices (line 19)
- email **verification** (line 12) — SC-1 only covers the domain check
- QR code on posters (line 38)

**D. Measurability of SC-1…SC-10.** For each one, ask: *"What exact test would show this passed or failed?"*

| SC | Something to check (not a correction) |
|---|---|
| SC-1 | Covers register **and** log in **and** domain rejection. Is verification part of it? How will you show "rejected"? |
| SC-2 | "all approved clubs … images" — but line 43 lists six fields without images. Which is right? |
| SC-3 | "availability" — same as "membership status" in SC-2? |
| SC-4 | Two outcomes (saved **and** shown to the correct admin). Will you test them separately? |
| SC-5 | "save and display the updated request status" — displayed to whom? |
| SC-6 | "an appropriate message" — how will you judge "appropriate"? |
| SC-7 | Clear and testable. |
| SC-8 | How will you test that a blocked action is really blocked (not just hidden in the UI)? |
| SC-9 | Contains three separate features (propose, approve/reject, assign admin). |
| SC-10 | "submitted activity information" — what is this exactly? It is not described elsewhere. |

**E. Computational context.** The descriptor asks you to **explain the choice**, not only list tools.
For each technology you keep (web app, relational database, role-based access, regex validation),
check that you say *why it suits this problem* rather than *what it is*.

**F. Small language points.** "website()" (line 49), "Students because have difficulty…" (line 33),
"in one web" (line 37).

**G. Regex note (check yourself).** Line 15 gives the pattern `@shineue.edu.mn`. Think about what a
`.` means in a regular expression, and whether the pattern only matches at the **end** of the address.
You will need to justify and test this in Criteria C/D.

---

## 4. Questions to think about before you rewrite

1. If you could keep only five success criteria, which ones prove the client's problem is solved?
2. Which of your requirements did Odgerel Manager actually ask for, and which did you add yourself?
3. Is your product scope realistic for the development time you have — which features are essential and which are "nice to have"?

---

## 5. Revision checklist

- [ ] Heading changed to **Criterion A: Problem specification**
- [ ] One scenario, one computational-context explanation, one SC list
- [ ] Scenario states the **measurable requirements** the client needs
- [ ] Every SC is numbered, measurable and testable later in Criterion E
- [ ] Every requirement in the scenario is either an SC or deliberately left out
- [ ] Technology choices are **explained**, not only listed
- [ ] Notes-to-self removed; section close to ~300 words
- [ ] Decomposition / structure chart moved to **Criterion B** (not yet in this repository)
