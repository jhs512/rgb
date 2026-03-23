# Coding in the Age of AI Requires a Separation of Powers

### The RGB Development Methodology (Rules, Guard, Build)

*"Don't wish for it. Be it."*
— Neale Donald Walsch, Conversations with God, Book 1

---

## Core Structure

| Government | RGB Methodology | Actual Form |
|---|---|---|
| Legislature | Rules | Structure Rules (Constitution/Laws), Spec Rules (Constitution/Laws) |
| Judiciary | Guard | Test Cases |
| Executive | Build | Application Code |

---

## Summary

- In the age of AI, what matters most in a project is no longer how fast you ship code — it's **how well you establish and maintain order**.
- The RGB methodology manages that order by separating concerns into three roles: **legislative, judicial, and executive.**
- **Rules** is the legislature. And Rules is divided into **Structure Rules and Spec Rules.**
- Each of these consists of two levels: **Constitution and Laws.**
- **Guard (Test Cases)** is the judiciary. It determines whether Rules have been violated and enforces the project's order through tests.
- **Build (Application Code)** is the executive. The actual service code — controllers, use cases, event handlers — operates only within the boundaries defined by Rules and Guard.
- When I say "previously successful projects," I do not mean commercial success. The success I refer to is purely **architectural success**.
- Meaning: clean boundaries, strong tests, and structures that did not collapse as features accumulated.
- RGB is not a one-time documentation effort. It is a **repeating loop: Rules → Guard → Build → reinforce Rules**.
- You define Rules first, make them enforceable through Guard (Test Cases), and build within them. As implementation reveals issues, Rules and Guard are reinforced.
- Throughout this process, AI performs as much of the work as possible. Humans review and approve.
- Ultimately, RGB is a methodology for creating **repeatable order that prevents a project from collapsing — even when AI writes most of the code**.

---

When starting a new project, you've probably said something like this to Claude Code or GPT at least once:

- "Set up the initial structure like Project A."
- "Make the controllers follow the style of Project B."
- "Reference Project C for the test style."
- "Let's go with the package structure that worked well last time."

This isn't strange. It's completely natural.

Developers don't want to start from a blank slate. If you've experienced even one project with a solid structure, you want to carry that order into the next one. Package boundaries, test styles, sync/async flows, where shared code belongs, the role of real-time channels — once you've seen these work well, it's natural to want to reuse that sense.

The problem starts here.

Everyone agrees the structure was good — but when the next project begins, the same debates start again from scratch. How far does shared go? When do we switch to events? Can domains reference each other directly? How far should integration tests go? What is allowed in real-time channels?

You clearly did it well before. But in a new project, it becomes blurred again.

Why?

The reason is simple.

The structure existed — but it was never fixed as **reusable order**.

- People remember. But memory is not a standard.
- Teams share intuition. But intuition is not a test.
- AI follows examples. But examples are not principles.

That is why I have come to believe that what matters most in development today is not raw code output — but **establishing order first**.

And I call the simplest framework for organizing that order: **the RGB Development Methodology**.

RGB reads as follows:

- **Rules**: Define the order of the project.
- **Guard**: Enforce that order.
- **Build**: Implement within that order.

To put it more vividly, RGB is the **separation of powers** for software development.

- The legislature is Rules.
- The judiciary is Guard.
- The executive is Build.

This analogy may sound exaggerated. But it fits better than expected.

---

# Why I Started Thinking This Way

What developers want in the age of AI is not complicated.

- Let LLMs handle as much implementation as possible.
- Ship features quickly.
- Maintain sufficient testing.
- Keep code quality stable.
- Prevent the project from collapsing as features accumulate.

And one more thing:

- Reuse a structure that worked well in the next project.

By “worked well,” I do not mean revenue, users, or funding.

I mean **architectural success**.

- Boundaries were clear.
- Dependencies were healthy.
- Shared code was not polluted.
- Tests protected the structure.
- The system did not collapse as features accumulated.
- Code quality remained stable even when AI did most of the implementation.

---

# "Everyone Knows This. Even LLMs Know This."

