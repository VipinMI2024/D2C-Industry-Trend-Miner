# D2C Industry Trend Miner

An automated n8n workflow that fetches articles about the D2C (Direct-to-Consumer) industry, analyzes them to identify emerging themes, and generates insightful reports on volume, trajectory, and sentiment.

## About The Project

This project provides a powerful, no-code/low-code solution for market research and trend analysis using n8n. It automatically gathers dozens of articles from various RSS feeds (like Google News, Inc42, YourStory), deduplicates them, and uses a simple keyword frequency analysis to group them into 3-5 distinct themes.

For each theme, it calculates:
* **Volume**: The number of articles related to the theme.
* **Trajectory**: Whether the theme's momentum is rising, falling, or steady.
* **Tone**: A simple sentiment analysis (positive, negative, neutral) based on headlines.

The final outputs are three distinct files, perfect for reports and further analysis:
* `trends.csv`: A full dataset of all processed articles with their assigned theme.
* `themes.json`: A structured JSON file with metadata for each identified theme.
* `INSIGHTS.md`: An auto-generated Markdown report summarizing the key themes.



## Features

* **Automated Data Collection**: Fetches 50+ unique articles from configurable RSS sources.
* **Dynamic Theme Generation**: Automatically identifies 3-5 key themes from article titles and descriptions.
* **Trend Analysis**: Calculates the volume, trajectory (momentum), and sentiment for each theme.
* **Multiple Export Formats**: Generates CSV, JSON, and Markdown reports.
* **Customizable**: Easily change the search query, date range, and RSS feeds via the `Params` node.
* **Cost-Effective**: Requires no external paid APIs.

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

* A running instance of n8n (Desktop, Docker, or Cloud).

### Installation

1.  Download the `workflow.json` file from this repository.
2.  In your n8n canvas, go to **Import > From File...**.
3.  Select the downloaded `workflow.json` file.
4.  The workflow will be imported into your n8n instance.

## Configuration

All major settings can be configured in the **`Params`** (Set) node at the beginning of the workflow.

* **`days`**: The number of days to look back for articles (e.g., `7`, `14`, `21`).
* **`maxItems`**: The maximum number of unique articles to process (e.g., `80`).
* **`query`**: The main search term for Google News RSS (e.g., `D2C startups`, `ecommerce India`).

You can also add more news sources by adding more `RSS Read` nodes and connecting them to the `Merge` node.

## Usage

1.  Open the "D2C Trend Miner" workflow in n8n.
2.  (Optional) Adjust the values in the `Params` node.
3.  Click **Execute Workflow**.
4.  Once the workflow completes successfully, your output files (`themes.json`, `trends.csv`, `INSIGHTS.md`) will be saved to the destination you configured in the final nodes (e.g., Google Drive, local file system).

## Built With

* [n8n.io](https://n8n.io/) - Workflow Automation Tool

## License

Distributed under the MIT License. See `LICENSE.txt` for more information.
