# Consumer Complaint Performance, Discrepancy Investigation & Decision Analytics

**A business-focused analysis of 482,074 CFPB consumer complaints received in 2025**  
**Scope:** Checking or savings accounts, credit cards, debt collection, and mortgages  
**Source:** [Consumer Financial Protection Bureau — Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)

> **Reading guide.** This report describes the observed complaint records, tests competing explanations for unusual patterns, and evaluates conditional improvement scenarios. It is not an assessment of any individual institution's internal operations. “Untimely” means the CFPB dataset records `Timely response? = No`; it does not independently establish why a complaint was late, whether the underlying consumer allegation was valid, or whether the record captures the complete operational context.

## Executive summary

The principal business finding is **concentration, not merely volume**. Across 482,074 complaints, 9,523 were marked as untimely, an overall rate of **1.98%**. Debt collection accounted for **283,204 complaints (58.7%)**, but **8,196 untimely complaints (86.1%)**. Its **2.89%** untimely rate was materially above the other analyzed product categories. In practical terms, a portfolio-wide improvement strategy will have the largest arithmetic effect when it addresses the product that generates most of the recorded untimely cases. This is a prioritization signal, not evidence that a specific operational intervention will succeed.

Three additional findings change how performance should be interpreted. **First**, monthly volume and response timeliness did not move together: January produced the most complaints (**53,474**), whereas April recorded the highest untimely rate (**2.61%**). **Second**, a deep investigation of **CCS Financial Services, Inc.**, within debt collection, found a striking drop in its recorded untimely rate from **58.24% (January–August)** to **2.64% (September–December)**. Decomposition showed that changing issue composition did **not** explain the decline; the dominant movement occurred within issue categories. **Third**, apparent geographic underperformance partly reflects the mix of companies generating the complaints: excluding CCS reduces Georgia's benchmark-adjusted excess untimely cases from **275.41** to **144.27**, a **47.6% decrease**.

A decision model translates these observations into measurable *conditional* outcomes. Under a specified strong-improvement scenario spanning all four products, modeled untimely cases decrease from **9,523** to approximately **4,896**—about **4,627 fewer cases (48.6%)** at unchanged complaint volumes. Separately, a 10,000-run historical-pattern simulation gives a mean of **9,541** untimely cases and a **13.18%** modeled probability of exceeding a hypothetical **10,000-case** threshold. These are decision-support illustrations based on assumptions and historical patterns—not forecasts or validated causal effects.

**Business conclusion:** prioritize evidence-led review of the debt-collection response process, investigate abrupt changes before attributing causes, and use impact-adjusted metrics alongside raw rates to determine where a closer company-level investigation is warranted.

## 1 | The business question: where does recorded response risk concentrate?

Complaint volume alone is an incomplete performance measure. A high-volume category may have a low rate of recorded untimeliness; a smaller category may have a high rate but contribute little to the total number of late responses. The analysis therefore evaluates **volume**, **untimely-response rate**, and **absolute untimely cases** together.

### Product performance in 2025

![Performance overview — complaint volume, response timeliness and product-level comparisons](/images/1_performance_overview.png)

*Figure — Performance overview — complaint volume, response timeliness and product-level comparisons.*

| Financial product | Complaints | Untimely complaints | Untimely rate |
|---|---:|---:|---:|
| Debt collection | 283,204 | 8,196 | 2.89% |
| Credit card | 89,978 | 345 | 0.38% |
| Checking or savings account | 84,195 | 609 | 0.72% |
| Mortgage | 24,697 | 373 | 1.51% |
| **Total** | **482,074** | **9,523** | **1.98%** |

**What the pattern reveals.** Debt collection's share of untimely complaints (**86.1%**) is considerably larger than its share of complaint volume (**58.7%**). The concentration is not simply a by-product of complaint volume; the category also has the highest rate among the four analyzed products. Mortgage has a higher rate than checking/savings and credit cards, but a much smaller absolute untimely burden. These distinctions matter when the business objective is to reduce the *number* of delayed responses rather than only to rank categories by rate.

**Decision implication.** Debt collection should receive the first diagnostic review, while lower-volume products should not be ignored: operational significance depends on the metric and on the feasibility and cost of a proposed intervention.

## 2 | Monthly patterns: peak activity is not peak untimeliness

The monthly view reveals different rhythms for demand and response status.

![Monthly performance — complaint volumes, untimely rates and changes over time](/images/2_Monthly%20Performance%20Analysis.png)

*Figure — Monthly performance — complaint volumes, untimely rates and changes over time.*

