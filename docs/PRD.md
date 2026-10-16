# Product Requirements Document (PRD)
## DXP Front-Line Sales Candidate Assessment MVP

**Document status:** Draft for team review  
**Alignment:** Brought into line with the submitted proposal (`PROPOSAL.pdf`) on 2026-10-16. Where this document and the proposal differ, the proposal wins.  
**Version:** 1.0  
**Project duration:** 10 weeks (planned)  
**Planned start:** 2 November 2026  
**Source of truth:** DXP project brief and approved project decisions

---

## 1. Product overview

The DXP Front-Line Sales Candidate Assessment MVP is a web-based assessment and review tool intended to help hiring teams evaluate front-line sales candidates more consistently. It structures evidence across six role-relevant capability areas, presents understandable results to hiring managers, and supports careful comparison with suitable existing sales employees where consent and data quality permit.

The MVP is a decision-support tool. It must not make autonomous hiring decisions or present an opaque single score as the only basis for selecting a candidate.

## 2. Problem statement

Current front-line sales recruitment uses job boards, referrals, application forms, and interviews. Existing assessment forms are outdated or inconsistent, so candidates may be evaluated differently by different interviewers. Concerns about role suitability can surface only after several interview rounds, creating repeated recruitment, onboarding, and training effort.

Sales experience alone may not show whether a candidate can adapt to digital tools and data-driven workflows. Hiring teams need consistent, explainable evidence of candidate strengths, development gaps, and areas that require follow-up.

## 3. Goals and success measures

### Goals
1. Standardise assessment against agreed front-line sales role requirements.
2. Provide evidence-backed capability profiles rather than relying only on interviewer impressions.
3. Help hiring managers identify strengths, development areas, and questions to explore in interviews.
4. Support candidate comparison using consistent criteria.
5. Explore benchmarking against suitable existing sales employees without overstating conclusions.
6. Establish a traceable basis for testing and improving assessment quality.

### Success targets (from the submitted proposal)

Confirmed with the company in week 1 and reported in the validation report.

| Measure | Target | How measured |
|---|---|---|
| Scoring accuracy | 100% | Automated tests against hand-scored answer sheets. Any miss is a defect. |
| Assessment completion | 90% or above | Candidates who finish divided by candidates who start. |
| Internal consistency per area | 0.70 or above, provisional | Pilot data of 20 to 30 candidates. |
| Language equivalence | No item flagged as harder in one language after fixes | Cross-language item difficulty check. |
| Usability | 4.0 out of 5 or above | Candidate and manager survey, with observed sessions. |
| Hiring manager usefulness | 4.0 out of 5 or above | Post-pilot survey. |
| Employee benchmark | Reported as a range only | About 10 employees. No prediction claim. |

### Additional measures
- Completion rate for pilot assessments.
- Percentage of results with traceable evidence and scoring rationale.
- Agreement between reviewers applying the same rubric to the same responses.
- Candidate and hiring-manager usability feedback.
- Time required to review a candidate profile compared with the current process.
- Percentage of assessment items reviewed for language clarity and role relevance.
- Number of scoring or content defects found during validation.

Do not claim that the MVP reduces turnover or predicts job performance unless a sufficiently designed evaluation supports that conclusion.

## 4. Users and responsibilities

| User | Main needs | Responsibilities |
|---|---|---|
| Candidate | Clear, accessible assessment in a supported language | Read instructions, answer questions, submit responses |
| Hiring manager / recruiter | Understandable evidence and candidate comparisons | Review profiles, investigate gaps, make the hiring decision |
| Assessment administrator / authorised owner | Maintain assessment content and scoring configuration | Manage questions, versions, language variants, and publication |
| Project evaluator / analyst | Assess whether the MVP is consistent and useful | Review pilot evidence and limitations |
| Existing sales employee (benchmark participant) | Understand why their data is used | Provide informed consent where required; participate only under approved data-handling rules |

Access should follow least-privilege principles. The MVP should not require a general-purpose account-management feature unless it is needed for the agreed pilot.

## 5. Capability framework

The assessment should cover the six capability areas identified in the project brief:

