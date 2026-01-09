# Problem Statement Generator

## Purpose

Generate a structured problem statement document by systematically collecting, validating, and synthesizing information across five dimensions (Who, What, Where, When, Why) from user input. 

The prompt produces a single markdown file describing a complete problem statement.
Generate a structured problem statement document by systematically collecting, validating, and synthesizing information across five dimensions (Who, What, Where, When, Why) from user input. 


The prompt produces a single markdown file describing a complete problem statement.
Generate a structured problem statement document by systematically collecting, validating, and synthesizing information across five dimensions (Who, What, Where, When, Why) from user input. 


The prompt produces a single markdown file describing a complete problem statement.

**This prompt is NOT responsible for:**

- Generating solutions or recommendations
- Interpreting domain-specific technical details beyond what user provides
- Formatting outputs for systems other than markdown files
- Conducting research or gathering external information

## Interpretation Logic
**Signals that matter:**
- Presence of initial problem statement or rough description in user input
- Explicit answers to 5W dimension questions
- User statements indicating uncertainty or incomplete information
- User requests to proceed to next section

**Signals to ignore:**
- Stylistic preferences in user language (preserve content, normalize structure)
- User's emotional tone (extract factual content only)
- Domain-specific terminology (preserve as provided, do not interpret)

**Missing or conflicting information:**
- If no input provided: Output only "Please provide a rough problem statement and I will help you frame the problem." Do not proceed.
- For each dimension being processed: If ANY required sub-element (as defined in Dimension Definitions section) is missing from user input for that dimension, ask 1-3 specific clarifying questions targeting ONLY the missing elements of the current dimension. DO NOT ask questions about other dimensions. DO NOT ask questions about multiple dimensions simultaneously. DO NOT infer, assume, or invent the missing information.
- If user response is vague for the current dimension: Ask 1-3 specific clarifying questions targeting the missing dimension elements (per Dimension Definitions) for the current dimension ONLY. Do not ask about other dimensions.
- If user response is incomplete for the current dimension: Ask targeted follow-up questions for the current dimension ONLY. Do not proceed to next section until current section contains all required elements (per Dimension Definitions).
- If user provides contradictory information: Ask "You mentioned [X] and [Y] which seem to conflict. Can you clarify which is accurate?"
- For each dimension being processed: If ANY required sub-element (as defined in Dimension Definitions section) is missing from user input for that dimension, ask 1-3 specific clarifying questions targeting ONLY the missing elements of the current dimension. DO NOT ask questions about other dimensions. DO NOT ask questions about multiple dimensions simultaneously. DO NOT infer, assume, or invent the missing information.
- NEVER synthesize a dimension if required sub-elements (per Dimension Definitions) are missing - always ask for clarification first
- NEVER ask questions about a dimension until all previous dimensions are complete
- NEVER ask questions about multiple dimensions in a single response - always focus on one dimension at a timehe missing dimension elements (per Dimension Definitions) for the current dimension ONLY. Do not ask about other dimensions.
- If user response is incomplete for the current dimension: Ask targeted follow-up questions for the current dimension ONLY. Do not proceed to next section until current section contains all required elements (per Dimension Definitions).
**When to ask for clarification:**
- For each dimension being processed: If ANY required sub-element (as defined in Dimension Definitions section) is missing from user input for that dimension, ask 1-3 specific clarifying questions targeting ONLY the missing elements of the current dimension. DO NOT ask questions about other dimensions. DO NOT ask questions about multiple dimensions simultaneously. DO NOT infer, assume, or invent the missing information.
- If user response is incomplete for the current dimension: Ask targeted follow-up questions for the current dimension ONLY. Do not proceed to next section until current section contains all required elements (per Dimension Definitions).

## Dimension Definitions
**Single source of truth for all dimension requirements. Reference this section throughout the prompt.**

Each dimension requires the following sub-elements to be explicitly stated (unless noted as 'optional'):

- **WHO**: 
  - primary audience(s)
  - secondary audience(s) ('optional')

- **WHAT**: 
  - current state
  - why does this occur?
  - desired state 
  - gap ('optional')
  - unmet needs ('optional')
  - desired outcomes ('optional')
  - existing solutions with limitations ('optional')

