# Auto_Labeling
Overview

This project is focused on automating the process of generating general labels for given topics based on their associated labels. The goal is to provide a more efficient and standardized approach to labeling topics, reducing the need for manual effort and subjectivity.

Methodology

The project utilizes natural language processing (NLP) techniques and the Transformers library to analyze the labels and extract meaningful information. The following steps are involved in the auto labeling process:

Data Preparation: The input data, stored in an Excel file, is read using the pandas library to create a DataFrame. The DataFrame contains three columns: topic_no, labels, and expert label.
Text Processing: The labels associated with each topic are preprocessed using tokenization, lemmatization, and stop word removal. This step aims to standardize the labels and remove any irrelevant words that do not contribute to the labeling process.
Word Frequency Analysis: The frequency of each word in the labels is analyzed to identify the most common and relevant terms. This helps in capturing the key aspects of the topics and generating informative general labels.
Named Entity Recognition (NER): NER is performed to identify named entities in the labels. Specifically, location-based entities are extracted using part-of-speech tagging and chunking techniques. This allows the generation of location-specific general labels.
General Label Generation: Based on the word frequency analysis and NER results, a general label is generated for each topic. The general label represents a concise summary of the topic, capturing its main keywords and, if applicable, location-specific information.
Transfer Learning: The Transformers library is used to apply pre-trained models for named entity recognition (NER). This helps in extracting organization-based entities from the labels, further enhancing the generated general labels.
Label Assignment: The generated general labels are assigned to each topic and stored in a new column called general_label in the DataFrame.
Usage

To use the auto labeling project, follow these steps:

Ensure that you have Python 3.x installed on your system.
Install the required libraries by running the following command:
