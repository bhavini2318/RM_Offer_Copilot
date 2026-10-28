# Project brief for Claude Code

## What this project is

A portfolio project: a market-agnostic AI copilot for bank relationship managers (RMs). For each customer it detects money flowing to other institutions, filters campaigns by eligibility and suitability, ranks them by net new money, and generates a grounded talk track. Owner: Bhavini Sapra (product manager).

## Current stage

Discovery is done. Strategy, PRD, UX, technical design and build plan are still being written.

**Do not write application code until `docs/06-build-plan.md` exists and the owner names the milestone to build.** If asked to build before then, say which documents are missing.

## Source of truth

- `docs/` holds every approved product document. Read the relevant ones before any task.
- If a build decision conflicts with a document, stop and flag it rather than silently changing direction.
- If a decision changes during the build, update the document in the same commit.

## Product principles (non-negotiable)

1. **Suitability first.** Eligibility and suitability rules run before scoring. An unsuitable offer is never shown.
2. **Net new money.** Scoring rewards money coming from outside the bank and penalises money moving between the bank's own products (for example savings into fixed deposits).
3. **Grounded talk tracks.** The language model writes only from campaign facts passed to it. It never invents rates, fees or features, and always includes required disclosures.
4. **Human decides.** The RM always makes the final call. Every recommendation shows its reasons and is logged.
5. **One core, a rule pack per bank.** No country, regulator or currency is hard-coded in the core. Everything local lives in the rule pack.
6. **Three AI layers, rules on top.** An ML model predicts acceptance; rules decide eligibility and suitability and can never be overridden by the model; a language model writes the talk track. Every model prediction needs a plain-language reason code.

## Rule pack

Each bank configures a rule pack. The core engine reads it and never assumes a specific market.

| Setting | What the bank defines |
| --- | --- |
| Currency and formats | Currency code, number and date formats |
| Payment types for leak detection | Which recurring debit and bill payment types count as money leaving |
| Credit and eligibility | Credit score bands and eligibility rules per product |
| Suitability | Risk-profile bands, product risk ratings, hard blocks and warnings |
| Licensing | Which RM licences are needed to discuss each product type |
| Consent and data | Marketing consent and opt-out rules |
| Disclosures | Required wording per product type |
| Product catalogue | Products and campaigns, including optional Shariah-compliant variants (which use "profit rate", never "interest") |
| Languages | Talk track languages |

The demo uses a fictional sample bank with a sample rule pack.

## Data rules

- Synthetic data only. Never use or request real customer data.
- Mark every rate and campaign figure as illustrative.
- Large generated files stay out of git (see `.gitignore`); commit the generator scripts and small samples.

## Folder map

- `docs/` product documents, numbered in reading order
- `docs/04-ux/` flows and wireframes
- `data/campaigns/` campaign catalogues per market
- `data/synthetic/` generated customers and transactions
- `app/` application code

## Working rules

- Build one milestone at a time, as listed in the build plan.
- Commit after each working step with a clear message.
- Writing style for docs and UI text: plain English, short sentences, no em dashes.
