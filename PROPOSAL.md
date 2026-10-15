---
pagetitle: "Front-Line Sales Candidate Assessment MVP"
---

# Front-Line Sales Candidate Assessment MVP

**Concept proposal for a structured, three-language candidate assessment with a hiring manager dashboard.** Submitted by Irfan Ali, Muhammad Fahmi Bin Muhamad and team. [Remaining team names to be completed before upload.]

**Program:** Digital Acceleration Program (DXP). **Duration:** 10 weeks. **Proposed start:** 2 November 2026. **Date:** 13 October 2026.

**The problem.** A front-line sales hire is interviewed in several rounds. Each round is a different interviewer with a different form, and the forms do not test what the job now demands: reading a dashboard, working from data, using digital sales tools, making sound calls alone in the field. A candidate with strong sales experience can still struggle in a data-driven way of working, and nobody sees that until after the offer. If the person leaves, the company pays again for recruitment, onboarding and training. The company already knows turnover is high. It has no consistent evidence on why some hires succeed and others do not.

> **Our answer in one line.** The assessment gives evidence, not a verdict. Every result traces back to the questions behind it, every flag says what it means in plain words, and the hiring manager still decides.

## 1. What each person sees

1. **Candidate.** Opens a private link on a phone or laptop, picks English, Bahasa Malaysia or Mandarin, reads what is measured and how the result is used, tries one practice question, then takes the timed assessment. Extra time can be switched on for a candidate who needs it.
2. **Hiring manager.** Opens a one-page profile per candidate: six capability areas, each shown as a level against the level the role needs. Strengths, development gaps and risk indicators are listed separately, each with the evidence behind it and suggested interview questions to probe it. Candidates for the same role can be compared side by side.
3. **HR admin.** Manages the role profile, the question bank, translations, scoring keys and user access. Exports results to Excel or CSV.
4. **Analyst.** Sees item statistics, language comparisons and the benchmark against existing employees.

## 2. How each requirement in the brief is met

| Requirement | How the MVP meets it |
|---|---|
| Consistent assessment against agreed requirements | A role profile agreed with the company, and the same scored assessment for every candidate. Section 3. |
| Six capability areas | Numerical and analytical, logical, situational judgement, problem-solving, self-leadership, digital and data literacy. Section 4. |
| English, Bahasa Malaysia, Mandarin | One item, three reviewed translations, one scoring key. Section 5. |
| Strengths, gaps and risks | Rules agreed with the company decide which gaps are manageable and which are risks. Section 6. |
| Hiring manager dashboard | Profile and comparison views. Section 7. |
| Benchmark against existing employees | Consented, pseudonymised employee results give a reference range. Section 8. |
| Validation and analytics | A validation plan and report produced from the pilot. Section 9. |
| Database, question and scoring management, export, access control | Section 10. |
| Documentation and handover | Section 12. |

## 3. Agreeing the requirements first

The system is only as fair as the definition of the job it tests against. Before any question is written, we run a short job analysis with HR and a mix of strong and average front-line sales managers.

- For each capability area the group agrees the **level the role needs**, on a five-level scale, and whether the area is **critical** (a shortfall affects performance) or **trainable** (a shortfall can be developed on the job).
- The agreement is stored as the role profile. It is versioned, and every candidate result records which version it was scored against.
- A new role, for example a different sales channel, is a new profile, not new code.

## 4. The assessment

| Area | What the candidate does | How it is scored |
|---|---|---|
| Numerical and analytical | Reads tables and charts that look like sales dashboards, works out margins, targets and trends. | Automatic, one correct answer. |
| Logical thinking | Rules, sequences and deductions. | Automatic, one correct answer. |
| Situational judgement | Field scenarios: an angry customer, a missed target, a pricing request outside policy. Rates or ranks the responses. | Automatic against a key set by a panel of experienced managers. Score is closeness to the panel. |
| Problem-solving | A short multi-step case with structured choices at each step. | Automatic against a written rubric. |
| Self-leadership | Forced-choice statements about planning, persistence and self-correction. | Automatic. Self-report, so it carries less weight and can never trigger a risk flag on its own. |
| Digital and data literacy | Practical tasks: find the figure in a dashboard, spot the error in a spreadsheet extract, choose the right filter. | Automatic, one correct answer. |

The MVP does not use AI to score answers. Scoring is plain, testable rules, so a hiring manager or an auditor can see exactly why a score is what it is. Each form is drawn from a larger question bank, so candidates who compare notes do not see identical papers. The time limit is enforced on the server, not the browser.

## 5. Three languages, one test

Translating a question does not guarantee it is as hard in the other language. Our process:

1. Write the item in English. A linguist produces the Bahasa Malaysia and Mandarin versions independently.
2. A second linguist translates each back to English, and differences are resolved with HR.
3. Each item keeps one ID across languages and one scoring key. Numbers, currency and units are localised, and a candidate sees only one language.
4. After the pilot, each item's difficulty is compared across languages. An item that is harder in one language is flagged and fixed or removed. Until that check has run, we report language results as provisional.