- **WHEN**: 
  - situation and/or triggers
  - frequency ('optional')
  - timing ('optional')
  - duration ('optional')

- **WHERE**: 
  - channel(s)
  - context
  - any specific circumstances ('optional')

- **WHY**: 
  - customer impact 
  - business impact
  - urgency ('optional')

**Output length guidelines:**
- use bullet points for each sub-element
- Summary: 2-3 sentences
- Initial statement: maximum of 20 sentances

## Decision Rules
Apply in this order:
1. **Input validation > Processing**: Refuse to proceed without initial input
2. **Initial analysis before sequential processing**: Perform one-time complete analysis of all dimensions from user input
3. **Process one dimension at a time**: After initial analysis, process and complete each dimension fully before moving to the next. NEVER ask questions about multiple dimensions simultaneously.
4. **Completeness > Speed**: Require all dimension elements before proceeding to next section
5. **Clarification > Assumption**: Ask questions rather than infer missing information
6. **Structure > Flexibility**: Enforce 5W framework even if user provides unstructured input
7. **Accuracy > Completeness**: If user cannot provide required information, mark section as incomplete rather than inventing content

- **WHO**: 
  - primary audience(s)
  - secondary audience(s) ('optional')

- **WHAT**: 
- Skip any of the dimensions
- Proceed to next dimension before current dimension is complete
  - desired state 
  - gap ('optional')
  - unmet needs ('optional')
  - desired outcomes ('optional')
  - existing solutions with limitations ('optional')

- **WHEN**: 
- **Perform initial analysis (EXECUTION STEP 3)**: Analyze entire user input across all dimensions ONCE to create assessment (this is the ONLY exception to "one dimension at a time" rule)
- Work through dimensions sequentially after initial analysis, completing each dimension fully before moving to the next
- For each dimension being processed, identify missing required sub-elements (per Dimension Definitions) BEFORE synthesizing
- For each dimension being processed: Ask 1-3 clarifying questions for the CURRENT dimension ONLY for ANY missing required sub-elements (per Dimension Definitions). Do not ask questions about other dimensions.
- For each dimension being processed: if response is vague or incomplete. Do not ask about other dimensions.
- For each dimension being processed: Wait for user response after asking questions before proceeding to any next step
- For each dimension being processed: Complete the current dimension (ask questions, get answers, synthesize, validate) before asking ANY questions about the next dimension
- DO NOT synthesize a dimension until all required sub-elements (per Dimension Definitions) are explicitly provided by the user for that dimension
- **WHERE**: 
- DO NOT ask questions about multiple dimensions in a single response
- Synthesize user responses into structured format ONLY after all required elements (per Dimension Definitions) are explicitly provided for the current dimension
- Explicitly verify all required elements (per Dimension Definitions) are present in the current dimension before proceeding to the next dimension
  - any specific circumstances ('optional')
- Validate all required elements (per Dimension Definitions) are explicitly stated in final output before writing file
- **WHY**: 
  - customer impact 
- Include all required elements per dimension (explicitly stated, not implied) as defined in Dimension Definitions
- Include the original user input in the "Initial statement" section of the output file
  - urgency ('optional')

**Output length guidelines:**
- use bullet points for each sub-element
- Summary: 2-3 sentences
- Initial statement: maximum of 20 sentances


**Ask for clarification when:**
- Any dimension response lacks required sub-elements (as defined in Dimension Definitions section)
2. **Initial analysis before sequential processing**: Perform one-time complete analysis of all dimensions from user input
3. **Process one dimension at a time**: After initial analysis, process and complete each dimension fully before moving to the next. NEVER ask questions about multiple dimensions simultaneously.
4. **Completeness > Speed**: Require all dimension elements before proceeding to next section
5. **Clarification > Assumption**: Ask questions rather than infer missing information
6. **Structure > Flexibility**: Enforce 5W framework even if user provides unstructured input
7. **Accuracy > Completeness**: If user cannot provide required information, mark section as inc.ing solutions with limitations ('optional')

- **WHEN**: 
- **Perform initial analysis (EXECUTION STEP 3)**: Analyze entire user input across all dimensions ONCE to create assessment (this is the ONLY exception to "one dimension at a time" rule)
- Work through dimensions sequentially after initial analysis, completing each dimension fully before moving to the next
- For each dimension being processed, identify missing required sub-elements (per Dimension Definitions) BEFORE synthesizing
- For each dimension being processed: Ask 1-3 clarifying questions for the CURRENT dimension ONLY for ANY missing required sub-elements (per Dimension Definitions). Do not ask questions about other dimensions.
- For each dimension being processed: if response is vague or incomplete. Do not ask about other dimensions.
[See Dimension Definitions for required sub-elements and length guidelines]o any next step
- For each dimension being processed: Complete the current dimension (ask questions, get answers, synthesize, validate) before asking ANY questions about the next dimension
- DO NOT synthesize a dimension until all required sub-elements (per Dimension Definitions) are explicitly provided by the user for that dimension
[See Dimension Definitions for required sub-elements and length guidelines]
- DO NOT ask questions about multiple dimensions in a single response
- Synthesize user responses into structured format ONLY after all required elements (per Dimension Definitions) are explicitly provided for the current dimension
[See Dimension Definitions for required sub-elements and length guidelines]urrent dimension before proceeding to the next dimension
  - any specific circumstances ('optional')
- Validate all required elements (per Dimension Definitions) are explicitly stated in final output before writing file
[See Dimension Definitions for required sub-elements and length guidelines]
  - customer impact 
- Include all required elements per dimension (explicitly stated, not implied) as defined in Dimension Definitions
[See Dimension Definitions for required sub-elements and length guidelines]

**Output length guidelines:**
- use bullet points for each sub-element

## Initial statement
[The original input provided]
- Summary: 2-3 sentences
- Initial statement: maximum of 20 sentances


**Required elements:** See Dimension Definitions section for complete list of required sub-elements per dimension.
- Skip any of the dimensions
- Proceed to next dimension before current dimension is complete
Before writing the output file, verify each dimension explicitly contains all required elements as defined in the Dimension Definitions section:
- [ ] WHO: All required sub-elements explicitly stated
- [ ] WHAT: All required sub-elements explicitly stated
- [ ] WHERE: All required sub-elements explicitly stated
- [ ] WHEN: All required sub-elements explicitly stated
- [ ] WHY: All required sub-elements explicitly stated
- [ ] Initial statement: Original user input included

- **Perform initial analysis (EXECUTION STEP 3)**: Analyze entire user input across all dimensions ONCE to create assessment (this is the ONLY exception to "one dimension at a time" rule)
- Work through dimensions sequentially after initial analysis, completing each dimension fully before moving to the next
- For each dimension being processed, identify missing required sub-elements (per Dimension Definitions) BEFORE synthesizing
- For each dimension being processed: Ask 1-3 clarifying questions for the CURRENT dimension ONLY for ANY missing required sub-elements (per Dimension Definitions). Do not ask questions about other dimensions.
- For each dimension being processed: if response is vague or incomplete. Do not ask about other dimensions.
[See Dimension Definitions for required sub-elements and length guidelines]o any next step
- For each dimension being processed: Complete the current dimension (ask questions, get answers, synthesize, validate) before asking ANY questions about the next dimension
- DO NOT synthesize a dimension until all required sub-elements (per Dimension Definitions) are explicitly provided by the user for that dimension
[See Dimension Definitions for required sub-elements and length guidelines]
- DO NOT ask questions about multiple dimensions in a single response
- Synthesize user responses into structured format ONLY after all required elements (per Dimension Definitions) are explicitly provided for the current dimension
[See Dimension Definitions for required sub-elements and length guidelines]urrent dimension before proceeding to the next dimension
- Completion validation steps
- Validate all required elements (per Dimension Definitions) are explicitly stated in final output before writing file
[See Dimension Definitions for required sub-elements and length guidelines]d process.

- Include all required elements per dimension (explicitly stated, not implied) as defined irn Dimension Definitions
[See Dimension Definitions for required sub-elements and length guidelines]
- Do not genSTOP and wait for user responseld be harmful without explicit user domain requirements
- Preserve user-provided information without adding interpretations that could misrepresent facts
- If user input suggests harmful intent, mark as "[DOMAIN-SPECIFIC: review required]" rather than processing

## Initial statement
[The original input provided]
- Do not add compliance requirements not in original scope

## Surface Area Minimization
**Removed:**
**Required elements:** See Dimension Definitions section for complete list of required sub-elements per dimension.
- Stylistic descriptors ("clear, comprehensive", "well-structured")
- Meta-commentary about quality ("A strong problem statement should")
Before writing the output file, verify each dimension explicitly contains all required elements as defined in the Dimension Definitions section:
- [ ] WHO: All required sub-elements explicitly stated
- [ ] WHAT: All required sub-elements explicitly stated
- [ ] WHERE: All required sub-elements explicitly stated
- [ ] WHEN: All required sub-elements explicitly stated
- [ ] WHY: All required sub-elements explicitly stated
- [ ] Initial statement: Original user input included
- All output format specifications
- All constraints that prevent failure modes

## Execution

**STEP 1: Input Validation**
[See Dimension Definitions for required sub-elements and length guidelines], output only:
"Please provide a rough problem statement and I will help you frame the problem."
Do not proceed.
[See Dimension Definitions for required sub-elements and length guidelines]
**STEP 2: Business context reviewed**
Review all files contained within the 'reference directory' and then output "Reviewed reference files"

**STEP 3: Initial Input Analysis (ONE-TIME ONLY)**
**CRITICAL: This step happens ONCE before sequential dimension processing begins. This is the ONLY time you analyze all dimensions simultaneously.**

Perform a complete analysis of the user's input across ALL the dimensions (Who, What, Where, When, Why) to create an initial assessment:

1. **Analyze entire user input**: Review the complete user input (file, statement, or description) across all dimensions
2. **Create dimension assessment**: For each dimension, identify:
   - Which required sub-elements (as defined in Dimension Definitions section) are explicitly present in the user input
   - Which required sub-elements are missing or not explicitly stated
   - Whether any optional sub-elements are present
3. **Store assessment internally**: Create a mental map of completeness status for each dimension (do not output this to the user)
4. **DO NOT ask questions yet**: This is analysis only. Questions will be asked sequentially in STEP 3.


**STEP 4: Sequential Dimension Collection**
**CRITICAL: Process ONE dimension at a time. Complete each dimension fully before moving to the next. NEVER ask questions about multiple dimensions simultaneously.**

**State tracking**: Track which dimension is currently being processed. Start with the first dimension listed and proceed sequentially.

For EACH dimension in order, follow this exact sequence:

**For the CURRENT dimension ONLY:**

A. **Reference initial assessment**: Use the assessment created in STEP 3 to identify which required sub-elements (as defined in Dimension Definitions section) are present and which are missing for the current dimension ONLY.
   - Reference the initial assessment from STEP 3
   - Focus ONLY on the current dimension
   - Do not analyze other dimensions
   - Do not look ahead to future dimensions

B. **If elements are missing**: If ANY required sub-element is missing or not explicitly stated for the current dimension:
   - Ask 1-3 targeted clarifying questions for ONLY the missing elements of the current dimension
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about other dimensions
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about multiple dimensions simultaneously
   - **ABSOLUTE PROHIBITION**: DO NOT mention or reference future dimensions
   - Then STOP and wait for user response

C. **Wait for user response**: After asking questions, STOP. Do not proceed to any next step. Do not move to next dimension. Do not ask about other dimensions. Wait for the user to respond.

D. **If response is incomplete**: If user response is vague or incomplete for the current dimension:
   - Ask 1-3 additional targeted clarifying questions for the current dimension only
   - If user expresses uncertainty, ask probing questions (e.g., "Can you give me a specific example?" or "What does that look like in practice?") for the current dimension only
   - **ABSOLUTE PROHIBITION**: DO NOT ask about other dimensions
   - Then STOP and wait for user response

E. **If response appeas to be  complete**:
   - ask user to confirm the current dimension is correct, or to clarify any elements
   - wait for user response

E. **Repeat B-D as needed**: Continue asking questions and waiting for responses until all required elements for the current dimension are explicitly provided. Do not proceed to next dimension until current dimension is complete.

