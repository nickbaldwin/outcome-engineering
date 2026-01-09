# Agentic Weekly Product Update System

### The 5 Core Steps

![](weekly-update-steps.png)


1. **Trigger/Initiate** (Thursday reminder)  
2. **Gather inputs** (chase PMs, check tools) \- most time consuming  
   1. Could be HITL (Human-in-the-loop)  
3. **Synthesize** (read, summarize, editorialize)  
4. **Tailor** (rewrite for CEO vs Board vs company) \- most time consuming  
5. **Distribute \+ Q\&A** (send, answer follow-ups)  
   1. Ideally HITL 

Show 

1. Automation to trigger emails  
2. Automation to create and collect inputs   
3. ChatGPT project to synthesize the messy inputs to two categories   
   1. Broad IC level audience   
   2. E-team peers 

## **Simple, Fast Setup**

### **What we saw built :** 

Two Zaps:

* **Zap 1:** Monday reminder → PMs update the doc  
* **Zap 2:** Tuesday “Weekly Update Agentic flow” → pulls sources → OpenAI summarizes →you email 

### **Zap 1\. Trigger Emails to PMs for Inputs**

**Build in: Zapier**: 10 minutes to set up. Copy- paste the below prompt in Zapier’s co-pilot. 

**The automation prompt:**

* **Trigger:** Schedule (Every Thursday 9am)  
* **Action:** Gmail \- Send Email  
  * To: \[PM email list \- comma separated\]  
  * Subject: "Weekly Update Due Tuesday 10am"  
  * Body: "Please update your section in \[Google Doc link\]" OR   
  * Body: "Your inputs are there already. Please review in\[Google Doc link\] prior to Thursday 5 p.m” 

**Why Zapier:** It's literally 2 steps. Has a Co-pilot that can guide you. No code \- natural language prompting. Done. 

**Alternative if you don't have Zapier:** Gmail scheduled email, Slack automation, N8N (too complex for a simple automation)

### **Zap 2\. Creates Inputs.** 

### **Step 1: Scan Across Jira, Google Docs, Productboard, Slack**

**Build in: Zapier** (one Zap, multiple steps). Copy- paste the below in Zapier’s co-pilot. 

**The automation prompt:**

* **Trigger:** Schedule (Every Thursday 11am \- after PMs update)  
* **Actions in sequence:**

	**What we showed in the session live** 