- "Tests should run independently."
- "Direct domain coupling will create problems later."
- "Shared code should be extracted."
- "Async flows are better handled through events."
- "Mutating state inside an SSE handler feels wrong."

These are all familiar ideas.

But here is the problem.

- Common sense is rarely written down.
- What is not written down does not become a standard.
- Without a standard, compromises happen under pressure.
- Repeated compromises accumulate into exceptions.
- Exceptions accumulate until the structure collapses.

What is needed is not good thinking.

**It is fixed rules.**

And in RGB, that is exactly what Rules represents.

---

# Structure Rules and Spec Rules

Rules are divided into two categories:

- **Structure Rules**
- **Spec Rules**

Each category has two levels:

- **Constitution**
- **Laws**

---

## Structure Rules vs Spec Rules

These two address completely different concerns.

- Structure Rules define **how the code must be built**.
- Spec Rules define **what must be built**.

If these are mixed, rules become ambiguous and exceptions grow rapidly.

---

## Structure Rules

### Structure Constitution

The highest-level architectural principles.

- Domains must have clear boundaries.
- Direct dependencies between domains are forbidden.
- Asynchronous flows must be handled through events.
- Real-time channels must remain read-only.

---

### Structure Laws

Concrete rules enforceable in code.

- Direct imports across domains are not allowed.
- Shared code must not reside inside domain modules.
- Tests must be independently executable.
- Transaction boundaries must begin outside domain logic.

---

## Spec Rules

### Spec Constitution

Domain-level invariants.

- A user must have a unique identifier.
- A payment must always result in success or failure.
- Messages must have ordering.
- Events must be idempotent.

---

### Spec Laws

Concrete feature-level rules.

- Nickname is required during signup.
- Failed payments must transition to FAILED state.
- Messages must be ordered by creation time.
- Duplicate requests must not be processed twice.

---

## Key Insight

Structure and Spec influence each other, but they are not the same layer.

- Structure is the container.
- Spec is what runs inside it.

Separating them makes the system significantly more stable.

---

# Guard Is the Judiciary

Guard is not just a collection of tests.

**It is the judiciary of the project.**

- Did this reference another domain directly?
- Did a read-only channel mutate state?
- Are tests no longer independent?
- Has a spec been violated?

If any rule is broken, **tests must fail**.

---

# Build Is the Executive

Build is the actual implementation.

Controllers, use cases, services, and event handlers  
operate **only within the constraints defined by Rules and Guard**.

That is why Build is not just coding.

**It is execution under enforced order.**

---

# In Practice: RGB Repeats

Rules (define/refine Structure & Spec)
↓
Guard (enforce with tests)
↓
Build (implement)
↓
Reinforce Rules
↓
Reinforce Guard
↓
Repeat

---

# RGB Is Not a Human Procedure

Most of this process is performed by AI.

- AI drafts the Rules.
- AI writes the Guard.
- AI performs the Build.
- AI refines the Rules.

Humans review and approve.

---

# Finally

RGB is not fundamentally new.

Good teams have always:

- cared about structure,
- cared about tests,
- cared about boundaries.

What has changed is this:

**Now that order must include AI.**

Before, good rules prevented teams from collapsing.  
Now, good rules prevent **AI from collapsing the codebase**.

---

# Conclusion

- The RGB Development Methodology is an approach for establishing and maintaining order in AI-driven software development.
- Rules are divided into Structure Rules and Spec Rules, each consisting of a Constitution and Laws.
- Guard enforces that order through tests.
- Build implements within that order.

Through this loop,  
**architectural integrity and implementation consistency are continuously maintained and strengthened**.

---

## Addendum 1: The Power of Short Rules

Complex strategies matter less than **short, clear rules**.

- Constitutions are concise.
- Laws are concise.
- Tests are unambiguous.

LLMs follow simple and clear rules far more reliably.

---

## Addendum 2: Don't Wish for Good Order. Have It.

*"Don't wish for it. Be it."*

RGB says:

**"Don't wish for good order. Have it. And within that order, code and structure align themselves."**
