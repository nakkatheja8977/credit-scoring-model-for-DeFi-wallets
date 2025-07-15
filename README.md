# 💳 DeFi Credit Scoring – Aave V2 Wallet Analyzer

This project assigns a **credit score between 0 and 1000** to DeFi wallets based on their historical behavior on the Aave V2 protocol.

## 📌 Objective
To evaluate Ethereum wallets interacting with Aave using a rule-based model that mimics traditional credit scoring.

## 🛠️ Methodology

### Data Used
- Raw Aave V2 transactions (`wallet`, `action`, `amount`, timestamps)
- Actions include: `deposit`, `borrow`, `repay`, `redeemunderlying`, `liquidationcall`

### Feature Engineering
We extract features per wallet:
- Total Deposits, Borrows, Repays, Redeems
- Liquidation Count
- Borrow/Deposit and Repay/Borrow Ratios
- Number of Transactions

### Scoring Logic
```python
score = 1000
score -= 100 × liquidations
score -= 200 × (1 - repay/borrow ratio)
score -= 100 × (borrow/deposit ratio - 1 if > 1)
```
Then scaled between 0–1000 using MinMaxScaler.

## 📈 Architecture

```text
Excel Data (.xlsx)
     │
     ▼
Feature Engineering (pandas)
     │
     ▼
Heuristic Scoring Model
     │
     ▼
wallet_credit_scores.xlsx (0–1000 scores)
```

## 📊 Example Output

See `analysis.md` for score breakdown and insights.

## 🧪 How to Run

```bash
pip install -r requirements.txt
python src/credit_score.py
```

## 📁 Project Structure

```
├── data/                   # Raw transaction file
├── src/                    # Credit scoring script
├── output/                 # Scored wallet output
├── assets/                 # Charts & images
├── README.md               # Overview & usage
├── analysis.md             # Result insights
└── requirements.txt        # Python dependencies
```

## 👨‍💻 Author
Developed by [NAKKA THEJA](https://github.com/nakkatheja)