| Month | Complaints | Untimely rate |
|---|---:|---:|
| January | 53,474 | 1.39% |
| February | 30,451 | 1.95% |
| March | 33,518 | 2.38% |
| April | 34,276 | **2.61%** |
| May | 36,837 | 2.10% |
| June | 36,684 | 2.04% |
| July | 41,553 | 1.64% |
| August | 42,096 | 2.02% |
| September | 43,482 | 1.55% |
| October | 41,359 | 1.95% |
| November | 40,863 | 2.31% |
| December | 47,481 | 2.14% |

**Volume observation.** January was the highest-volume month, despite having one of the lowest rates of untimely responses. Complaint volume then fell **43.05%** in February. It rebounded later in the year, with December reaching **47,481** complaints, **16.20%** higher than November.

**Timeliness observation.** April's **2.61%** rate was the highest, even though April volume was far below January's. This difference cautions against using raw complaint counts as a proxy for response quality.

**The January exception.** Within *checking or savings accounts*, **9,907 complaints** were recorded during **January 15–18**. Two institutions represented **8,563 (86.43%)** of those complaints: **Navy Federal Credit Union (4,417)** and **Capital One Financial Corporation (4,146)**. This is strong evidence of a concentrated reporting or complaint-volume episode; it is **not** enough to conclude that the underlying cause was a service outage, operational failure, or erroneous record. Any account of the January peak should acknowledge this concentration rather than imply a broad, evenly distributed surge.

**Decision implication.** Review periods of unusual activity by date, product and company before allocating resources based on aggregate monthly peaks. Monitor rates and volumes as separate measures.

## 3 | Issue-level patterns: the type of problem matters

The issue analysis helps distinguish the most common consumer-reported problems from those with the highest recorded late-response rates.

![Issue analysis — complaint topics, frequency and timeliness differences](/images/4_Issue_Analysis.png)

*Figure — Issue analysis — complaint topics, frequency and timeliness differences.*

| Selected issue | Complaints | Untimely complaints | Untimely rate |
|---|---:|---:|---:|
| Attempts to collect debt not owed | 115,682 | 2,989 | 2.58% |
| Written notification about debt | 64,049 | 1,181 | 1.84% |
| Took or threatened to take negative or legal action | 48,578 | 2,182 | 4.49% |
| Managing an account | 44,959 | 363 | 0.81% |
| False statements or representation | 38,461 | 1,261 | 3.28% |
| Communication tactics | 9,519 | 361 | 3.79% |

**What stands out.** “Attempts to collect debt not owed” was the largest listed issue category by volume, but “Took or threatened to take negative or legal action” had a higher untimely rate (**4.49%**) and contributed **2,182** untimely cases. The latter is an example of how a somewhat smaller segment can have substantial *rate and count* significance. “Communication tactics” also had a relatively high untimely rate (**3.79%**) despite a much smaller volume.

**Interpretive boundary.** CFPB issue categories describe reported complaint topics, not independently established violations. These comparisons point to useful investigative segments; they cannot, on their own, establish why companies responded late.

## 4 | Company-level investigation: explaining the CCS shift

![Company analysis — variation in complaint volumes and response outcomes by company](/images/3_Company_Analysis.png)

*Figure — Company analysis — variation in complaint volumes and response outcomes by company.*

A particularly consequential outlier emerges when companies are compared within **debt collection**. Among the high-volume companies shown in the workbook, **CCS Financial Services, Inc.** had **6,450 debt-collection complaints**, of which **2,259 (35.02%)** were recorded as untimely. That annual average obscures a dramatic change over the year.

### A large break between two periods

![CCS discrepancy investigation — response-rate break, evidence and decomposition](/images/6_Discrepancy_Investigation.png)

*Figure — CCS discrepancy investigation — response-rate break, evidence and decomposition.*

| CCS — debt collection | Jan–Aug 2025 | Sep–Dec 2025 |
|---|---:|---:|
| Total complaints | 3,757 | 2,693 |
| Untimely complaints | 2,188 | 71 |
| Untimely rate | **58.24%** | **2.64%** |

The rate fell by **55.60 percentage points**, a **95.47% relative reduction** from the earlier rate. A two-proportion test in the workbook yields **Z = 46.16, p < 0.001**, indicating a large statistical difference between the recorded periods under the test's assumptions. Statistical significance does **not** determine the cause of the change.

### Competing explanation: did the issue mix simply change?

The investigation decomposed the observed change into a **composition (mix) effect** and a **within-issue response-rate effect**:

| Component | Contribution to rate change |
|---|---:|
| Change attributable to issue mix | **+0.45 pp** |
| Change attributable to within-issue rates | **−56.05 pp** |
| Net observed change | **−55.60 pp** |

