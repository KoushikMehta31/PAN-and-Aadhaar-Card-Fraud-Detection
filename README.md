## 📌 Project Title: Pan and Aadhaar card Fraud Detection using MySQL and Power BI

---

## 📝 Project Overview

This project involved the design and implementation of a **Fraud Detection and Employee Analytics System** aimed at improving the accuracy of identity data and monitoring attendance-related anomalies.

The system focused on:
- Validating employee identity documents such as **PAN** and **Aadhaar** numbers
- Detecting irregularities in attendance behavior like duplicate swipes
- Creating an interactive **Power BI dashboard** using **MySQL**, **Excel**, and **DAX** for real-time monitoring and decision-making

---

## 🛠️ Tools & Technologies Used

| Tool/Technology | Role in the Project                                      |
|------------------|----------------------------------------------------------|
| **MySQL**         | Data extraction, transformation, validation logic using SQL queries |
| **Power BI**      | Building interactive reports and dashboards              |
| **Excel (CSV)**   | Data cleaning, formatting, and import into BI tools      |
| **DAX**           | Calculating KPIs, measures, and applying filters in Power BI |

---

## 🔍 Identity Validation Rules

### ✅ PAN Card Validation

**Structure**: `AAAAA9999A` (10-character alphanumeric)

**Validation Rules**:
- First 5 characters: Letters `[A-Z]`
- Next 4 characters: Digits `[0-9]`
- Last character: Letter `[A-Z]`
- 5th character must match:
  - First letter of the **surname**
  - If surname is unavailable, use the **first name’s initial**

📌 **Examples**:
- `ABCDE1234M` – valid for `Koushik Mehta`
- `ABCDK1234P` – valid if only `Koushik` is available without surname

---

### ✅ Aadhaar Card Validation

**Structure**: 12-digit numeric code

**Validation Rules**:
- Must be exactly 12 digits
- Cannot start with 0 or 1
- Should pass the **Verhoeff algorithm** (checksum validation)
- No alphabet or special characters allowed

📌 **Examples**:
- `2345 6789 1234` ✅ Valid  
- `0123 4567 8901` ❌ Invalid (starts with 0)  
- `1234-5678-9012` ❌ Invalid (contains symbols)

---

## 📊 Power BI Dashboard Highlights

An interactive dashboard was developed to visualize fraud detection metrics and employee activity patterns.

### Key Features:
- Identification of invalid PAN and Aadhaar numbers
- Attendance anomalies (duplicate or missing swipes)
- Fraud pattern analysis across departments or locations
- Employee-wise drill-down for targeted investigation
- Time-based and department-wise filtering using slicers

### 🔢 DAX Measures Used:
- `Total Invalid PAN`
- `Suspicious Aadhaar Count`
- `Fraud % by Department`
- `Missing Swipe Count`

---

## 🖥️ Dashboard Structure & Explanation

The Power BI dashboard is divided into multiple interactive pages:

### 1. **Fraud Detection Overview**
- 🔹 **KPI Cards** show:
  - Total Employees
  - Invalid PANs
  - Suspicious Aadhaar Counts
  - Duplicate Swipes
- 🔹 **Department-wise Fraud Bar Chart**
- 🔹 **Filter Controls (Slicers)** for:
  - Month, Department, and Location
- 🔹 **Data Table** listing all flagged entries

### 2. **Attendance Analysis**
- 🔹 **Duplicate Swipe Tracker** – Highlights employees with multiple in/out entries on the same day
- 🔹 **Missing Swipe Heatmap** – Visualizes patterns of missing swipes across days and weeks
- 🔹 **Drill-down Filters** – Allows user to view anomalies for individual employees

### 3. **Identity Validation Summary**
- 🔹 **PAN Validation Pie Chart** – Valid vs. Invalid PAN formats
- 🔹 **Aadhaar Format Breakdown** – Categorizes Aadhaar entries by validity
- 🔹 **Fraud Distribution by Department**

This dashboard enables easy exploration of fraud trends, suspicious employee activity, and identity inconsistencies—making it valuable for HR, compliance, and internal audit teams.

---
