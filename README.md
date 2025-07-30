📄 Full README.md

# 🧬 get-papers

A Python command-line tool that fetches PubMed research papers based on a search query and filters the results to include only those with **non-academic authors** — such as those affiliated with pharmaceutical or biotech companies.

It saves the results as a CSV file with useful metadata like PubMed ID, title, publication date, company affiliation, and more.

---

## 🚀 Features

✅ Supports full PubMed query syntax  
✅ Fetches PubMed papers using official E-Utilities API  
✅ Filters authors by company-related keywords in affiliation  
✅ Outputs results to console or CSV  
✅ Clean CLI built with Typer  
✅ Poetry-powered for dependency management  
✅ Written with modular, typed Python code

---

## 📦 Installation

### 1. Clone the Repository

>git clone https://github.com/<your-username>/get-papers.git
>cd get-papers

2. Install Poetry
If you don’t have Poetry installed, run:

>(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
Or visit: https://python-poetry.org/docs/#installation

3. Install Dependencies

poetry install

4. Activate the Virtual Environment

poetry shell

💻 Usage
Run from Terminal:

get-papers-list "your pubmed search query" --debug --file output.csv

Example:
get-papers-list "covid vaccine" --debug --file covid_results.csv
Options:
Option	Description
query (argument)	PubMed-compatible search string (required)
--debug, -d	Print debug logs to console
--file, -f	Output CSV file path (default: print to console)

🧠 How It Works
Uses PubMed’s esearch API to find paper IDs for your query

Fetches paper details using efetch API in XML format

Parses author affiliations

Filters for non-academic affiliations using simple heuristics:

Keywords like pharma, ltd, inc, biotech, company, etc.

Collects:

PubMed ID

Title

Publication Year

Non-academic Author(s)

Company Affiliation(s)

Corresponding Email(s)

Outputs the results to CSV or console

🗃️ Output CSV Columns
Column	Description
PubmedID	Unique identifier of the paper
Title	Title of the paper
Publication Date	Year of publication
Non-academic Author(s)	Names of filtered non-academic authors
Company Affiliation(s)	Affiliation strings of those authors
Corresponding Author Email	Email addresses found in affiliations (if any)

🧪 Technologies Used
Typer – CLI app framework

Requests – HTTP API calls

LXML – XML parsing

Rich – Console logging and formatting

Poetry – Dependency and environment management

🧱 Project Structure

get-papers/
│
├── get_papers/           # Package folder
│   ├── __init__.py
│   ├── main.py           # Core logic (API requests, parsing, filtering)
│   └── cli.py            # CLI entry point using Typer
│
├── pyproject.toml        # Project config for Poetry
├── README.md             # 📘 You are here
└── output.csv            # Sample generated CSV (optional)
🧑‍💻 Development & Testing
You can run the CLI while in the project folder like this:

poetry run get-papers-list "cancer immunotherapy" --debug

📤 Publishing to TestPyPI (Bonus)
Build and publish to TestPyPI:

poetry config repositories.test-pypi https://test.pypi.org/legacy/
poetry build
poetry publish -r test-pypi
Install your package from TestPyPI (for testing):

pip install --index-url https://test.pypi.org/simple/ get-papers
✍️ Author
Surya Pratyusha
📧 Email: 21031a0556@gmail.com

📄 License
This project is licensed under the MIT License.
See the LICENSE file for details.

🌟 Acknowledgements
Thanks to the NCBI PubMed API and the open-source community.


---

## ✅ What to do now:

1. In terminal:
   ```powershell
   notepad README.md
