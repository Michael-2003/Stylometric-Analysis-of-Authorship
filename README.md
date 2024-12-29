# Stylometric-Analysis-of-Authorship-

## Overview
This project focuses on **author classification** using **stylometric analysis** techniques, leveraging advanced **Large Language Models (LLMs)**. The system is designed to classify texts written by three prominent authors: **Edgar Allan Poe**, **Mary Shelley**, and **H.P. Lovecraft**. By analyzing the unique stylistic features of each author's writing, the model predicts the authorship of a given text.

The project utilizes the **Llama** models with a **Retrieval-Augmented Generation (RAG)** framework to improve the accuracy and robustness of the stylistic analysis process.

## Key Features
- **Author Classification**: Predict the authorship of texts based on writing style.
- **Stylometric Analysis**: Examines sentence structure, word choice, and stylistic nuances to differentiate between authors.
- **Retrieval-Augmented Generation (RAG)**: Enhances the model's performance by incorporating related texts during analysis, improving contextual understanding and reducing hallucinations.

## Models Used
The project employs the following **Llama** models:
1. **Llama 2 (7B)**: A model with 7 billion parameters. It captures stylistic features with moderate accuracy.
2. **Llama 3 (8B)**: A model with 8 billion parameters. It performs reasonably well but struggles with distinguishing certain authors.
3. **Llama 3.2 (3B)**: A model with 3 billion parameters. This model shows the best performance, achieving a high classification accuracy of 94%.

### Weighted Voting Mechanism
- This mechanism combines the predictions from all three models to provide a more reliable and accurate classification. It significantly improves performance by mitigating the individual weaknesses of each model.

## Methodology
1. **Text Representation**: Each text sample is transformed into **high-dimensional embeddings** using **HuggingFace embeddings**, capturing both semantic and stylistic aspects of the text.
2. **Data Retrieval**: The **FAISS (Facebook AI Similarity Search)** and **ChromaDB** are used to index and retrieve relevant samples during the RAG process.
3. **Model Setup**: The analysis leverages **Langchain**, a popular framework for building AI applications, to construct the RAG setup and enhance the models’ performance.

## Dataset
- The dataset consists of **19,579 text samples** authored by Edgar Allan Poe, Mary Shelley, and H.P. Lovecraft. 
- Each sample includes:
  - **ID**: A unique identifier for the text.
  - **Text**: The body of the text to be analyzed.
  - **Author Label**: The corresponding author of the text.

## Results
- **Llama 2 (7B)**: Achieved moderate accuracy of 70%, performing well with some authors but struggling with others.
- **Llama 3 (8B)**: Delivered the lowest accuracy of 54%, indicating difficulty in distinguishing between the authors.
- **Llama 3.2 (3B)**: The best-performing model with 94% accuracy, demonstrating a strong understanding of authorial styles.
- **Weighted Voting**: Combined the strengths of all models, achieving 93% accuracy, closely matching the performance of Llama 3.2 (3B).

![WhatsApp Image 2024-12-29 at 02 09 24_3509b602](https://github.com/user-attachments/assets/4b3bc583-7dd9-4537-a14f-a44d52b05747)


### Predicted Author Distributions
- **Llama 2 (7B)**: Predicted **Edgar Allan Poe (EAP)** most frequently, with moderate misclassifications for **H.P. Lovecraft (HPL)** and **Mary Shelley (MWS)**.
- **Llama 3 (8B)**: Predicted **Edgar Allan Poe (EAP)** often but struggled with other authors, resulting in frequent misclassifications.
- **Llama 3.2 (3B)**: Made balanced predictions across all three authors, capturing subtle stylistic variations effectively.
- **Weighted Voting**: Provided a well-balanced set of predictions, reducing errors by combining the strengths of each individual model.

![WhatsApp Image 2024-12-29 at 02 09 24_28f195d4](https://github.com/user-attachments/assets/a34ba86c-5a7a-4e56-ae0a-d72a8c9687da)


### Confusion Matrices

![WhatsApp Image 2024-12-29 at 02 09 24_34d4c8eb](https://github.com/user-attachments/assets/21393bba-e95e-4c0c-b4f8-2737db9a4fff)


## Conclusion
This project demonstrates the effectiveness of **Llama models** in performing **stylometric analysis** for author classification. By integrating **Retrieval-Augmented Generation (RAG)** and using a **Weighted Voting mechanism**, the models can capture intricate stylistic features and provide accurate authorship predictions.