We assume Simplified Chinese for Mandarin unless the company says otherwise.

## 6. Strengths, gaps and risks

For each area the system compares the candidate's level with the required level from the role profile.

- **Strength.** At or above the required level.
- **Development gap.** Below the level in an area marked trainable, by no more than one level.
- **Risk indicator.** Below the level in an area marked critical, or more than one level below in any area.

These rules are held as data and shown on the dashboard, so the company can change them and see what changed. Each flag lists the exact questions answered wrongly or the scenario choices that drove it, and a suggested interview question to test it. A risk indicator is a prompt to look closer, never a rejection.

## 7. Hiring manager dashboard

- **Candidate profile:** six bars with a marker for the required level, the three flag lists, and the evidence behind each.
- **Comparison:** candidates for one role side by side. We deliberately do not show a single ranked score by default. One number invites mechanical use and hides exactly the strengths and gaps the brief asks to make visible.
- **Decision log:** the manager records the decision and a reason. Over time this shows whether the assessment informs decisions or is ignored.
- **Export** to Excel and CSV, with the role profile version and scoring version in every row.

## 8. Comparing with existing sales employees

HR selects about 10 current front-line sales employees, who take the same assessment on a no-stakes basis with their consent. HR joins their results to performance and retention data using a pseudonymised ID, and the key stays with HR.

The honest limits:

- With about 10 people, no correlation between score and performance is meaningful, and we will not report one. The MVP shows **where a candidate sits within the range of current employees** in each area, with the group size printed beside it. It cannot prove that a score predicts success. If HR can supply more employees, the range steadies, but the claim stays the same.
- Current employees are survivors of the existing hiring process. A reference group built from them can repeat the old process's blind spots.
- Proving prediction needs candidates who are scored, hired and followed. So the MVP records every candidate's result, hire decision, and retention and performance outcome at agreed points, such as 3 and 6 months. The analysis pack is built now, and the evidence grows with each hiring round.

The benchmark is advisory and is never used to reject a candidate automatically.

## 9. Validation evidence

| Check | What it shows | How |
|---|---|---|
| Content | The questions reflect the job. | Job analysis, and a manager panel reviews every item against the role profile. |
| Scoring accuracy | The software scores as intended. | Automated tests against hand-scored answer sheets. The target is 100%, because scoring is deterministic. |
| Reliability | Each area gives consistent results. | Internal consistency per area from the pilot. Target 0.70 or above, the commonly used floor. With a pilot of 20 to 30 candidates the estimate is rough, so it is reported with its uncertainty and labelled provisional. |
| Item quality | Items are neither too easy nor too hard, and separate stronger from weaker candidates. | Difficulty and discrimination per item. Poor items are flagged. |
| Language equivalence | The three versions are equally fair. | Item difficulty compared across languages. |
| Fairness | No group is disadvantaged without a job reason. | Optional, separate, consented demographic data used only for monitoring, with score differences reported by group. |
| Usability | Candidates understand it. | Observed sessions with 5 to 8 candidates per language. |

With small pilot samples we publish the statistics with their uncertainty and label them provisional. The validation report states which claims are supported and which are not yet.

### Success targets

Agreed with the company in week 1 and reported in the validation report.

| Measure | Target | How it is measured |
|---|---|---|
| Scoring accuracy | 100% | Automated tests against hand-scored answer sheets. Any miss is a defect. |
| Assessment completion | 90% or above | Candidates who finish divided by candidates who start. |
| Internal consistency per area | 0.70 or above, provisional | Pilot data of 20 to 30 candidates. |
| Language equivalence | No item flagged as harder in one language after fixes | Cross-language item difficulty check on pilot data. |
| Usability | 4.0 out of 5 or above | Candidate and manager survey, with observed sessions. |
| Hiring manager usefulness | 4.0 out of 5 or above | Post-pilot survey: did the profile change what you asked or decided? |
| Employee benchmark | Reported as range only | About 10 employees. No prediction claim. |

## 10. Architecture and security

React and Tailwind front end that works on a phone, with react-i18next for the three languages. Node.js and Express back end. MySQL for candidates, questions, translations, forms, responses, scores, role profiles, employee benchmark data and the audit log. The scoring engine is a set of pure functions, versioned, and every score stores the key version it used.

- **Roles:** candidate (private link, one attempt), hiring manager (own roles only), HR admin, assessment admin, analyst. Employee benchmark data is visible only to analyst and HR admin.
- **Question and scoring management:** draft, review, approve and retire items. An approved item is never edited in place, so past scores stay reproducible.
- **Privacy:** Malaysian personal data law applies to candidate records. Candidates see the purpose and consent text first. Retention is a setting HR controls, and a candidate's data can be exported or deleted on request.
- **Audit:** every view and change of a candidate result is logged.
- **Unproctored risk:** remote tests can be shared or coached. The profile therefore tells the interviewer which two or three items to re-ask live to confirm a high score.