1. Numerical and analytical ability
2. Logical thinking
3. Situational judgement
4. Problem-solving
5. Self-leadership
6. Digital and data literacy

Each capability should have a clear definition, observable indicators, an assessment method, and a scoring rubric. The team must validate the mapping between each question and the capability it is intended to measure.

### Role profile, gaps and risks

Before any question is written, HR and sales managers agree a **role profile**. For each of the six areas it sets the **required level** on a five-level scale and whether the area is **critical** (a shortfall affects performance) or **trainable** (a shortfall can be developed on the job). The profile is versioned, and every result records which profile version it was scored against.

Flags for each area:
- **Strength:** at or above the required level.
- **Development gap:** below the level in a trainable area, by no more than one level.
- **Risk indicator:** below the level in a critical area, or more than one level below in any area.

These rules are held as data, shown to the user, and changeable by HR. A risk indicator is a prompt to look closer, never a rejection.

## 6. Language support

Candidate-facing assessment content should support:
- English
- Bahasa Malaysia
- Mandarin

Language versions should be reviewed for meaning equivalence, not only literal translation. Use translation and back-translation or an equivalent review process, followed by checks with fluent reviewers and pilot participants. Record the content version and language used for each completed assessment. Do not assume scores are directly comparable across languages until comparability has been evaluated.

## 7. MVP scope

### In scope
- Candidate-facing web assessment experience.
- Selection of one supported language before starting.
- Assessment questions mapped to the six capabilities.
- Response capture and submission confirmation.
- Deterministic, versioned scoring rules for supported question types.
- Capability-level results with supporting evidence and clear explanations.
- Role profile with required levels, versioned.
- Hiring-manager view of candidate results: strengths, development gaps, risk indicators, evidence, and follow-up prompts.
- Side-by-side candidate comparison using the same assessment version where possible.
- Question and scoring configuration for authorised users.
- Version tracking for questions, translations, rubrics, and scoring rules.
- Basic pilot analytics and validation reporting.
- Employee benchmark of about 10 employees, shown as a range with group size, only where approved and consented.
- Export of results to CSV and Excel.
- Basic access control and protection of candidate data.
- Documentation and handover.

### Out of scope for the MVP unless explicitly approved
- Autonomous accept/reject or ranking decisions.
- Automated or AI-drafted question edits, and automatic publication of changed assessments. Configuration checks (FR-09) are in scope. Improvement suggestions are not.
- Claims of validated prediction of future sales performance without appropriate evidence.
- Advanced proctoring or guaranteed prevention of cheating.
- Full HRIS, applicant-tracking, payroll, or onboarding integrations.
- Broad production-grade account administration unrelated to the pilot.
- Benchmark conclusions from very small or non-comparable samples.

## 8. Core user journeys

See `user-flows.md` for Mermaid diagrams. The primary journeys are:
1. Candidate completes an assessment.
2. Hiring manager reviews and compares candidate evidence.
3. Authorised administrator maintains and publishes assessment content.
4. Configuration checks flag missing mappings, missing translations and invalid scoring rules.
5. Project team evaluates suitable employee benchmarking data.

## 9. Functional requirements

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| FR-01 | Select assessment language | Must | Candidate can choose English, Bahasa Malaysia, or Mandarin before beginning; the chosen language is recorded |
| FR-02 | Deliver assessment | Must | Candidate can read instructions, answer the configured questions, and submit responses |
| FR-03 | Map questions to capabilities | Must | Each active question is linked to at least one approved capability and has a recorded version |
| FR-04 | Score consistently | Must | The same response set and scoring version always produce the same computed score |
| FR-05 | Explain results | Must | Results show capability-level findings, flags, and the questions and rubric behind each |
| FR-06 | Review candidate profile | Must | Hiring manager can inspect strengths, development gaps, risk indicators, limitations, and suggested follow-up questions |
| FR-07 | Compare candidates | Should | Hiring manager can compare candidates using compatible assessment versions and see when comparisons are not directly comparable |
| FR-08 | Manage questions and rubrics | Must | Authorised administrator can draft, review, version, and publish assessment content |
| FR-09 | Validate assessment configuration | Should | System flags missing capability mappings, missing translations, invalid scoring rules, and unapproved content |
| FR-10 | Record audit information | Must | Results retain the assessment, question, language, and scoring versions used |
| FR-11 | Benchmark employees | Should / gated | Only approved, consented, appropriately protected data is used; shown as a range with group size; no correlation reported from a sample too small to support it |
| FR-12 | Export results | Must | Authorised user can export agreed fields in CSV/Excel format without exposing unnecessary personal data |
| FR-13 | Report pilot quality | Should | Project team can review completion, missing data, scoring consistency, and item-level validation observations |
| FR-14 | Role profile | Must | HR can create and version a role profile with a required level and critical or trainable mark for each area; every result records the profile version |
| FR-15 | Gap and risk flags | Must | Strength, development gap and risk indicator are generated from the role profile by visible rules, each listing the questions that drove it |

