# Coding in the Age of AI Requires a Separation of Powers

### The RGB Development Methodology (Rules, Guard, Build)

*"Don't wish for it. Be it."*
— Neale Donald Walsch, Conversations with God, Book 1

## Core Structure

| Government | RGB Methodology | Actual Form |
|---|---|---|
| Legislature | Rules | Constitution / Laws / Specs |
| Judiciary | Guard | Test Cases |
| Executive | Build | Application Code |

---

## Summary

- In the age of AI, what matters most in a project is no longer how fast you ship code — it's **how well you establish and maintain order**.
- The RGB methodology manages that order by separating concerns into three roles: **legislative, judicial, and executive.**
- **Rules** is the legislature. And Rules itself breaks down further: the **constitution**, which defines the top-level structural principles of the project; the **laws**, which translate those principles into operational rules; and the **specs**, which define the features to be built.
- **Guard (Test Cases)** is the judiciary. It rules on whether Rules have actually been violated, and enforces the project's order through tests.
- **Build (Application Code)** is the executive. The actual service code — controllers, use cases, event handlers — operates only within the boundaries set by Rules and Guard.
- When I say "previously successful projects" in this document, I don't mean commercial success whatsoever. The success I'm talking about is purely **architectural success**.
- Meaning: clean boundaries, strong tests, structures that didn't collapse when features kept piling on.
- **The constitution and laws are about structure (architecture), not domain logic.**
- **Specs define domain logic and the features to be implemented.**
- RGB is not a one-time document exercise. It's a **repeating loop: Rules → Guard → Build → reinforce Rules**.
- You set the Rules first, make them enforceable through Guard (Test Cases), and build within them. As implementation reveals problems, you reinforce Rules and Guard.
- Throughout this process, AI does as much as possible. Humans review and approve.
- Ultimately, RGB is a methodology for creating **repeatable order that keeps a project from collapsing — even when AI is writing most of the code**.

---

When starting a new project, you've probably said something like this to Claude Code or GPT at least once:

- "Set up the initial structure like Project A."
- "Make the controllers follow the style of Project B."
- "Reference Project C for the test style."
- "Let's go with the package structure that worked well last time."

This isn't strange. It's completely natural.

Developers don't want to start a new project from a blank slate. If you've had even one project where the structure was solid, you want to carry that order into the next one. Package boundaries, test style, sync/async flow, where shared code lives, the role of real-time channels — once you've felt these working well, it's only natural to want to bring that sense back.

The problem starts here.

Everyone agreed the order was good — but when the next project begins, the same debates start from scratch. How far does shared go? When do we hand off to events? Can we reference another domain directly? How far do we push integration tests? What's allowed in real-time channels? All of it comes up again.

You clearly did it well before. But in the new project, it blurs.

Why?

I think the reason is simple.

The good structure existed — but it was never fixed as **reusable order**.

- People remember. But memory doesn't become a standard.
- Teams share intuition. But intuition isn't a test.
- AI follows examples. But examples aren't principles.

That's why I've come to believe that what matters most in development today isn't raw code output — it's **establishing order first**.

And I've given the simplest framework I know for organizing that order a name: **the RGB Development Methodology**.

RGB reads like this:

- **Rules**: Define the order of the project.
- **Guard**: Make that order hold.
- **Build**: Implement within that order.

To put it more vividly, RGB is the **separation of powers** for software development.

- The legislature is Rules.
- The judiciary is Guard.
- The executive is Build.

This analogy might sound absurd. But it fits better than you'd expect.

---

# Why I Started Thinking This Way

What developers want in the age of AI isn't complicated.

- Have LLMs handle as much implementation as possible.
- Ship features fast.
- Have enough tests.
- Keep code quality up.
- And keep the project from losing its philosophy and collapsing under the weight of new features.

There's one more thing.

- Reuse a structure that worked well — in the next project.

By "worked well," I don't mean revenue. I don't mean users. I don't mean funding.

The success I'm talking about is **architectural success**.

