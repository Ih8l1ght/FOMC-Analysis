# FOMC-Analysis



<details>
<summary>## Introduction and brief history</summary>

From the dawn of ancient civilizations, expectations have fundamentally shaped the decision-making processes of consumers, investors, governments, and other economic actors. In the annals of classical thought, Aristotle alludes to the prescient activities of Thales of Miletus, who, through “precise” astronomical observations, anticipated a bountiful olive harvest. This prediction allowed Thales to capitalize on the future scarcity of olive presses, thereby influencing market prices. Such anecdotes underscore the enduring significance of expectations in economic behavior.

However, it was not until 1972 that expectations were formally integrated into economic theory through the pioneering work of economist Robert Lucas. Lucas's formulation of the Rational Expectations Hypothesis revolutionized economic thought by positing that economic agents, utilizing all available information, construct rational forecasts about the future state of markets. This hypothesis challenged the prevailing Keynesian orthodoxy, emphasizing that individuals and institutions form expectations based on an understanding of policy impacts and economic conditions, rather than relying on historical data alone.

One institution where expectations wield unparalleled influence is the Federal Reserve of the United States (Fed). The Fed's ability to shape economic outcomes through monetary policy renders its communications and signaling highly consequential. The anticipation of interest rate changes, quantitative easing, or other monetary interventions can precipitate significant shifts in market behavior, influencing everything from investment decisions to consumer confidence.

The importance of the Fed's signaling extends beyond the immediate financial markets, impacting broader economic conditions such as inflation, employment, and economic growth. As such, the Fed's role in managing expectations is not merely a matter of academic interest but a pivotal aspect of contemporary economic management. 

The objectives of the Federal Reserve (Fed) are straightforward: promoting maximum employment, stabilizing prices, and moderating long-term interest rates. However, the implementation of these goals is anything but simple. Effective signaling of future policy decisions is crucial for economic agents' planning. A minor misalignment between the Fed’s signals and its enacted policies can have disruptive consequences. A notable recent instance is the collapse of Silicon Valley Bank in 2023, which failed to anticipate the Fed's early interest rate increases, highlighting the significant impact of communication mismatches.

Conversely, direct communication by the Federal Reserve carries inherent risks. Markets often overreact to such signals, leading to instability. This dynamic was evident in 2014 when the Fed announced a scaling back of its expansionary monetary policy and quantitative easing. Markets overinterpreted this shift, resulting in significant global volatility, an event now known as the "taper tantrum."

Therefore, it is expected that the Federal Reserve will interpret its own signaling from the perspective of economic agents. With the proliferation of Large Language Models (LLMs) and Natural Language Processing (NLP) in financial markets for tasks ranging from predicting stock prices to analyzing policymakers’ speeches, the Fed logically would scrutinize its communications using exactly the same tools..

</details>

## Relevant Research

Natural Language Processing (NLP) has become a pivotal technique in analyzing signaling, even detecting nuances imperceptible to humans. While its primary application has been in predicting stock price fluctuations through web scraping, the focus is increasingly shifting towards anticipating Federal Reserve decisions.

One of the earliest explorations of using Natural Language Processing (NLP) in finance was conducted in 2012, focusing primarily on basic techniques (Schilder, 2012). A more comprehensive study followed in 2015, emphasizing the prediction of stock market volatilities (Ding et al., 2015). Research on analyzing and forecasting Federal Reserve policies remains limited due to inherent challenges. Unlike stock markets, there is no clear benchmark for comparison. Consequently, text data can be analyzed, but measuring the precision of these analyses is difficult, if not impossible.

A clear example of this is Doh et al. (2021), who compared Federal Reserve statements to alternative statements with slightly altered tones, demonstrating that NLP models can detect even subtle differences. Kim and Gallen (2023) conducted a study to assess the precision of these models by manually labeling a sample of Fed statements, finding that different models produced varying results. There have also been efforts to adapt existing NLP models to better interpret central bank language, with CentralBankRoBERTa (Pfeifer & Marohl, 2023) being a notable example.

## Methodology & Results

To determine whether the Federal Reserve is adapting its signaling approach and modifying the formulation of its official reports and speeches in response to the increasing use of NLPs, it is essential to examine a specific report over time. For this project, we focus on the Federal Open Market Committee's (FOMC) data, which serves as a primary indicator of the Fed’s communication strategies. The FOMC communicates through three main channels: speeches, meeting minutes, and press conference transcripts. Meeting minutes are particularly valuable for our analysis as they are published post-meeting and undergo thorough scrutiny by policymakers, in contrast to speeches and transcripts, which can exhibit greater volatility due to their real-time, human-delivered nature.

