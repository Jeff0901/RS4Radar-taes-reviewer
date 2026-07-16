# TAES RS4Radar Reviewer

`taes-rs4radar-reviewer` is an author-side, pre-submission review Skill for radar and electronic-system manuscripts targeting IEEE Transactions on Aerospace and Electronic Systems (TAES).

It reviews more than English expression. The Skill checks TAES fit, radar-system closure, contribution clarity, the physical-to-mathematical modeling chain, method validity, experiment sufficiency, concern severity, and revision priority.

## Intended Use

- Review an author-owned or lab-authorized manuscript before submission.
- Review a complete manuscript or a focused section.
- Diagnose Title, Abstract, Introduction, Problem Formulation, Proposed Method, Experiments, and Conclusion.
- Apply additional range-Doppler recovery checks only when the manuscript's dominant task matches that scope.

Do not use this Skill to process an assigned confidential peer-review manuscript and manuscript writing. The Skill does not represent IEEE, TAES editors, or official reviewers, and it does not predict acceptance. Both this skill and AI agents can make mistakes, please maintain an objective and rigorous attitude towards academic researching, writing, and reviewing.

## Installation

Tell your agent:

```text
Installing the skill from URL:https://github.com/Jeff0901/RS4Radar-taes-reviewer
```

## Usage

Invoke the Skill explicitly:

```text
Use $taes-rs4radar-reviewer to assess this radar manuscript for TAES fit,
technical completeness, and revision priorities.
```

The review output contains:

1. Overall TAES Readiness
2. TAES Fit Assessment
3. Main Strengths
4. Major Concerns
5. Minor Concerns
6. Section-Level Review
7. Radar-Specific Technical Review
8. TAES-Style Writing Review
9. Prioritized Revision Plan
10. Representative Example Revisions

## Evidence Boundary

- Official requirements are separated from corpus-derived observations.
- Nonofficial patterns are labeled as `RS4Radar corpus patterns`, not TAES-wide rules.
- The RD recovery guide is a narrow secondary synthesis and must not be generalized to unrelated radar topics.
- Representative rewrites are limited to key sentences or short passages; the Skill does not rewrite an entire manuscript.

## Repository Contents

```text
SKILL.md
agents/openai.yaml
assets/templates/
references/
```

The minimal distribution excludes source PDFs, Zotero data, observation cards, construction notes, and project-specific manuscript material.

## License

MIT
