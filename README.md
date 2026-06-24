# Resume Genius — Research Data

Raw datasets from Resume Genius' original surveys on the career space — covering job seekers, hiring managers, and workplace trends, with demographic breakdowns.

We publish this data openly so journalists, analysts, and researchers can verify our findings and build on them. If you use it, we just ask that you credit Resume Genius (see [How to cite](#how-to-cite) below).

## What's inside

Each survey lives in its own folder. Most surveys are published in two layers:

- **Raw data** — a single CSV with one row per respondent, for your own analysis.
- **Tabulated results** — a `questions/` folder with one JSON per survey question. Each file contains the overall result plus crosstabs by Age, Gender, US State, Household income, Education Level, and Employment Status. If you just want the numbers, start here.

Some surveys are published as **tabulated results only**, with no raw CSV, when the respondent-level data cannot be safely de-identified (see [Privacy & de-identification](#privacy--de-identification)). For these, the aggregated JSON is the complete public release.

Each folder also includes `survey_meta.json` with the survey's title, sample size, vendor, fieldwork dates, and topic tags.

```
research-data/
├── README.md
├── LICENSE
└── us_job_seeker_survey_2026/
    ├── survey_meta.json                # title, n, vendor, dates, topic tags
    ├── us_job_seeker_survey_2026.csv   # raw, one row per respondent
    └── questions/
        ├── q1_*.json                   # per-question results: overall + demographic crosstabs
        ├── q2_*.json
        └── ...                         # one file per question
```

**A note on small cells:** in the tabulated JSON, any demographic group with fewer than 5 respondents is suppressed (shown as `"suppressed": true`) to protect respondent privacy and avoid reporting unreliable percentages. Blank cells are intentional, not missing data.

## Privacy & de-identification

The raw CSV has been de-identified before release. Respondents were anonymous to begin with (no names, emails, or contact details were collected), and we additionally removed or coarsened fields that could be combined to single someone out:

- **Geography** is reported no finer than state. ZIP code, county, metro/statistical area, and media-market (DMA) fields were removed; State, Region, and Division are retained.
- **Age** is reported as generation band rather than exact age.
- **Household income** is reported in broad bands in the raw CSV (e.g. "$75,000–$99,999"). The tabulated JSON retains the detailed survey brackets, since the n<5 suppression already protects small cells at the aggregate level.
- **Details about respondents' children** (specific age/gender) were removed; only a high-level parental-status indicator is retained.
- **Vendor and operational fields** (internal quota IDs, individual start/finish timestamps) were removed.

The tabulated JSON additionally suppresses any group with fewer than 5 respondents, as noted above.

**Surveys published as aggregates only.** For some surveys, the raw respondent-level data carries too much re-identification risk to release safely, even after de-identification. In those cases we publish only the tabulated JSON (with the same n<5 suppression) and withhold the raw CSV. This is a deliberate privacy decision, not an omission.

| Dataset (folder) | Survey | Respondents | Field date | Data published |
| :--------------- | :----- | :---------- | :--------- | :------------- |
| `us_hiring_trends_2024/` | US Hiring Trends Survey, 2024 | 625 U.S. hiring managers | Jan 2024 | JSON only |
| `us_hiring_changes_2025/` | US Hiring Changes Survey, 2025 | 1,000 U.S. hiring managers | Jan 2025 | CSV + JSON |
| `us_gen_z_workers_2025/` | US Gen Z Workers Survey, 2025 | 1,000 U.S. Gen Z workers | 2025 | JSON only |
| `us_job_seeker_survey_2026/` | US Job Seekers Survey, 2026 | 1,000 U.S. job seekers | Mar 2026 | CSV + JSON |
| `us_hiring_managers_survey_2026/` | US Hiring Managers Survey, 2026 | 1,500 U.S. hiring managers | Jun 2026 | CSV + JSON |

## Reports based on each dataset

**US Hiring Trends Survey, 2024**
- [2024 Hiring Trends Report](https://resumegenius.com/blog/job-hunting/hiring-trends-survey)
- [8 in 10 Hiring Managers Have Ghosted Candidates](https://resumegenius.com/blog/job-hunting/job-ghosting)
- [65% of Hiring Managers Will Hire You For Your Skills Alone](https://resumegenius.com/blog/job-hunting/skills-based-hiring)
- [Nearly 3 in 4 Hiring Managers Lie to Applicants](https://resumegenius.com/blog/job-hunting/hiring-managers-lie-to-candidates)

**US Hiring Changes Survey, 2025**
- [AI's Impact on Hiring](https://resumegenius.com/blog/job-hunting/ai-impact-on-hiring)
- [2025 Mental Health and Employability Report](https://resumegenius.com/blog/job-hunting/mental-health-and-employability)
- [2025 Education and Earnings Report](https://resumegenius.com/blog/job-hunting/education-and-earnings)
- [2025 Unfiltered Hiring Insights Report](https://resumegenius.com/blog/job-hunting/unfiltered-hiring-insights)

- **US Gen Z Workers Survey, 2025**
- [2025 Gen Z Career Prospects Report](https://resumegenius.com/blog/career-advice/gen-z-career-prospects)
- [2025 Gen Z and AI in the Workplace Report](https://resumegenius.com/blog/career-advice/gen-z-and-ai)
- [2025 Gen Z Work Mindset Report](https://resumegenius.com/blog/career-advice/gen-z-work-mindset)

- **US Job Seekers Survey, 2026**
- [2026 Job Seeker Insights Report](https://resumegenius.com/blog/job-hunting/job-seeker-insights-report-2026)

## Methodology

Surveys are fielded using Pollfish Random Device Engagement (RDE) to reach a demographically balanced sample; respondents are screened for relevance to each survey's population. Full per-survey methodology is documented in each codebook and article Methodology section.

## License

This data is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to share and adapt the data for any purpose, including commercial use, as long as you give appropriate credit. The full license text is in [`LICENSE`](LICENSE).

## How to cite

Please attribute the data to Resume Genius with a link back to the source.

**Plain text**

> Resume Genius. "[Report title]." [Year]. https://resumegenius.com/[report-url]

**With a live link (for web/online use)**

```html
Source: <a href="https://resumegenius.com/[report-url]">Resume Genius, "[Report title]" ([Year])</a>
```

**Example**

> Resume Genius. "US Job Seekers Survey, 2026." 2026. https://resumegenius.com/[report-url]

## Contact

For press inquiries or questions about the data: [press contact / email].
