Tax Reform Project — agentic RAG notebook
========================================

Purpose
-------
I build and iterate an agentic RAG (retrieval-augmented generation) notebook that ingests tax policy documents from the Tax_Project folder, indexes them with FAISS, and exposes two tools: a document retriever and a tax calculator.

- **Project files:** [tax_reform.ipynb](tax_reform.ipynb), [requirements.txt](requirements.txt), folder [Tax_Project](Tax_Project).
- **Secrets:** Put `OPENAI_API_KEY` in a `.env` file at the project root.


Notes
-----
- The notebook loads PDFs, TXT, and DOCX files from the `Tax_Project` folder and builds a FAISS index saved to `./faiss_index_agentic_rag`.


---------------------------
- The notebook contains helper tools: `retrieve_documents(query)` — returns retrieved excerpts; and `tax_calculator(...)` — returns marginal tax computations. Both are wired into an agent graph for interactive use.



Files
-----
- [tax_reform.ipynb](tax_reform.ipynb)
- [requirements.txt](requirements.txt)
- [Tax_Project](Tax_Project) (your source documents)
