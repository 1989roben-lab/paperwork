---
name: paperwork
description: Generate, normalize, and improve MongoDB internal paperwork and manager-ready business writing. Use when the user asks for company paperwork, MongoDB paperwork, internal submission text, approval or justification language, workload writeups, bilingual Chinese/English professional wording, or fields such as New Workload, Application Overview, Discovery Notes, Use Case, Next Steps, Why Anything, Why MongoDB, Why Now, NARR, close date, or customer/workload descriptions.
---

# Paperwork

## Workflow

Use this skill as the general entry point for MongoDB company paperwork. Default to MongoDB internal context and produce concise, professional, manager-ready writing.

1. Classify the paperwork type using `references/routing.md`.
2. Load `references/style-guide.md` for shared language and tone rules.
3. Load the specific reference for the classified paperwork type.
4. If the type is ambiguous, ask only for the missing decision that changes the output.
5. If the type is new, complete the current case first, then suggest adding a new reference file that captures the reusable pattern.

## Supported Paperwork

- MongoDB New Workload paperwork: load `references/mongodb-new-workload.md`.

## Expansion Pattern

Add one reference file per new paperwork type. Keep `SKILL.md` as a router and lightweight operating guide; put templates, field rules, examples, and edge cases in references.

Each new paperwork reference should include:

- Purpose and trigger phrases
- Required inputs
- Optional inputs
- Output fields
- Tone and length rules
- Decision logic
- Example input
- Example output
- Questions to ask when critical information is missing

Update `references/routing.md` when a new paperwork type is added.
