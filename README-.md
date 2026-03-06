# Sentiment Analysis of AI News Coverage

## Overview

Artificial intelligence has become one of the most visible and debated topics in modern news coverage. Some articles present AI as a major breakthrough that can improve productivity, accelerate research, and transform industries. Others focus on the risks, including regulation, misinformation, job displacement, safety concerns, and ethical questions.

This project examines how AI is framed in recent news articles by applying natural language processing techniques to a large collection of media content. The goal is not just to label articles as positive or negative, but to better understand the broader patterns in how AI is discussed. By combining sentiment analysis with topic modeling, the project identifies both the tone of coverage and the major themes that appear across AI-related news.

The analysis is based on roughly 1,800 English-language news articles collected using AI-related search terms. These articles were then cleaned, processed, scored for sentiment, and grouped into topics. Together, these steps provide a structured way to study how the media portrays artificial intelligence.

## Objectives

This project was designed to answer several important questions about AI news coverage:

- Does news coverage of AI tend to be mostly positive, mostly negative, or mostly neutral?
- Are some AI-related topics described more favorably than others?
- Do different sentiment analysis methods produce similar results?
- What major themes appear most often in AI news coverage?
- How does sentiment change depending on whether an article is focused on innovation, business, ethics, or regulation?

These questions help move the discussion beyond individual headlines and toward a broader understanding of media trends.

## Dataset

The dataset was collected from **NewsAPI** using 18 AI-related keywords. These keywords were chosen to capture both broad AI concepts and specific tools, companies, or debates that frequently appear in the news.

Examples of tracked keywords include:

- ChatGPT
- Claude
- Gemini
- Grok
- OpenAI
- Anthropic
- Google AI
- Meta AI
- Deep Learning
- Neural Networks
- LLM
- AI Ethics
- AI Safety
- AI Regulation
- Microsoft AI

For each keyword, up to 100 recent English-language articles were retrieved. The most useful text fields from each article were the **title** and **description**, which were combined into a single text input for analysis. This created a dataset large enough to identify trends while still being focused on current AI media coverage.

### Dataset Summary

- **Source:** NewsAPI
- **Articles collected:** Approximately 1,800
- **Language:** English
- **Collection strategy:** Keyword-based search
- **Time focus:** Recent articles sorted by recency

This dataset reflects a snapshot of contemporary AI reporting and provides a practical foundation for sentiment and topic analysis.

## Methodology

The project follows a three-stage NLP pipeline. Each stage plays a different role in turning raw news articles into meaningful analytical results.

### 1. Data Collection and Preprocessing

The first stage involved gathering article data and preparing the text for analysis.

For each selected keyword, the project queried NewsAPI and collected article metadata such as title, description, source, and publication date. Because raw news text often includes noise that can interfere with analysis, the text needed to be cleaned before any modeling could be performed.

The preprocessing steps included:

- combining article titles and descriptions into one text field
- converting all text to lowercase
- removing URLs and unnecessary special characters
- cleaning punctuation and formatting issues
- tokenizing the text into smaller units for modeling

This step is important because sentiment analysis and topic modeling perform better when irrelevant noise has been removed and the text is in a consistent format.

### 2. Sentiment Analysis

The second stage focused on measuring the emotional tone of each article. Rather than relying on one sentiment model, the project used two different methods so that the results could be compared.

#### VADER

VADER produces a compound sentiment score ranging from **-1 to 1**. A score closer to -1 indicates more negative language, a score near 0 suggests neutral language, and a score closer to 1 indicates more positive language.

VADER is especially useful for short-form text and is widely used in sentiment analysis because it handles emotionally loaded wording well.

#### TextBlob

TextBlob also assigns a polarity score from **-1 to 1**, where negative values suggest negative sentiment and positive values suggest positive sentiment.

TextBlob provides a second perspective on sentiment and helps confirm whether the overall results are stable across methods.

Using both models adds credibility to the findings. If the two tools identify similar patterns, it suggests that the sentiment trends are not simply the result of one model’s design.

### 3. Topic Modeling

The third stage used **Latent Dirichlet Allocation (LDA)** to identify recurring themes in the article collection.

Topic modeling helps answer a different question than sentiment analysis. Sentiment tells us *how* articles are framed emotionally, while topic modeling helps show *what* those articles are mainly about.

To do this, the cleaned article text was converted into a dictionary and corpus format. An LDA model was then trained to discover **6 latent topics** across the dataset. Each topic is represented by a cluster of words that frequently appear together, allowing articles to be grouped into common themes such as product launches, policy debates, regulation, research, or industry competition.

Once topics were assigned, the project compared sentiment across these groups. This made it possible to see whether certain types of AI stories were consistently more positive or negative than others.

## Results

## Overall Sentiment Distribution

The sentiment analysis showed that AI news coverage has a **slight positive skew overall**. This means that, across the full dataset, positive sentiment appears somewhat more often than negative sentiment.

At the same time, the majority of articles remain close to **neutral**. This suggests that much of AI reporting is descriptive and informational rather than strongly emotional. News stories often explain product updates, company announcements, or policy developments in a relatively factual tone.

Even so, there is also a noticeable **negative tail** in the sentiment distribution. This indicates that some articles use clearly negative language, usually when discussing issues such as:

