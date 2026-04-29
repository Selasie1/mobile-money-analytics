#  Mobile Money Transaction Analytics — Africa Focus

> An end-to-end data science project analysing 6.3 million mobile money 
> transactions using the PaySim dataset, with a focus on fraud detection, 
> customer segmentation, and credit scoring insights relevant to 
> African retail banking.

---

##  Business Context

Mobile money is the backbone of financial services across Africa. 
Platforms like M-Pesa, MTN MoMo, and Vodafone Cash process millions 
of transactions daily — yet many customers remain invisible to 
traditional credit bureaus due to lack of formal financial history.

This project analyses transaction behaviour to:
- Detect fraudulent transactions using statistical signals
- Segment customers by activity level
- Build a creditworthiness proxy score from transaction history
- Provide actionable recommendations for a bank operating in Africa

---

##  Key Findings

### Fraud Detection
| Finding | Value |
|---|---|
| Total transactions analysed | 6,362,620 |
| Fraud rate | 0.129% |
| Total fraud value | $12.06 billion |
| Average fraud transaction | $1,467,967 |
| Average legitimate transaction | $178,197 |
| Fraud detection rule accuracy | 97.6% |

**The Zero-Balance Signal:** 98.1% of all fraud transactions drain 
the sender's account to exactly zero. A simple rule — flag any 
TRANSFER or CASH_OUT that empties an account — catches 97.6% of 
all fraud cases.

**Fraud only occurs in 2 transaction types:**
- TRANSFER — fraud rate 0.77%
- CASH_OUT — fraud rate 0.18%
- PAYMENT, CASH_IN, DEBIT — zero fraud

### Customer Segmentation
| Segment | Definition | Key Insight |
|---|---|---|
| Active | 10+ transactions | Highest value, highest fraud risk |
| Moderate | 3-9 transactions | Growing relationship |
| Thin-file | 1-2 transactions | Largest group, unbanked population |

### Africa-Specific Insight
Thin-file customers lack formal credit history but their mobile 
money behaviour reveals creditworthiness signals. Transaction 
frequency, consistency, and diversity can proxy for credit scoring 
— the same approach used by M-Shwari in Kenya and MoMo Pay in Ghana.

---

##  Tools & Technologies

| Category | Tools |
|---|---|
| Data Analysis | Python, pandas, NumPy |
| Visualisation | matplotlib, seaborn, Power BI |
| Machine Learning | scikit-learn, MinMaxScaler |
| Environment | Jupyter Notebook, VS Code |
| Version Control | Git, GitHub |

---

##  Project Structure

---

##  How to Run

**1. Clone the repository**
```bash
git clone https://github.com/Selasie1/mobile-money-analytics.git
cd mobile-money-analytics
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

**3. Download the dataset**
- Go to kaggle.com/datasets/ealaxi/paysim1
- Download and place CSV in `data/raw/`

**4. Run notebooks in order**
```bash
jupyter notebook
```
Open and run:
- `notebooks/01_eda.ipynb`
- `notebooks/02_fraud_analysis.ipynb`
- `notebooks/03_customer_segmentation.ipynb`

**5. Open the dashboard**
- Open `powerbi/dashboard.pbix` in Power BI Desktop

---

##  Dashboard Preview

The Power BI dashboard has 3 pages:
- **Overview** — transaction volume, value, and fraud KPIs
- **Fraud Analysis** — fraud patterns, detection rule performance
- **Customer Segments** — transaction mix, value by type, fraud rates

---

##  Business Recommendations

**1. Implement Zero-Balance Fraud Alert**
Flag any TRANSFER or CASH_OUT that drains an account to zero 
in real time. This single rule catches 97.6% of fraud with 
minimal engineering effort.

**2. Enhanced Monitoring for High-Balance Accounts**
Fraudsters target accounts with 8x the average balance. 
Apply step-up authentication for large TRANSFER transactions 
above a defined threshold.

**3. Mobile Credit Scoring for Thin-file Customers**
Build a credit scoring model using transaction frequency, 
consistency, and diversity as features. This unlocks credit 
products for the unbanked population — a major growth 
opportunity across African markets.

---

##  Author

**Selasie**  
Data Scientist | Machine Learning Engineer  
📧 delbertpecker@gmail.com  
🔗 linkedin.com/in/selasie-pecker0a830a145  
📍 Accra, Ghana

---

##  Dataset

PaySim Mobile Money Simulation  
Source: kaggle.com/datasets/ealaxi/paysim1  
Original research based on real M-Pesa transaction data from Africa




## s Dashboard Preview

The Power BI dashboard has 3 pages:
- **Overview** — transaction volume, value, and fraud KPIs
- **Fraud Analysis** — fraud patterns, detection rule performance  
- **Customer Segments** — transaction mix, value by type, fraud rates

> The .pbix file exceeds GitHub's 100MB limit.
> To view the dashboard, download the file from this 
> Google Drive link: https://drive.google.com/file/d/1_nto_-ht9F_bDv2rhHURyR-CmT8LBfoW/view?usp=sharing
> Or view the PDF preview in reports/dashboard_preview.pdf