Priority meanings: **Must** = essential for a credible MVP; **Should** = important if time permits; **Should / gated** = committed in the proposal, but only after governance, consent and data readiness checks.

## 10. Configuration checks

Configuration checks are quality control, not an autonomous judge and not an editor. The system flags:
- Questions with no capability mapping.
- Missing or unreviewed language variants.
- Duplicated questions.
- Scoring rules that are missing, inconsistent, or not versioned.
- Changes that would make comparisons with earlier results unreliable.

An authorised human fixes each finding. Published assessments remain immutable versions. A change to a question, translation, rubric, or scoring rule creates a new version and is tested before publication, with a record of what changed, why, who approved it, and when it became active.

Suggesting or drafting edits to questions is out of scope for the MVP.

## 11. Hiring manager analysis

The manager view should present:
- Capability-level results and their rubric-based interpretation.
- Supporting response evidence or examples.
- Strengths and possible development areas.
- Uncertainty, missing responses, or limits affecting interpretation.
- Suggested interview probes tied to observed evidence.
- Candidate comparisons only where the assessment versions and context are sufficiently comparable.

The system must not treat an assessment result as a definitive statement about a person's character or future performance. Hiring managers remain responsible for considering the full recruitment context and making decisions.

## 12. Employee benchmarking and validation

Benchmarking is optional and subject to approval. Before comparing candidates with existing sales employees:
1. Confirm a lawful and approved purpose and appropriate consent or other valid basis.
2. Minimise personal data and restrict access.
3. Check that roles, assessment versions, language conditions, and testing contexts are reasonably comparable.
4. Report the number and composition of participants.
5. Avoid presenting small-sample patterns as reliable norms.
6. Label exploratory findings as exploratory.
7. Do not infer predictive validity from similarity to current employees alone.

Pilot validation should include content review, language review, usability testing, scoring checks, and reviewer consistency checks. Any claims about prediction of job outcomes require a separate, appropriately designed study.

## 13. Non-functional requirements

- **Privacy:** Collect only data needed for the approved assessment and pilot.
- **Security:** Restrict access to candidate results and benchmarking data; use secure transport and appropriate storage protections.
- **Auditability:** Retain versions and explain how each result was produced.
- **Reliability:** Prevent duplicate or partial submissions from silently corrupting results; show clear error and submission states.
- **Accessibility:** Use readable layouts, clear instructions, keyboard-accessible controls, and suitable contrast.
- **Usability:** Keep instructions concise and make progress and submission status clear.
- **Maintainability:** Keep questions, translations, rubrics, and scoring configuration organised and versioned.
- **Performance:** Agree practical response-time targets with the team before pilot testing.
- **Responsible use:** No fully automated hiring decisions; explain limitations and keep humans accountable.

## 14. Data requirements

Potential entities:
- Candidate / candidate reference
- Assessment session
- Assessment definition and version
- Question and question version
- Language variant and review status
- Capability and question-to-capability mapping
- Response
- Scoring rubric and scoring-rule version
- Capability result and evidence reference
- Hiring-manager review / interview probe
- Employee benchmark participant reference and consent status, if approved
- Validation observation and item-quality finding
- Audit event

