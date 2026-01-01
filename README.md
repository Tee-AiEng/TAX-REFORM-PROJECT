Tax Reform Project — agentic RAG notebook
========================================

Purpose
-------
I build and iterate an agentic RAG (retrieval-augmented generation) notebook that ingests tax policy documents from the Tax_Project folder, indexes them with FAISS, and exposes two tools: a document retriever and a tax calculator.

Quick Start
-----------
- **Requirements:** Python 3.11 recommended (Python 3.14 often requires compiling wheels and toolchains).
- **Project files:** [tax_reform.ipynb](tax_reform.ipynb), [requirements.txt](requirements.txt), folder [Tax_Project](Tax_Project).
- **Secrets:** Put `OPENAI_API_KEY` in a `.env` file at the project root.

Setup (PowerShell)
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
.venv\Scripts\python -m pip install --upgrade pip setuptools wheel
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python -m pip install ipykernel
.venv\Scripts\python -m ipykernel install --user --name=taxenv --display-name="Python (taxenv)"
```

Run the notebook
----------------
- Start Jupyter (from the activated venv):
```powershell
.venv\Scripts\python -m notebook  # or jupyter lab
```
- Open [tax_reform.ipynb](tax_reform.ipynb) and choose the kernel `Python (taxenv)`.

Notes
-----
- The notebook loads PDFs, TXT, and DOCX files from the `Tax_Project` folder and builds a FAISS index saved to `./faiss_index_agentic_rag`.
- If pip fails building packages (Rust/toolchain or MSVC errors), either install the required toolchains (Rust, Visual Studio Build Tools) or create a Conda/Miniforge environment with Python 3.11 to avoid many build-from-source issues.
- If scripts (like `pip`) are reported as installed to a `Scripts` folder but not on PATH, add the `...\Python...\Scripts` path to your user PATH or always use `python -m pip`.

What I changed / how I work
---------------------------
- The notebook contains helper tools: `retrieve_documents(query)` — returns retrieved excerpts; and `tax_calculator(...)` — returns marginal tax computations. Both are wired into an agent graph for interactive use.

If you want, next I can:
- finish installing the environment into `.venv` and verify the notebook runs, or
- create a Conda environment (recommended if builds fail).

Files
-----
- [tax_reform.ipynb](tax_reform.ipynb)
- [requirements.txt](requirements.txt)
- [Tax_Project](Tax_Project) (your source documents)

Contact
-------
If you'd like me to run the install now, tell me whether to (A) complete the `.venv` install or (B) create a Conda environment with Python 3.11.
