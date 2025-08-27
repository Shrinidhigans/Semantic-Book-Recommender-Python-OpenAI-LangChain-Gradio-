# Semantic Book Recommender 📚 

This repository contains my implementation of a **Semantic Book Recommender System** as part of an LLM course project.  
The system combines **data preprocessing, sentiment & text classification, and semantic search with embeddings** to recommend books from a dataset of 5,000+ titles.  
An interactive **Gradio UI** lets users explore recommendations in real time.  

## ⚡ What is Semantic Search?  

Semantic search goes beyond keyword matching by understanding the **meaning and context** of queries.  

In this project:  
1. Each book’s metadata is cleaned and enriched (categories + emotions).  
2. Descriptions are embedded into **vector space** using **Google Gemini API**.  
3. Embeddings are stored in-memory with **LangChain’s vectorstore**.  
4. Queries are matched with semantically similar books.  
5. Recommendations are displayed via a **Gradio interface**.  

## 🛠️ Tech Stack  

- **Python** – Core implementation  
- **LangChain** – Embeddings, retriever, orchestration  
- **Pandas / NumPy** – Dataset handling (5k+ books)  
- **Gradio** – Interactive web UI  
- **Google Gemini API** – Embeddings (instead of OpenAI)  

## ⚙️ Workflow  

1. **Data Cleaning**  
   - Removed duplicates, handled missing values, standardized columns.  
   - Saved as `books_cleaned.csv`.  

2. **Categorization (Fiction vs Non-Fiction)**  
   - Classified books into **Fiction** / **Non-Fiction**.  
   - Output in `books_with_category.csv`.  

3. **Sentiment & Emotion Tagging**  
   - Ran **sentiment analysis** + **emotion classification** (happy, sad, inspiring, etc.) on book descriptions.  
   - Output stored in `books_with_emotions.csv`.  

4. **Text Classification**  
   - Additional tagging and description refinement for better retrieval.  
   - Stored in `tagged_description.csv`.  

5. **Embeddings Generation**  
   - Converted descriptions into vector embeddings using **Google Gemini API**.  

6. **Vector Search**  
   - Used **LangChain vectorstore (in-memory)** for similarity search.  
   - Jupyter notebook: `vector-search.ipynb`.  

7. **Gradio Dashboard**  
   - Built multiple UIs (`gradio-dashboard1.ipynb`, `gradio-dashboard2.ipynb`).  
   - User enters query → retriever fetches top matches → results shown interactively.  

## ⚠️ Known Issue  
Currently, the Gradio recommender only returns **3 book suggestions**,  
even though the dataset has **5k+ entries**.  
This seems to be a retrieval or filtering limitation in the pipeline — needs further debugging.  

## 🔮 Future Enhancements  
- Expand recommendations beyond top-3  
- Improve emotion-based personalization  
- Add support for multi-modal inputs (images, speech → mood → recommendations)  
- Deploy as a web app (Streamlit/Next.js frontend)  

## 💡 Reflections  
This project taught me a ton about:  
- Data preprocessing & enrichment (cleaning, tagging, sentiment analysis)  
- Semantic embeddings with **Google Gemini API**  
- Building retrieval-augmented pipelines in Python  
- Deploying quick prototypes using **Gradio**  

It was super fun and insightful to combine **LLMs + emotions + recommendations** into one project 🚀📚  

## 👨‍💻 Author  
Built with ❤️ using **Python, LangChain, Gradio, and Google Gemini API**  
by *Shrinidhi*  



