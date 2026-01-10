

Analyzes request within broader context (mission, product vision, strategy, ICP etc)


- understand the user

1. discover problems to consider
   - from discovery
2. identify problem 
3. understand the problem 
4. validate problem ?
   - research
4. identify opportunities
   - match against business objectives
consider others?
   - ost
5. explore problem 
   - confirm its the right problem
   - what do we need to know and learn?
create validation work
7. confirm the problem 
   - validate with users

8. generate ideas
9. idemtify possible solutions
9. research opinions on idea
   - competing agents
10. validation plan
11. design test
12. solution brief
13. generate design
14. create prototype
15. validate with users
- analyse learnings
...


to do
- share, get feedback, update
- publish, feedback and check - can be done as needed
- check for inputs





### Opportunity Framing

```
You are a product management expert. Ask the user for a Problem Exploration  document and any other input they wish to include - suggesting the areas described in the input heading, then write "opportunity-framing-{name}.md" 

Clearly define and frame the opportunity
Start by getting absolute clarity about the problem we want to solve, the potential impact, outcomes for the customer and the business objectives/outcomes it should drive. 

Create a simple, powerful problem statement to clearly define the user's pain or challenge. A practical format could be: "Remote workers struggle with productivity because of frequent distractions at home that negatively impact their job performance."

Identify precisely who experiences the problem, being as specific and narrow as possible to understand their behaviors, motivations, and pain points deeply.

Clarify why this problem is strategically important to the 
product strategy and the outcomes it drives e.g. customer retention, market expansion, revenue growth, brand differentiation.

Do not yet include full solutions.

Use this structure:

0. TL;DR Summary – Clear opportunity summary and why it matters now
1. Problem Statement – Validated and scoped user pain point
2. Desired UUser Outcomes – Who is affected most and why? How will solving this problem help them?
3. JTBD – Specific jobs this user group wants to solve
4. Business Impact – Why solving this is valuable to the company
5. Scope – What’s in/out of our initial MVP scope
6. Success Hypothesis – If we solve this, what will improve?
7. Open Questions – What must we still research or confirm?
8. Risks – Misframing, invalid assumptions, etc.

Input data:
[Insert insights, pain points, validation interviews]
```


### Discovery Plan

```
You are a product management expert. Ask the user for an Opportunity Framing  document, then write "discovery-plan-{name}.md" 

Create a clear plan of evidence, data and activities needed from the opportunity framing document.

Do not yet include full solutions.

Use this structure:

1. Discovery Goals (What We Must Learn)
2. Key Hypotheses to Validate (Condensed from the hypothesis tree)
3. Discovery Workstreams
4. Data & Evidence Inventory (What we aim to collect by the end of discovery)
5. Risks & Mitigations
7. Discovery Outputs (Definition of Done)
8. Decision Gate
```


### PRD Opportunity Solution Exploration

```
You are a product management expert. Ask the user for a Problem Exploration  document and any other input they wish to include - suggesting the areas described in the input heading, then write "opportunity-solution-exploration-{name}.md" 

Review the opportunity solution document provided by the user to understand the problem we want to solve, the potential impact, outcomes for the customer and the business objectives/outcomes it should drive. 

Brainstorm potnetial solutions that could help solve the problem - but clarify any contraints first with the user.

Structure:

0. TL;DR Summary – Problem + high-level idea + outcome goal
1. Problem Statement – Refined problem definition
2. User Stories – Sample real-life usage contexts
3. JTBD – Actionable job statements
4. Business Impact – What shifts if we get this right?
5. Scope – What’s tentatively in/out
6. Assumptions – What must be true for this to work?
7. Success Criteria – What indicators should improve? (directional)
8. Solution ideas
9. Validation Plan – What do we test first, with whom, and how?
10. Risks – UX failures, false positives, competitor moves

User input:
[solution ideas, hypotheses, research]
```

### PRD 0.7 Prompt — MVP Execution Spec (Ideate)

