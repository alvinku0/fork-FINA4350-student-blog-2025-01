---
Title: Evaluating LLMs as an Alternative for VADER and FinBERT in Financial Sentiment Analysis (by Group "FinText")
Date: 2025-04-28 00:00
Category: Reflective Report
Tags: Group FinText
---

## Introduction

Sentiment analysis has become an indispensable tool in quantitative finance, where extracting market-moving signals from news requires speed and accuracy. Our News-driven NLP Quant project currently employs two established methods: VADER, a lexicon-based approach, and FinBERT, a financial domain-specific model. With the emergence of sophisticated large language models (LLMs), we must examine whether these advanced systems can surpass traditional techniques in financial sentiment analysis.

This comparative study analyses three real-world financial news cases to assess the strengths and limitations of each approach. The findings provide actionable insights for practitioners considering sentiment analysis methodologies. For this analysis, we utilised DeepSeek as our test LLM.

## Comparative Case Analysis

| Approach    |                | Case 1   | Case 2   | Case 3   |
|-------------|----------------|----------|----------|----------|
| **VADER**   | Title sentiment    | 0        | 0.1531   | -0.4938  |
|             | Summary sentiment  | -0.5106  | -0.2960  | 0.3818   |
| **FinBERT** | Title sentiment    | 0.9480   | -1       | -1       |
|             | Summary sentiment  | 1        | -0.9954  | -1       |
| **DeepSeek**| Title sentiment    | 0.35     | -0.65    | -0.70    |
|             | Summary sentiment  | 0.60     | -0.55    | -0.45    |

---

### Case 1: Market Reaction to Geopolitical News

The article **"Wall Street Rallies as West Hits Russia with New Sanctions"** presented an interesting test case for sentiment analysis. VADER produced a neutral score (0.00) for the title and negative (-0.51) for the summary, failing to capture the market's positive interpretation of events. FinBERT correctly identified positive sentiment with high confidence, while DeepSeek produced scores of +0.35 for the title and +0.60 for the summary. All three methods captured different aspects of the complex sentiment landscape.

### Case 2: Macroeconomic Downturn Report

Analysis of **"Weak Manufacturing Drags Down Q3 GDP Growth"** revealed important differences in approach. VADER produced an unexpected positive score (+0.15) for the negative-leaning headline. FinBERT generated a strongly negative classification, while DeepSeek produced scores of -0.65 for the title and -0.55 for the summary. This case highlights how different methodologies handle gradations in negative sentiment.

### Case 3: Corporate Earnings Announcement

The Zoom earnings report demonstrated the challenges of interpreting mixed financial signals. VADER produced contradictory scores (-0.49 for the title versus +0.38 for the summary). FinBERT consistently classified both components as negative, while DeepSeek provided scores of -0.70 for the title and -0.45 for the summary. This suggests that while transformer-based models may be more consistent than lexicon approaches, they can differ significantly in their interpretation of ambiguous cases.

## Methodological Comparison

### Accuracy and Nuance

The LLM demonstrated great performance in capturing contextual relationships and producing graduated sentiment scores. FinBERT also maintained high accuracy in classification. VADER proved unreliable, particularly with complex financial narratives.

### Computational Considerations

FinBERT offers a favourable balance of speed and accuracy, processing documents in seconds while maintaining domain-specific relevance. VADER provides the fastest processing but at significant accuracy costs. LLMs typically require substantially more computational resources and processing time, which may limit their real-time applications.

### Implementation Factors

FinBERT's pretrained nature makes it immediately deployable, while LLMs require careful prompt engineering and parameter tuning. The interpretability of results also differs significantly, with FinBERT's classifications being more easily traceable to its training data than LLM outputs.

## Practical Recommendations

For high-frequency trading applications where latency is critical, FinBERT represents a robust solution, providing sufficient accuracy with minimal computational overhead. Research-oriented applications that benefit from nuanced interpretation might consider LLM-based approaches, though with awareness of their higher resource requirements. VADER may serve for preliminary screening, but shows significant limitations for final sentiment classification in financial contexts.

## Conclusion

This comparative analysis demonstrates that both LLMs and specialised models like FinBERT have distinct roles in financial sentiment analysis. While LLMs, as evidenced by articles like Fatouros et al. (2023), excel at processing nuanced financial texts and show superior correlation with market reactions, FinBERT remains indispensable for production environments due to its computational efficiency and predictable outputs.

Future work should focus on developing hybrid approaches that leverage the strengths of both specialised financial models and general-purpose LLMs, along with standardised evaluation frameworks for comparing different sentiment analysis methodologies. The financial NLP community would benefit from continued research into more efficient LLM architectures and a better understanding of how these different approaches complement each other in real-world applications.

## References

Fatouros, G., Soldatos, J., Kouroumali, K., Makridis, G., & Kyriazis, D. (2023)  
Transforming sentiment analysis in the financial domain with ChatGPT.  
Machine Learning with Applications, 12, 100508. [https://doi.org/10.1016/j.mlwa.2023.100508](https://doi.org/10.1016/j.mlwa.2023.100508)

