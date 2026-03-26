# Auto Tagging Support Tickets Using LLMs

## Task Objective
Support systems often receive large volumes of customer tickets, making manual categorization inefficient and time-consuming.  
**Objective:** Automatically classify support tickets into predefined categories using Large Language Models (LLMs), comparing Zero-Shot and Few-Shot approaches without traditional training.

## Dataset Used
- No labeled dataset was used.
- Synthetic examples created for testing, such as:
  - "I was charged twice for my subscription"
  - "App crashes when uploading image"
  - "I cannot login to my account"
  - "Where is my order? It is delayed"
  - "Please add dark mode feature"

## Models Applied
1. **Zero-Shot Learning**
   - Model: `facebook/bart-large-mnli`
   - Classifies tickets without task-specific training.
   - Outputs top tags with confidence scores.

2. **Few-Shot Learning**
   - Model: `gpt2` (prompt-based)
   - Uses example tickets with tags to improve contextual understanding.
   - Outputs tags in predefined format: `Tag1, Tag2, Tag3`.

## Key Results and Findings
- **Zero-Shot Learning:** Fast, works well for general ticket classification; top tags usually relevant, confidence scores provide insight.
- **Few-Shot Learning:** Improves contextual understanding and aligns better with examples; formatting may vary slightly.
- **Overall Insights:**
  - LLMs can effectively classify support tickets without labeled datasets.
  - Few-shot prompting enhances performance but is sensitive to prompt design.
  - Potential future improvements include fine-tuning on real ticket datasets and using advanced LLMs like GPT-4 or LLaMA for higher accuracy.