Meeting minutes from the Federal Open Market Committee (FOMC) are available dating back to 1996. However, due to evolving Federal Reserve policies and administrative changes, a more recent starting point—2014—was selected, coinciding with Ben Bernanke’s departure as Chair of the Federal Reserve. Data was downloaded from the Federal Reserve's official website, totaling 83 meeting minutes. These minutes were scraped from the website and saved as individual text files. Most existing studies on Fed minutes fall into two categories: analyzing the minutes sentence by sentence or aggregating all texts into one corpus. This project takes a different approach by analyzing each minute individually.

The central question of this project—whether there is evidence of the Federal Reserve adjusting its communication in response to NLP analysis—is addressed in multiple facets. The task would be simpler if we were merely identifying text generated by Large Language Models (LLMs). However, our focus is on detecting whether the Fed's communication has been modified to counteract the analytical tools employed by investors, rather than on the generation of the text itself.

The primary approach hinges on the notion that any shift in the Federal Reserve's signaling strategy would render recent texts distinct from earlier ones. Consequently, some discernible difference should be present. In this context, "observable" does not imply noticeable to humans but detectable by NLP models and LLMs. Thus, the analysis employs various criteria specifically designed to influence these models.

**The tests include:**
- Lexical diversity
- Average sentence length
- Usage of idioms
- Readability Score 
- Topic modeling
- Sentiment analysis

### Lexical Diversity & ASL

The initial step involves converting the PDFs, automatically downloaded from the Federal Reserve’s website, into text files for greater analytical flexibility. This process is straightforward. The analysis then employs two simpler metrics: lexical diversity and average sentence length. Lexical diversity is calculated by dividing the number of unique words by the total number of words. Initially, results showed extreme volatility in both metrics. Upon further examination, the inclusion of Fed predictions in samples up to 2020 significantly reduced average sentence length. After excluding samples with an average sentence length (ASL) of less than 20, we observed a downward trend line with persistent volatility. Notably, the lexical diversity score exhibited high volatility due to the use of various niche theoretical terms, but it stabilized at a high level post-2021.


### Topic Modeling

Following this, topic modeling was applied based on the premise that text comprises a mixture of topics, each representing a distribution of words. Various methods were tested: initially, Latent Dirichlet Allocation (LDA) was utilized to categorize the words in each meeting minute into topics. To capture more niche topics and identify differences, the number of passes and topics was increased. However, even after expanding the number of topics to 20 and doubling the passess, the outcomes remained largely consistent. Due to the generation of a high number of topics (1760), a detailed examination of each is impractical. Given their similarities and minimal differences, a word cloud effectively summarizes all generated topics in a single visualization.

### Readability Formulas

#### 1. Flesch-Kincaid Grade Level
Estimates the US school level to comprehend the text:

$ \text{FKGL} = 0.39 \left( \frac{W}{S} \right) + 11.8 \left( \frac{Syll}{W} \right) - 15.59 $

#### 2. Gunning Fog Index
Estimates the years of formal education required to understand a text on a first reading:

$text{GFI} = 0.4 \left( \left( \frac{W}{S} \right) + 100 \left( \frac{CW}{W} \right) \right)$

#### 3. SMOG Index
Estimates the years of education needed to understand a text:

$\text{SMOG} = 1.0430 \cdot \sqrt{ \frac{PSW \times 30}{S} } + 3.1291 $

#### 4. Coleman-Liau Index
Estimates the US school grade level necessary to understand a text, based on characters per word:

$\text{CLI} = 0.0588 \left( \frac{C}{W} \times 100 \right) - 0.296 \left( \frac{S}{W} \times 100 \right) - 15.8 $

#### 5. Automated Readability Index
Provides a readability score based on characters per word and words per sentence:

$\text{ARI} = 4.71 \left( \frac{C}{W} \right) + 0.5 \left( \frac{W}{S} \right) - 21.43 $

#### 6. Dale-Chall Readability Score
Estimates the comprehension level required, considering familiar words and sentence complexity:

$\text{DCRS} = 0.1579 \left( \frac{DW}{W} \times 100 \right) + 0.0496 \left( \frac{W}{S} \right) $


The scores were normalized to enable comparability. From 2014 to 2020, the indices tracked closely, but diverged afterward—a notable anomaly given that they do measure the same parameters. The Dale-Chall readability score and the Coleman-Liau index slightly increased post-2020, while others, such as the Automated Readability Index, sharply decreased. This divergence suggests a structural change in the text: the introduction of more specialized vocabulary, leading to longer words but shorter sentences (as indicated by the increase in the Dale-Chall score but the decrease in the Automated Readability Index). Given that the indices measuring the proportion of complex, non-everyday words show an increase in specialized terms, the shift likely reflects a reduction in redundant explanations of the same concepts.