- regulation
- safety risks
- bias and ethics
- misinformation
- labor market disruption

This combination of neutral dominance, slight optimism, and a meaningful negative tail creates a more nuanced picture than a simple “AI news is positive” conclusion.

## Sentiment by Keyword

When sentiment is broken down by keyword, clear differences emerge.

Keywords tied to products, major AI platforms, or new technical capabilities tend to appear in more positive coverage. Terms such as **ChatGPT** and **Gemini** are often associated with stories about innovation, new releases, adoption, and competitive growth. These themes naturally produce more optimistic language.

By contrast, keywords related to governance and social concern—such as **AI Regulation** and **AI Ethics**—tend to appear in more negative articles. These stories often emphasize uncertainty, risk, accountability, or the need for control.

This result shows that media sentiment about AI is highly dependent on context. The same broad topic—artificial intelligence—can be framed very differently depending on whether the article is discussing opportunity or concern.

## Comparison Between Sentiment Models

One of the most important findings is that **VADER and TextBlob produced similar overall sentiment patterns**. Their scores were strongly positively correlated, meaning both methods generally agreed about which articles were more positive and which were more negative.

This matters because sentiment analysis can sometimes be sensitive to the specific tool being used. If two separate models point in the same direction, confidence in the findings increases. In this project, the agreement between VADER and TextBlob suggests that the observed media patterns are not random or model-specific.

## Topic Modeling Insights

The topic modeling results revealed that AI news coverage can be organized into several recurring thematic groups. While each topic is represented mathematically through word distributions, the themes can be interpreted in more familiar terms, such as:

- product announcements and releases
- company competition and strategy
- technical research and development
- regulation and governance
- ethics and safety concerns
- economic or labor-related impact

These topic groups also showed different average sentiment levels. Topics centered on innovation and new capabilities tended to be more positive, while topics focused on policy and risk were more negative.

This strengthens the overall interpretation of the project: sentiment is not random across AI news. Instead, it is closely tied to the type of story being told.

## Key Findings

### 1. AI News Coverage Is Slightly Positive Overall

Across the dataset, positive sentiment appears somewhat more frequently than negative sentiment. This suggests that the media often frames AI as a source of progress, innovation, and opportunity.

### 2. Neutral Reporting Still Makes Up Most Coverage

Despite the slight positive tilt, many articles remain near neutral. This indicates that a large share of AI journalism is explanatory or descriptive rather than strongly emotional.

### 3. Negative Sentiment Is Concentrated in Risk-Focused Stories

Articles about ethics, safety, regulation, and job loss are more likely to use negative language. This creates a distinct group of cautionary reporting within the broader AI conversation.

### 4. Product and Innovation Stories Tend to Be More Positive

Coverage focused on specific AI tools, launches, and advancements is generally framed more optimistically than coverage focused on policy or societal consequences.

### 5. Sentiment Patterns Are Consistent Across Models

Because VADER and TextBlob produced similar results, the overall findings are more reliable and less dependent on a single analysis method.

### 6. Topic Modeling Explains Why Sentiment Varies

The LDA model shows that different themes carry different emotional tones. In other words, sentiment changes because the media is covering different sides of AI, not because coverage is inconsistent or random.

## Key Takeaways

- AI news coverage is best understood as **mixed but structured**, not simply positive or negative.
- The overall tone leans slightly positive, largely because innovation-focused stories are common.
- Neutral reporting remains dominant, showing that much of the media coverage is informational.
- Negative sentiment appears most strongly in discussions of regulation, ethics, and broader societal risk.
- Sentiment analysis becomes more convincing when multiple models point to the same conclusions.
- Topic modeling adds important context by showing that the emotional tone of AI coverage depends heavily on the subject being discussed.

## Conclusion

This project provides a data-driven view of how artificial intelligence is discussed in the news. Rather than treating AI coverage as one single narrative, the analysis shows that media framing is shaped by the specific angle of the story.

Overall, AI coverage leans slightly positive, especially when articles focus on product development, innovation, and business momentum. However, this optimism is balanced by a substantial set of articles centered on regulation, safety, ethics, and labor concerns, which tend to be framed more negatively.

The strongest contribution of this project is that it combines sentiment analysis with topic modeling. Sentiment scores reveal the tone of the coverage, while topic modeling explains why that tone changes across different parts of the AI conversation. Together, these methods show that AI media coverage reflects both excitement and caution at the same time.

In the end, the results suggest that the public narrative around AI is not one-dimensional. It is a blend of technological optimism, practical curiosity, and social concern. That makes sentiment analysis especially useful here: it helps quantify how those competing narratives appear in the media and how they vary depending on what kind of AI story is being told.

## Future Improvements

This project could be extended in several ways to produce even deeper insights.

One possible improvement would be to track **sentiment over time**, which would make it possible to see how public framing changes in response to major product launches, policy debates, or global events.

Another extension would be to include **international or non-English news sources**, allowing for comparison across regions and media systems.

The project could also compare sentiment **by publisher or outlet**, which might reveal whether some organizations consistently frame AI more positively or negatively than others.

A more advanced version of the analysis could use **transformer-based language models** for sentiment classification, which may capture context more effectively than lexicon-based methods.

Finally, the results could be presented in an **interactive dashboard**, making it easier to explore trends by keyword, topic, date, or source.
