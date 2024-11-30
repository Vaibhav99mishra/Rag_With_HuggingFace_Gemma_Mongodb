# Building a RAG System with Gemma, MongoDB, and Open Source Models

This repository demonstrates how to build a Retrieval-Augmented Generation (RAG) system leveraging MongoDB, Gemma language models, and Hugging Face open-source tools. The step-by-step guide walks through the setup of a vector database, embeddings generation, and using the system to perform advanced vector-based search and question answering.

---

## Features

- **Data Sourcing**: Utilizes datasets from Hugging Face to extract and preprocess movie information.
- **Embedding Generation**: Generates embeddings using the `gte-large` model from Hugging Face's SentenceTransformers library.
- **Vector Database Integration**: Configures MongoDB for efficient vector storage and search using MongoDB's vector search index.
- **RAG System**: Implements a system to retrieve the most relevant documents using vector similarity and combines them with a Gemma language model for query answering.
- **Flexible Querying**: Allows users to input natural language queries and retrieve contextual answers based on stored embeddings and metadata.

---

## Prerequisites

Before running the notebook, ensure you have the following installed and set up:

- Python 3.8+
- MongoDB Atlas account with a free or paid cluster
- Google Colab (or a local environment with GPU support)

### Libraries to Install

Run the following commands to install the required libraries:

```bash
!pip install datasets pandas pymongo sentence_transformers
!pip install -U transformers
!pip install accelerate
```

---

## Steps in the Notebook

### Step 1: Installing Libraries

Installs the required Python libraries for interacting with MongoDB, generating embeddings, and handling large language models.

### Step 2: Data Sourcing and Preparation

Loads the `embedded_movies` dataset from Hugging Face, preprocesses it, and ensures data integrity by removing empty or irrelevant fields.

### Step 3: Generating Embeddings

Generates vector embeddings for movie plots using the `gte-large` embedding model from SentenceTransformers.

### Step 4: Database Setup and Connection

- Sets up a MongoDB cluster on MongoDB Atlas.
- Configures a database and collection for storing embeddings and metadata.
- Ingests preprocessed data into the MongoDB collection.

### Step 5: Creating a Vector Search Index

Configures a vector search index in MongoDB to enable efficient and accurate vector-based queries.

### Step 6: Establishing Data Connection

Utilizes `PyMongo` to connect to the MongoDB cluster and insert data from the pandas DataFrame.

### Step 7: Performing Vector Search

Implements a pipeline for vector-based search using MongoDB's `$vectorSearch` aggregation framework. Retrieves the most relevant documents based on query embeddings.

### Step 8: Query Answering with Gemma

Uses the Gemma language model to generate a natural language answer based on the retrieved documents. The response includes details such as movie titles, plots, and genres.

---

## How to Run

1. **Setup MongoDB Atlas**:
   - Create a MongoDB cluster on Atlas.
   - Copy the connection URI and whitelist the IP for your Python environment.

2. **Update Environment Variables**:
   - Store the MongoDB URI in an environment variable named `MONGO_URI`.

3. **Run the Notebook**:
   - Execute the notebook cells step by step in Google Colab or a local environment.

4. **Query the System**:
   - Enter a query (e.g., "What is the best romantic movie to watch?") and retrieve results augmented with Gemma's response.

---

## Sample Output

**Query**: What is the best romantic movie to watch and why?

**Response**:
```
Title: Shut Up and Kiss Me!
Plot: Ryan and Pete are 27-year-old best friends in Miami, each searching for the perfect woman...
```

**Generated Answer**:
Based on the search results, the best romantic movie to watch is **Shut Up and Kiss Me!** because it explores the complexities of love and relationships in a funny and heartwarming way.

---

## Technologies Used

- **Hugging Face**:
  - Datasets
  - SentenceTransformers
  - Transformers
- **MongoDB**:
  - Atlas
  - Vector Search Index
- **Gemma Language Model**: Open-source large language model for answering complex queries.
- **Python Libraries**:
  - Pandas
  - PyMongo
  - Accelerate

---

## Key Learnings

- Efficiently integrating vector-based search with MongoDB.
- Generating embeddings and storing them in a scalable database.
- Leveraging RAG systems to enhance natural language query answering.

---

## Author

**Vaibhav Mishra**  
- GitHub: [Vaibhav99mishra](https://github.com/Vaibhav99mishra)  
- LinkedIn: [Vaibhav Mishra](https://www.linkedin.com/in/vaibhav-r-mishra/)  
```