The mix-only counterfactual is approximately **58.69%**, slightly *above* the early-period actual rate of **58.24%**. A changed distribution of complaint issues therefore cannot explain the decline. Instead, recorded untimeliness fell **within all seven investigated issue categories**. The workbook also tests both recorded company response classifications, finding declines within each.

**What this establishes:** the recorded rate change is real in the analyzed extract and is not explained by the measured issue-mix shift. **What it does not establish:** whether the change resulted from a process improvement, a response-classification change, a reporting-channel difference, a business rule change, or another unobserved factor. The period split was identified after viewing the data, so it should be interpreted as an exploratory investigation rather than a preregistered causal test.

**Suggested business follow-up:** reconcile response-status definitions across periods, check reporting and submission workflows, examine operational or vendor changes, and confirm the pattern using internal process records before claiming a successful intervention.

## 5 | Screening beyond one company: three additional anomalies

The workbook documents a **curated discrepancy screen**, extending the investigation beyond CCS. These cases were identified through segmentation and then checked against the data; they do not represent an exhaustive algorithmic scan of every company.

| Screened pattern | Verified evidence | Business interpretation / next question |
|---|---|---|
| Servicer under contract with Federal Student Aid | **651 of 651** complaints marked untimely; **59.29%** occurred in Q4 | Why is the rate consistently 100%? Review response records, channel and status definitions before inferring an operational cause. |
| Rent Recovery Solutions | Jan–May **0%** untimely; Oct–Dec **100%**; **575 complaints** in the annual screening cohort | Was there a change in response workflow, reporting, or complaint composition? The extremes warrant targeted reconciliation. |
| January checking/savings concentration | **8,563 of 9,907 (86.43%)** complaints on Jan 15–18 linked to Navy Federal and Capital One | Is the episode attributable to a specific event or reporting concentration? The dataset alone cannot answer. |

This screening layer matters because it makes the investigative workflow explicit: **detect a disproportionate or abrupt pattern → verify the numerator and denominator → test competing explanations → decide what additional evidence is needed**. A flagged anomaly is a candidate for investigation, not necessarily a data error or evidence of poor practice.

## 6 | Geographic patterns: an impact measure, with an important qualification

A geographic view compares complaints attributed to the **50 U.S. states**, rather than treating all geographic codes as comparable. The state-only benchmark includes **477,871 complaints** and **9,451 untimely cases**, or **1.98%**. This benchmark excludes Washington, DC and other non-state jurisdictions; records with missing geography remain in the broader overall dataset.

![Geographic analysis — state-level rate map, excess cases and geographic priorities](/images/5_Geographic_Analysis.png)

*Figure — Geographic analysis — state-level rate map, excess cases and geographic priorities.*

Three different rankings answer different questions:

- **Highest volume:** Texas — **75,632 complaints**.
- **Highest untimely rate:** North Dakota — **6.35%**, but only **28 untimely cases among 441 complaints**.
- **Highest excess untimely cases against the 50-state benchmark:** Georgia — **+275.41**.

The geographic **excess-case** calculation compares observed untimely cases with the number expected if the state had the pooled 50-state rate: `observed untimely − state volume × benchmark rate`. Unlike a raw rate ranking, it incorporates the size of the complaint population. It is a descriptive benchmark, not a causal estimate of geographic performance.

| State | Complaints | Untimely cases | Untimely rate | Excess cases vs 50-state benchmark |
|---|---:|---:|---:|---:|
| Georgia | 33,907 | 946 | 2.79% | **+275.41** |
| North Carolina | 17,466 | 433 | 2.48% | **+87.57** |
| Florida | 51,360 | 1,088 | 2.12% | **+72.24** |
| Louisiana | 9,341 | 231 | 2.47% | **+46.26** |
| Arizona | 10,850 | 255 | 2.35% | **+40.42** |

### The company-mix correction changes the interpretation

Of Georgia's **946** untimely cases, **296 (31.29%)** were associated with **CCS Financial Services**. When CCS is excluded from both Georgia's observed cases and the benchmark population, Georgia's calculated excess falls from **+275.41 to +144.27**—a **47.6% reduction**. Geography is therefore partly reflecting **which companies are represented in each state**. Product composition is another potential confounder.

**Decision implication.** Use the map to locate concentrations of affected consumers and identify where to investigate companies and product mix. Do **not** recommend that a U.S. state “improve its complaint response performance”: companies, not states, answer CFPB complaints.

## 7 | Decision analysis: convert observed gaps into explicit scenarios

Descriptive findings become more useful when stakeholders can see the implications of a defined assumption. The workbook compares the actual baseline with hypothetical reductions in untimely response rates at the observed 2025 complaint volumes.

### Portfolio-wide scenario comparison

![Baseline and what-if model — modeled changes in annual untimely complaints](/images/7_%20Baseline%20%26%20What-If%20Scenario%20Model.png)

*Figure — Baseline and what-if model — modeled changes in annual untimely complaints.*

| Scenario | Modeled untimely cases | Cases avoided vs observed 2025 |
|---|---:|---:|
| Observed baseline | **9,523** | — |
| Moderate portfolio improvement | **≈6,602** | **≈2,921** |
| Strong portfolio improvement | **≈4,896** | **≈4,627** |

The strong case corresponds to a **48.6%** modeled reduction in untimely cases. Under that scenario, debt collection contributes approximately **3,948 of the 4,627** modeled avoided cases (**85.3%**), again reinforcing its numerical importance to the overall portfolio.

**These are conditional scenarios.** The improved response rates are assumed inputs, not predictions derived from an intervention model. The table communicates the *potential arithmetic payoff if those rates were attained*, not the likelihood or cost of attaining them.

### A decision target for debt collection

![Sensitivity analysis — two-variable scenario comparison](/images/7_Sensitivity%20Analysis%20-%20Two-Variable%20Data%20Table.png)

*Figure — Sensitivity analysis — two-variable scenario comparison.*

![Goal Seek — required improvement to meet the specified target](/images/7_Goal%20Seek%20-%20Required%20Improvement%20Analysis.png)

*Figure — Goal Seek — required improvement to meet the specified target.*

The workbook also frames a reverse question: at the same annual debt-collection complaint volume (**283,204**), what untimely rate would correspond to a target of **5,000** untimely cases rather than **8,196**?

The required rate is **approximately 1.77%**, a **1.13-percentage-point** reduction from the observed **2.89%**; that is a target of **3,196 fewer cases**. This provides a transparent planning benchmark, without claiming that the target is feasible or cost-effective.

## 8 | Risk simulation: how variable might the outcome be?

A deterministic scenario reports a single expected number under a fixed assumption. The Monte Carlo analysis instead asks how recorded annual untimely cases could vary if **historical month-level patterns** recurred in different combinations.

The model uses **10,000 seeded simulation runs**. It pairs monthly complaint volume and response rates during historical resampling, while translating outcomes to the fixed 2025 annual product volumes. This preserves important structure that would be lost if volumes and rates were drawn independently. It is a historical-pattern risk illustration, not a time-series forecast.

### Current-condition distribution

![Monte Carlo outcomes — modeled distribution and illustrative 10,000-case threshold](/images/8_SIMULATED%20OUTCOME%20DISTRIBUTION%20VISUALIZATION.png)

*Figure — Monte Carlo outcomes — modeled distribution and illustrative 10,000-case threshold.*

| Measure | Simulated result |
|---|---:|
| Observed 2025 untimely cases | **9,523** |
| Simulated mean | **9,541** |
| Standard deviation | **408** |
| 5th percentile | **8,883** |
| 95th percentile | **10,230** |
| Probability of exceeding 10,000 cases | **13.18%** |

The **10,000-case** threshold is an **illustrative decision threshold**, not an established regulatory limit or service-level agreement. The modeled **13.18%** exceedance probability is conditional on the simulation design and limited 2025 historical patterns; it must not be interpreted as an externally validated future probability.

### Why debt collection dominates simulated variability

Debt collection contributes approximately **90.94%** to total simulated variance under a **covariance-based contribution** calculation. Checking/savings contributes **5.52%**, credit cards **3.71%**, and mortgages **−0.17%**. The small negative mortgage contribution indicates an offsetting covariance in these simulations, **not** negative complaints or a claim that mortgages pose no risk.

### Targeted debt-collection scenarios

![Scenario distribution comparison — current conditions versus 15% and 30% debt-collection improvements](/images/8_SCENARIO%20DISTRIBUTION%20COMPARISON.png)

*Figure — Scenario distribution comparison — current conditions versus 15% and 30% debt-collection improvements.*

These scenarios are **different from the portfolio-wide moderate and strong scenarios above**: here, only debt collection's untimely rates are reduced by a relative percentage.

| Debt collection assumption | Simulated mean | Mean cases avoided | Modeled probability above 10,000 |
|---|---:|---:|---:|
| Current conditions | **9,541** | — | **13.18%** |
| 15% relative reduction | **8,310** | **1,230** | **0 observed in 10,000 runs** |
| 30% relative reduction | **7,080** | **2,461** | **0 observed in 10,000 runs** |

