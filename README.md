A complete data analytics project focused on understanding overdraft behavior, account profitability, customer risk segmentation, and refund patterns using Tableau dashboards and a 10,000-row realistic dataset.

This project includes:
- 10K+ synthetic overdraft transaction dataset  
- Tableau dashboard guide  
- LOD-based Top 10 overdraft user identification  
- Account-type profitability logic  
- BRD (Business Requirements Document)  
- Portfolio-ready documentation

- This project analyzes **overdraft behavior** across banking customers to identify:
- High-risk customers  
- Top 10 overdraft users  
- Customer-level cost (Fees + APR + Monthly fee – Refunds)  
- Student account zero-fee behavior  
- Account type profitability  
- Monthly overdraft trends  

This analysis supports:
- Customer risk management  
- Pricing strategy optimization  
- Refund decision-making  
- Customer retention initiatives  

---

## 📈 Dataset Description

The dataset contains **10,000+ rows** generated to resemble real banking transactions.

### **Fields Included**
| Column Name | Description |
|------------|-------------|
| Customer_ID | Unique identifier |
| Account_Type | Select, Silver, Platinum, Primer, Student |
| Transaction_Date | Date of overdraft event |
| Overdraft_Amount | Amount overdrafted |
| Overdraft_Fee | Fee charged (0 for Student accounts) |
| Refund_Amount | Fee refunded |
| Monthly_Fee | Based on account type |
| APR_Charge | 39.49% APR for Select Account only |

---

## 🧮 Key Business Rules

### **1. Student Account Rule**
- Student accounts incur **no overdraft fees**.

### **2. Account Type Monthly Fees**
- Select Silver → £8  
- Select Platinum → £18  
- Primer Account → £31.99  
- Select Account → £0  
- Student → £0  

### **3. APR Calculation (Select Account Only)**
APR = Overdraft_Amount * 0.3949

yaml
Copy code

---

## 🧠 Tableau Calculated Fields (Summary)

### **Monthly Fee**
CASE [Account_Type]
WHEN "Select Account" THEN 0
WHEN "Select Silver Account" THEN 8
WHEN "Select Platinum Account" THEN 18
WHEN "Primer Account" THEN 31.99
WHEN "Student Account" THEN 0 END

markdown
Copy code

### **Top 10 Overdraft Users (LOD Expression)**
{ FIXED [Customer_ID] : SUM([Overdraft_Amount]) }

css
Copy code

Filter:
INDEX() <= 10

yaml
Copy code

---

## 📊 Tableau Dashboards to Build

### **1. KPI Summary**
- Total overdraft fees  
- Refunds  
- Net revenue  
- APR contribution  
- Student account zero-fee impact  

### **2. Overdraft Trends**
- Monthly overdraft amount  
- Monthly fees vs refunds  

### **3. Customer Behavior**
- Heatmap → overdraft frequency by customer  
- Lifetime overdraft via LOD  

### **4. Account Type Impact**
- Monthly fee revenue  
- Overdraft fee revenue  
- Student vs non-student behavior  

### **5. Top 10 Overdraft Users**
- Ranked bar chart  
- Scatter: Overdraft vs Refund  
- Account type badge  

### **6. Net Customer Cost**
- Fee + APR + Monthly Fee – Refund  
- Monthly cost trend  

---

## 🚀 How to Use This Project

1. Clone or download this repository  
2. Open Tableau → Import `overdraft_10000rows.csv`  
3. Add calculations from `docs/Tableau_Dashboard_Guide.md`  
4. Build dashboards (or ask ChatGPT to generate them for you)  
5. Publish on Tableau Public  
6. Share the GitHub repo in your portfolio  

---

## 🤝 Contribution

Feel free to submit pull requests for:
- Additional dashboards  
- ML or prediction models  
- SQL transformations  

---

## 📜 License

MIT License — Free to use for learning, portfolio, and professional projects.

---

## ⭐ Author

**Pradeep Kumar**  
Overdraft & Customer Risk Analytics | Tableau | Power BI | SQL  
