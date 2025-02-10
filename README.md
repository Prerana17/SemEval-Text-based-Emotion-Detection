# SemEval: Text-based Emotion Detection
## Key Concepts
Emotion Detection, Large Language Models (LLMs), BERT, RoBERTa, Multi-label Classification

## Key Findings/Results
* The study achieved a high F1 score by fine-tuning the RoBERTa model, showing significant success in predicting inputs. 
* BERT and RoBERTa models were trained to identify emotions in text-based input. The emotions were categorized into five categories: joy, fear, sadness, surprise, and anger.
* The F1 score improved significantly with weight adjustments in the binary cross-entropy loss function: The initial F1 score was around 0.60 for underrepresented emotions. Post-adjustment, F1 scores increased to approximately 0.75-0.80.
* RoBERTa model enhancements resulted in better generalization and performance: Validation loss decreased from 0.5904 to 0.1694, and the F1 score increased from 0.4775 to 0.7531 over 20 epochs.

 
    <img src="https://github.com/Prerana17/SemEval-Text-based-Emotion-Detection/blob/main/graphs/f1_score_plot.png" width="600" class="center">

  
## Methodology
* The dataset used for this project was from the SemEval Competition 2025, specifically Track A: Multi-label Emotion Detection. The dataset includes key columns such as ID, Text, and binary labels for emotions like anger, sadness, joy, fear, and surprise. Data pre-processing involved handling emojis, contractions, acronyms, and special characters, using a function defined based on a subsample from the training dataset.

    <img src="https://github.com/Prerana17/SemEval-Text-based-Emotion-Detection/blob/main/graphs/emotions.png" width="600" class="center">


* For the modeling step, the study utilized the Hugging Face model "emotion-english-distilroberta-base" to pre-train the BERT model due to its high technical performance and diverse training datasets. The tokenization process converted raw input text into a format compatible with BERT using the BERT tokenizer. Embeddings were computed for each token to retain the order of tokens.

* The experimental procedures involved fine-tuning the BERT model with RoBERTa by implementing multiple changes to the original BERT pre-training approach. This included dynamic masking and a learning rate warm-up strategy. Class imbalance was addressed by incorporating positive weight adjustments into the binary cross-entropy loss function.
   
    <img src="https://github.com/Prerana17/SemEval-Text-based-Emotion-Detection/blob/main/graphs/class_adj.png" width="600" class="center">

## Interventions and Outcomes

* Weighted Loss Function Adjustments:
    * Increased penalties for misclassifications of minority classes.
    * Improved model sensitivity to minority classes and overall performance.
      
* Fine-Tuning with RoBERTa:
    * Enhanced pre-training with dynamic masking and larger training corpus.
    * Implemented warm-up strategy for learning rate adjustments.
      
* Model Performance Improvements:
    * Significant increase in F1 scores for underrepresented emotions.
    * Better generalization and performance metrics observed.
      
## Limitations
  * Class Imbalance: Despite adjustments, there were still challenges in accurately predicting minority classes.
  * Complex Sentences: Misclassifications occurred in sentences with overlapping sentiments.
  * The limited scope of datasets used may not cover all nuances in real-world emotional expressions.
    
## Conclusions
  * The study successfully demonstrated that fine-tuning BERT with RoBERTa and adjusting the loss function can significantly improve emotion detection from text.
  * High F1 scores and improved performance metrics validate the effectiveness of these methods.
  * The approach fosters a deeper understanding of nuanced emotional expressions in textual data.
    
## Future Research/Recommendations
  * Explore advanced architectures like Retrieval-Augmented Generation (RAG) for better handling of complex sentences.
  * Incorporate additional contextual features to improve accuracy.
  * Conduct further studies using more diverse datasets to enhance model robustness.
  * Address ethical considerations by ensuring transparency in prediction processes and mitigating biases in training data.

