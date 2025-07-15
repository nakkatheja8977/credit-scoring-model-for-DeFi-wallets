# 📊 Wallet Credit Score Analysis

This document provides a summary of how wallets performed under the credit scoring model.

## 🔢 Score Distribution

Wallets were grouped into the following score ranges:
- 0–100
- 100–200
- 200–300
- ...
- 900–1000

### 📉 Chart

![Score Distribution](assets/score_distribution.png)

## 📌 Score Bucket Summary

| Score Range | Wallet Count | Avg Score | Min Score | Max Score |
|-------------|--------------|-----------|-----------|-----------|
| 0-99 | 3 | 70.8 | 25.33 | 100.0 |
| 100-199 | 2 | 174.34 | 167.17 | 181.51 |
| 200-299 | 3 | 240.82 | 202.97 | 285.5 |
| 300-399 | 7 | 367.85 | 325.22 | 400.0 |
| 400-499 | 10 | 458.34 | 400.0 | 500.0 |
| 500-599 | 17 | 567.14 | 500.0 | 600.0 |
| 600-699 | 35 | 656.94 | 600.0 | 700.0 |
| 700-799 | 2283 | 799.22 | 700.0 | 800.0 |
| 800-899 | 275 | 823.28 | 800.0 | 900.0 |
| 900-999 | 746 | 990.14 | 900.01 | 1000.0 |

---

## 🟥 Low Score Behavior (0–300)
- Many liquidations and missed repayments.
- Borrowing far exceeds deposits.
- Likely bots or exploit-prone addresses.

## 🟩 High Score Behavior (700–1000)
- Strong repayment history.
- No liquidation calls.
- Balanced deposits and borrows.

## 📦 Notes
- Total wallets: {df.shape[0]}
- Score file: [`wallet_credit_scores.xlsx`](../output/wallet_credit_scores.xlsx)