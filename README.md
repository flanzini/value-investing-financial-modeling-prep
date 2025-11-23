# Value Investing & Financial Modeling

This repository contains a Jupyter notebook that walks through a **value investing workflow**
using Python, including:

- Downloading fundamental and market data for listed companies
- Computing key financial ratios (profitability, leverage, efficiency, valuation multiples)
- Building simple intrinsic value estimates (e.g. discounted cash flow and/or multiples-based)
- Comparing intrinsic value vs. market price to identify potential mispricings

The project is based on the **Financial Modeling Prep (FMP)** API / similar data sources and is
designed as a compact, reproducible example of programmatic fundamental analysis.

---

## Repository Structure

```text
value-investing-financial-modeling/
├─ notebooks/
│  └─ value_investing_financial_modeling.ipynb   # main cleaned notebook (no API keys)
├─ data/
│  └─ .gitkeep                                   # placeholder; put any downloaded data here
├─ src/
│  ├─ __init__.py
│  └─ utils.py                                   # optional helper functions
├─ README.md
├─ requirements.txt
└─ .gitignore
```

> **Important:**  
> The notebook has been cleaned to remove any hard-coded API keys.  
> You should provide your own API key via environment variables or a local `.env` file that is
> **not** committed to Git.

---

## Setup & Usage

### 1. Create and activate a virtual environment (optional but recommended)

```bash
python -m venv .venv
source .venv/bin/activate      # on Windows: .venv\Scripts\activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Provide your API key (if needed)

If the notebook uses an API such as Financial Modeling Prep (FMP), set an environment variable
locally before running:

```bash
export FMP_API_KEY="your_real_api_key_here"      # macOS/Linux

# on Windows PowerShell:
# $env:FMP_API_KEY="your_real_api_key_here"
```

Alternatively, you can create a `.env` file (not tracked by Git) and load it in the notebook
using `python-dotenv`.

**Do not hard-code your API keys in the notebook or commit them to GitHub.**

### 4. Run the notebook

```bash
jupyter notebook notebooks/value_investing_financial_modeling.ipynb
```

Then follow the steps inside the notebook to:

- fetch financial data,
- calculate ratios,
- perform valuation,
- and explore investment ideas.

---

## Notes & Extensions

- You can refactor frequently used logic from the notebook into functions in `src/utils.py`.
- You can add example tickers or a small CSV of symbols (without sensitive data) into `data/`.
- For a more advanced workflow, you could:
  - add backtesting of simple strategies,
  - export valuation results to CSV/Excel,
  - or wrap parts of the analysis into a small CLI or web app.

---

## Disclaimer

This repository is for **educational purposes only** and does not constitute financial advice.
Always do your own research and consider consulting a licensed financial professional before
making investment decisions.
