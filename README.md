# ERC-4626 Stablecoin Vault Analytics

Analyze and compare the best-performing ERC-4626 stablecoin vaults across multiple blockchains using Python. This project scans, collects, and analyzes vault performance data, focusing on quantitative finance metrics such as returns, Sharpe, and Sortino ratios.

---

## 🚀 Project Overview

- **ERC-4626** is a standard for tokenized yield-bearing vaults on Ethereum and EVM-compatible chains.
- This project discovers ERC-4626 vaults, collects their historical share price data, and analyzes their performance.
- Vaults are categorized into risk-free (lending) and volatile (with drawdown) types.
- The analysis covers both recent (last 3 months) and all-time performance.

---

## 📊 Features

- **Automated vault discovery** across blockchains using HyperSync and web3.
- **Historical price data extraction** for all detected vaults.
- **Quantitative analytics**: returns, Sharpe ratio, Sortino ratio, and more.
- **Separation of vault types**: lending (risk-free) vs. volatile.
- **Efficient data storage** in Parquet format for fast analytics.
- **Jupyter notebook workflow** for interactive exploration.

---

## 🗂️ Project Structure

```
stablecoin_vaults/
├── notebooks/
│   └── 01_scanning_all_vaults.ipynb   # Main notebook for scanning and analysis
├── database/
│   ├── chain-1-vaults.parquet         # Vault metadata
│   ├── vault-db.pickle                # Raw vault detection data
│   └── vault-prices.parquet           # Historical price data
├── requirements.txt                   # Python dependencies
└── README.md
```

---

## ⚡ Quickstart

### 1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/erc4626-vault-analyzer.git
cd erc4626-vault-analyzer
```

### 2. **Install Dependencies**
```bash
pip install -r requirements.txt
```

### 3. **Set Up Your RPC Endpoint**
Get an Ethereum RPC URL (e.g., from [Infura](https://infura.io/) or [Alchemy](https://alchemy.com/)).

```bash
export JSON_RPC_URL="https://mainnet.infura.io/v3/YOUR_PROJECT_ID"
```

### 4. **(Optional) Set Output Directory**
By default, output is saved to `~/.tradingstrategy/vaults/`.  
To save in your project folder:
```bash
export OUTPUT_FOLDER="/path/to/your/project/database"
```

### 5. **Run the Notebook**
Open and run `notebooks/01_scanning_all_vaults.ipynb` in Jupyter.

---

## 📈 Example Usage

```python
import pandas as pd

# Load vault metadata
vaults = pd.read_parquet("database/chain-1-vaults.parquet")
print(vaults.head())

# Load historical price data
prices = pd.read_parquet("database/vault-prices.parquet")
print(prices.head())
```

---

## 🧮 Analysis Ideas

- **Compare vault returns** over different timeframes
- **Calculate Sharpe and Sortino ratios** for risk-adjusted performance
- **Visualize share price growth** for top vaults
- **Identify best-performing stablecoin vaults** across chains

---

## 🛠️ Dependencies

- `web3`
- `web3-ethereum-defi[hypersync]`
- `pandas`
- `numpy`
- `scipy`
- `matplotlib`
- `seaborn`
- `tqdm`
- `pyarrow` or `fastparquet`
- `jupyter`
- (see `requirements.txt` for full list)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to fork the repo and submit a pull request.

---

## 📄 License

MIT License

---

## 🙏 Acknowledgements

- [ERC-4626 Standard](https://eips.ethereum.org/EIPS/eip-4626)
- [web3.py](https://github.com/ethereum/web3.py)
- [web3-ethereum-defi](https://github.com/tradingstrategy-ai/web3-ethereum-defi)
- [Infura](https://infura.io/), [Alchemy](https://alchemy.com/)

---

**Happy analyzing!** 🚀

