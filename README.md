🧠 Total Experience Extraction

To identify the total years of experience required from job descriptions (JDs), we evaluated multiple approaches:

✅ Best Model: **spaCy Pattern Matcher**
- Extracted valid experience info from **91 out of 200** JDs
- Consistently returned realistic ranges (e.g., "2–5 years")
- Avoided hallucinations or misinterpretations
- Lightweight and fast — no GPU or heavy inference needed
- Easy to tweak patterns for improvements

❌ Limitations of Other Models:
- **BERT QA / RoBERTa QA**: Returned wild outliers (e.g., "40,000 years"), misread unrelated numbers
- **TARS (Zero-shot)**: Accurate but **only worked on 42 JDs**, limited flexibility
- **Prompt-based Heuristics**: Too naive — often picked up unrelated values (e.g., salaries)
- **DistilBERT NER**: Missed numeric patterns unless very explicit in the JD

⚠️ Common Challenges:
- No ground-truth labels for training/evaluation
- Huge variation in JD formats
- Frequent model hallucinations
- Hard to normalize extracted values
- Transformer-based models were slow and inconsistent
