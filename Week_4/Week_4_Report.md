# Week 4 Report

## Overview
This week focused on text summarization. I learned how to use the Pegasus model to create abstractive summaries, which means the AI writes new sentences to summarize the text. I also compared this with extractive summarization, which just pulls exact sentences from the original text.

## Task A: Setup and Basic Summarization
I selected three technical articles to summarize. Each article with minimum 200 words. I loaded the google/pegasus-xsum model and gave it the articles. It successfully shrank Article 1 down to 19 words, Article 2 down to 13 words, and Article 3 down to 17 words. 

## Task B: Parameter Exploration
Experimented to see how changing the model settings would affect the summary for Article 1.
* First, I tested the beam search size. A beam size of 1 gave a 20 word summary. A beam size of 4 gave a 24 word summary. A beam size of 8 gave a 19 word summary. Increasing it to 4 made the sentence structure better, but it did not help much as it just made the code run slower.
* Next, I tested the length penalty. A penalty of 0.5 resulted in 24 words, a penalty of 1.0 resulted in 24 words, and a penalty of 2.5 resulted in 34 words. The higher penalty forced the model to generate much longer and more descriptive sentences.

## Task C: Evaluation
Used ROUGE metric to see how well the AI summaried match human written summaries.
ROUGE table-

|  Article  | ROUGE 1 | ROUGE 2 | ROUGE 3 |
| ----------| ------- | ------- | ------- |
| Article 1 | 0.1000  | 0.0000  | 0.1000  |
| Article 2 | 0.1081  | 0.0000  | 0.1081  |
| Article 3 | 0.1000  | 0.0000  | 0.1000  |

These scores are around 10 percent for ROUGE-1 and 0 percent for ROUGE-2. This happens because Pegasus is an abstractive model, so it uses its own words instead of copying mine. Even though the meaning was correct, the exact words did not match the reference, which caused the low scores.

## Task D: Comparative Analysis
Used Sumy LSA to create extractive summaries and compared them to the Pegasus abstractive summaries. The extractive method copies whole sentences directly from the text. It is highly accurate with facts but keeps a lot of extra unnecessary words. The abstractive method is much shorter and reads like a human wrote it, but it carries a small risk of making up words. Extractive methods are better when exact wording is required, like in legal documents, while abstractive methods are better for quick overviews.

## Task E: Domain Checkpoint Comparison
For the bonus task, a complex scientific text was given to two different models. The normal pegasus-xsum model gave a very brief and general one sentence summary. The specialized pegasus-arxiv model kept the complex scientific words like Navier-Stokes. At first, the arxiv model got stuck in a loop and kept repeating the same phrase over and over. I fixed this by adding a no repeat ngram size parameter set to 3 in the code. After that, it worked perfectly. This showed that while specialized models are great for technical words, they need to be tuned carefully so they do not break.