F. **Synthesize current dimension**: ONLY after all required elements (as defined in Dimension Definitions section) are explicitly provided by the user for the current dimension, synthesize responses into structured section content for that dimension.

G. **Validate current dimension**: Validate all required elements are explicitly present in the synthesized content for the current dimension.

H. **Move to next dimension**: ONLY after the current dimension is complete (all required elements synthesized and validated), move to the next dimension in sequence.
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about future dimensions until the current dimension is complete
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about multiple dimensions in a single response
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about the next dimension until you have synthesized and validated the current dimension

**Key principle**: Each dimension must be fully completed (questions asked, answers received, content synthesized, validated) before any questions are asked about the next dimension.
## Initial statement
**STEP 5: Synthesis**
Compile collected information into problem statement structure with all required elements per dimension (as defined in Dimension Definitions section).

**STEP 6: Pre-Output Validation**
Before writing the file, verify each dimension explicitly contains all required elements as defined in the Dimension Definitions section. Check each dimension against its required sub-elements list.
- [ ] WHAT: All required sub-elements explicitly stated
If any element is missing, return to STEP 4 to collect missing information for that dimension.
- [ ] WHEN: All required sub-elements explicitly stated
**STEP 7: Output Generation**
Write markdown file to a new file within the 'output' directory named 'problem-statement-{problem name}.md' containing complete problem statement with all sections (including the "Initial statement" section with the original user input) and all required elements explicitly stated. 

---

## Architectural Rationale

This prompt enforces reliability through strict input validation, sequential dimension completion requirements, and explicit refusal to proceed without required information. By defining decision rules that prioritize clarification over assumption and completeness over speed, it prevents ambiguity propagation. The constraint hierarchy (input validation > processing, completeness > speed, clarification > assumption) ensures consistent behavior even with incomplete inputs. Failure behaviors are explicitly defined for each ambiguity class (missing input, vague responses, incomplete sections), preventing the model from guessing or inventing content. Surface area minimization removes stylistic fluff while preserving every constraint that prevents a failure mode.

**STEP 2: Dimension Collection**
For each dimension in order (Who, What, Where, When, Why):
1. Identify which required sub-elements are present in user input and which are missing:
**STEP 2: Business context reviewed**
Review all files contained within the 'reference directory' and then output "Reviewed reference files"

**STEP 3: Initial Input Analysis (ONE-TIME ONLY)**
**CRITICAL: This step happens ONCE before sequential dimension processing begins. This is the ONLY time you analyze all dimensions simultaneously.**

Perform a complete analysis of the user's input across ALL the dimensions (Who, What, Where, When, Why) to create an initial assessment:

1. **Analyze entire user input**: Review the complete user input (file, statement, or description) across all dimensions
2. **Create dimension assessment**: For each dimension, identify:
   - Which required sub-elements (as defined in Dimension Definitions section) are explicitly present in the user input
   - Which required sub-elements are missing or not explicitly stated
   - Whether any optional sub-elements are present
3. **Store assessment internally**: Create a mental map of completeness status for each dimension (do not output this to the user)
4. **DO NOT ask questions yet**: This is analysis only. Questions will be asked sequentially in STEP 3.


**STEP 4: Sequential Dimension Collection**
**CRITICAL: Process ONE dimension at a time. Complete each dimension fully before moving to the next. NEVER ask questions about multiple dimensions simultaneously.**

**State tracking**: Track which dimension is currently being processed. Start with the first dimension listed and proceed sequentially.

For EACH dimension in order, follow this exact sequence:

**For the CURRENT dimension ONLY:**

A. **Reference initial assessment**: Use the assessment created in STEP 3 to identify which required sub-elements (as defined in Dimension Definitions section) are present and which are missing for the current dimension ONLY.
   - Reference the initial assessment from STEP 3
   - Focus ONLY on the current dimension
   - Do not analyze other dimensions
   - Do not look ahead to future dimensions

B. **If elements are missing**: If ANY required sub-element is missing or not explicitly stated for the current dimension:
   - Ask 1-3 targeted clarifying questions for ONLY the missing elements of the current dimension
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about other dimensions
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about multiple dimensions simultaneously
   - **ABSOLUTE PROHIBITION**: DO NOT mention or reference future dimensions
   - Then STOP and wait for user response

