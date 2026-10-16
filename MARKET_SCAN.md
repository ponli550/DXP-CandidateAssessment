# Market and open-source scan

Date: 2026-10-16. Shallow web search, not a due-diligence review. "Not found" means not found, not "does not exist". Pricing was not checked, so quote none.

## Commercial tools

| Tool | What we saw | Gap in what we saw |
|---|---|---|
| Mercer Mettl | 400+ pre-built tests incl. sales potential and retail sales. Simplified Mandarin versions listed. | "Bahasa" listed, but the sales tests shown are Indonesian. Bahasa Malaysia not confirmed. |
| TestGorilla | Numerical reasoning, situational judgement and personality, built around business scenarios. | No language details found. |
| TestnHire | Situational judgement tests. Hosted. | Not open source. |
| IKM | Sales assessment localised for Malaysia. Basic maths for retail sales. | Languages and scoring approach not checked. |
| Hipeople | Mandarin basic proficiency test for sales and service roles. | Tests language, not sales capability. |
| SHL, Criteria Corp, Hogan | Nothing confirmed. | Not checked directly. |

## Open source

- No open-source hiring-assessment product found with situational judgement tests, a role profile and three languages.
- Eval (openeval/eval) assesses coding through open-source issues. Not a match.
- General exam engines: TCExam (AGPL-3.0), TAO from Open Assessment Technologies (GPL-2.0, QTI and LTI standards), QST (GPLv2, activity unclear).
- Analysis libraries: mirt (R) and girth (Python) for item response theory and differential item functioning.

## What follows for us

1. The category is not new. Do not claim "first". Our angle is the combination: an agreed role profile, gap versus risk flags, three reviewed languages including Bahasa Malaysia, and honest validation limits.
2. Do not fork a copyleft exam engine. The licence could carry over to the handover code. Build fresh.
3. Use mirt or girth only in offline validation scripts, after checking each licence.
4. Unverified, from memory: IPIP personality items are public domain, and O*NET data is free with attribution. Verify before relying on either.

## Sources

- https://mettl.com/en-gb/core-functions/sales-tests/
- https://mercermettl.com/skills-assessment-test/
- https://www.testgorilla.com/test-library/cognitive-ability-tests/numerical-reasoning/facts/
- https://webcatalog.io/en/apps/testnhire
- https://ikmnet.com/assessments/sales
- https://hipeople.io/assessment-library/mandarin-basic-test
- https://github.com/openeval/eval
- https://github.com/tecnickcom/tcexam
- https://github.com/oat-sa
- https://github.com/bobb34/QST
- https://rdrr.io/cran/mirt/f/README.md
- https://pypi.org/project/girth/0.7.5
