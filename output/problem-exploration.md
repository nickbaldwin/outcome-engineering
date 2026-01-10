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
