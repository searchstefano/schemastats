# SchemaStats

An open-source observatory and intelligence platform for **Schema.org** usage statistics, real-world validation, and semantic search insights.

This repository serves as the public hub for community discussions, feature requests, and project proposals. The live platform can be found at [schemastats.com](https://www.schemastats.com).

---

## 📊 Project Overview

With the release of the official dataset on structured data adoption, **SchemaStats** turns raw, massive data snapshots into an interactive, visual dashboard. Our goal is to help SEOs, developers, and GEO (Generative Engine Optimization) specialists understand how semantic data is shaping the AI-driven future of search.

---

## 🚀 Key Features

- **Global Analytics Observatory:** High-level KPIs and distribution charts showcasing the most popular Entity Types vs. Properties based on real-world adoption.
- **Deep-Dive Explorer:** Client-side search, filtering, and sorting to explore the entire Schema.org vocabulary.
- **Schema Validation & Comparison:** On-demand inspection of `JSON-LD`, `Microdata`, and `RDFa` directly from any URL, paired with a dedicated Google Rich Results readiness layer.
- **Side-by-Side Comparison:** Compare structured data between two competitor URLs to identify missed semantic opportunities.

---

## ℹ️ Methodology & Data

### What it is
Schema.org publishes, in collaboration with Google, a public dataset tracking the real-world usage of vocabulary terms (types like `Person` or properties like `price`) across millions of domains. SchemaStats provides a clean visual wrapper for this data.

### How the data is collected
- **Aggregated per Domain:** Term frequencies are measured by Google's public crawling infrastructure and aggregated by domain, not per page. Using a specific tag on 100 pages of the same site counts as 1 unique domain.
- **Popularity Tiers:** Instead of noisy exact numbers, sites are grouped into popularity buckets for stability and privacy.
- **Monthly Snapshots:** A new dataset snapshot is published on GitHub every month.

### The Domain Buckets
Every term is classified into one of the following tiers based on unique domain counts:
` < 1K ` | ` 1K - 10K ` | ` 10K - 100K ` | ` 100K - 1M ` | ` 1M - 10M ` | ` 10M+ `

> 📌 **Note:** The `< 1K` bucket includes brand-new terms as well as highly specialized ones (e.g., medical or government schemas). It does not mean they are ignored or irrelevant.

### Important Nuances
- The dataset does **not** distinguish between JSON-LD, Microdata, or RDFa; they are counted together.
- Statistics reflect the web as indexed by Google; no web crawl covers 100% of the entire internet.
- The format is open, meaning other public crawlers can contribute their own statistics using the exact same schema.

---

## 🤖 SchemaStatsBot (Our Crawler)

**SchemaStatsBot** is the on-demand crawler behind the Schema.org validator on SchemaStats. It strictly fetches URLs that a visitor explicitly submits to extract and analyze their structured markup.

### Why it is a good bot:
- **User-Triggered Only:** It only runs after a human submits a URL in the validator or compare tool. It never crawls the web autonomously.
- **Robots.txt Compliant:** It checks your site's `robots.txt` before every single fetch and stops immediately if disallowed.
- **Identifiable & Safe:** It uses a clear, stable User-Agent string. Requests are strictly rate-limited and capped (timeouts, size limits, and no private-network access to prevent SSRF).

### User-Agent
Use this string to identify our crawler in your server logs, WAF rules, or `robots.txt`:
```
SchemaStatsBot/1.0 (+[https://schemastats.com/bot](https://schemastats.com/bot))
```

## How to block it
If you wish to disallow SchemaStatsBot from crawling your site, add the following directive to your robots.txt. When blocked, our validator will gracefully display a "Blocked by robots.txt" message to the user instead of fetching the page:

```
User-agent: SchemaStatsBot
Disallow: /
```

---

### 🔮 Roadmap & Future Vision

We want to evolve SchemaStats from a static dataset viewer into a live global semantic graph (similar to BuiltWith, but open and vertical):

[ ] Traffic & Geo Filtering: Integrating global ranking metrics (e.g., Cloudflare Radar data) to filter Schema adoption by country, region, and website popularity buckets.

[ ] AI & LLM Readiness Score: A custom grading system evaluating how optimized a website's semantic markup is for AI Overviews, SearchGPT, and LLM crawlers.

---

### 💬 Join the Discussion!

We are using this repository space exclusively to gather ideas, feedback, and architectural advice from the global SEO & Dev community.

We highly encourage you to [Open an Issue](https://github.com/searchstefano/schemastats/issues) or start a discussion if you want to propose new filtering capabilities, UI charts, or technical integrations.

---

### 📌 Sources & Disclaimer

[Schema.org Public Stats Dataset Announcement](https://blog.schema.org/2026/06/04/announcing-the-schema-org-usage-statistics-dataset/)

[Google Search Central — Structured Data Documentation](https://developers.google.com/search/docs/appearance/structured-data)

> Disclaimer: SchemaStats is an independent community project and is not affiliated with, sponsored by, or endorsed by Google, Microsoft, or the Schema.org foundation.

---

## 🤝 Contributions & Community Stars

SchemaStats is a community-driven project. We believe that valuable contributions come in many forms—whether it's writing code, improving documentation, suggesting UX enhancements, or opening insightful issues.

### Special Thanks to Our Contributors:
*   [@alisonsainsbury-adx](https://github.com/alisonsainsbury-adx) — For opening the foundational issue on accessibility, global contrast improvements, and validation legends.
*   [@glenngabe](https://x.com/glenngabe) - For the support <3

### How You Can Contribute:
1.  **Report Bugs & Suggest UX Improvements:** Notice something broken or hard to read? Open an issue!
2.  **Feature Requests:** Want to see a specific chart or integration? Let's discuss it in the issues.
3.  **Code & Docs:** Feel free to pick up any open issues or propose fixes via Pull Requests.

> 💡 **Want to be featured here?** Every meaningful issue, bug report, or discussion that helps shape the platform will be recognized and tagged in this section!
