# Identifying Nigerian YouTube Creators in Analytics Engineering Using YouTube Data API

[![YouTube Data API](https://img.shields.io/badge/API-YouTube%20v3-red)](https://developers.google.com/youtube/v3)
[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/status-active-brightgreen)]()


# 📊 YouTube Analytics Engineering Content Scraper

This project scrapes YouTube for educational videos related to **Analytics Engineering** and its key tools (like dbt, Airbyte, Prefect, etc.) using the YouTube Data API. It collects video metadata, channel details, and engagement metrics to help identify high-quality content and top creators in the data space — especially those relevant to the Nigerian tech scene.

---

## 🧠 Problem Statement

Finding high-quality, localized content for learning analytics engineering is tough in the endless sea of YouTube videos. This project aims to solve that by programmatically searching, analyzing, and ranking videos and channels that focus on analytics engineering tools and topics.

---

## 📜 Problem Overview

With the growth of modern data tools like Prefect, dbt, Airbyte, and Hex, the demand for up-to-date learning resources has exploded. But learners—particularly in underrepresented regions—struggle to find the most relevant content. This scraper:
- Searches for targeted keywords,
- Aggregates metadata from videos and channels,
- Ranks creators and content by engagement,
- Helps surface the most impactful videos and educators in the space.

---

## 🔑 Key Questions This Project Answers

- Which videos about analytics engineering tools have gained the most traction since 2023?
- Who are the most influential content creators in this niche?
- Are there any standout Nigerian or African creators?
- Which keywords yield the most valuable content?
- How do different tools compare in terms of engagement and visibility?

---

## 🛠️ Tech Stack

| Purpose            | Tool/Library                            |
|--------------------|------------------------------------------|
| API Interaction    | YouTube Data API v3                      |
| Language           | Python                                   |
| Data Handling      | pandas                                   |
| API Client         | google-api-python-client                 |
| Data Storage       | CSV (`Nezzar_results.csv`)               |
| Visualization (Optional) | Hex        |

---

## 🌟 Features

- 🔍 **Keyword-based Video Search** for analytics engineering-related topics
- 🧠 **Deduplication Logic** to avoid overlapping video results
- 📊 **Engagement Metrics Extraction**: Views, likes, comments
- 📺 **Channel Stats Extraction**: Channel title and subscriber count
- 🔁 **Robust Retry Logic** for API call failures
- 🧹 **Clean CSV Export** ready for analysis
- 📈 **Sorted Output** by view count to spotlight top-performing videos

---

## ⚙️ How It Works

1. **Search Phase**  
   Iterates through predefined search terms (e.g., `dbt data analytics tutorial`) and collects up to 5 pages of results (max 250 videos per term).

2. **Deduplication**  
   Ensures each video appears only once in the final dataset.

3. **Details Collection**  
   Fetches additional statistics for each video and corresponding channel.

4. **Data Enrichment**  
   Merges channel and video metadata into a single structured DataFrame.

5. **Output**  
   Exports the final result to a CSV file named `Nezzar_results.csv`, sorted by view count.

---

## 📦 Output File

- **Filename**: `Nezzar_results.csv`
- **Columns**:
  - `video_id`
  - `title`
  - `description`
  - `published_at`
  - `view_count`
  - `like_count`
  - `comment_count`
  - `channel_id`
  - `channel_title`
  - `subscriber_count`