- Boundaries were clean.
- Dependencies were healthy.
- Shared code stayed uncontaminated.
- Tests protected the structure.
- The project didn't collapse when features kept getting added.
- Code quality didn't tank even when AI was doing most of the implementation.

---

# "Who Doesn't Know This? Even LLMs Know This."

- "Tests should run independently, obviously."
- "If domains reference each other directly, it'll knot up later."
- "Common code should be extracted to shared."
- "Async flows are better handled through events."
- "Isn't it a bit off to mutate state inside an SSE handler?"

These things are familiar to any developer.

But here's the problem.

- Common sense rarely gets written down.
- What doesn't get written down doesn't become a standard.
- Without a standard, compromises happen when things get busy.
- Repeated compromises accumulate as exceptions.
- Exceptions accumulate until the structure breaks.

What's needed, then, isn't good thinking.

**It's fixed rules.**

In RGB, that's exactly what Rules is.

---

# The Constitution and Laws Must Not Know Domain Logic

To be more precise:

- **The constitution and laws don't know domain logic. They know architecture.**
- **Specs define domain logic.**

In RGB, Rules isn't a single layer — it's three layers:

- **Constitution**: Structural philosophy
- **Laws**: Structural rules
- **Specs**: Domain logic and features to be implemented

---

# Why Rules Must Be Split Into Constitution, Laws, and Specs

| Layer | Role | Nature | Example |
|---|---|---|---|
| Constitution | Top-level structural principles | Abstract | **No direct dependencies between domains** |
| Laws | Operational rules | Concrete | **All JPA-related tests must ultimately roll back** |
| Specs | Definition of what to implement | Feature-focused | **Nickname input is required during sign-up** |

The constitution sets the direction.
The laws set the operational rules.
The specs define what gets built.

---

# Guard Is the Judiciary

Guard is not just a bundle of tests.

**It is the judiciary of the project.**

- Did this reference another domain directly?
- Is a read-only channel mutating state?
- Are tests no longer running independently?

If any rule is broken, **the test must fail.**

---

# Build Is the Executive

Build is the actual implementation.

Controllers, use cases, services, event handlers — the real code — move **only within the boundaries set by Rules and Guard**.

That's why Build isn't just coding.

**It's execution under the jurisdiction of Rules and Guard.**

---

# In Practice: RGB Repeats

```
Rules (add/refine Constitution / Laws / Specs)
↓
Guard (add/refine Test Cases)
↓
Build (implement)
↓
Reinforce Rules
↓
Reinforce Guard
↓
Repeat
```

---

# RGB Is Not a Human Procedure

Most of it is **performed by AI**.

- AI drafts the Rules.
- AI writes the Guard.
- AI does the Build.
- AI refines the Rules again.

Humans occasionally **review and approve**.

---

# Finally

The RGB approach isn't new at all.

Good teams always:

- Cared about structure.
- Cared about tests.
- Cared about boundaries.

What's changed is this:

**That order now has to include AI.**

Before, good rules kept teams from falling apart.
Now, good rules keep **AI from making the code fall apart**.

---

# Conclusion

- The RGB Development Methodology is an approach for establishing project order first — and iteratively evolving that order — in the age of AI-driven software development.
- In the Rules phase, define and refine the constitution, laws, and specs to establish structural order and clarify what gets built.
- In the Guard phase, use Test Cases to rule on whether that order is actually being upheld — and make it enforceable.
- In the Build phase, implement the actual Application Code within that order.

Through this repeating loop, **clean spec implementation and architectural integrity are continuously maintained and strengthened**.

---

## Addendum 1: The Power of Short Text

Complex AI coding strategies matter less than **short, clear rules**.

- The constitution is short and clear.
- The laws are short and clear.
- The tests are unambiguous.

Same goes for LLMs.

Simple, clear rules are followed far more reliably.

---

## Addendum 2: Don't Wish for Good Order. Have It.

*"Don't wish for it. Be it."*
— Neale Donald Walsch, Conversations with God, Book 1

RGB says:

**"Don't wish for good order. Have it. And within that order, code and structure align themselves."**