Use pseudonymous identifiers where feasible. Define retention, deletion, access, export, and consent handling with the project owner before using real candidate or employee data.

## 15. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Translation changes the meaning or difficulty of a question | Review translations with fluent reviewers and pilot them; version each language variant |
| Questions do not measure the intended capability | Map items to capabilities and review content with subject-matter experts |
| Scoring is inconsistent or opaque | Use deterministic, documented, versioned rubrics and test repeatability |
| Managers over-rely on a summary score | Show capability-level evidence, caveats, and interview probes; do not make automated decisions |
| Employee benchmark sample is too small or biased | Treat benchmarking as gated and exploratory; show sample limits |
| Candidate responses are assisted or unrepresentative | Use clear instructions and follow-up interview probes; do not claim automated proctoring prevents cheating |
| Scope exceeds the 10-week project | Prioritise candidate assessment, transparent scoring, manager review, and basic validation before optional analytics |
| Personal data is exposed or retained unnecessarily | Minimise data, restrict access, and agree retention and deletion rules |

## 16. Delivery sequence

From the submitted proposal. Ten weeks from 2 November 2026 if awarded. Each week has an acceptance test.

| Week | Work | Accepted when |
|---|---|---|
| 1 | Job analysis, role profile, pilot gates, privacy review. | Role profile signed off by HR. |
| 2 | Question bank draft, translation starts, data model. | Draft items for all six areas. Schema reviewed. |
| 3 | Backend foundation, scoring engine. | Scoring passes all hand-scored test sheets. |
| 4 | Candidate flow. | A candidate completes the assessment end to end in each language, on phone and laptop. |
| 5 | Profiling and flag rules. | Strengths, gaps and risks generated from the role profile with evidence. |
| 6 | Hiring manager dashboard. | Profile, comparison of 2 to 5 candidates, decision and reason logged. |
| 7 | Employee benchmark and access control. | Range shown with group size. Each role sees only what it is allowed to. |
| 8 | Admin, export, analytics, pilot readiness. | Item management, export and item statistics work. |
| 9 | Candidate pilot and usability sessions. | Pilot completed, findings logged. |
| 10 | Validation report, fixes, handover. | Report states what is proven and what is not. |

Known calendar risk: week 9 is 28 December to 1 January. Plan to move employee sessions to week 7 and start the candidate pilot in week 8. Week 5 holds the 5 December hackathon, so keep it light. See `KICKOFF.md`.

## 17. Open questions

The project owner and team should resolve:
1. Which question formats and approximate assessment length are approved?
2. Which capability scoring scales and weights, if any, will be used?
3. Who approves questions, translations, rubrics, and published versions?
4. What candidate and employee data may be collected, and what are the retention rules?
5. What is the approved consent process for employee benchmarking?
6. Which user roles and access permissions are required for the pilot?
7. Is CSV/Excel export required for the first MVP release?
8. What sample size and evidence are required before reporting benchmark insights?
9. Which languages and devices will be included in usability testing?
10. What measurable acceptance targets will the sponsor approve?

Already answered by the submitted proposal: question formats and scoring (section 4), scale and weights (five levels per area, no composite score), approval roles (HR admin and assessment admin), user roles and access (section 10), export (required, Excel and CSV), languages (English, Bahasa Malaysia, Mandarin), and numeric targets (section 3 above). Still open: who approves published versions at the company, data retention and consent wording, benchmark sample access, and device coverage for usability testing.

## 18. Definition of done

The documentation and MVP are ready for review when:
- The agreed in-scope requirements are traceable to user journeys.
- Each active question is mapped to an approved capability and scoring rule.
- Repeated scoring of the same versioned responses produces the same result.
- The candidate can complete and submit an assessment in each supported language included in the pilot.
- A signed role profile exists, and results show strengths, development gaps and risk indicators against it.
- Hiring managers can review capability evidence and limitations.
- Changes to assessment content are versioned and require approval.
- Privacy, access, retention, and benchmarking decisions are documented.
- End-to-end tests and pilot observations are recorded.
- Known limitations and handover instructions are provided.
