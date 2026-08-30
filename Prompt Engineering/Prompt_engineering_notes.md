### 1. First: What exactly is a prompt?
At the simplest level:
> A prompt is the information and instructions you provide to an LLM to influence what it produces.

But don't think of a prompt as merely a question.

Compare these:

#### Prompt A

> Review my code.

#### Prompt B

> You are a senior Java Spring Boot developer. Review the changed Java files in my current branch against master. Check for security vulnerabilities, bugs, Spring Boot best practices, and unnecessary complexity. Don't recommend unrelated refactoring.

Both are asking for a code review.

But B gives the model much more direction.

That's the heart of prompt engineering.

--- 

### 2. Prompt Engineering ≠ "Finding magic words"
Prompt Engineering is not equal to finding magic words, this is an important misconception.

You might see videos saying things like:

> "Use these 5 magic words to get 10x better AI responses."

Don't focus on that.

Prompt engineering is fundamentally about **communicating the task clearly enough that the model has less ambiguity about what you want.**

Think about giving requirements to another developer.

--- 
### 3. Our Six-Part Framework
| Dimension            | Question                                                 |
| -------------------- | -------------------------------------------------------- |
| **Clarity**          | Does the AI understand what I want?                      |
| **Context**          | Does it know the necessary background?                   |
| **Specificity**      | Have I defined exactly what to focus on?                 |
| **Constraints**      | What should it/shouldn't it do?                          |
| **Output Format**    | What should the response look like?                      |
| **Token Efficiency** | Am I giving useful information without unnecessary text? |

### More words ≠ better prompt.

This:

> You are an extremely highly experienced world-class senior Java developer with decades and decades of experience who understands everything there is to know about Java...

is mostly noise.

This:

> Act as a senior Java/Spring Boot engineer.

does almost the same job with far fewer tokens.

That's token efficiency.

---

### 6. Context doesn't mean "dump everything"

This is where beginners often go wrong.

They think:

> More context = better answer.

Not necessarily.

Suppose you're asking the AI to review one Java class.

You don't necessarily need to give it:

- 500 lines of unrelated code
- Entire Git history
- Every Jira ticket ever created
- Complete database schema

Give it relevant context.

This is similar to debugging.

If your colleague asks:

> Why is this method failing?

You don't send them your entire company's source code.

You give them the relevant information.

---

### 7. Specificity

This is where your prompt can become significantly better.

You wrote:

> Check for security issues.

That's good, but vague.

What security issues?

You could specify:

> Check for SQL injection, authentication/authorization issues, insecure input handling, sensitive-data exposure, and unsafe logging.

Now the AI has a concrete checklist.

But there's another danger.

Don't turn every prompt into a 500-line specification.

You need enough specificity to remove important ambiguity.

--- 

### 8. Constraints (Limitation) 

You must provide the limitation or less it may redesign the entire source code. So it's always better to provide it's constraints.

---

### 9. Output Format 
You must provide the expected output format 

### Let's build your prompt layer by layer
Layer 1 — Role

> Act as a senior Java/Spring Boot engineer.

Layer 2 — Task

> Review the code changes in the current branch.

↓

Layer 3 — Scope

> Compare against master using git diff master...HEAD and review only changed Java files.

↓

Layer 4 — Criteria

> Check for bugs, security vulnerabilities, Spring Boot best practices, performance issues, and maintainability problems.

↓

Layer 5 — Constraints

> Avoid unrelated refactoring and don't suggest changes that alter existing behavior unless necessary to fix a problem.

↓

Layer 6 — Output

> For each finding, provide severity, file/line, issue, and recommendation.

Now we have a much stronger prompt.































