
# Build a RAG API with FastAPI

I learnt the concepts and followed the guidance provided by nextwork.org

Learning and exploring has always been my top priority, Building alongside learning is a great way to explore the concepts and understand how things work. 

## Introducing Project!

In this project, I built a RAG pipeline with FAST API and ChromaDB. This helped me understand how RAG works and give me an insight on how to retrieve only relevant information using the FAST API and ChromaDB.  I'm interested in this because I want to learn about AI and stay in the race of AI.

### Key tools and concepts

The key tools I used include FastAPI, ChromaDB, Ollama and Swagger UI.  Key concepts I learnt include RAG pipeline, metadata filtering, embeddings.

### Challenges and wins

This project took me approximately 60 minutes.The most challenging part was dealing with version issues and embeddings.

---

## Performing RAG Manually

In this step, I performed a manual RAG demo to understand RAG, and setup an environment and everything to build an AI powered API.
RAG stands for Retrieval Augmented Generation


### Understanding the three parts of RAG

I performed RAG manually by:
1. Retrieval - Found Relevant text(personal information)
2. Augmentation - added the text to the  prompt
3. Generation - AI used that context to generate accurate answer.
The three parts are Retrieving, Augmentation, Generation

### Comparing the two AI models

The key difference I noticed is nomic-embed-text is an embedding tool that converts texts into vectors to capture the meaning of texts and qwen2.5:0.5b is a chat model that generates answers from the text-personal information provided.

---

## Building a Personal Knowledge Base

In this step, I created a personal profile document, build a python script that loads, chunks, and stores my profile as embedddings. Embeddings are texts converted to vectors.


### Creating the profile document

I included information about myself so that it can generate answers grounded and accurate to my profile. I used RAG to give AI my personal profile.

### How semantic search finds relevant chunks

When I ask a question, ChromaDB finds the chunks whose vectors - which are locally stored at ./chroma_db - are closest in that high-dimensional space. This is semantic search.

---

## Creating the RAG API with FastAPI

In this step, I built an API that has /ask endpoint that is going to answer questions using grounded answers . I tested it using Swagger UI.

### How the /ask endpoint works

When a question comes in, my endpoint retrieves 2 most relevant chunks from ChromaDB, augments the prompt by combining those chunks with question, and generates a grounded answer using qwen2.5:0.5b.

### Testing with Swagger UI

I tested my API by asking "What is my name?" and  "What are my hobbies?" The AI answered with the grounded answers-with correct detailes. The context used was the same context that we stored in ChromaDB.

---

## Extending to a Multi-User AI Directory

In this project extension, I'm adding multi-user support because it allows us to add multiple profiles an dlet AI give more personalized context based on the User behind the API.  Multi-tenancy means different users can have different data and one tenant's data is never exposed to another.


### Adding the POST /documents endpoint

In this project extension, I added a POST endpoint that allows users to upload their own profiles. Metadata filtering allows us to filter context based on the user.

### Verifying multi-user filtering

In this project extension, I tested multi-user queries by first adding no user filter and then by adding the user filter for the second test. The filter works because it retrieved only specifieed user's hobbies. Chunks were given user Metadata when stroing in ChromaDB.

---
**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-devops-api)

**Author:** Shreya Kulkarni
**Email:** shreyakulkarni.pp@gmail.com
