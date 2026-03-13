# In the Age of AI-Written Code, Software Needs a Separation of Powers

## The RGB Methodology: Rules, Guard, Build

### Core Structure

| Separation of Powers in the Real World | RGB Methodology | Actual Form |
|---|---|---|
| Legislature | Rules | Constitutional / legal text |
| Judiciary | Guard | Test Cases |
| Executive | Build | Application Code |

## Summary

- In the AI era, the hard part of software projects is no longer just writing code quickly. What matters more is establishing order before a large amount of code gets written.
- What I call the **RGB methodology** is a way of treating that order like a system of legislation, judgment, and execution.
- **Rules** are the legislative branch. And Rules themselves split into two layers: **Constitution** and **Laws**.
- **Guard (Test Cases)** is the judicial branch. It determines whether Rules have actually been violated, and enforces project order through tests.
- **Build (Application Code)** is the executive branch. The actual application code—controllers, use cases, event handlers, services—must move only within the boundaries defined by Rules and Guard.
- When I say a “successful past project,” I do **not** mean commercial success. I mean **architectural success**.
- In other words: strong boundaries, strong tests, and a structure that did not collapse even as features kept being added.
- Rules are **not** business logic. They are not signup policies, discount policies, or settlement formulas. They are higher-order structural rules that define the order of the project itself.
- RGB is not a one-time documentation exercise. Just as TDD is iterative, RGB is iterative too.
- First you establish Rules, then you make them enforceable through **Guard (Test Cases)**, and then you develop **Build (Application Code)** inside those constraints. As implementation reveals new problems, you strengthen Rules and Guard again.
- As much of this cycle as possible can be carried out by AI, while humans review and approve the whole.
- Ultimately, RGB is a way to create a **repeatable order that prevents a project from collapsing even when AI writes a great deal of the code**.

At the start of a new project, most of us have said something like this to Claude Code or GPT at least once:

> “Set up the initial structure like Project A.”  
> “Match the controller style from Project B.”  
> “Use the testing style from Project C.”  
> “Let’s use that package structure we liked before.”

There is nothing strange about this. In fact, it is perfectly natural.

When developers start a new project, they do not want to begin from a true blank slate. If they have ever worked on a project whose structure felt right, they want to carry that order into the next one as much as possible. Package boundaries, testing style, synchronous and asynchronous flow, the location of shared code, the role of realtime channels—if those things worked once, of course they want that same feeling again.

And that is where the problem begins.

Everyone remembers that the previous structure felt good. But once the next project begins, the same debates start all over again. How much should live in `shared`? When should a flow be turned into an event? Is direct domain-to-domain dependency ever acceptable? How far should integration testing go? What exactly should be allowed in a realtime channel?

In other words, even when a team has already done something well before, the next project often starts to drift again.

Why?

My answer is simple:

Because the good structure existed, but it was never fixed into a **reusable order**.

People remember. But memory is not a standard.  
Teams share intuition. But intuition is not a test.  
AI can imitate examples. But examples are not principles.

That is why I have come to think that in modern development, what matters is not code output by itself, but the work of establishing order first. And for that order, I use a simple name:

**RGB**

- **Rules**: define the project’s order
- **Guard**: make that order enforceable
- **Build**: implement within that order

Or, in a more playful way:

**RGB is software development as a separation of powers.**

- Rules are the legislature.
- Guard is the judiciary.
- Build is the executive.

That may sound like a joke at first, but the metaphor fits better than it seems.

---

## Why I Started Thinking About This

What developers want in the age of AI is not actually very complicated.

They want LLMs to do as much implementation work as possible.  
They want feature development to be fast.  
They want tests to be strong enough.  
They want code quality to hold up.  
And they want the project not to lose its principles and collapse under continuous feature growth.

There is one more thing.

They want to reuse a structure that worked well once.