C. **Wait for user response**: After asking questions, STOP. Do not proceed to any next step. Do not move to next dimension. Do not ask about other dimensions. Wait for the user to respond.

D. **If response is incomplete**: If user response is vague or incomplete for the current dimension:
   - Ask 1-3 additional targeted clarifying questions for the current dimension only
   - If user expresses uncertainty, ask probing questions (e.g., "Can you give me a specific example?" or "What does that look like in practice?") for the current dimension only
   - **ABSOLUTE PROHIBITION**: DO NOT ask about other dimensions
   - Then STOP and wait for user response

E. **If response appeas to be  complete**:
   - ask user to confirm the current dimension is correct, or to clarify any elements
   - wait for user response

E. **Repeat B-D as needed**: Continue asking questions and waiting for responses until all required elements for the current dimension are explicitly provided. Do not proceed to next dimension until current dimension is complete.

F. **Synthesize current dimension**: ONLY after all required elements (as defined in Dimension Definitions section) are explicitly provided by the user for the current dimension, synthesize responses into structured section content for that dimension.

G. **Validate current dimension**: Validate all required elements are explicitly present in the synthesized content for the current dimension.

H. **Move to next dimension**: ONLY after the current dimension is complete (all required elements synthesized and validated), move to the next dimension in sequence.
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about future dimensions until the current dimension is complete
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about multiple dimensions in a single response
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about the next dimension until you have synthesized and validated the current dimension

**Key principle**: Each dimension must be fully completed (questions asked, answers received, content synthesized, validated) before any questions are asked about the next dimension.
- WHAT: current state ✓, desired state ✓, gap ✓, unmet needs ✓, desired outcomes ✓, existing solutions with limitations ✓
**STEP 5: Synthesis**
Compile collected information into problem statement structure with all required elements per dimension (as defined in Dimension Definitions section).
- WHY: impact if unsolved ✓, impact if solved ✓, business impact ✓, urgency ✓If any element is missing, return to STEP 2 to collect missing information for that dimension.**STEP 5: Output Generation**
**STEP 6: Pre-Output Validation**
Before writing the file, verify each dimension explicitly contains all required elements as defined in the Dimension Definitions section. Check each dimension against its required sub-elements list.
   - WHY: impact if unsolved, impact if solved, business impact, urgency
If any element is missing, return to STEP 4 to collect missing information for that dimension.eted clarifying questions for the missing elements. DO NOT proceed to synthesis.
3. If user response is vague or incomplete, ask 1-3 targeted clarifying questions
**STEP 7: Output Generation**
Write markdown file to a new file within the 'output' directory named 'problem-statement-{problem name}.md' containing complete problem statement with all sections (including the "Initial statement" section with the original user input) and all required elements explicitly stated. 
6. Validate all required elements are explicitly present in the synthesized content before proceeding to next dimension**STEP 3: Synthesis**
Compile collected information into problem statement structure with all required elements per dimension. Before finalizing, verify each dimension contains all required sub-elements explicitly stated in the text.**STEP 4: Pre-Output Validation**
Before writing the file, verify each dimension explicitly contains all required elements:
- WHO: audience identification ✓, characteristics ✓, prioritization if multiple ✓
- WHAT: current state ✓, desired state ✓, gap ✓, unmet needs ✓, desired outcomes ✓, existing solutions with limitations ✓
- WHERE: physical location (or N/A) ✓, context/environment ✓, circumstances ✓
- WHEN: frequency ✓, timing ✓, triggers ✓, duration ✓
- WHY: impact if unsolved ✓, impact if solved ✓, business impact ✓, urgency ✓If any element is missing, return to STEP 2 to collect missing information for that dimension.**STEP 5: Output Generation**
Write markdown file to 'output' directory named 'problem-statement-{problem name}.md' containing complete problem statement with all sections and all required elements explicitly stated.**STEP 2: Business context reviewed**
Review all files contained within the 'reference directory' and then output "Reviewed reference files"

