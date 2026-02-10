# BC Charity Explorer

A discovery app for 12,290 registered charities across British Columbia, built on open CRA data.

**[Live Demo →](https://yourusername.github.io/bc-charity-explorer)** *(update this link after deployment)*

![BC Charity Explorer](https://img.shields.io/badge/Charities-12%2C290-1B6B5A) ![Data Source](https://img.shields.io/badge/Data-CRA%20T3010%20(2023)-D4883E)

## What It Does

Not every registered charity provides the same level of community impact. This app helps donors discover high-quality charities by separating signal from noise using CRA financial data.

### Three-Tier Discovery System

| Tier | Name | Criteria | Count |
|------|------|----------|-------|
| 💎 | **Hidden Gems** | Small-medium charities (<$500K revenue) with 60%+ program spending ratio. Lean, high-impact, actively seeking donors. | 4,836 |
| 🏛️ | **Established** | Large or mid-tier charities. Well-known, well-funded, steady operations. | 5,308 |
| 📋 | **Low Activity** | Dormant charities (zero revenue + expenses) or private foundations (CRA designation code 0003). | 2,146 |

### Features

- **12 category tiles** — Faith, Animal Welfare, Environment, Health, Arts, and more
- **City filter** — Top 60 BC cities
- **Search** — By charity name or city
- **Financial detail modals** — Revenue, expenses, program spending ratio, fund allocation bars
- **Flow-through detection** — Flags entities with high revenue but zero receipted donations
- **CRA deep links** — One click to view official filings on the CRA website

## Data Sources

- **Charity Directory**: [CRA List of Charities](https://open.canada.ca/data/en/dataset/05b3abd0-e70f-4b3b-a9c5-acc436bd15b6) — 138K national records, filtered to 12,290 BC registered charities
- **Financial Data**: T3010 Annual Returns (2023 fiscal year) — 85 columns of financial line items per charity

### Key Financial Metrics

| Metric | T3010 Line | Description |
|--------|-----------|-------------|
| Total Revenue | 4700 | All income sources |
| Total Expenditures | 5100 | All spending |
| Program Expenses | 5000 | Direct charitable program spending |
| Program Ratio | 5000 ÷ 5100 | Efficiency — % going to charitable work |
| Tax-Receipted Gifts | 4500 | Public donations (receipted) |
| Government Funding | 4570 | All government sources |
| Total Assets | 4200 | Balance sheet total |

## Data Quality Notes

- **Designation codes**: 0001 = Charitable Organization, 0002 = Public Foundation, 0003 = Private Foundation
- **City names**: Cleaned and standardized (40+ corrections for misspellings, neighbourhood consolidation)
- **Category assignment**: Keyword-based classification using charity names + CRA charity type codes
- **Known CRA issue**: Some charities report in thousands vs. actual dollars, which can inflate aggregates

## Tech Stack

Single self-contained HTML file — no build step, no dependencies to install:

- React 18 (CDN)
- Babel standalone (in-browser JSX compilation)
- DM Sans + Fraunces fonts (Google Fonts)
- All 12,290 charity records embedded as a JSON array (~2.2MB)

## Local Development

Just open `index.html` in a browser. That's it.

## Deployment (GitHub Pages)

1. Create a new repository on GitHub
2. Upload the `index.html` file
3. Go to **Settings → Pages → Source → Deploy from branch → main**
4. Your site will be live at `https://yourusername.github.io/repo-name`

## License

Data is from the Government of Canada Open Data Portal under the [Open Government Licence](https://open.canada.ca/en/open-government-licence-canada).

---

*Built with open CRA data. This is not financial advice. Always verify charity information directly with the CRA.*
