# Veruschka ILS Data Hub — frontend start

This is a local, reviewable frontend preview based on the revised **IDS Blueprint** (28 October 2026). It is intended for deployment to Vercel after Tanya creates and shares the client-owned Supabase, GitHub and Vercel projects under `goal@theveruschkafoundation.org`. Do not create parallel infrastructure.

## Current state

- Three dashboard pages cover the 13 KQs currently in the live KQ sheet.
- The data collection page shows the proposed form flows.
- Role switching previews the navigation for Faculty, Programme Associate, Programme Manager and Leadership.
- **All chart values are illustrative sample data.** No Veruschka records are read, changed or saved.
- Form fields and Save are disabled until Tanya's Supabase project, schema and row-level access policies are verified.
- Role switching in this preview is a design aid, **not access control**.
- The current colour direction follows [Veruschka Foundation's website](https://theveruschkafoundation.org/): white surfaces, navy text/navigation, and bright blue accents. The website is a reference until the client provides formal brand guidance.
- Every top-level dashboard scorecard, chart, summary, and table is numbered by page (1.x, 2.x, 3.x). The monthly lead pipeline uses one blue because its columns are one metric over time. Ranked comparisons are sorted from highest to lowest.

## Run locally

```sh
npm ci
npm run dev
```

## Required to connect real data

1. Wait for Tanya's Veruschka Supabase project ID and access details under the client-owned `goal@theveruschkafoundation.org` setup. The currently connected Supabase account only exposes an unrelated HFH project.
2. Share Tanya's current schema, migrations, table/column meanings, status values and anonymised sample records.
3. Agree the source table(s), filters and denominator for each metric in the blueprint. The blueprint currently names conceptual records, not actual tables.
4. Agree which users can read and change which records, then implement and test Supabase Auth and RLS. Programme Associate has read-only programme access in the revised blueprint.
5. Confirm the comments in the blueprint: lead-to-enrolment prefill, direct enrolment route and optional exit field in enrolment.
6. Confirm the remaining unresolved rules in the blueprint, especially attendance, grade thresholds and IFSP review timing.
7. Get the client-owned GitHub repository and Vercel project details from Tanya, then configure deployment there. Only the Supabase URL and **publishable** key belong in browser configuration. Never use a secret/service-role key in the frontend.

## Confirmed dashboard interpretation

The KQ sheet has separate KQ04 (batch fill) and KQ05 (batches and unique learners). The user confirmed on 28 October 2026 that one combined batch section should answer both questions while retaining both KQ IDs. The preview follows this structure.