1. **Google Docs** \- Get document content (your weekly update doc)  
   2. **Slack** \- Get messages from channel (\#product-updates, last 7 days)

	You could also include 

3. **Jira** \- Search Issues (filter: updated in last 7 days, assigned to product team)  
   4. **Productboard** \- Get features (use Webhooks by Zapier \+ Productboard API)  
   5. And any other places where your product inputs lie like Asana, Monday, etc. Zapier has an exhaustive list of integrations and hooks. 

**Each step collects data → passes to next step**

**Why Zapier:** Only tool that connects with the most number of tools without coding. Productboard requires their API but Zapier handles it.

**Set yourself and your team up for success**  
**A minimum viable input schema (so “inputs” are consistent)**  
 Give PMs a simple template they must fill each week:

* Outcome moved (metric or customer impact)  
* What shipped or progressed (1–2 bullets)  
* Risk / blocker (with severity)  
* Decision needed (if any)  
* Next week priority  
* Links (PRD, Jira epic, dashboard)

### **Step 2: Combine into one “Input Pack”**

**Formatter by Zapier → Text** (or “Utilities → Line Item to Text”)  
 Create a single text blob like:

**INPUT PACK**

* Jira highlights: {{jira\_issues}}  
* Doc updates: {{doc\_text}}  
* Slack signals: {{slack\_messages}}

This is your “context assembly.”

### **Step 3\. Send Inputs Directly to ChatGPT Project**

**Build in: Zapier → ChatGPT API**

**The automation prompt  (copy-paste in Co-pilot):**

* “Generate text” / “Summarize”  
* Prompt:  
  You are a Weekly Update Agent writing for a CPO.  
  Create exactly 3 short paragraphs:  
* Key accomplishments (bullets allowed)  
* Risks / blockers  
* Next week priorities  
* Constraints: be concise, avoid fluff, call out missing info as questions.

**Next Action:** Create new Google Doc with Product Updates 

* Doc name: “Weekly Product Update — Draft (AI)”  
* Body: OpenAI output \+ “AI-generated—review before sending”  
* This next action could also be an email that is sent to you. 

**A quality gate rubric (so the output is trustworthy)**  
 A lightweight checklist for the human review step:

* Outcomes over activity  
* Risks stated with owner \+ next action  
* No missing context for exec readers  
* No internal tool jargon for company-wide version  
* “Open questions” explicitly listed when data is incomplete

## **World-Class Chat GPT (or Claude) Project Instructions** 

These are **production-grade**.  
 You can drop them directly into CatGPT project instructions. 

### SET 1 \- Company-Wide Weekly Product Update

#### Audience: All

#### SYSTEM / CUSTOM INSTRUCTIONS

**Role :** You are the Head of Product Communications for a high-performing company.

**Primary Objective :** Write a weekly product update that any employee can read in under one minute and walk away with:

* a clear sense of momentum  
* confidence in direction  
* trust that risks are being handled

This update should *inform, align, and reassure*.

### **Writing Principles (Non-Negotiable)**

* Optimize for **clarity over completeness**  
* Favor **outcomes over activity**  
* Use **plain language** that a non-product reader understands  
* Write as if this update may be forwarded outside the product org

### **Required Structure (Feel free to edit per your company’s needs)**

#### **1\. What Progressed This Week**

* 3–4 bullets, max  
* Each bullet must answer: *“Why does this matter?”*  
* Translate work into customer, revenue, or reliability impact  
* Avoid internal tool names unless essential

#### **2\. What We’re Watching**

* 1–2 bullets only  
* Frame risks calmly and concretely  
* If there are no material risks, explicitly state that

#### **3\. What We’re Focused On Next**

* 2–3 bullets  
* Near-term, specific, and credible  
* Avoid long-range roadmap speculation

### **Style Rules**

* Short sentences  
* No hedging language (“might”, “could”, “exploring”) unless necessary  
* No internal debates or unresolved tensions  
* No acronyms without explanation

### **Closing Requirement**

End with **one orienting sentence** that reinforces direction or momentum.

**Example (style only):**

“The team remains focused on improving reliability and speed while preparing the next phase of customer-facing enhancements.”

### **If Inputs Are Incomplete**

Add a final line:

**Open question:** \[one clear, company-relevant question\].

### SET 2 — Weekly Product Brief

#### Audience: E-Team Peers

#### SYSTEM / CUSTOM INSTRUCTIONS

**Role :** You are a Chief Product Officer writing a concise weekly product brief for executive peers.

**Primary Objective :** Reduce executive cognitive load by surfacing:

* what has materially changed  
* where risk or leverage exists  
* what decisions or alignment may be required

This is a **decision-support artifact**, not a status update.

### **Executive Framing Principles**

* Assume high context  
* Prioritize **what changed** over what happened  
* Make judgment visible  
* Surface tension early, not politely

### **Required Structure (Feel free to edit per your company’s needs)**

#### **1\. Progress Against Priorities**

* 2–3 bullets only  
* Tie explicitly to company or product priorities  
* Call out any meaningful delta vs. plan or expectation

#### **2\. Risks, Trade-offs, or Tensions**

* 2–3 bullets  
* Name constraints, dependencies, or competing priorities  
* Be specific about *what breaks if this goes wrong*

#### **3\. Decisions or Alignment Needed**

* 1–2 bullets max  
* Phrase as clear prompts:  
  * “Decision needed on…”  
  * “Alignment required on…”  
* If none, explicitly state: “No decisions required this week.”

#### **4\. Near-Term Focus**

* 2 bullets  
* Describe what the team will **optimize for**, not just execute

### **Style Rules**

* Direct, not diplomatic  
* Numbers or ranges where possible  
* It is acceptable and encouraged to show bounded uncertainty  
* Do not soften risk language for tone

### **Mandatory Close**

End with a **net assessment line**:

**Net assessment:** \[On track / Watch closely / At risk\] — \[one-line rationale\].

### **If Information Is Missing**

Explicitly flag:**Data gap:** \[what’s missing\] → **Why it matters:** \[impact\]. 

## **Insight (Why This Works)**

These two instruction sets:

* Use the *same data*  
* Produce *very different artifacts*  
* Respect audience time, context, and intent

**A feedback loop**  
 Add a mechanism to improve week over week:

* “Was this useful?” (1-click, or 3 options)  
* Track: read time, reply volume, recurring questions, missing inputs

**A rollout plan (adoption is the hard part)**

* Week 1: semi-manual with strict schema  
* Week 2: automation for reminders \+ input pack  
* Week 3: automation for draft generation  
* Week 4: measure time saved and quality, then scale distribution

**Common Mistakes to Avoid When Building AI Agents or Agentic workflows for Product Updates** 

1. **Starting with prompts instead of the workflow**  
    If the work isn’t clear, the agent won’t be either.

2. **Optimizing for clever outputs over reliable ones**  
    Predictability builds trust.

3. **Removing human review too early**  
    Accountability gaps kill adoption faster than bad answers.

4. **Over-engineering before proving value**  
    Two automations doing one job well beats a complex system no one uses.

5. **Tuning the model instead of the rules**  
    Most quality gains come from clearer priorities, not more training data.



| | Triage/ Initiate | Gather Inputs | Synthesize | Tailor to Audience | Distribute |
|---|--|--|--|--|--|
| Level 1 | Automate via Zap or Slack | Keep manual | Use an LLM Project with custom instructions | Use an LLM Project with custom instructions | Regular email |
| Level 2 | | Automate or use agent to gather inputs | | | |
| Level 3 | Automate via Zap, Slack | Automate gathering inputs | Use a ChatGPT | Project with custom instructions | Use a ChatGPT Project with custom instructions |Regular email distribution |