# 🧑‍💼 Front-Line Sales Candidate Assessment MVP

![status](https://img.shields.io/badge/status-interview%20stage-orange)
![duration](https://img.shields.io/badge/duration-10%20weeks-blue)
![start](https://img.shields.io/badge/start-2%20Nov%202026-informational)
![languages](https://img.shields.io/badge/languages-EN%20%7C%20BM%20%7C%20%E4%B8%AD%E6%96%87-green)
![stack](https://img.shields.io/badge/stack-React%20%7C%20Node%20%7C%20MySQL-lightgrey)
![repo](https://img.shields.io/badge/repo-private-red)

> 🎯 **Evidence, not a verdict.** A structured, three-language assessment that shows a hiring manager each candidate's strengths, development gaps and risks. The manager still decides.

⚠️ **Status:** shortlisted for interview on 2026-10-15. **Not awarded.** Everything below is the plan if the project is awarded. Issues here are planned work, not committed work.

## 📚 What is in this repo

| 📄 File | What it is |
|---|---|
| `PROPOSAL.pdf` / `PROPOSAL.md` | The submitted proposal. **It wins over every other doc.** |
| `KICKOFF.md` | Questions for the company, week 1 workshop, calendar risks |
| `INTERVIEW_PREP.md` | Likely questions and honest answers |
| `MARKET_SCAN.md` | Existing tools and open-source options, dated 2026-10-16 |
| `VIDEO_SCRIPT.md` | Pitch video script, problem first |
| `docs/PRD.md` | Product requirements, aligned with the proposal |
| `docs/user-flows.md` | Journey diagrams |

## 🧭 How a candidate becomes a profile

```mermaid
flowchart LR
    A[📨 Private link] --> B[🌐 Pick language]
    B --> C[✍️ Six capability areas]
    C --> D[🧮 Plain-rule scoring]
    D --> E[📊 Profile vs role profile]
    E --> F[🧑‍💼 Hiring manager decides]
```

## 🚦 How a gap becomes a flag

The company agrees a **role profile** first: a required level per area, marked critical or trainable.

```mermaid
flowchart TD
    A[Candidate level vs required level] --> B{At or above?}
    B -->|Yes| C[💪 Strength]
    B -->|No| D{Critical area, or more than one level below?}
    D -->|Yes| E[🚩 Risk indicator: look closer]
    D -->|No| F[🌱 Development gap: trainable]
```

A risk indicator is a prompt to look closer. It is never a rejection.

## 🗓️ Plan if awarded

```mermaid
gantt
    title Ten weeks from 2 November 2026
    dateFormat YYYY-MM-DD
    axisFormat %d %b
    section Setup
    W1 Role profile and privacy        :w1, 2026-11-02, 7d
    W2 Item bank and data model        :w2, 2026-11-09, 7d
    section Build
    W3 Scoring engine                  :w3, 2026-11-16, 7d
    W4 Candidate flow three languages  :w4, 2026-11-23, 7d
    W5 Profiling and flags (light)     :w5, 2026-11-30, 7d
    W6 Hiring manager dashboard        :w6, 2026-12-07, 7d
    W7 Employee benchmark and access   :w7, 2026-12-14, 7d
    W8 Admin and export                :w8, 2026-12-21, 7d
    section Prove it
    W9 Pilot over year-end (risk)      :crit, w9, 2026-12-28, 7d
    W10 Validation report and handover :w10, 2027-01-04, 7d
    section Dates to watch
    Codex hackathon                    :milestone, 2026-12-05, 0d
```

⚠️ Week 9 is the worst week of the year for a pilot. The plan is to run employee sessions in week 7 and start the candidate pilot in week 8. See `KICKOFF.md`.

## ✅ What we promise, and what we do not

| ✅ We promise | 🚫 We do not claim |
|---|---|
| 100% scoring accuracy on hand-scored sheets | That a score predicts job success |
| Every flag traces to the questions behind it | An automated hire or reject |
| Three reviewed languages, difficulty checked across them | That three languages are equal before the check runs |
| Benchmark shown as a range with group size | A correlation from about 10 employees |
| A validation report that says what is not proven | Psychometric certification |

## 🔄 How work moves

```mermaid
flowchart LR
    A[📝 Issue in a weekly milestone] --> B[🌿 Branch off main]
    B --> C[🔧 Commit]
    C --> D[🔀 Pull request: Closes #n]
    D --> E[✅ Tests pass]
    E --> F[🚀 Squash merge, delete branch]
```

1. Every piece of work is a GitHub issue, attached to a weekly milestone.
2. Branch from `main`: `<type>/<issue>-<short-desc>`, for example `feat/10-scoring-engine`. Types: feat, fix, docs, chore.
3. Open a pull request that says `Closes #<issue>`. One issue per pull request.
4. Merge with squash once tests pass. Delete the branch.
5. No direct pushes to `main` after the first commit.
6. A change to someone else's document goes in a pull request they review before it merges.

## 🔒 Never commit

- 🙅 Real candidate or employee data, in any form, including screenshots.
- 🔑 Credentials or `.env` files.
- 🎬 Videos.
- 🧪 Test data must be synthetic.
