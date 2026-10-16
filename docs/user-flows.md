# User Flows
## DXP Front-Line Sales Candidate Assessment MVP

These flows describe the core MVP journeys. They intentionally focus on the product's business functions rather than generic login, registration, or account-management flows.

## 1. Candidate completes an assessment

```mermaid
flowchart TD
    A([Start]) --> B[Open assessment link]
    B --> C[Read purpose, instructions, and privacy notice]
    C --> D{Consent / required acknowledgement completed?}
    D -- No --> E[Explain requirement and allow exit]
    D -- Yes --> F[Choose English, Bahasa Malaysia, or Mandarin]
    F --> G[Load approved assessment version]
    G --> H[Answer questions across the six capability areas]
    H --> I{Required responses complete?}
    I -- No --> J[Show missing responses and allow review]
    J --> H
    I -- Yes --> K[Review answers]
    K --> L[Submit assessment]
    L --> M[Validate and store responses with version metadata]
    M --> N[Apply deterministic scoring rules]
    N --> O[Generate capability-level results and evidence]
    O --> P[Show submission confirmation]
    P --> Q([End])
```

**Notes**
- The exact consent and acknowledgement wording must be approved by the project owner.
- The candidate should know whether answers can be changed after submission.
- Store the language, question version, rubric/scoring version, and timestamps needed for auditability.
- Do not show a misleading “pass/fail” decision unless the project explicitly approves and validates such a use.

## 2. Hiring manager reviews a candidate

```mermaid
flowchart TD
    A([Start]) --> B[Open hiring manager view]
    B --> C[Select vacancy or assessment cohort]
    C --> D[View candidate list and assessment status]
    D --> E[Select a candidate]
    E --> F[Review capability profile]
    F --> G[Inspect evidence, strengths, gaps, and limitations]
    G --> H[Review suggested interview probes]
    H --> I{Need comparison with other candidates?}
    I -- Yes --> J[Select comparable candidates]
    J --> K[Compare capability evidence and assessment versions]
    K --> L[Review caveats and missing data]
    I -- No --> M[Record review notes / next step]
    L --> M
    M --> N[Make human-led recruitment decision outside automated scoring]
    N --> O([End])
```

**Notes**
- Show when candidates completed different assessment versions or used conditions that make direct comparison unreliable.
- Interview probes should be linked to evidence or a capability gap, not invented as facts about a candidate.
- The tool supports decisions; it does not autonomously hire or reject candidates.

## 3. Authorised administrator manages assessment content

```mermaid
flowchart TD
    A([Start]) --> B[Open assessment configuration]
    B --> C[Create or edit a draft assessment version]
    C --> D[Add or update questions]
    D --> E[Map each question to capability and response type]
    E --> F[Add English, Bahasa Malaysia, and Mandarin variants]
    F --> G[Define documented scoring rules]
    G --> H[Run configuration checks]
    H --> I{Missing mapping, translation, or invalid scoring?}
    I -- Yes --> J[Fix issues and repeat checks]
    J --> H
    I -- No --> K[Request authorised review]
    K --> L{Approved?}
    L -- No --> M[Return draft with review comments]
    M --> C
    L -- Yes --> N[Publish immutable version]
    N --> O[Record approver, version, and publication date]
    O --> P([End])
```

**Notes**
- Published versions should not be silently overwritten.
- Changes to questions, translations, or scoring should create a new version.
- The project owner must define who is authorised to approve and publish content.

## 4. Assessment harness checks quality and proposes improvements

```mermaid
flowchart TD
    A([Start]) --> B[Select draft or published assessment version]
    B --> C[Check capability mapping and question coverage]
    C --> D[Check translation completeness and review status]
    D --> E[Check rubric/scoring consistency and version metadata]
    E --> F[Review pilot observations when available]
    F --> G[Generate traceable quality findings]
    G --> H{Any issues or improvement opportunities?}
    H -- No --> I[Record checks passed]
    H -- Yes --> J[Draft suggested change or follow-up test]
    J --> K[Human owner reviews evidence and impact]
    K --> L{Approve change?}
    L -- No --> M[Reject or defer with reason]
    L -- Yes --> N[Create a new draft version]
    N --> O[Run validation and regression checks]
    O --> P[Approve and publish new version if checks pass]
    I --> Q([End])
    M --> Q
    P --> Q
```

**Notes**
- “Self-improving” means the system helps identify and manage quality improvements; it does not rewrite or publish questions without human approval.
- Every finding should identify the affected item, reason, severity or priority, and suggested next action.
- A pilot pattern from a small sample should be labelled uncertain rather than treated as proof.

## 5. Employee benchmarking and pilot validation

```mermaid
flowchart TD
    A([Start]) --> B[Project owner proposes benchmark cohort]
    B --> C[Confirm approved purpose, consent/basis, and access rules]
    C --> D{Data use approved?}
    D -- No --> E[Do not use benchmark data]
    D -- Yes --> F[Minimise and prepare the data]
    F --> G[Check role, assessment version, language, and testing comparability]
    G --> H{Sample and data quality adequate for intended analysis?}
    H -- No --> I[Report limitations; defer or keep exploratory]
    H -- Yes --> J[Calculate descriptive comparisons]
    J --> K[Review potential bias and uncertainty]
    K --> L[Present findings with sample size and caveats]
    I --> M[Record validation conclusion and next steps]
    L --> M
    E --> M
    M --> N([End])
```

**Notes**
- Benchmarking is optional and gated by the project owner's approval and applicable privacy requirements.
- Similarity to current employees does not by itself prove future job performance.
- Do not report identifiable employee-level benchmark results to users who do not need that access.

## Flow-to-requirement traceability

| Flow | Related requirements |
|---|---|
| Candidate assessment | FR-01, FR-02, FR-03, FR-04, FR-10 |
| Hiring manager review | FR-05, FR-06, FR-07 |
| Content management | FR-03, FR-08, FR-09, FR-10 |
| Assessment harness | FR-08, FR-09, FR-10, FR-13 |
| Benchmarking and validation | FR-11, FR-13 and privacy/security requirements |

## Implementation boundary

These are proposed flows for review, not evidence that the functionality already exists. The team should confirm the exact candidate consent wording, scoring scales, approval roles, assessment length, data retention, and pilot criteria before implementation.