And by “worked well,” I do **not** mean revenue, user growth, or fundraising. Those kinds of success matter too, of course—but that is not what I mean here.

I mean **architectural success**.

- The boundaries were clear.
- The dependencies stayed healthy.
- Shared code did not become polluted.
- Tests protected the structure.
- The project did not collapse even as features kept coming.
- Even when AI generated a lot of code, the overall quality did not degrade too badly.

That is the kind of success I mean.

That is also why developers want to reference past projects. What they really mean is:

> “That project had good boundaries.”  
> “That project’s tests really protected order.”  
> “That project used a lot of AI-generated code, but somehow it didn’t fall apart.”

They want to reproduce that feeling.

But most of the time, this desire survives only as vague language.

> “We organized `shared` really well back then.”  
> “The domain boundaries were solid.”  
> “We did a good job blocking direct dependencies.”  
> “The tests were great.”

Those sentences are fine for retrospectives.  
They are not strong enough to become the legal order of the next project.

---

## “Who Doesn’t Already Know This?”

> “Tests should be independently runnable, obviously.”  
> “If domains depend on each other directly, it gets messy later.”  
> “Shared code belongs in `shared`.”  
> “Async flows should usually go through events.”  
> “Mutating state through SSE feels wrong.”

Every developer has heard things like this.  
They are familiar. They do not sound profound.  
And someone could easily respond:

> “Who doesn’t already know that?”

Exactly.

Most developers already know these things. None of this is some new revelation. It is practically common sense.

And that is exactly the problem.

Common sense is rarely written down.  
What is not written down does not become a standard.  
What is not a standard gets compromised when people are busy.  
Repeated compromises accumulate exceptions.  
And accumulated exceptions eventually destroy structure.

So the problem is not that people lack good instincts.  
The problem is that those instincts remain trapped inside people’s heads.

What we need, then, is not “good ideas,” but **good ideas fixed into short, strong rules**.

In RGB, that is what **Rules** are for.

---

## Rules Are Not Business Logic

There is an important distinction that has to be made early.

**Rules are not business logic.**  
**Rules are not domain logic.**

Signup policy, discount policy, settlement formulas, point expiration rules—those are not Rules. Those belong to the domain. They vary from product to product, service to service.

What I mean by Rules is something above that level:

the structural order that determines **how the project itself is allowed to move**.

For example:

- Domains must have clear boundaries.
- Direct dependencies between domains are forbidden.
- Shared code belongs in shared areas.
- Synchronous calls must go through approved paths.
- Asynchronous flows should be handled through events.
- Tests must be independently runnable.
- Realtime channels should be read-only.

These are not feature rules.  
They are structural rules.

They define the order in which the program is allowed to exist.

---

## Why Legislation Must Split into Constitution and Laws

If you think of Rules as just a flat list, you miss something important.

Legislation is not one layer. And just as real-world legislation is not just a pile of rules, project Rules should be divided into two levels:

1. **Constitution**
2. **Laws**

First comes the **Constitution**.

These are the highest-level principles.  
They sit above all concrete rules.  
They define the direction.

For example:

- Domains must have clear boundaries.
- Direct dependencies between domains are forbidden.
- Shared code belongs in shared areas.
- Realtime channels should be read-only.

These are somewhat abstract.  
But that abstraction is exactly what makes them powerful.  
When a new situation appears that the concrete rules do not yet cover, the Constitution still provides direction.

Then come the **Laws**.

These are the project-level rules derived from the Constitution.

For example:

- Synchronous inter-domain calls must go through an API client.
- Asynchronous flows must be implemented through events.
- `shared` must not contain domain entities or domain policies.
- In test environments, asynchronous behavior must be verifiable deterministically.

So legislation is not just “write down a few rules.”  
It is a structured system made of abstract Constitution and concrete Laws.

Why bother making that distinction?

Because rules change too.

Teams change.  
Technology changes.  
AI usage changes.  
Project character changes.