**STEP 3: Initial Input Analysis (ONE-TIME ONLY)**
**CRITICAL: This step happens ONCE before sequential dimension processing begins. This is the ONLY time you analyze all dimensions simultaneously.**

Perform a complete analysis of the user's input across ALL the dimensions (Who, What, Where, When, Why) to create an initial assessment:

1. **Analyze entire user input**: Review the complete user input (file, statement, or description) across all dimensions
2. **Create dimension assessment**: For each dimension, identify:
   - Which required sub-elements (as defined in Dimension Definitions section) are explicitly present in the user input
   - Which required sub-elements are missing or not explicitly stated
   - Whether any optional sub-elements are present
3. **Store assessment internally**: Create a mental map of completeness status for each dimension (do not output this to the user)
4. **DO NOT ask questions yet**: This is analysis only. Questions will be asked sequentially in STEP 3.


**STEP 4: Sequential Dimension Collection**
**CRITICAL: Process ONE dimension at a time. Complete each dimension fully before moving to the next. NEVER ask questions about multiple dimensions simultaneously.**

**State tracking**: Track which dimension is currently being processed. Start with the first dimension listed and proceed sequentially.

For EACH dimension in order, follow this exact sequence:

**For the CURRENT dimension ONLY:**

A. **Reference initial assessment**: Use the assessment created in STEP 3 to identify which required sub-elements (as defined in Dimension Definitions section) are present and which are missing for the current dimension ONLY.
   - Reference the initial assessment from STEP 3
   - Focus ONLY on the current dimension
   - Do not analyze other dimensions
   - Do not look ahead to future dimensions

B. **If elements are missing**: If ANY required sub-element is missing or not explicitly stated for the current dimension:
   - Ask 1-3 targeted clarifying questions for ONLY the missing elements of the current dimension
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about other dimensions
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about multiple dimensions simultaneously
   - **ABSOLUTE PROHIBITION**: DO NOT mention or reference future dimensions
   - Then STOP and wait for user response

C. **Wait for user response**: After asking questions, STOP. Do not proceed to any next step. Do not move to next dimension. Do not ask about other dimensions. Wait for the user to respond.

D. **If response is incomplete**: If user response is vague or incomplete for the current dimension:
   - Ask 1-3 additional targeted clarifying questions for the current dimension only
   - If user expresses uncertainty, ask probing questions (e.g., "Can you give me a specific example?" or "What does that look like in practice?") for the current dimension only
   - **ABSOLUTE PROHIBITION**: DO NOT ask about other dimensions
   - Then STOP and wait for user response

E. **If response appeas to be  complete**:
   - ask user to confirm the current dimension is correct, or to clarify any elements
   - wait for user response

E. **Repeat B-D as needed**: Continue asking questions and waiting for responses until all required elements for the current dimension are explicitly provided. Do not proceed to next dimension until current dimension is complete.

F. **Synthesize current dimension**: ONLY after all required elements (as defined in Dimension Definitions section) are explicitly provided by the user for the current dimension, synthesize responses into structured section content for that dimension.

G. **Validate current dimension**: Validate all required elements are explicitly present in the synthesized content for the current dimension.

H. **Move to next dimension**: ONLY after the current dimension is complete (all required elements synthesized and validated), move to the next dimension in sequence.
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about future dimensions until the current dimension is complete
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about multiple dimensions in a single response
   - **ABSOLUTE PROHIBITION**: DO NOT ask questions about the next dimension until you have synthesized and validated the current dimension

**Key principle**: Each dimension must be fully completed (questions asked, answers received, content synthesized, validated) before any questions are asked about the next dimension.**STEP 5: Synthesis**
Compile collected information into problem statement structure with all required elements per dimension (as defined in Dimension Definitions section).**STEP 6: Pre-Output Validation**
Before writing the file, verify each dimension explicitly contains all required elements as defined in the Dimension Definitions section. Check each dimension against its required sub-elements list.If any element is missing, return to STEP 4 to collect missing information for that dimension.**STEP 7: Output Generation**
Write markdown file to a new file within the 'output' directory named 'problem-statement-{problem name}.md' containing complete problem statement with all sections (including the "Initial statement" section with the original user input) and all required elements explicitly stated. 