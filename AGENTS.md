# Sarros Agent Instructions

## Project context

This repository belongs to Sarros Workspace. Sarros operates Electrical, Plumbing, Hot Water, and Appliances divisions. Internal software often supports SimPRO workflows, quote intelligence, estimators, service operations, dashboards, customer/admin workflows, and operational automation.

Treat Sarros systems as business-critical internal tooling. Prioritise correctness, data integrity, maintainability, and clear staff workflows over cleverness.

## How to work in this repo

1. Inspect existing code before designing new architecture.
2. Follow current patterns unless they are clearly unsafe or broken.
3. Make small, reviewable changes.
4. Never invent API contracts, schemas, environment variables, or business rules.
5. Confirm commands from package scripts, CI config, docs, or existing conventions before relying on them.
6. Keep user-facing copy clear, professional, and in Australian English unless the repo already uses a different convention.

## Safety rules

- Do not log secrets, tokens, customer data, or sensitive operational data.
- Do not change database schemas without following the repo migration pattern.
- Do not loosen validation broadly to make an error disappear.
- Do not silently drop customer, quote, job, lead, invoice, transcript, estimator-note, or AI-summary data.
- Do not perform broad rewrites unless explicitly requested.

## Feature workflow

For new features, provide a short plan first:

- User and business outcome.
- Existing patterns found.
- Files likely to change.
- Data/API touchpoints.
- Validation plan.
- Known risks.

Build the smallest complete implementation, then validate with tests/type checks/linting where available and at least one manual scenario.

## Bugfix workflow

For bugs:

1. Capture the exact symptom.
2. Reproduce or narrow the failure.
3. Trace the entrypoint, failing code, related callers, and downstream consumers.
4. State the root cause before editing.
5. Apply the smallest safe patch.
6. Validate the fixed path and one adjacent path.

## SimPRO and quote intelligence rules

- Do not invent SimPRO field names, endpoint shapes, IDs, or relationships.
- Preserve raw source data when creating AI summaries.
- Keep AI-generated fields distinguishable from human-entered fields.
- Treat estimator notes, transcripts, pre-build items, leads, opportunities, jobs, customers, sites, and quote items as important business data.
- Handle missing external data, partial payloads, rate limits, and retryable sync failures explicitly.

## Final response format

Use this format after changes:

```md
## What changed

## Why

## Files touched

## Validation

## Remaining risks / follow-ups
```
