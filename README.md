# RM Offer Copilot

An AI copilot that helps bank relationship managers (RMs) pick the right campaign for each customer, ranked by **net new money** to the bank, filtered by **suitability**, and delivered with a **grounded, compliant talk track**.

Built as a product management portfolio project, run like a real product team: discovery, strategy, PRD, UX, technical design, build and launch.

## The problem

Banks compete hard for cheap deposits. RMs carry deposit, cross-sell and campaign targets, but choose what to pitch largely by judgement. Offers chosen this way often move money *inside* the bank (savings into fixed deposits) instead of bringing new money in, and regulators are tightening rules on mis-selling.

## The approach

1. Detect money leaving the bank (loan instalments, card bills and transfers to other institutions)
2. Filter campaigns by eligibility and suitability rules
3. Predict each customer's chance of accepting each remaining offer with a machine learning model
4. Rank by expected new money, minus internal cannibalisation
5. Explain every recommendation in plain words
6. Generate a talk track grounded only in campaign facts, with required disclosures
7. Capture the outcome to improve campaigns over time

The product is **market-agnostic**: one core engine, plus a **rule pack** each bank configures with its own regulations, compliance requirements, products, payment rails and languages. The demo runs on a fictional sample bank.

## Status

| Stage | Status | Document |
| --- | --- | --- |
| Discovery | Done | [docs/01-discovery.md](docs/01-discovery.md) |
| Strategy | Draft | [docs/02-strategy.md](docs/02-strategy.md) |
| PRD | Draft | [docs/03-prd.md](docs/03-prd.md) |
| UX | Next | docs/04-ux/ |
| Technical design | Planned | docs/05-tech-design.md |
| Build plan | Planned | docs/06-build-plan.md |
| Build | Not started | app/ |

## Note on data

All customer and transaction data in this project is synthetic. All rates and campaign figures are illustrative. The copilot supports bank staff; it does not sell or advise customers directly.
