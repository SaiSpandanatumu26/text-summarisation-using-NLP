# text-summarisation-using-NLP
Key Features of This Code:
Hybrid Approach (Extractive + Abstractive Summarization):

Extractive Phase: First, the most important sentences are selected using TF-IDF, reducing the length of the input text.

Abstractive Phase: The reduced text is then passed to the BART model to create an abstractive summary, which helps retain a coherent, context-rich summary.

Unlimited Input Size:
The text size is not restricted by BART's 1024-token limit. The extractive method significantly reduces the input text size before abstractive summarization.
This allows you to summarize very large documents, articles, or books without manually chunking the text.

Customization:
You can control how much the text is reduced in the extractive phase (number of sentences) and the length of the final abstractive summary (max_length and min_length).
Provides interactive control for easy parameter adjustments.

GPU Support:
Checks for GPU availability and uses it if available, otherwise defaults to CPU.

Additional features of this code:
number of key sentences for extractive phase:
num_sentences Parameter: This is the number of key sentences that will be extracted from the text before the abstract summarization is applied.
For example, if you set num_sentences=5, the extractive summarizer will select 5 of the most important sentences from the original input text, based on a ranking mechanism (in this case, using TF-IDF scores).

max length for abstractive summary:
The max_length parameter defines the maximum number of tokens (words or subwords) that the final abstractive summary can contain.
This acts as a cap on how long the summary will be. If the generated summary reaches this length, the summarizer will stop producing additional tokens.

min length for abstractive summary:
The min_length parameter specifies the minimum number of tokens (words or subwords) that the generated summary should contain.
This ensures that the summary is not too short, allowing the model to include essential details and context.
