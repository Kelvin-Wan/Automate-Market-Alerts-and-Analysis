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


💡 Example Output
Here is an example of the output an investor might receive.

****************************************************************************
Dear Investors,

Here's a summary of key market-moving news and potential impacts:

Positive Market Signals:

Technology Sector: Apple's $600 billion US investment plan signals strong confidence in domestic growth and could benefit related industries. OpenAI's GPT-5 release and Duolingo's AI-driven growth also indicate continued innovation and expansion in the AI space. AppLovin anticipates benefits from the Apple-Epic suit. The GSA's deals with Oracle and OpenAI provide federal agencies discounted access to ChatGPT.
Financial Sector: Japanese investment firm hitting record highs suggests continued strength in that market. Flutter (FanDuel) exceeding earnings expectations points to a positive outlook for the online betting industry. Cboe's potential expansion into Australian sharemarket listings may create new opportunities. Eli Lilly's increased guidance and strong earnings driven by weight loss and diabetes drugs is positive for the pharmaceutical sector. Instacart's earnings surpass Wall Street estimates.
Consumer Discretionary: CBRE survey indicating increased office attendance may indirectly support businesses that benefit from in-person work.
Negative Market Signals:

Political/Economic Uncertainty: Trump's selection for the Federal Reserve and ongoing tariff policies introduce uncertainty and could impact trade relationships. Trump's call for Intel CEO's resignation negatively impacted Intel shares. Oil price decline following tariff announcements suggests trader skepticism regarding policy follow-through. Increased tariffs may cause tactical portfolio moves.
Company-Specific Concerns: Pete Bannon's departure from Tesla raises questions about the company's direction. Pinterest's earnings miss on EPS is a cause for concern. Restaurant chain decline in extended trading due to beef prices indicates inflation pressures. Meta faces a privacy lawsuit loss. Neometals shares have dropped significantly due to its lithium ion battery recycling stake sale.
Social Media/Privacy: Instagram's new map feature raises privacy concerns, potentially impacting user trust and engagement.
Commodities: Oil closed 1% lower on Wednesday after Trump announced new India tariffs.
Neutral/Mixed Signals:

Executive order related to private market investments in 401(k) plans presents both risks and rewards for investors, requiring careful consideration.
Block's weaker-than-expected earnings offset by increased full-year guidance presents a mixed picture.
Overall Outlook:

The market presents a mixed bag of opportunities and risks. Positive developments in the technology, financial, and consumer sectors are tempered by political uncertainty, company-specific challenges, and emerging privacy concerns. We recommend a diversified portfolio and a cautious approach to volatile sectors.

Sincerely,
Your Market Analyst

****************************************************************************************
Here is an example of the sentiment analysis output:
<img width="1128" height="84" alt="image" src="https://github.com/user-attachments/assets/61a87367-b99d-4875-9f18-670031eee979" />


🛠️ Prerequisites
n8n: A running instance of n8n (either self-hosted or cloud).

NocoDB: A NocoDB project with a configured base and a table to store the sentiment analysis data.

Google Gemini API Key: An API key for the Gemini model.

Email/Messaging Service Credentials: Credentials for the service you use to send alerts (e.g., an SMTP server or Slack Webhook).
