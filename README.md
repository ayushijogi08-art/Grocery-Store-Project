# 🛒 Grocery Management Dashboard

A comprehensive, real-time web application designed to manage the daily operational workflows, inventory, and financials of a retail grocery store. 

**🔴 Live Demo:** https://ayushi-grocery-app.netlify.app

## 💻 Tech Stack

* **Frontend:** HTML5, Tailwind CSS, Vanilla JavaScript (ES6 Modules)
* **Backend & Database:** Firebase Firestore (NoSQL, Real-time syncing)
* **Authentication:** Firebase Auth 
* **Data Visualization:** Chart.js

## 🚀 Core Features

* **Real-Time Inventory Management:** Add new products, categorize them, and set pricing and initial stock. The system visually flags low inventory (under 10 units).
* **Point of Sale (POS) & Purchase Logging:** Record daily sales to customers and stock purchases from vendors. The system handles multiple items per invoice and calculates total costs dynamically.
* **Credit & Cash Handling:** Every transaction can be logged as 'Cash' (settled immediately) or 'Credit' (added to the customer's or vendor's pending balance).
* **Operational Expense Tracking:** Log day-to-day business expenses (e.g., rent, utility bills, disposable goods) separately from inventory purchases.
* **Contact Ledgers:** Dedicated databases for Customers and Vendors. The system tracks running balances, showing exactly who owes the store money and who the store owes.

## ⚙️ How It Works (Business Logic & Data Flow)

The application operates on a strict cause-and-effect loop between user input and real-time database updates:

1. **Data Entry:** The operator inputs a transaction (Sale, Purchase, or Expense) via the respective form, selecting items from a dynamically populated dropdown list tied to current inventory.
2. **Automated Processing:** * Logging a **Sale** automatically *decreases* the stock of the selected items.
    * Logging a **Purchase** automatically *increases* the stock of the selected items.
    * If a transaction is marked as **"Credit,"** the system locates the specific Customer or Vendor profile and adjusts their outstanding balance.
3. **Real-Time Rendering:** The DOM listens for Firebase snapshot changes and instantly updates tables, charts, and dashboard totals without requiring a page reload.

## 📊 System Outputs

By feeding data into the system, the user generates the following outputs:
* **Daily Summaries:** Immediate calculation of "Today's Sales," "Today's Expenses," and "Today's Net Profit."
* **Financial Reports:** Structured income vs. expense reports filtered by custom date ranges.
* **Visual Analytics:** Interactive bar charts displaying the top 5 highest-volume products and top 5 revenue-generating products.
* **Automated Invoicing:** Itemized lists generated for every logged transaction.
* **Balance Sheets:** Clear status outputs for every contact (e.g., "Credit Due: ₹500", "Overpaid: ₹50", or "Settled").