When that happens, the split between Constitution and Laws helps you understand **what should be revised at the level of principle, and what should be revised at the level of implementation**.

When details are missing, the Constitution gives direction.  
When implementation begins, the Laws provide operational standards.

That is why legislation becomes much stronger when it is divided this way.

---

## Why This Fits the LLM Era Even Better

This structure is not useful only because of people.  
If anything, it matters even more because of AI.

LLMs follow short, separated principles far better than they follow vague intention hidden inside long paragraphs.

Compare these two:

> “Interactions between domains should remain appropriately loose depending on context.”

A human can sort of understand that.  
An AI can sort of understand that too.

The problem is **sort of**.

Now compare it to this:

- Direct dependencies between domains are forbidden.
- Synchronous calls must go through approved paths.
- Asynchronous flows must be handled through events.

That is strong for humans.  
And it is strong for LLMs too.

Even the naming helps.

Telling an AI, “Please refer to these rules,” is one thing.  
Telling it, “This is the Constitution of the project. These are the Laws of the project,” is something else.

LLMs are surprisingly sensitive to names and hierarchy.  
So “Constitution” and “Laws” are not decorative labels.  
They are an interface for communicating the rank and force of each rule.

---

## Guard Is the Judiciary

Legislation alone does not make a system function.

In the real world, if laws exist but there is no institution that judges violations, the law is little more than text. The same is true in software.

What prevents Rules from ending as documents is **Guard**.

Guard includes tests, architecture checks, package dependency checks, integration validation, constraint checks, and other mechanisms of enforcement. But the core idea is simple:

**If a rule is violated, something must fail.**

- Did one domain directly reference another?
- Did a read-only channel mutate state?
- Did the shared layer start swallowing domain logic?
- Are tests no longer independently runnable?
- Has async flow become impossible to verify?

Guard is what judges these things.

So Guard is not just “a bundle of tests.”  
It is the project’s judiciary.

Tests are not merely tools for saying, “The feature works.”  
A strong Guard says, “This implementation violated the Rules.”

That is a very different role.

---

## Build Is the Executive

Finally, there is **Build**.

Build is the actual implementation:

controllers, use cases, services, domain methods, event handlers, schedulers, realtime delivery code, and so on.

Build is what actually gets work done.  
But it must not act arbitrarily.

Rules exist above it.  
Guard exists beside it.  
Build moves only within that order.

That is why Build is not just coding.  
It is **execution under a legal structure**.

This metaphor is useful because it also shows that the roles must not collapse into each other.

- Execution code must not invent rules for itself.
- Guard must not be reduced to checking functionality without Rules.
- If Build grows without Rules, the project becomes a kind of lawless state.

A good project is not just a pile of code.  
In a slightly dramatic way, it is closer to a small state with legislation, judgment, and execution clearly separated.

---

## RGB in Practice: It Repeats Like TDD

RGB is not a declaration.  
In practice, it has to run as a loop.  
In that sense, RGB resembles TDD.

TDD goes like this:

- write a failing test
- make it pass
- refactor
- repeat

RGB has its own loop:

### 1. Establish Rules

First, define the order this project needs.

And those Rules split into two levels:

- **Constitution**: the most abstract and highest principles
- **Laws**: concrete project rules derived from that Constitution

So Rules are not just a checklist.  
They are a legislative system.

### 2. Create Guard (Test Cases)

Then turn those Rules into something enforceable.

That means test cases and other validation mechanisms.

The core idea remains simple:

**If a rule is broken, the test must fail.**

That is why Guard is not just a collection of tests.  
It is the project’s judiciary.

### 3. Build (Application Code)

Now write the actual application code.

Controllers, use cases, services, domain methods, event handlers, schedulers—this is where the working software gets built.

But this part matters most:

**Application Code must move only inside the boundaries created by Rules and Guard.**

So Build is not just coding.  
It is the executive branch of the project.

