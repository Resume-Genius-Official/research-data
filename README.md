# Resume Genius — Research Data
Raw datasets from Resume Genius' career space surveys. Contains data on job seekers, hiring managers, and more with demographic breakdowns.

We publish this data openly so journalists, analysts, and researchers can verify our findings and build on them. If you use it, we ask that you credit Resume Genius (see [How to cite](#how-to-cite) below).

## What's inside

Each survey lives in its own folder and is published in two layers:

- **Raw data** — a single CSV with one row per respondent, for your own analysis.
- **Tabulated results** — a `questions/` folder with one JSON per survey question. Each file contains the overall result plus crosstabs by Age, Gender, US State, Household income, Education Level, and Employment Status. If you just want the numbers, start here.

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
- **Details about respondents' children** (specific age/gender) were removed; only a high-level parental-status indicator is retained.
- **Vendor and operational fields** (internal quota IDs, individual start/finish timestamps) were removed.

The tabulated JSON additionally suppresses any group with fewer than 5 respondents, as noted above.

| Dataset | Survey | Respondents | Field date | Source report |
| :------ | :----- | :---------- | :--------- | :------------ |
| `us_job_seeker_survey_2026/` | US Job Seekers Survey, 2026 | 1,000 U.S. job seekers | [fieldwork dates] | [Link to report](#) |
| `[folder]/` | [Survey name] | [n] | [year] | [Link] |

## Methodology

Surveys are fielded using Pollfish Random Device Engagement (RDE) to reach a demographically balanced sample; respondents are screened for relevance to each survey's population. Full per-survey methodology is documented in each codebook and under the Methodology section of each article, e.g. [https://resumegenius.com/blog/job-hunting/hiring-insights-report#methodology]([url](https://resumegenius.com/blog/job-hunting/hiring-insights-report#methodology))

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
