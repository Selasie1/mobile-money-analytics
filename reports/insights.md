
# Mobile Money Fraud Analysis - Key Insights
## Dataset: PaySim (6.3M transactions, 30 days)

---

## Finding 1: Fraud is rare but extremely costly
- Only 0.129% of transactions are fraudulent (8,213 out of 6,362,620)
- Yet fraud accounts for $12,056,415,427 in total value
- This means fraud punches far above its weight in financial impact

## Finding 2: Fraudsters target high-value accounts
- Average fraud transaction: $1,467,967
- Average legitimate transaction: $178,197
- Fraudsters target accounts with 8x the average balance
- Recommendation: Apply enhanced monitoring to high-balance accounts
  making TRANSFER or CASH_OUT transactions

## Finding 3: Fraud only occurs in two transaction types
- TRANSFER fraud rate: 0.77% (4,097 cases)
- CASH_OUT fraud rate: 0.18% (4,116 cases)
- PAYMENT, CASH_IN, and DEBIT have ZERO fraud cases
- The criminal pattern: TRANSFER stolen funds then CASH_OUT to disappear
- Recommendation: Apply stricter verification for TRANSFER and CASH_OUT
  transactions above a threshold amount

## Finding 4: The Zero-Balance Signal
- 98.1% of all fraud transactions drain the sender account to exactly zero
- Only 56.7% of legitimate transactions end in a zero balance
- A simple rule: flag any TRANSFER or CASH_OUT that empties an account
  catches 97.6% of all fraud (8,012 of 8,213 cases)
- Recommendation: Implement real-time zero-balance alert as a first-line
  fraud detection rule. Add a 30-minute hold on large TRANSFER transactions
  that drain an account completely before allowing CASH_OUT

## Business Impact of Recommendations
If the zero-balance rule had been applied across this 30-day period:
- Fraud caught: 8,012 transactions
- Estimated value protected: $11,760,000,000+
- Fraud missed: 201 transactions (2.4%)
- False positive rate: manageable, requires further tuning with ML model
