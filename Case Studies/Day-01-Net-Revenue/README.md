# 📈 Case Study 01 – Calculating Net Revenue using SUMX()

## 🎯 Business Requirement

The business wanted to calculate the **Net Revenue** generated from sales after accounting for the discount offered on each transaction.

Since this measure would be reused throughout the project, it was important to calculate it accurately from the beginning.

---

## 🧠 Business Understanding

Revenue is not simply calculated as **Quantity × Unit Price** because customers may receive discounts on their purchases.

To determine the actual revenue earned by the business, the discount needs to be deducted from every transaction.

This Net Revenue measure serves as the foundation for several business metrics such as Profit, Profit Margin, and Average Order Value.

---

## 🛠️ DAX Solution

```DAX
Net Revenue =
SUMX(
    Sales,
    Sales[Quantity] *
    Sales[Unit Price] *
    (1 - Sales[Discount])
)
```

---

## 🔍 DAX Breakdown

- **SUMX()** is an iterator function.
- It evaluates the expression **row by row** for every sale.
- For each transaction, it calculates:
  
  **Quantity × Unit Price × (1 - Discount)**

- Finally, it adds the results from all rows to return the total Net Revenue.

---

## 📊 Dashboard Output

> *(Insert `dashboard.png` here.)*

The KPI card displays the total Net Revenue after considering discounts, providing an accurate view of the revenue earned by the business.

---

## 💼 Business Insight

Using Net Revenue instead of Gross Revenue ensures that business decisions are based on the **actual revenue collected**, rather than the listed selling price.

Since discounts directly affect profitability, this measure becomes the starting point for many future calculations.

---

## 📚 Key Learning

This was my first introduction to an **iterator function**.

I learned that:

- **SUM()** simply adds the values of an existing column.
- **SUMX()** performs a calculation for each row before adding the final result.

Whenever a calculation has to be performed before aggregation, an iterator like function is the right choice.

