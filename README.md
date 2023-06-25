# Auto_Labeling

This project focuses on auto labeling and topic similarity analysis using the BERTopic library and NLP techniques. T

Methodology

The project follows the following steps:

1. Data Loading: The project assumes that the input data is stored in a CSV file named "AI.csv". It uses the pandas library to load the data into a DataFrame and drops any rows with missing values.
2. Data Preparation: The "Title" and "Abstract" columns are combined into a new column called "new" to create a list of documents for further analysis.
3. Auto Labeling: The BERTopic library is used to perform auto labeling on the documents. The BERTopic class is instantiated with the parameter calculate_probabilities=True to calculate the probabilities for each topic. The fit_transform method is then applied to the documents to obtain the topics and their associated probabilities.
Saving and Loading Model: The fitted BERTopic model and the document list are saved using the pickle library. This allows the model and data to be reused without retraining in future runs.
4. Text Summarization: The T5 language model and tokenizer from the Transformers library are utilized for text summarization. The summarizer pipeline is created to generate summaries for a given list of articles. The generated summaries are then combined to create a headline using the headline_generator model.
5. Topic Label Generation: The generate_topic_label function is defined to generate topic labels by summarizing the articles related to a specific topic. It randomly samples articles and generates summaries until the maximum token length is reached. The summaries are then concatenated and used as input to the headline generator model to generate a label.
6. Topic Filtering: The project demonstrates how to filter documents based on a specific topic ID. The documents corresponding to the desired topic ID are extracted and stored in a list called topic_3.
7. Multiple Topic Label Generation: The run_generate_topic_label function is defined to generate multiple topic labels for a given list of articles. It calls the generate_topic_label function multiple times and stores the generated labels in a list.
8. Similarity Measurement: The measure_similarity_of_topic function measures the similarity between topic labels. It uses cosine similarity to compute a similarity matrix based on the embeddings of the labels. The function returns the similarity matrix, the label with the highest similarity score, and the average score across all pairs.
9. Similarity Matrix Visualization: The plot_similarity_matrix function visualizes the similarity matrix using a heatmap. It uses the Plotly library to create a heatmap trace and layout, and then generates a figure to display the matrix.