```
You are a senior product owner preparing an MVP for build and learning. Write PRD version 0.7 optimized for design and engineering alignment. Include all tactical components and test plan.

Structure:

0. TL;DR Summary – What we're building and why
1. Problem Statement – Root cause and user motivation
2. User Stories – Prioritized flows
3. JTBD – What users are really trying to solve
4. Goal & Business Impact – KPIs, growth lever, revenue, retention
5. Scope – Define MVP line clearly
6. Success Metrics – Add ranges (e.g., Retention Day 7 > 30%)
7. Assumptions – What still needs testing
8. Risks & Edge Cases – Technical, UX, data integrity issues
9. Technical Tasks – Split by frontend/backend, labeled P1–P3
10. Prototype Prompt – Detailed, for design/code handoff
11. Post-Launch Plan – What success looks like in 2 weeks

Feed:
[Paste MVP concept, UX plan, user feedback, business goals]
```

### PRD 1.0 Prompt — Ready-to-Build (Test)

```
You are a senior product delivery manager preparing for final build. Write PRD version 1.0. This is the fully validated, engineering-ready spec. It should contain no major unknowns.

Use this format:

0. TL;DR Summary – Concise one-liner + KPI targets
1. Problem Statement – Final statement linked to outcomes
2. User Stories – Realistic and confirmed
3. JTBD – Fully synthesized
4. Goal & Business Impact – Growth, retention, strategic alignment
5. Scope – MVP + fast-follower backlog
6. Success Metrics – Firm KPIs + targets (e.g. CTR ≥ 12%)
7. Assumptions – Note remaining soft spots
8. Key Risks and Edge Cases – Full spectrum
9. Technical Tasks – FE/BE split, P1 (critical), P2 (stretch), P3 (future)
10. Post-Launch Validation Questions – What are we watching?
11. Prototype Prompt – Ready for design/dev
12. Release Plan – Timeline, launch strategy, ownership

Input:
[Paste polished spec, validation results, user flows, tech context]
```

##











Please share input across these areas
1. Context & Name

Problem name / working title (used for {name} in the filename)

Domain / product / system this relates to (e.g. underwriting, marketplace, internal tooling)

Who is this for? (end users, operators, execs, customers, partners)

2. User Feedback (Raw & Unfiltered)

Paste anything you have:

Direct quotes from users or stakeholders

Support tickets, Slack messages, emails

Complaints, workarounds, “this is painful” moments

Things people say vs what they do

Examples:

“We always end up re-checking this manually”

“No one trusts the output, so we redo it in Excel”

“This takes days and no one knows why”

3. Observed Behaviours (Not Opinions)

What you’ve seen happening:

Repeated manual steps

Shadow systems (spreadsheets, side tools)

Bottlenecks, handoffs, rework

Delays, escalations, approvals

4. Data Signals (If Any)

Even if weak or directional:

Time, cost, error rates

Volume trends

Drop-offs, retries, overrides

“We don’t measure this, but…”

5. Who Feels the Pain Most?

Primary user(s)

Secondary / downstream users

Who absorbs the cost vs who experiences the friction?

6. Constraints & Realities

Regulatory, legal, policy constraints

Org / process constraints

Tech or data limitations (known or suspected)

7. Why This Matters Now

What triggered this exploration?

What breaks if we ignore it?

Why hasn’t this been solved already?

How I’ll Use This

Once you respond, I will:

Write problem-discovery-{name}.md in a clean, product-strategy style

Stay strictly in problem framing (no solutions)

Explicitly list:

Assumptions

Unknowns

Systemic gaps vs surface symptoms

Call out contradictions and tensions

Make the problem legible to execs and practitioners

If you want, you can also say:

“Assume this is pre-discovery”

“Assume we’re pitching this to leadership”

“Assume this feeds into an AI / platform strategy”



1.
name: providing-information
domain: insurance quotes
for: end customers, and internally for underwriters and customer support staff processing applications

2. universally, feedback is applications takes too long (weeks instead of hours/days). information provided is unstructured and takes internal users days to extract, structure and identify missing information that is required

3.
many manual steps, bottlenecks and delays

4.
unknown - cannot track currently

5. 
customers - time for response, time to provide info
internal - lots of manual work that should be automated

7.
huge profitability gains if we reduce 2 week process to 2 hours








# problem-discovery-providing-information.md

## 0. TL;DR Summary
Insurance quote applications routinely take weeks instead of hours because information provided by customers is unstructured, inconsistent, and difficult for internal teams to interpret and validate. The resulting manual effort, rework, and delays create poor customer experience and high operational cost. Before attempting to “fix” this, we need to clearly understand where information breaks down, why humans must compensate, and which assumptions are masking the true root causes.

---

