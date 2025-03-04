# Car-ing is Sharing - Chatbot Prototype

## Overview

This repository contains a prototype chatbot application designed for "Car-ing is Sharing," a car sales and rental company. The chatbot leverages Large Language Models (LLMs) to handle various customer inquiries efficiently. This prototype focuses on sentiment analysis, translation, extractive question answering, and summarization tasks.

## Features

- **Sentiment Analysis:** Classifies sentiment of car reviews and evaluates model performance using accuracy and F1 score.
- **Translation:** Translates customer reviews from English to Spanish and assesses translation quality using BLEU score.
- **Extractive QA:** Extracts insights regarding brand perception using a question-answering model.
- **Summarization:** Condenses lengthy reviews into concise summaries.

## Dataset

- `car_reviews.csv`: Contains customer reviews of cars.
- `reference_translations.txt`: Provides reference translations for BLEU score evaluation.

## Implementation Details

- **Sentiment Classification**

  - Uses a pre-trained LLM to classify sentiments in car reviews.
  - Stores results in `predicted_labels` and maps them to binary labels in `predictions`.
  - Computes and stores `accuracy_result` and `f1_result`.

- **Translation & Evaluation**

  - Extracts the first two sentences of the first review.
  - Translates them from English to Spanish.
  - Stores the translated text in `translated_review`.
  - Computes BLEU score for translation quality and stores in `bleu_score`.

- **Extractive Question Answering**

  - Uses `deepset/minilm-uncased-squad2` for QA.
  - Extracts an answer to "What did he like about the brand?" from the 2nd review.
  - Stores inputs (`question` and `context`) and the answer in `answer`.

- **Summarization**

  - Summarizes the last review to \~50-55 tokens.
  - Stores the summary in `summarized_text`.

## Dependencies

- Python 3.8+
- Transformers
- Hugging Face `deepset/minilm-uncased-squad2`
- NLTK (for BLEU score computation)
- Scikit-learn (for evaluation metrics)

## How to Run

1. Install dependencies:
   ```bash
   pip install transformers nltk scikit-learn
   ```
2. Run the script:
   ```bash
   python chatbot_prototype.py
   ```

## Results

- **Sentiment Analysis**: Displays accuracy and F1 score.
- **Translation**: Outputs Spanish translation and BLEU score.
- **Extractive QA**: Extracts brand-related insights.
- **Summarization**: Provides concise review summaries.

## Future Improvements

- Expand sentiment analysis to multi-class classification.
- Enhance translation with fine-tuned models.
- Implement multilingual QA capabilities.

## Contributors

- Aruhi pallavi



