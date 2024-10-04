# LangChain & GPT-2 Question Answering System

This repository contains a **question-answering system** integrated with **LangChain** and an open-source **GPT-2 model**. The system retrieves relevant information from a document and generates responses based on user queries. It also supports **conversation memory**, allowing it to retain context across multiple questions.

## Features

- **Document Retrieval**: The system uses FAISS and sentence embeddings to retrieve the most relevant document sections based on user queries.
- **GPT-2 for Answer Generation**: The GPT-2 model from Hugging Face’s `transformers` library generates context-based answers.
- **Memory Buffer**: LangChain’s memory module is integrated to store and retrieve conversation history, allowing the system to handle follow-up questions and maintain context.
  
---

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Memory Integration](#memory-integration)
- [Customization](#customization)
- [Project Structure](#project-structure)
- [Future Enhancements](#future-enhancements)
- [License](#license)

---

## Installation

### Prerequisites

To run the project, you need to have the following dependencies:

- **Python 3.x**
- **Hugging Face Transformers**
- **LangChain**
- **Sentence Transformers**
- **FAISS**
- **OpenAI API** (optional)

### Steps to Set Up the Environment

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/langchain-qa-system.git
   cd langchain-qa-system
   
2.Install the required dependencies:

```bash

pip install -r requirements.txt
```
Alternatively, you can manually install the necessary packages:
```
pip install transformers langchain sentence-transformers faiss-cpu
```

## Usage

1.Load the GPT-2 Model: The GPT-2 model and tokenizer are loaded from Hugging Face. The model will generate text in response to the user’s question, leveraging the context retrieved from the document database.

2.Document Retrieval: You can customize the documents stored in the system. The embedded documents will be indexed using FAISS for efficient retrieval.

3.Running the QA System: You can start asking questions, and the system will return context-based answers.

Example:
python code

#Initialize QA system
qa_system_with_memory = CustomQAWithMemory(retriever, memory)

#Ask a question
response1 = qa_system_with_memory.run("What is LangChain?")
print("Response 1:", response1)

#Ask a follow-up question
response2 = qa_system_with_memory.run("Who developed GPT-2?")
print("Response 2:", response2)


This will generate answers using the GPT-2 model based on the context retrieved from the stored documents.

---

## Memory Integration

The system utilizes LangChain’s ConversationBufferMemory to maintain a conversation across multiple questions. This allows the model to take previous interactions into account and provide coherent responses, enhancing the quality of follow-up answers.

---

## Customization
You can easily customize the following aspects of the system:

Documents: Add or modify the documents used for context retrieval.
Model: Swap the GPT-2 model for another Hugging Face model, like GPT-J or GPT-Neo, depending on your needs.
Memory: The system uses buffer memory, but you can explore LangChain’s other memory mechanisms (e.g., summarizing memory) for more advanced conversation tracking.

---

## Project Structure

├── main.py                  # Main script to run the QA system
├── requirements.txt         # Required Python packages
├── README.md                # Documentation
└── notebooks/               # Optional Jupyter notebooks for testing and experimentation

---

## Future Enhancements

Tool Integration: Adding external tools like web scraping or APIs to provide real-time information and expand the context.
Fine-tuning GPT-2: Training the model on specific domains to improve its performance in specialized areas.
Additional Memory Types: Exploring different memory modules, such as summarizing memory or knowledge graphs, to improve context retention.

---

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## Acknowledgments

LangChain: For providing the framework to build language model-powered applications.
Hugging Face: For the GPT-2 model and tokenizer.
FAISS: For efficient vector search and retrieval.

---
