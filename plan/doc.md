
## What is the real value of AI?


Use AI to amplify your craft, not replace it

it’s expanding my capacity to do it well.



---

Time, scale, quality = better bets

---

make more confident, considered and better informed decisions - better bets and accelerated value

Faster decisions = more iterations -> quicker validation -> value

## Al in Product Discovery

1. Widen & accelerate top of funnel discovery
2. Scale reasoning across unstructured data
3. Jump to validation





"Context comes in fragments: user feedback, metrics, market changes, internal constraints, past decisions, intuition. As PMs, our job is to assemble those pieces into a clear picture—shaping the problem, forming the hypothesis, and defining the solution space."

When you can pull that together, you build products that solve real problems so well that customers change habits for them, pay for them, and genuinely feel the impact. But doing that synthesis in your head, and doing it over and over again, can literally feel impossible.

That’s where AI comes in. When you feed in all of that context that you’ve been trying to juggle yourself, your ChatGPT Project becomes a second brain that can store the information and synthesize it for you. That means that it can know and retrieve the right piece of data for the right problem—like an instantaneous librarian—and even use what it knows to run analyses and generate recommendations, like an associate PM.

Amir







Prompt-free, proactive applications

The prompt box is a temporary interface. In 2026, **the best AI products will stop waiting for instructions and start acting based on context**. Software will observe what you’re doing and step in at the right moment with suggestions or actions that feel obvious in hindsight.

Marc Andrusko


Sarah Wang — Systems of record lose ground

For decades, enterprise software has revolved around systems of record. CRMs, ERPs, and ITSM tools stored data while humans did the thinking and execution. AI collapses that separation.

In 2026, the strategic layer shifts upward. **The system that understands intent and executes workflows becomes the product users care about. The database underneath becomes a commodity.** 


Olivia Moore — Voice agents take over workflows

Voice agents already handle calls. Next, they manage entire workflows. Scheduling, intake, follow-ups, and resolution happen through conversation instead of dashboards.

**This works because voice removes friction.** When agents connect deeply to business systems, they stop being a feature and become an interface.

[2] [a16z Partners Just Laid Out the AI Playbook for 2026](https://www.the-ai-corner.com/p/a16z-ai-ideas-2026-partners)



>"I think the most valuable thing an AI assistant can do isn’t to write your PRD or draft your strategy docs. It’s to push back on weak reasoning, spot gaps you missed, and force you to articulate why your idea is actually good."
<br>&nbsp;<br>Rian van der Merwe [1]

---

disconnects
 - e.g. between strategy, discovery, planning, delivery 

time/focus
 - short cuts
 - visibility e.g. usability research

feedback and changes not reflected





## Preventing AI slop

AI models fill in the blanks. To get deterministic-like outputs, we must set the right expectations, scope, context and contraints.

it needs to understand the business context, your product and your product philosophy.



break down into more discrete steps

making things explicit


data


chatgpt with files, data, tools, shortcuts... 

can be versioned, shared, collab improved

quality, assesed

prompts -> context -> pipeline / 

"structure is thinking"

"cover more space"

"check thinking, what missed, uncover blindspots and assumptions"

"models"

evals - notebooks

context switching, data schlepping, prompt fatigue






## The Building Blocks

The system works because of how all the pieces fit together. Here’s an overview of the general folder structure I maintain with a series of Markdown files inside:

```
llm-prompts/
├── prompts/           # System prompts for different use cases
│   ├── pm/            # Product management prompts
│   └── technical/     # Technical/engineering prompts
├── context/           # Personal context files (who I am, how I work)
├── reference/         # Syntax guides and reference docs
└── work/              # Saved feedback and refined docs
```

The magic isn’t in any single prompt—it’s in how you combine them. Let me break down each layer.

### Layer 1: System Prompts

These are the instructions that tell the AI how to behave for a specific task. I have different prompts for different jobs:

* **General PM sparring:** A prompt that knows my product philosophy and pushes back on weak reasoning. I use this for thinking through tradeoffs, preparing for meetings, and sanity-checking my approach.
* **Document review:** Prompts specifically designed to critique PRDs, OKRs, strategy docs, and other artifacts. These encode what “good” looks like and call out common anti-patterns.
* **Idea stress-testing:** A prompt that I stole from my friend [Stephen](https://www.linkedin.com/in/stephenballot/), which simulates a debate between an optimist and a skeptic to pressure-test new ideas before I get too attached to them.
* **Technical understanding:** Prompts that help me understand systems, architectural decisions, and technical concepts well enough to lead effectively (I’m not an engineer, but I need to hold my own in architecture reviews).

The key is that each prompt is opinionated. They’re not generic “be helpful” instructions—they encode specific philosophies about what good work looks like.

### Layer 2: Personal Context

This is where it gets powerful. I maintain files that describe:

* **Who I am:** My role, my experience, my communication style
* **How I work:** My product philosophy, my management approach, my values
* **What I’m working on:** Current projects, team context, company priorities

When I start a conversation, I can pull in the relevant context files alongside my prompt. The model then has the background it needs to give me advice that actually fits my situation—not generic best practices from a blog post.

### Layer 3: Reference Materials

Sometimes you need the model to follow specific formats or conventions. I keep reference files for things like wiki markup syntax, documentation templates, or internal style guides. These ensure the output is actually usable without a bunch of reformatting.

## How I Actually Use This

I use [Windsurf](https://windsurf.com/) as my daily driver, and it has a feature that makes this whole system work: the `@` mention. In the chat panel, I can reference any file by typing `@` followed by the path. Windsurf then includes that file’s contents as context for the conversation.

This means I can compose my “assistant” on the fly by combining:

1. A system prompt for the task at hand
2. Relevant personal context files
3. The document or code I’m working on

### Example: Document Review

When I need feedback on a PRD before sharing it with stakeholders, I’ll start a conversation and reference my PRD review prompt plus my product philosophy context. Then I paste in the PRD and ask for critique.

The model comes back with feedback grounded in my own standards—not generic advice. It’ll call out if my problem statement is vague, if my success metrics aren’t measurable, or if I’m jumping to solutions before properly framing the problem. Exactly the kind of pushback I’d want from a senior colleague.

### Example: Brainstorming Partner

For early-stage thinking, I use a more conversational prompt that knows how I like to explore ideas. I’ll describe what I’m thinking about and ask it to poke holes, suggest angles I haven’t considered, or help me articulate why something feels off.

This is particularly useful before big meetings. I can rehearse my reasoning and get challenged on the weak spots before I’m in front of stakeholders.

### Example: Technical Understanding

I’m not an engineer, but I work with technical teams. When I need to understand how a system works—well enough to ask good questions or spot when something doesn’t add up—I use prompts designed for technical explanation.

The key is that these prompts know to explain things without condescension but also without assuming I know the jargon. They cite specific files and line numbers when relevant, and they explain the “why” behind design decisions.

## Connecting to Real Data

One feature that’s made a big difference is MCP (Model Context Protocol) servers. These connect the AI to external data sources—internal wikis, [documentation sites](https://developers.cloudflare.com/agents/model-context-protocol/mcp-servers-for-cloudflare/), code repositories, APIs—so it can ground its responses in actual information rather than just its training data.

In my prompts, I tell the model which MCP servers are available and when to use them. For example, my technical prompts instruct the model to:

* Search official documentation first to ground answers in verified information
* Check internal wikis for known issues, edge cases, and workarounds
* Look at code repositories when documentation is incomplete
* Always cite sources with links so I can verify

This turns the AI from a general-purpose assistant into something more like an expert who has access to your company’s actual knowledge base. The difference in answer quality is significant—instead of generic advice, I get responses that reference real docs and real code.





Bibliography

1. [AI for Product Management](https://elezea.com/2025/12/ai-for-product-management)