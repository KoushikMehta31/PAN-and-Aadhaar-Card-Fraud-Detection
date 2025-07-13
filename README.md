# 💼 Tata Steel Internship Project (May – July 2025)

## 📌 Project Title: Fraud Detection System using SQL and Power BI

---

## 📝 Overview

This project was developed during my **2-month summer internship at Tata Steel**, where I worked on building a fraud detection and employee analysis system.  
The project focused on validating employee identity data (like **PAN** and **Aadhaar** numbers), analyzing attendance patterns, and creating a dynamic **Power BI dashboard** using **MySQL, DAX**, and **Excel data**.

---

## 🛠️ Tools & Technologies Used

| Tool/Technology | Purpose                                      |
|------------------|----------------------------------------------|
| MySQL            | Writing queries, joining tables, fraud logic |
| Power BI         | Dashboard creation and DAX calculations      |
| Excel (CSV)      | Data cleaning and import                     |
| SAP ABAP/BIS/ETD | Understanding enterprise fraud systems       |
| DAX              | Creating dynamic KPIs and filtering logic    |

---

## 🔍 PAN and Aadhaar Number Validation

### ✅ PAN Card Format:

A valid PAN number must follow this structure:


**Validation Rules**:
- First 5 characters: Letters  
- Next 4 characters: Digits  
- Last character: Letter  
- **5th character** should match:
  - The **first letter of the surname**
  - If surname is missing, match **first name’s first letter**

📌 **Real Use Case**:  
If an employee's name is `Koushik Mehta`, the PAN should be like `ABCDE1234M`  
If surname is missing, for `Koushik`, PAN should start like `ABCDK1234P`

---

### ✅ Aadhaar Card Format:

A valid Aadhaar number should:
