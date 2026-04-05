# Bumeran Scraper

Extract structured data from [bumeran.com.ar](https://bumeran.com.ar) — bumeran.com.ar — the largest job board across 8 LATAM countries. Work modality, contract type, and incremental change tracking.

**[Bumeran Scraper on Apify →](https://apify.com/blackfalcondata/bumeran-scraper)**

---

## Key features

**Search with filters** — Search by keyword and location. Filter by country, sort order, and more.

**Detail enrichment** — Fetch full job descriptions, salary data for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

---

## Use cases

**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from bumeran.com.ar on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from bumeran.com.ar.

---

## Quick start

```json
{
  "query": "developer",
  "maxResults": 50,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `query` | string | — | Job search keywords (e.g. "developer", "analista"). Use JSON array for multiple queries. |
| `country` | enum | `"AR"` | Which LATAM market to search. Each country uses the local brand. |
| `location` | string | — | City or province filter (e.g. "Buenos Aires", "Lima"). Use JSON array for multiple. |
| `sort` | enum | `"RELEVANTES"` | Sort results by relevance or date. |
| `maxResults` | integer | `50` | Maximum total job listings to return (0 = unlimited). |
| `includeDetails` | boolean | `true` | Include full job description text (returned inline by the API at no extra cost). |
| `descriptionMaxLength` | integer | `0` | Truncate description to this many characters. 0 = no truncation. |
| `compact` | boolean | `false` | Output only core fields (for AI-agent/MCP workflows). |
| `incrementalMode` | boolean | `false` | Compare against previous run state. Requires stateKey. |
| `stateKey` | string | — | Stable identifier for the tracked search universe (e.g. "ar-developer"). |
| `emitUnchanged` | boolean | `false` | When incremental, also emit records that haven't changed. |
| `emitExpired` | boolean | `false` | When incremental, also emit records no longer found. |

---

## FAQ

<!-- WRITE: 4-6 Q&A pairs relevant to this product -->

**Is it legal to scrape bumeran.com.ar?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check the target site's terms of service for your specific use case.

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->

---

## Related products by Black Falcon Data

- [StepStone Scraper](https://github.com/BlackFalconData-org/stepstone-scraper) — Job listings from 18 European portals
- [Indeed Job Scraper](https://github.com/BlackFalconData-org/indeed-job-scraper) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://github.com/BlackFalconData-org/glassdoor-job-scraper) — Glassdoor listings with company ratings

---

*Last updated: 2026 04*
