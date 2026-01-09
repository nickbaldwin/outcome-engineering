

# Problem Statement: Providing Information for Insurance Quotes

## WHO

**Primary audience:** Insurance brokers/advisors who act on behalf of end customers (individuals seeking personal insurance across all types). These brokers submit quote requests and provide the required information and supporting documents through unstructured channels like email.

**Secondary audiences:**
- **Underwriters** (mixed experience levels) who review applications and make underwriting decisions. They currently spend significant time manually extracting and structuring information rather than focusing on actual underwriting work.
- **Customer support staff** who verify that all required information is present before applications move to underwriting.

The company interacts directly with brokers, not end customers, until a policy is accepted. End customers are the ultimate beneficiaries who experience the delays but don't directly interact with the system.

## WHAT

**Current state:** Brokers email unstructured information (free-text emails, PDFs, scanned documents, images) for insurance quotes. Underwriters pull requests from a queue and manually check them against internal templates and checklists, spending days extracting and structuring data. Conditional requirements (e.g., mental health history triggering additional questions, or building features requiring sprinkler information) are identified through manual review of guidelines, often relying on individual judgment. When information is missing, underwriters reply to brokers via email, creating back-and-forth cycles that extend the process to weeks instead of hours or days.

**Desired state:** Brokers continue submitting unstructured data (lowest common denominator constraint), but the system automatically extracts and structures information, validates completeness, and identifies conditional requirements. This enables upfront identification of missing information, reducing back-and-forth and enabling faster processing (hours/days instead of weeks).

**The gap:** The difference between manual extraction and structuring versus automated extraction; manual identification of missing and conditional requirements versus automated validation; reactive back-and-forth cycles versus proactive identification of needs.

**Unmet needs:** Brokers need visibility into required information before or at submission; underwriters need structured, complete data to focus on decision-making rather than data preparation; support staff need quick completeness checks; the system must handle conditional requirements automatically.

**Existing solutions:** Internal templates and checklists exist but cannot be enforced on brokers (who work with multiple insurers and use their own processes). The current manual review process is time-consuming, error-prone, and creates capacity constraints.

## WHERE

**Primary channel:** Email is the main submission channel, but the problem occurs across any channel brokers use (email, portals, other systems) because submissions are consistently unstructured regardless of channel.

**Workflow stage:** The problem manifests at the initial intake stage, when information first enters the system and needs to be extracted, structured, and validated before underwriting can proceed.

**Context:** The issue is consistent across insurance types since the workflow is essentially the same—unstructured data arrives and must be processed before underwriting can proceed.

## WHEN

**Frequency:** The problem occurs with every quote request submitted by brokers—a continuous, recurring issue that affects every application.

**Duration:** Each quote takes an average of 2 weeks from initial submission to decision. If required information were provided in the right structure, this could be reduced to hours instead.

**Timing:** The problem manifests immediately upon initial intake, when unstructured information enters the system and requires manual processing, creating delays that compound throughout the workflow.

## WHY

**Impact on audience:** For brokers, the lengthy process creates poor customer experience and likely lost sales as customers abandon applications or choose faster competitors. For end customers, weeks-long wait times create uncertainty and frustration, leading to poor experience and lost sales. For internal staff (underwriters and support), this creates drudge work—time-consuming manual processing that prevents them from focusing on actual underwriting decisions, reducing capacity to work through requests and creating opportunity loss.

**Impact of solving:** Solving this problem would dramatically improve customer experience through faster quote turnaround, reduce manual drudge work for internal teams, increase capacity to process more quotes, and reduce lost sales from abandonment. Underwriters could focus on decision-making rather than data preparation, and support staff could quickly verify completeness.

**Business impact:** This problem directly impacts revenue opportunity (more quotes processed, faster conversions, reduced lost sales), cost savings (reduced manual processing time and operational overhead), competitive advantage (faster than competitors), and customer satisfaction/retention. The potential profitability gains are significant—reducing a 2-week process to 2 hours would unlock substantial operational efficiency and revenue potential.

**Urgency:** This is critical to address. The current process creates capacity constraints, lost revenue opportunities, poor customer experience, and operational inefficiency that compounds with every quote request.

## Summary

Insurance brokers submit unstructured quote information via email and other channels, requiring underwriters and support staff to spend days manually extracting, structuring, and identifying missing information—work that could be automated. This extends quote turnaround from hours to weeks, creating poor customer experience, lost sales, and operational inefficiency. Solving this through automated extraction and validation would unlock significant revenue opportunity, cost savings, and competitive advantage while improving experience for all stakeholders.