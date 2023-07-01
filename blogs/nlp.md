## Things to know:
- What is sequential data?
- Common Evaluation parameters
    - Accuracy
        This is a commonly used evaluation metric for classification problems. It is simply the number of correctly predicted examples divided by the total number of examples.
    - Precision, Recall, and F1-Score
        These are three other metrics used for evaluating classification problems. 
        - Precision is the proportion of true positives (tp) over the sum of true positives and false positives (fp), calculated as tp / (tp + fp). 
        - Recall is the proportion of true positives over the sum of true positives and false negatives (fn), calculated as tp / (tp + fn). 
        - F1 score is the harmonic mean of precision and recall, calculated as 2 * (precision * recall) / (precision + recall).
    - BLEU (Bilingual Evaluation Understudy) Score
        This metric is typically used for tasks like machine translation where the output is a sequence of words. It measures the proportion of n-grams in the model's output that also appear in the target output, weighting shorter sequences more heavily.
    - ROUGE (Recall-Oriented Understudy for Gisting Evaluation) Score
        This is used for tasks like text summarization. There are several versions of ROUGE, such as 
        - ROUGE-N : measures the overlap of N-grams between the system and reference summaries 
        - ROUGE-L : measures the longest common subsequence
        - ROUGE-S : measures skip-bigram statistics
    - Perplexity
        This is used to evaluate language models. It's a measure of how well a probability model predicts a sample. A lower perplexity means the probability distribution is a better model for the data. In the context of language models, it's calculated as the inverse probability of the test set, normalized by the number of words.
