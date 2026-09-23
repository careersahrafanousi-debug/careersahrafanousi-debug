## Sahra Fanousi

Healthcare appeals analyst in Texas. I work on the operations side of a payer —
appeals intake through adjudication — and I build the SQL and reporting that
operations leaders use to decide where to put people and money.

Finishing an M.S. in Business Analytics and AI (May 2027).
Open to remote analyst and BI roles.

---

### Portfolio

Nine end-to-end projects on **fully synthetic** data — five in healthcare
operations, four deliberately outside it. Each one ships runnable code, a
data-quality gate that excludes bad records instead of quietly fixing them, SQL
analysis, a live dashboard, and the business-analysis documents that make a
finding implementable — charter, requirements, process maps, KPI definitions,
UAT test cases.

**[See all nine on one page →](https://careersahrafanousi-debug.github.io/)**

### Healthcare operations

#### [Appeals Friction Radar](https://github.com/careersahrafanousi-debug/appeals-friction-radar)
*Where does an appeal actually lose its days?*

Urgent appeals take **15.5 days against a 7-day target** while standard appeals take 14.8 against 30. The queue with the tightest deadline is the one that misses it — SLA compliance collapses to **16.5%**. Built on 3,966 appeals and 35,443 workflow events, using SQL window functions to measure stage dwell time.

[Live dashboard](https://careersahrafanousi-debug.github.io/appeals-friction-radar/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/appeals-friction-radar)

#### [Denial Prevention Simulator](https://github.com/careersahrafanousi-debug/denial-prevention-simulator)
*Which denials were preventable before the claim went out?*

Of **$5.42M denied** across 11,967 claims, **$4.48M — 82.7% of denied dollars** — traces to five causes that are checkable at submission. Turned that into a pre-submission risk queue that scores unsubmitted claims before they leave.

[Live dashboard](https://careersahrafanousi-debug.github.io/denial-prevention-simulator/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/denial-prevention-simulator)

#### [Case Assignment Fairness](https://github.com/careersahrafanousi-debug/case-assignment-fairness)
*Are some teams slower, or are they handed harder work?*

Team SLA compliance ranged from **25.9% to 84.2%**, which looked like a performance gap. It was routing: 14% of cases — Authorization Review, averaging 79 hours against a 48-hour target — produced **41% of all lateness**. This reversed the stakeholder's starting hypothesis, across 15,908 cases and 35 analysts.

[Live dashboard](https://careersahrafanousi-debug.github.io/case-assignment-fairness/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/case-assignment-fairness)

#### [KPI Trust Ledger](https://github.com/careersahrafanousi-debug/kpi-trust-ledger)
*Why does the same KPI have four different values?*

Six appeals KPIs reconciled across three source systems. Backlog alone reported as **423 / 611 / 509 / 211** depending on which system you asked. Attributed every variance, then **certified 2 of 6** for leadership use and documented exactly why the other four could not be.

[Live dashboard](https://careersahrafanousi-debug.github.io/kpi-trust-ledger/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/kpi-trust-ledger)

#### [Capacity-to-Deadline Optimizer](https://github.com/careersahrafanousi-debug/capacity-to-deadline-optimizer)
*Can cancelled slots be refilled from the waitlist in time?*

No-show rate is **5.3% with a reminder and 15.7% without**. Found **507 refillable** cancelled slots and ranked 1,786 waitlisted patients against them with a match score, across 13,951 appointments and 22 providers.

[Live dashboard](https://careersahrafanousi-debug.github.io/capacity-to-deadline-optimizer/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/capacity-to-deadline-optimizer)

---

### Beyond healthcare

The same method applied to four domains I do not work in, because it is a
method rather than a domain: establish what the data can actually support,
compare against the process already in place, and say where the answer runs out.

#### [Subscription Churn and Retention](https://github.com/careersahrafanousi-debug/subscription-churn-retention)
*Which acquisition channel keeps customers, and is that the channel's fault?*

Month-6 retention ranged from **51.2% (Paid Social) to 78.3% (Member Referral)** — a 27-point spread that looked like a channel-quality story. Standardising on discount mix narrows it to **20.3 points**, so about a quarter of the gap is a discounting decision rather than a channel. 9,000 customers, 67,784 ledger rows, 24 months; GRR 89.7%, NRR 96.2%.

[Live dashboard](https://careersahrafanousi-debug.github.io/subscription-churn-retention/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/subscription-churn-retention)

#### [Funnel Conversion and Experiment Readout](https://github.com/careersahrafanousi-debug/funnel-experiment-readout)
*The A/B test won by 4.28 points. Should it ship?*

Ship it to desktop, not to mobile — and not because mobile lost. The **+4.28pp** headline (95% CI 2.35 to 6.22, p < 0.001) is a **+8.81pp desktop win** diluted by a mobile result of +0.43pp that was never powered to detect less than 4.09pp. Mobile is **inconclusive, not null**, which is a different decision. The sample-ratio check passes, no guardrail is breached, and a peek would have called significance on **27 of 28 days**.

[Live dashboard](https://careersahrafanousi-debug.github.io/funnel-experiment-readout/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/funnel-experiment-readout)

#### [Chargeback Screening](https://github.com/careersahrafanousi-debug/chargeback-screening)
*The chargeback rate looks like it fell 74%. Did it?*

No — disputes arrive up to 120 days late, so recent weeks only look clean. Mature weeks average **1.47%** against the **0.38%** the current report shows. Once label maturity is respected, a ranked queue catches **123 chargebacks against the live rule engine's 67** at identical analyst cost (McNemar χ² 29.66, **p < 0.001**), and one of the five live rules turns out to have a lift of 1.04 — no better than random. The threshold, though, should not move: bootstrapping puts the cost optimum anywhere between 1.75% and 7.50%. 226,585 transactions; logistic regression, ROC AUC, average precision, McNemar and the bootstrap all implemented in NumPy so every statistic can be read as code.

[Live dashboard](https://careersahrafanousi-debug.github.io/chargeback-screening/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/chargeback-screening)

#### [Store P&L Variance](https://github.com/careersahrafanousi-debug/store-pnl-variance)
*Sales beat plan by 2.18%. Why did four-wall profit miss by $371k?*

A price-volume-mix bridge for a fictional twelve-store coffee chain that **reconciles to the cent** in all 96 store-months — the build stops if it does not. Deeper discounting (**−$206,939**), a low-margin new product (**−$115,469** mix) and unproductive labor hours (**−$155,613**) more than consumed a **+$291,230** volume gain. Three stores lose money for three different reasons: Midtown is a schedule (positive at standard labor), Harbor Point is traffic (needs 24.1% more to break even), and Eastgate is only allocated overhead — closing it would **cut company profit by $144,817**. A staggered price rollout, read with difference-in-differences, raised net sales **2.57%** (95% CI 1.69 to 3.46, exact permutation p = 0.0022).

[Live dashboard](https://careersahrafanousi-debug.github.io/store-pnl-variance/dashboard/) · [Code and docs](https://github.com/careersahrafanousi-debug/store-pnl-variance)

---

### How the projects are built

Every repo runs the same way from a clean clone. Script names differ slightly where
a project needs an extra step — reconciliation, experiment statistics, a model fit —
but the shape is always the same:

```bash
python src/generate_data.py     # synthetic source files, fixed seed
python src/clean_validate.py    # data-quality gate; failures excluded, not repaired
python src/load_sqlite.py       # star schema
python src/model.py             # statistics, written back as queryable tables
python src/build_dashboard.py   # interactive HTML
python src/build_bi_assets.py   # Excel, Tableau, Power BI, charts
```

The last step is the part worth a conversation. One file of SQL
(`dashboard/dashboard_config.json`) is the single definition of every number,
and one generator renders it into five outputs — an interactive dashboard, an
Excel workbook with native charts, a Tableau `.twb`, a Power BI semantic model
in TMDL with DAX measures, and static PNG charts. Change a query and every
artifact changes together, so the dashboard and the workbook can't drift apart.

There are no `.pbix` or `.twbx` files in these repos, deliberately. A binary
workbook can't be reviewed in a pull request, can't be diffed, can't be opened
without a licence, and carries its own stale copy of the data. The Tableau XML
and the Power BI TMDL are committed as text instead.

---

### Tools

**SQL** — window functions, CTEs, star-schema modeling, reconciliation across systems
**Statistics** — hypothesis testing (z, χ², McNemar), confidence intervals, bootstrap, power and minimum detectable effect, logistic regression and calibration
**Power BI** — DAX measures, TMDL semantic models
**Tableau** · **Excel** — pivot tables, native chart objects via openpyxl
**Python** — pandas, NumPy, matplotlib, openpyxl, sqlite3
**Business analysis** — requirements elicitation, current/future-state process maps, KPI catalogs, UAT

---

### A note on the data

All nine projects use fully synthetic data generated from a fixed seed by the
scripts in each repository. They do not use employer data, patient information, protected health
information, or confidential business information. The scenarios are modeled on
real operational patterns; the records are not real.

---

Reach me at careersahrafanousi@gmail.com