## 11. Delivery plan

Ten weeks from the proposed start of 2 November 2026. Each week has an acceptance test, so progress is checked, not claimed.

| Week | Work | Accepted when |
|---|---|---|
| 1 | Job analysis, role profile, pilot gates, privacy review. | Role profile signed off by HR. Six areas, required levels and critical or trainable marks agreed. |
| 2 | Question bank draft, translation starts, data model. | Draft items for all six areas in English. Translation under way. Schema reviewed. |
| 3 | Backend foundation, scoring engine. | Scoring passes all hand-scored test sheets. Role profile stored and versioned. |
| 4 | Candidate flow. | A candidate completes the assessment end to end in each language, on phone and laptop. |
| 5 | Profiling and flag rules. | Strengths, gaps and risks generated from the role profile, with the evidence listed. |
| 6 | Hiring manager dashboard. | Manager sees a profile, compares 2 to 5 candidates, records a decision and reason. |
| 7 | Employee benchmark and access control. | Benchmark range shows with group size. Each role sees only what it is allowed to. |
| 8 | Admin, export, analytics, pilot readiness. | Item management, Excel and CSV export and item statistics work. Pilot invitations ready. |
| 9 | Pilot and usability sessions. | 20 to 30 candidates and about 10 employees complete the assessment. Findings logged. |
| 10 | Validation report, fixes, handover. | Report states what is proven and what is not. Documents delivered. Training done. |

## 12. Deliverables and handover

At the end of week 10 the company receives:

1. A working web-based candidate assessment MVP.
2. A question bank covering the six areas, with approved items and retired items kept.
3. English, Bahasa Malaysia and Mandarin versions, with the translation record.
4. A versioned scoring engine and its test sheets.
5. Capability profiles with strengths, development gaps and risk indicators, and the evidence behind each.
6. A candidate portal for phone and desktop.
7. A hiring manager dashboard with comparison, notes and a decision log.
8. The employee benchmark, as a range with group size.
9. Excel and CSV export.
10. Login, roles and access control.
11. Question and scoring management for admins.
12. A validation report stating what is proven and what is not.
13. Documents: admin guide, item-writing and translation guide, scoring specification, data dictionary, hiring manager guide on how to read the profile and what not to conclude, candidate FAQ, deployment runbook.
14. Source code, and a training session for HR and hiring managers.

## 13. Scope boundaries

**In the MVP:** the six areas, three languages, the candidate flow, automated explainable scoring, role profile, gap and risk flags, dashboard and comparison, employee benchmark range, validation and item statistics, export, access control, documentation and handover.

**Deferred, and why:**

- Automated hire or reject decisions. Not appropriate without proven validity, and a human must decide.
- Predictive modelling. It needs far more hires followed for longer than 10 weeks allows. The MVP records the outcomes that make it possible later.
- Adaptive testing that adjusts question difficulty as the candidate answers. Needs a calibrated bank first.
- Integration with a production applicant tracking system. Export covers the MVP.
- Save and resume. Included only if time permits, otherwise a post-MVP item, so the core flow is not put at risk.
- Formal psychometric certification of the test.

## 14. Risks we will not hide

| Risk | What we do |
|---|---|
| The assessment is not yet proven to predict success. | We say so, collect the outcomes that will prove or disprove it, and avoid automated rejection. |
| Small benchmark group. | Show group size, label results provisional. |
| Translation changes difficulty. | Independent translation, back-translation, cross-language item check. |
| Candidates fake self-report answers. | Forced-choice format, low weight, no solo risk flag. |
| Managers treat the profile as a pass or fail. | No single ranked score, risk indicators framed as questions to probe, decision log. |
| We are developers, not psychometricians. | We ask the company for an HR lead and, if available, an industrial and organisational psychologist to review the job analysis and item keys. If none is available, we use a published competency framework and the validation report states that keying was not reviewed by a psychologist. |

## 15. Team and relevant earlier work

| Member | Responsibility | Relevant experience |
|---|---|---|
| Muhammad Fahmi Bin Muhamad | Backend, architecture, database, scoring engine, access control | Compiler design, Node.js and Express, MySQL, REST APIs, role-based access. |
| Irfan Ali | Proposal and validation design, scoring rules, dashboard, testing | Built and deployed FatherPeng, a working system with a live board and deterministic checks, public at github.com/ponli550/FatherPeng. |
| [Name] | Frontend and candidate portal | [Experience] |
| [Name] | Question bank and role research, with HR input | [Experience] |
| [Name] | Translation review, pilot coordination, documentation | [Experience] |

The design follows habits from earlier work: rules held as data, every result traceable, and a human making the final decision. The stack matches what the backend lead already works in, so the plan does not depend on anyone learning a new framework.
