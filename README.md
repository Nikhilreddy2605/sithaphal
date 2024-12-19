# sithaphal

# TASK 1: PDF Processing
This task is designed to extract, process, and query information from uploaded PDF files using language models and vector search techniques.

Steps:
Library Installation: Installs necessary libraries for PDF extraction (pdfminer.six), embeddings (sentence-transformers), vector search (faiss-cpu), and language model querying (langchain-groq).

File Upload:

Utilizes Google Colab’s files.upload() function to allow users to upload PDF files.
Text Extraction:

Extracts text from uploaded PDFs using pdfminer.high_level.extract_text().
Text Chunking:

Splits the extracted text into smaller, manageable chunks using RecursiveCharacterTextSplitter (chunk size: 1000 characters with a 100-character overlap).
Embedding and Vector Store Creation:

Generates embeddings for the text chunks using the Hugging Face sentence-transformers/all-MiniLM-L6-v2 model.
Stores the embeddings in a FAISS vector database.
Saving the Index:

The FAISS vector store is saved as a pickle file (faiss_store_openai.pkl) for persistent storage.
Querying:

After processing, the user can input a question.
The FAISS vector store is loaded, and a RetrievalQA chain is created using the LangChain framework and the Groq-based language model (llama-3.1-70b-versatile).
The system retrieves the most relevant chunks from the database to answer the query.

# TASK 2: Website Content Processing
This task is aimed at scraping, processing, and querying information from web pages.

Steps:
Library Installation: Installs libraries for web scraping (BeautifulSoup from bs4), HTTP requests (requests), and other dependencies.

 # Web Scraping:

Accepts website URLs from the user.
Sends HTTP requests to the provided URLs using requests.get().
Scrapes the text content from <p> tags in the HTML using BeautifulSoup.
 # Text Chunking:

Similar to Task 1, the extracted text from websites is split into smaller chunks using RecursiveCharacterTextSplitter.
 # Embedding and Vector Store Creation:

Embeddings are generated for the text chunks using the same sentence-transformers/all-MiniLM-L6-v2 model.
These embeddings are stored in a FAISS vector database.
 # Saving the Index:

The FAISS vector store is saved as a pickle file (faiss_store_openai.pkl).
 # Querying:

After processing the website content, users can input a query.
The FAISS vector store is loaded, and a RetrievalQA chain is created using the same llama-3.1-70b-versatile language model.
The system retrieves relevant chunks from the database and answers the user’s query.
Common Features in Both Tasks
Use of FAISS: Both tasks leverage FAISS (Facebook AI Similarity Search) for fast and efficient nearest-neighbor search, enabling quick retrieval of relevant chunks.

Embedding Generation: The Hugging Face sentence-transformers model is used to create embeddings that map text chunks into a high-dimensional space for similarity comparisons.

LLM Integration: LangChain and the Groq-based llama-3.1-70b-versatile language model are used to provide context-aware, high-quality answers to user queries.

Purpose and Applications
Task 1 is useful for processing and querying large volumes of PDF documents, such as research papers, legal documents, or reports.
Task 2 enables users to gather information from online sources, making it useful for research, monitoring competitors, or extracting data from blogs and articles.
Both tasks can work together to build a robust information retrieval system for different content sources.
