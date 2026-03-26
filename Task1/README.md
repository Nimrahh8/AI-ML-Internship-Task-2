# BERT Text Classification on AG News Dataset

## Task Objective
The goal of this task is to build a text classification model that can automatically classify news articles into predefined categories using a transformer-based model. The model is trained to achieve high accuracy and F1-score, and it can perform inference on new, unseen headlines.

---

## Dataset Used
- **Dataset:** AG News
- **Number of Classes:** 4  
  - 0 → World  
  - 1 → Sports  
  - 2 → Business  
  - 3 → Sci/Tech
- **Training Samples:** ~120,000  
- **Test Samples:** ~7,600

---

## Models Applied
- **Transformer Model:** BERT (`bert-base-uncased`) for sequence classification
- **Tokenizer:** BERT tokenizer for text preprocessing
- **Training Framework:** Hugging Face `Trainer`
- **Evaluation Metrics:** Accuracy and weighted F1-score
- **Inference Pipeline:** Hugging Face `text-classification` pipeline

---

## Key Results and Findings
- Achieved high **accuracy** on the AG News dataset.
- Weighted **F1-score** confirms balanced performance across all classes.
- Model effectively captures the contextual meaning of news headlines.
- Transformer models outperform traditional ML methods for text classification.

### Sample Predictions
| Headline                                           | Predicted Label | Score  |
|----------------------------------------------------|----------------|--------|
| Stock markets surge as inflation fears ease       | Business       | 0.95   |
| Champions League final: Real Madrid defeats Liverpool | Sports      | 0.97   |
| NASA launches new Mars exploration rover          | Sci/Tech       | 0.94   |
| UN Security Council meets over Ukraine conflict  | World          | 0.93   |

### Limitations
- Training is computationally expensive.
- Requires GPU for faster performance.

### Future Improvements
- Train on the full dataset without subsampling.
- Hyperparameter tuning for better accuracy.
- Experiment with advanced models like RoBERTa or DistilBERT.
