# PAN and Aadhaar Card Fraud Detection Analysis

## Overview

The **PAN and Aadhaar Card Fraud Detection Analysis** is a data analytics project built using **Excel**, **MySQL**, and **Power BI**. It aims to detect anomalies and fraudulent entries in employee identity records and attendance logs.

---

## Tech Stack:

- **Excel**:
  - Data cleaning and formatting
  - Handling NULL or duplicate entries

- **MySQL**:
  - SQL queries for validation, joining tables, fraud detection logic
  - PAN and Aadhaar checks using REGEXP and CASE conditions

- **Power BI**:
  - Dashboard development and visual representation of fraud
  - Use of DAX to create KPIs and calculated metrics

---

## PAN and Aadhaar Validation Rules

### ✅ PAN Card Validation Rules

- **Format**: `AAAAA9999A` (10-character alphanumeric)

- **Validation Rules**:
  - First 5 characters: Must be uppercase letters `[A-Z]`
  - Next 4 characters: Must be digits `[0-9]`
  - Last 1 character: Must be an uppercase letter `[A-Z]`
  - The **5th character** must match:
    - The first letter of the **surname** (last name)
    - If the surname is **not available**, then it must match the first letter of the **first name**

📌 **Examples**:
- ✅ `ABCDM1234O` – Valid for employee **Koushik Mehta**  
- ✅ `ABCDK1234P` – Valid for employee **Koushik** (no last name)  
- ❌ `ABCD12345A` – Invalid format (not 5 letters + 4 digits + 1 letter)
- ❌ `A1CDE1234M` – Invalid: contains numbers in the letter section

---

### ✅ Aadhaar Card Format

- Format: 12-digit numeric code
- Rules:
  - Must be 12 digits
  - No alphabets or special characters

📌 Examples:
- ✅ `2345 6789 1234` → Valid
- ❌ `A123 4567 8901` → Invalid (contains alphabet)
- ❌ `1234-5678-9012` → Incalid (Contains symbols)

---

## 📊 Power BI Dashboard Overview

The final Power BI dashboard provides a detailed and interactive visualization of PAN and Aadhaar card fraud detection across departments, years, and genders.

---

### 🖼️ Dashboard Preview

![PAN & Aadhaar Card Fraud Detection Dashboard](assets/dashboard.png)


---

### 🔍 Key Dashboard Highlights

#### ✅ Top-Level KPIs (Cards)
- **Total Employees**: `4.00K`
- **Total PAN Errors**: `3.17K`
- **Total Aadhaar Errors**: `0.99K`

#### ✅ Filters
- **Gender Filter**: Toggle between male/female employees
- **Time Range Slider**: View fraud trend from 2020 to 2025

---

### 📈 Visual Breakdown

| Visualization | Description |
|---------------|-------------|
| **Count of Invalid Employee by Department Name** | Shows number of Aadhaar & PAN errors across departments (HR, Production, Logistics, etc.) |
| **Count of Invalid Employee by Joining Year** | Displays how PAN/Aadhaar errors are distributed from 2020–2025 |
| **Invalid Employee Breakdown (Pie Chart)** | Visualizes total PAN vs Aadhaar errors as a % share |
| **Invalid Count by Department (Donut Chart)** | Department-wise share of total fraud cases |
| **Invalid Comments Analysis** | Categorizes the type of error (e.g. `5th character not matching`, `alphanumeric Aadhaar`, `incorrect digit count`, etc.) |
| **Invalid Employees by Gender (TreeMap)** | Gender-wise distribution of invalid employees (e.g. 2.47K Male, 1.54K Female) |


### 🔽 Download Dashboard

📂 **[Download Power BI File](assets/dashboard.png)**  
> Open with Power BI Desktop to view full slicers, visuals, and interactivity.


