# 🇳🇬 Identifying Nigerian YouTube Creators in Analytics Engineering Using YouTube Data API

[![YouTube Data API](https://img.shields.io/badge/API-YouTube%20v3-red)](https://developers.google.com/youtube/v3)
[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/status-active-brightgreen)]()

## 🎯 Project Overview and Problem Statement

Despite the growth of analytics engineering globally, there is limited visibility into Nigerian creators producing educational content on tools like dbt, Airbyte, Prefect, and others. There's a need to identify, analyze, and promote these local voices who are creating valuable content — but they're buried under a mountain of global results on YouTube.

Key Questions:

- Who are the Nigerian creators in the analytics engineering niche?
- What are their most-viewed and most-engaged videos?
- Which tools are Nigerian creators actively teaching?

---

## Introduction 

In this project, I leveraged the YouTube Data API to systematically crawl and analyze YouTube content related to popular analytics engineering tools. I focused on content published from 2023 onward, filtered by Nigerian channels only, and explored metrics like video views, likes, and channel subscriber counts.
This project is part of a broader mission to map the Nigerian data content landscape, identify underrepresented creators, and understand the types of tools local educators are focused on. The end product is a clean dataset ready for KPI analysis and dashboarding.

---

## ⚙️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core scripting and logic |
| YouTube Data API v3 | Video + channel metadata |
| Pandas | Data wrangling |
| CSV | Data storage |
| Power BI / Hex (optional) | Visualization layer |

---

## 📂 Features

- ✅ Search YouTube using multiple analytics engineering keywords
- ✅ Cache video and channel IDs to **avoid duplicate API calls**
- ✅ Cap results to **2 pages per keyword** to manage API quotas
- ✅ Fetch detailed video + channel metadata
- ✅ Filter results to Nigerian creators only
- ✅ Export results to `engineering_youtube_NG_data.csv`

---

## 🚀 How It Works

1. **Search Setup**
   - Define search keywords
   - Set date range from 2023 onwards
   - Limit to 2 pages per keyword to stay within quota

2. **API Calls**
   - Search YouTube and retrieve `videoId`s
   - Call `videos().list()` for statistics
   - Call `channels().list()` for creator metadata

3. **Data Wrangling**
   - Join video and channel info
   - Filter to `channel_country = "NG"`
   - Clean, deduplicate, and sort by view count

4. **Save to CSV**
   - Output: `engineering_youtube_NG_data.csv`

---

## 🧪 Sample Output

| Video Title | Channel Title | View Count | Subscriber Count |
|-------------|----------------|------------|------------------|
| Getting Started with dbt | DataNaija | 12,309 | 4,211 |
| Airbyte vs Fivetran | AnalystKulture | 9,889 | 2,710 |
| ETL with Prefect in 2024 | NaijaDataOps | 8,342 | 1,301 |

---
