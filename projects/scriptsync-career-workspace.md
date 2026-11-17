# Scout — AI Job Search Agent

[Back to portfolio](../README.md)

Scout is a CV-aware career workspace conceived around autonomous job discovery and application assistance. Its implemented workflow combines AI reasoning with persistent state, evidence checks and human approval. Submission currently ends in a local Demo ATS record.

## From a CV to usable evidence

A server-side upload route accepts a text-based PDF. PDF.js extracts its text locally, with file-size, page-count and readable-text checks. Groq produces a structured candidate profile; schema and evidence validation check the result before persistence. The pipeline also reviews education and skill extraction for completeness.

CV-derived facts remain unconfirmed until the user confirms them. Existing confirmed facts are preserved, with conflicting information surfaced for review. Extracted text and provenance are stored locally in SQLite; the PDF binary is not retained by this workflow. Scanned-image OCR is not established.

## Discovery and suitability

Implemented adapters support **Jooble ZA** for South African searches and **Jobicy** for remote opportunities. Provider output is normalised, deduplicated and checked against location eligibility. Failures can select an explicitly labelled fictional demo provider. The manager permits one search-strategy adaptation and persists results so a page refresh does not initiate a new search.

Groq evaluates eligible opportunities against CV evidence. Validation checks evidence references and match semantics, including required versus preferred requirements. If matching fails, discovered jobs remain visible with matching unavailable. A remote label alone does not establish geographic eligibility.

## Answers, approval and submission

The Application Agent creates a role-dependent local form, fills available candidate facts, persists a missing question and pauses. Answers are classified by scope. Employer-specific answers stay with their application, while sensitive reuse requires consent.

An optional draft uses selected CV evidence and offers an extractive fallback. Draft checks validate evidence selection and basic text constraints; they do not prove that every generated sentence is accurate. The user must review the editable answer. A complete cover-letter or CV-document export is not established by this review.

Final submission requires an explicit approval action and a complete form. The implemented **DemoATSProvider** records a local timestamp and submission record. No external employer receives that submission, and no third-party ATS website is automated.

## Persistence and integration design

**Next.js, React, TypeScript, SQLite, Zod, PDF.js and Groq** support the core workflow. Candidate memory, questions, application checkpoints, opportunities and observable events persist across requests. Candidate scoping supports local separation, but does not establish a secure hosted multi-user authentication boundary.

Google OAuth, Gmail reading and Calendar integration are implemented in source. Career Monitor correlates recruitment messages with applications and tracks processed messages and calendar actions to avoid duplicates. A synthetic inbox exercises the same workflow using simulated actions. Live Google account behaviour was not exercised during this review.

## My involvement and demonstrated behaviour

Scout was developed within our university work by the ScriptSync development team. I contributed to this career application. Campus Crisis Agent is a separate project. Earlier history review supports my involvement; exact component authorship and shared starter rights remain unresolved.

Inspected tests cover synthetic PDF extraction, rejection of unsupported candidate claims, preservation of confirmed memory, provider normalisation, location checks, bounded search adaptation, matching failure recovery, answer scope and reviewable drafts. They use synthetic fixtures and substituted integrations where applicable.

Earlier portfolio preparation recorded 136 passing tests, four skipped live-provider checks and a synthetic Demo ATS browser workflow. Those results apply to the earlier prepared version. This mission inspected the current source without running the application, calling providers or submitting applications, so it does not establish that the current source passes that suite.

## Development limitations

Live provider adapters exist in code, but current credentials, service availability, production operation and real-account integration were not verified. External application submission, unrestricted autonomous applying and production readiness are not demonstrated. Source redistribution remains subject to starter and contributor rights.

[Copyright scope](../COPYRIGHT.md) · [Asset notices](../ASSET_NOTICES.md)
