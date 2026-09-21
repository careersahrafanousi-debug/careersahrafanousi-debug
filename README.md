## Sahra Fanousi

Healthcare appeals analyst in Texas. I work on the operations side of a payer —
appeals intake through adjudication — and I build the SQL and reporting that
operations leaders use to decide where to put people and money.

Finishing an M.S. in Business Analytics and AI (May 2027).
Open to remote analyst and BI roles.

---

### Portfolio

Five end-to-end projects on **fully synthetic** healthcare data. Each one ships
runnable code, a data-quality gate that excludes bad records instead of quietly
fixing them, SQL analysis, a live dashboard, and the business-analysis documents
that make a finding implementable — charter, requirements, process maps, KPI
definitions, UAT test cases.

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

### How the projects are built

Every repo runs the same way, from a clean clone:

```bash
python src/generate_data.py    # synthetic source files
python src/dq_checks.py        # data-quality gate
python src/load_sqlite.py      # star schema
python src/build_dashboard.py  # interactive HTML
python src/build_bi_assets.py  # Excel, Tableau, Power BI, charts
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
**Power BI** — DAX measures, TMDL semantic models
**Tableau** · **Excel** — pivot tables, native chart objects via openpyxl
**Python** — pandas, matplotlib, openpyxl, sqlite3
**Business analysis** — requirements elicitation, current/future-state process maps, KPI catalogs, UAT

---

### A note on the data

All five projects use fully synthetic data generated by the scripts in each
repository. They do not use employer data, patient information, protected health
information, or confidential business information. The scenarios are modeled on
real operational patterns; the records are not real.

---

Reach me at careersahrafanousi@gmail.com