### 4. Strengthen Rules and Guard Again

As implementation proceeds, reality reveals things:

- the Constitution was too vague
- the Laws were incomplete
- the Test Cases did not protect the order strongly enough
- the Application Code exposed structural issues nobody anticipated

Then you revise the Rules, strengthen the Guard, and continue building again.

So RGB runs like this:

**Rules → Guard (Test Cases) → Build (Application Code) → reinforce Rules → repeat**

That is why RGB, like TDD, is not a one-time activity.  
It is an iterative loop that keeps strengthening the project’s order.

---

## RGB Is Not a Process Humans Must Perform Alone

There is another important premise here.

RGB is **not** a process in which humans manually do everything.  
If anything, as much of it as possible should be carried out by AI.

- AI drafts the Rules.
- AI creates the Guard.
- AI writes the Build.
- Humans review and approve the whole.

So the role of the developer does not simply shrink.  
It changes.

The developer becomes less “the person who writes the most code” and more “the person who judges whether the rules and implementations produced by AI actually preserve the project’s order.”

I suspect this is where software skill will increasingly move:

- Can you design good legislation?
- Can you create strong judicial mechanisms?
- Can you evolve that order together with AI?
- Can you carry it into the next project?

Those may become some of the most important abilities in the field.

---

## How Does This Relate to TDD?

TDD is a loop for implementing behavior.  
Fail, pass, refactor.  
It is strong at making software do the right thing.

RGB is a loop for designing order.  
It defines what is allowed, what is forbidden, how that is enforced, and how implementation must happen within those boundaries.

So I think of them like this:

**TDD makes behavior correct.**  
**RGB makes structure durable.**

They are not competitors.  
They operate at different levels.

The outer loop is RGB.  
The inner loop can be TDD.

The outer loop creates order.  
The inner loop makes features work.

And this distinction becomes especially important in the age of AI, because AI is already fairly good at implementing features—but feature implementation without order eventually destroys the project.

---

## Do You Need to Reinvent It for Every Project?

This question comes naturally too:

> “Do we have to create Rules from scratch for every new project?”

My answer is: mostly no.

Rules are not domain knowledge.  
They are structural order.  
That means much of them is reusable.

A good Constitution can be reused.  
Good Laws can become templates.  
Good Guard can be reused repeatedly.  
Good Build patterns can become the team’s default starting point.

Over time, the beginning of a new project changes.

Instead of saying:

> “Let’s try to do it well again from scratch.”

You begin to say:

> “Let’s bring in the order that already worked well.”

That is the real value of RGB.

It turns one architectural success into something that can be **reproduced** in the next project.

---

## Final Thoughts

RGB is not radically new.

Good teams always cared about boundaries, tests, and structure.  
What has changed is that now we have to operate that order in a world where AI participates directly in code generation.

In the past, good rules helped keep teams from damaging a project too badly.  
Now, good rules help keep **AI** from damaging it too badly too.

---

## Conclusion

Developers already know many good principles.  
The problem is that those principles remain trapped in their heads.

So first, we need legislation.  
And that legislation should split into **Constitution** and **Laws**.

Then we need judiciary.  
That means turning Rules into something enforceable through **Guard (Test Cases)**.

Finally, we need execution.  
That means letting AI **Build (Application Code)** only inside that order.

That is how you preserve code quality even when AI generates large amounts of code.  
That is how you keep structure from collapsing even as features keep getting added.  
And that is how you make architectural success reusable from one project to the next.

In the age of AI, what matters most may no longer be raw code output, but the ability to create good legislation, establish strong judicial enforcement, and make AI execute well within that order.

## One-Sentence Summary

**The RGB methodology is an approach in which you first establish Rules as a system of Constitution and Laws, then make them enforceable through Guard (Test Cases), and finally let AI Build (Application Code) inside those boundaries—so that architectural success becomes repeatable, transferable, and durable.**
