# Automate-Market-Alerts-and-Analysis
Automate news extraction, analysis, email to investors and push sentiment analysis records into a database for ML forecasting

This project automates the entire process of monitoring financial news, analyzing market sentiment, and sending actionable alerts to investors. The core of this system is a powerful n8n workflow that orchestrates multiple services, including Google's Gemini large language model and a NocoDB database.

🌟 Features
Automated News Extraction: Fetches the latest news from various financial sources.

Gemini-Powered Analysis: Uses the Gemini API to summarize articles, analyze market sentiment (1-10, 1 being very negative, 10 being very positive), and assess potential market impact on assets like gold, bonds, and stock markets.

Investor Alerts: Automatically sends a concise summary and market impact analysis to designated investors via a channel like email, Slack, or another messaging service.

Sentiment Data Storage: Stores the sentiment analysis results in a NocoDB database, creating a historical record for future trend analysis, correlate with actual actual asset class, produce necessary forecasting and reporting.

⚙️ How It Works
The workflow is a seamless chain of operations:

A time trigger node initiates the process.

A RSS Read Request node extracts news articles from various sources.

A node processes the article content and sends it to the Gemini API with a specific prompt for summarization and sentiment analysis.

The output from Gemini is parsed, and the key insights are formatted into a human-readable alert.

A messaging node (e.g., Email, Slack, etc.) sends the alert to the investors.

The sentiment data is then passed to a NocoDB node, which creates a record with the analysis results.

<img width="1401" height="381" alt="image" src="https://github.com/user-attachments/assets/08d0068f-2e7f-4560-82a8-a7686badb4ea" />