## 1. Problem Statement
During the insurance quoting process, customers are required to provide information necessary for underwriting and pricing. While customers submit this information, it is often unstructured, incomplete, or ambiguous. Internal teams—underwriters and customer support staff—must then manually extract key details, interpret intent, restructure data, and identify what is missing before a quote can progress.

This manual interpretation work introduces significant delays. Applications stall not because underwriting decisions are complex, but because information readiness is unclear. There is no reliable system-level signal that an application is “complete” or “ready,” so progress depends on human judgment and follow-up.

As a result, quoting timelines stretch from hours or days into weeks. Bottlenecks accumulate across multiple handoffs, and both customers and internal teams experience frustration. The issue appears systemic: the way information is requested, provided, and prepared for underwriting is misaligned with the speed, scale, and predictability the business expects.

---

## 2. User Observations

### End Customers
Observed feedback patterns:
- “The application takes too long.”
- Quotes take weeks instead of hours or days.
- Customers are asked for additional information long after initial submission.

Observed behaviours:
- Customers provide information once and assume the process is complete.
- Customers respond to follow-up requests reactively, increasing overall cycle time.
- Time spent providing information feels disproportionate to progress made.

Primary pain:
- Long response times and repeated information requests create uncertainty and frustration.

---

### Internal Users (Underwriters & Customer Support)
Observed behaviours:
- Significant time spent reading, interpreting, and restructuring customer-provided information.
- Manual identification of missing or unclear data.
- Repeated back-and-forth with customers to clarify details.
- Bottlenecks forming around review and interpretation stages.

Primary pain:
- High volumes of manual work that feel automatable.
- Delays caused by information quality rather than underwriting complexity.

---

## 3. Jobs to Be Done

### Customers Are Trying To:
- Get an insurance quote quickly.
- Provide required information with minimal effort.
- Avoid repeated follow-ups or rework.
- Feel confident their application is “done.”

### Internal Users Are Trying To:
- Understand the customer’s situation accurately.
- Determine whether an application is complete enough to proceed.
- Identify gaps or inconsistencies efficiently.
- Keep applications moving without unnecessary delays.

### The Organisation Is Trying To:
- Reduce quote turnaround time.
- Lower operational cost tied to manual processing.
- Improve customer satisfaction and conversion.
- Unlock profitability by reducing end-to-end cycle time (e.g. from ~2 weeks to ~2 hours).

---

## 4. Open Questions
- What information is most frequently missing, unclear, or unusable?
- At which step(s) does the largest delay occur?
- How many times does a typical application require follow-up?
- What defines a “complete” application today?
- Is that definition consistent across underwriters, support staff, and products?
- Which steps truly require human judgment versus interpretation?
- How much variability exists by product type or customer segment?
- How do teams currently decide when an application is ready to move forward?

---

## 5. Assumptions (and Data Needed to Test Them)

| Assumption | Evidence / Data Needed |
|-----------|------------------------|
| Long cycle times are primarily driven by information handling | Time breakdown by process step |
| Customers are willing to provide correct info if expectations are clear | Customer interviews; submission behaviour analysis |
| Manual work exists because systems can’t assess completeness | Review of current tooling and decision rules |
| Internal teams are doing necessary (not redundant) work | Shadowing underwriters and support staff |
| Reducing cycle time will materially improve profitability | Cost-per-application and throughput analysis |
| Current systems were not designed for unstructured input | System capability and data model review |

---

## 6. Scope

### In Scope
- Information collection during quoting.
- Quality, structure, and clarity of customer-provided information.
- Internal interpretation, validation, and gap identification.
- Delays and rework within the quoting phase.

### Out of Scope
- Pricing and underwriting risk models.
- Policy binding and post-quote processes.
- Marketing or sales conversion optimisation.
- Changes to regulatory requirements themselves (though their impact is relevant).

---

## 7. Next Steps
To move from assumptions to evidence:
1. Map the end-to-end quoting process with a focus on information flow.
2. Shadow underwriters and support staff handling live applications.
3. Review a sample of recent applications to identify common patterns and gaps.
4. Manually track cycle time by step to establish a baseline.
5. Interview customers shortly after submission to understand intent vs outcome.
6. Define and document what “complete information” means across roles and products.
7. Quantify where delays accumulate and why.

The goal of these steps is to make the problem explicit, measurable, and shared—before any solutioning begins.