The zero exceedance outcomes are **observed simulation frequencies**, not proof that exceedance would be impossible. The exercise supports *comparative risk discussion*, not a guarantee of operational results.

## 9 | Business recommendations

![Executive decision dashboard — combined KPIs, scenarios and modeled risk](/images/9_Decision_Dashboard.png)

*Figure — Executive decision dashboard — combined KPIs, scenarios and modeled risk.*

**Prioritize a debt-collection diagnostic program, not a generic portfolio-wide intervention.** Debt collection accounts for the majority of untimely cases and simulated variability. Start by breaking the category down by company, issue, response classification, and month, then identify which operational hypotheses can be tested with additional internal evidence.

**Treat sudden performance shifts as questions before treating them as successes or failures.** The CCS example demonstrates why a large trend deserves a denominator check, segment-level comparison, mix analysis and reconciliation of status definitions. Its apparent improvement is large and statistically distinguishable, but the available records do not identify the cause.

**Separate operational workload from response performance.** Monitor complaint inflow, absolute untimely cases and untimely rates together. January's volume concentration and April's rate peak demonstrate the danger of a single-metric dashboard.

**Make benchmarking conditional on composition.** Excess-case analysis improves on simple rate rankings, yet Georgia's CCS adjustment shows that company mix changes the interpretation. Geographic analysis should guide *which company–product segments to review in which markets*, not assign performance responsibility to states.

**Use scenarios to organize decisions and trade-offs.** The portfolio what-if model quantifies the result of assumed improvements; the Monte Carlo model quantifies variation around historically informed conditions. Before funding an intervention, add operational feasibility, cost, accountability and internal validation—none of which can be inferred from this public dataset.

## 10 | Data scope, reliability and limitations

The analysis covers **482,074** selected CFPB complaints *received in 2025* across **four product categories**. The underlying public export was scoped upstream, followed by enrichment and validation. The geographic reference matched **480,344** records; **1,730** lacked state information, and the original record count was preserved. **158** sub-issue fields were missing. **12,762** records had forwarding intervals exceeding **30 days**; these were flagged, not declared erroneous. **64,231** records matched an earlier record on non-ID attributes, but all complaint IDs were unique and no records were removed solely for attribute similarity.

The strongest constraints are interpretive:

1. **Selection and reporting:** complaint submissions are not a random sample of all customers or transactions; complaint volume is not a measure of market share, prevalence or total customer dissatisfaction.
2. **Recorded timeliness:** the analysis uses the CFPB's public response-status field; reasons for delay and operational accountability require additional evidence.
3. **Confounding:** differences across states, companies, issues and months may reflect differences in case mix, submission practices and unobserved processes.
4. **Causality:** the CCS investigation documents a substantial association across periods; it does not establish an intervention effect. The split was identified after observing the time series.
5. **Scenario limits:** improvements are hypothetical; the historical-pattern simulation captures selected forms of variability but cannot account for all future structural changes.
6. **Geographic benchmark:** the 50-state comparison deliberately excludes DC, territories and missing-state records and should not be confused with the all-record overall rate.

### Source and reproducibility

**Primary source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/).  
**Workbook:** `CFPB_2025_Project.xlsx` (15 worksheets), with separate data quality, performance, company, issue, geographic, investigation, decision and simulation areas.  
**Analysis period:** receipt dates January 1–December 31, 2025.  
**Scope note:** this is a selected four-product analytical extract; published CFPB datasets may change over time as records are updated.

## Conclusion

The evidence points to **a concentrated response-timeliness burden in debt collection**, **nonparallel trends in complaint volume and late-response rates**, and **material composition effects behind apparent company and geographic disparities**. The most useful result is not any isolated metric: it is the analytic discipline of moving from an observed difference to denominator checks, segmentation, alternative explanations and conditional decisions. The next operational step is to test the leading hypotheses with organization-level process records rather than treat descriptive public complaint data as proof of the cause.

---

### Image integration notes

The figures above use root-relative `/images/` URLs for the portfolio website, matching assets placed in `public/images/`. Filenames preserve the exact capitalization and punctuation supplied for the exported screenshots. For a GitHub-only copy of this report, change the image URL prefix from `/images/` to the repository-relative folder (for example, `images/`) and commit the image files to that folder.

**Publication note:** before posting the actual workbook, verify that the saved copy no longer contains a cached `#N/A` in `Decision_Dashboard!C36`, that the January evidence pivot displays both companies, and that the risk-contribution table headers are visible. These issues affect the presentation of the workbook but do not invalidate the independently listed scenario calculations.
