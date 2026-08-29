# Learning-AI-Agent
This repo is created to learn and explore the AI Agent and it's related concept.


| Day | Topic                 | Outcome                                        |
| --- | --------------------- | ---------------------------------------------- |
| 1   | AI Agents Foundations | Understand LLM, Prompt, MCP, Agent Loop        |
| 2   | Prompt Engineering    | Write reusable prompts like a senior engineer  |
| 3   | MCP Deep Dive         | Understand GitLab, VS Code, Jira integration   |
| 4   | Copilot Agent Mode    | Review MRs and automate developer tasks        |
| 5   | Java AI Agent         | Build your first Spring Boot AI Agent          |
| 6   | Multi-Agent Systems   | Build Reviewer + Tester + Documentation agents |
| 7   | Enterprise Project    | Complete workflow + Final assessment           |

---

### Q) What is AI Agent? And is there any Mathematical expression to define it ?
The below can considered as mathematical expression to define, but Don't memorize this as a strict formula:
> LLM + Prompt + MCP + Memory + Planning = AI Agent

That's still an oversimplification.

There isn't one universally accepted mathematical formula for an agent.

A better mental model is:

> An agent is an LLM-based system that can decide what actions to take, use tools, observe results, and continue until the task is completed.

Memory, planning, tools, prompts, etc. are components/capabilities of agent systems, but not every agent necessarily has all of them in the same form.

For example, a simple agent might not have persistent long-term memory.

The above the formula is good for understand the AI Agent but don't consider the formula into Law. 

---

### Q) Difference between AI Assistant vs AI Agent ?
AI Assistant will reply to user just like a chatbot whereas AI Agent will do multiple actions an entire flow to accomplish the task.

---

### Q) What is Agent Loop? 
![Image description](https://images.openai.com/static-rsc-4/0PeLdJL3J2hkNb2Nr5G6R8Vx7hMGPrvnM6bTGdtGZ1GQUlVztjhz5tz70zdP1stLoerFKu8At612bbRtsLWesWVc6RNopwTQsZivsd50xl0HFDY37HdDMiwZQ8zrCPQ9wGD6CFXhIr8J4o8X4GH_m8Jag_HG-jBgv1nA41vPoe7jy1P_3zNDfLBmp0-AxlAL?purpose=fullsize)

This is probably the most important concept of the entire course.

Every agent repeatedly does this.
The loop is:
1. Think.
2. Choose a tool.
3. Execute.
4. Observe the result.
5. Repeat until the task is complete.

## Example: "Review My MR"

The internal workflow looks like this:

| Step     | Internal Action      |
| -------- | -------------------- |
| **User** | Review MR 145        |
| **LLM**  | I need GitLab        |
| **MCP**  | Get MR               |
| **LLM**  | I need changed files |
| **MCP**  | Fetch diff           |
| **LLM**  | Review code          |
| **MCP**  | Post comments        |
| **LLM**  | Done                 |

### 💡 Key Observation

Notice something interesting:

> **The LLM never "clicked GitLab."**

Instead, the LLM decided **what action was needed**, and the MCP/tool handled the interaction with GitLab.

In simplified form:

```text
User
  ↓
LLM → "I need GitLab"
  ↓
MCP → Get MR
  ↓
LLM → "I need changed files"
  ↓
MCP → Fetch diff
  ↓
LLM → Review code
  ↓
MCP → Post comments
  ↓
LLM → Done
```

---

### Q) What is MCP ? 
Model Context Protocol (MCP) is a standard protocol that allows an AI model to communicate with external tools, applications, and data sources.

---

### Understanding MCP with JDBC Analogy
JDBC = standard API/protocol for database access

JDBC Driver = implementation that knows how to communicate with a specific database

Similarly:
MCP = protocol

MCP Server = implementation exposing tools/resources through that protocol
That's an important distinction.

So your analogy becomes:

> JDBC : Java ↔ Database
> 
> MCP : AI application ↔ External tools/data

---

### Q) What exactly MCP Server does ?
MCP is a protocol that standardizes how an AI application discovers and interacts with external tools and data sources. An MCP server exposes capabilities such as reading files, querying Jira, or operating on GitLab, while the LLM decides when and how those capabilities should be used. 

The LLM generates the comment.

The GitLab tool performs the posting.

MCP provides the standardized mechanism through which the AI client can interact with that tool.

That's a crucial distinction.

---


