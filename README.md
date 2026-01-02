📘 Project Overview

The rapid expansion of digital news platforms and social media has significantly increased the volume and velocity of information consumption. While this democratization of information has many benefits, it has also facilitated the widespread dissemination of fake news—misleading or fabricated content that can influence public opinion, create social unrest, and undermine trust in credible information sources. Detecting fake news automatically has therefore become a critical and challenging problem in modern data science and machine learning.

This project presents a comprehensive machine learning–based Fake News Detection system that classifies textual content as real or fake across heterogeneous text domains, specifically long-form news articles and short, informal social media posts. Unlike many existing approaches that focus on a single type of text, this work emphasizes cross-domain generalization, analyzing how well models trained on structured news articles adapt to the fundamentally different characteristics of social media text.

🔍 Motivation and Problem Context

Traditional fake news detection models perform well on news articles because such text is typically long, grammatically structured, and context-rich. However, social media posts are often:

Extremely short (sometimes a single sentence)

Informal and noisy

Rich in stylistic cues such as punctuation, capitalization, and emotive language

Sparse in semantic content

As a result, text representations such as TF–IDF, which rely heavily on word frequency and context, tend to lose discriminative power when applied to short-form content. The core challenge addressed in this project is therefore to bridge the performance gap between long-form and short-form text classification through targeted feature engineering.

🧠 System Design and Methodology

The system was developed and evaluated in three structured stages, each designed to progressively analyze and improve model performance across domains.

Stage 1: Baseline Model on News Articles

In the first stage, the project reproduces the methodology of a published research paper on fake news detection using classical machine learning and ensemble models. A well-known labeled dataset of real and fake news articles was used, consisting of long, structured text.

Key components of this stage include:

Text preprocessing and normalization

TF–IDF vectorization using unigrams and bigrams

Extraction of basic linguistic features such as token count and average word length

Training multiple classifiers including Logistic Regression, Linear SVM, Random Forest, and ensemble methods

This stage achieved very high classification accuracy, establishing a strong baseline and confirming the effectiveness of traditional ML approaches on structured news content.

Stage 2: Cross-Domain Evaluation on Social Media Posts

In the second stage, the same trained models and feature extraction pipeline were applied to a manually collected dataset of one-line social media posts labeled as real or fake. This experiment was designed specifically to test cross-domain generalization.

Due to the short length and informal nature of the text, TF–IDF vectors became sparse and less informative, leading to a significant drop in performance across all classifiers. This outcome highlighted a critical limitation of content-based features when applied to short-form text and confirmed the hypothesis that models trained on news articles do not generalize well to social media data without adaptation.

Stage 3: Feature Engineering for Short-Form Text

To address the limitations observed in Stage 2, the third stage introduced an enhanced feature engineering pipeline inspired by prior research on fake news detection in social media.

In addition to TF–IDF features, the following linguistic, stylistic, and sentiment-based attributes were incorporated:

Lexical diversity (type–token ratio)

Uppercase character ratio

Digit and punctuation ratios

Average word length

Character-level statistics

Sentiment polarity score to capture emotional tone

These features are designed to capture writing behavior and stylistic patterns that are particularly prominent in deceptive or sensational social media content. By combining semantic representations with stylistic and emotional cues, the system was able to significantly improve classification performance on short posts.

📊 Evaluation and Results

The system was evaluated using multiple metrics, including accuracy, precision, recall, and F1-score, with cross-validation applied where appropriate to ensure result stability. Experimental results demonstrated that:

Models achieved near-perfect performance on long news articles using TF–IDF-based features.

Performance degraded substantially when the same features were applied to social media posts.

Introducing domain-specific linguistic and sentiment features resulted in a large improvement in accuracy and F1-score, increasing social media classification accuracy from approximately 68% to over 90%.

These findings confirm that feature design is often more critical than model selection, particularly when dealing with short and noisy text.

🧩 Key Contributions and Insights

Demonstrated the limitations of TF–IDF-based models on short-form text

Showed how cross-domain performance analysis reveals hidden weaknesses in ML pipelines

Designed and implemented an effective feature engineering strategy for social media fake news detection

Highlighted the importance of combining semantic, stylistic, and sentiment features

Delivered an end-to-end system, from research replication to deployment

✅ Final Takeaway

This project illustrates that robust fake news detection requires adapting features—not just models—to the nature of the text. By focusing on domain-specific feature engineering and rigorous evaluation, classical machine learning models can achieve strong performance even in challenging, real-world scenarios such as social media content analysis.
