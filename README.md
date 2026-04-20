# Client Monitoring Dashboard

> A static, single-file web app for small business owners to track sales, expenses, debts, and supplier payments — with client loyalty tracking and real-time charts.

## Features

### Core Tracking
- **Client Sales** — Track downpayments, full payments, and auto-calculated net sales
- **Expenses** — Log supplier payments, daily expenses, and operational costs
- **Debt Management** — Monitor what you owe vs what you've paid
- **Supplier Payments** — Track outstanding supplier debt and payment history

### Client Intelligence
- **Auto-generated Client IDs** — Reusable IDs when repeat customers return
- **Loyalty Status** — Auto-updates from New → Returning → Loyal → VIP based on purchase count
- **Client Profile Panel** — View lifetime spend, transaction count, average value, and last purchase
- **Active Clients Metric** — Tracks unique clients active in last 90 days

### Real-Time Analytics
- **Live Metric Cards** — Total Sales, Total Expenses, Net Cash Flow, Remaining Profit, Active Clients, Loyal/VIP %, Outstanding Debt
- **Auto-Calculation Engine** — No "calculate" button needed. Updates instantly when you edit any table
- **3 Charts** — Sales vs Expenses (bar), Profit vs Expenses (pie), Top 5 Clients by spend (bar)
- **Top 5 Suppliers by Debt** — See who you owe the most

### Data Management
- **localStorage Auto-Save** — Close your browser. Data is still there when you return
- **Export to CSV** — One-click export of all tables
- **Inline Editing** — Add, edit, or delete rows directly in the tables

## Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML/CSS/JS | No frameworks needed |
| Chart.js | Charts and visualizations |
| localStorage | Browser-based data persistence |

## How It Works

### Client Sales Table
| Column | Auto-Calculated? | Formula |
|--------|------------------|---------|
| Net Sales | ✅ | DP + Full Payment |
| Client ID | ✅ | Auto-generated (CLT-001, CLT-002) |
| Loyalty Status | ✅ | Based on purchase count for that client |

### Supplier Debt Table
| Column | Auto-Calculated? | Formula |
|--------|------------------|---------|
| Remaining Balance | ✅ | Total Debt - Amount Paid So Far |

### Supplier Payment History
- When you add a payment, it automatically updates the Supplier Debt table

### Dashboard Metrics
| Metric | Formula |
|--------|---------|
| Total Sales | SUM(Net Sales) |
| Total Expenses | SUM(Amount Paid) |
| Net Cash Flow | Total Sales - Total Expenses |
| Outstanding Debt | SUM(Remaining Balances) |

## Getting Started

### Installation
1. Download the `dashboard.html` file
2. Double-click to open in any modern browser (Chrome, Firefox, Edge, Safari)
3. No server required. No installation needed.

### First Time Use
- Sample data is pre-loaded to show you how it works
- Edit or delete sample rows as needed
- All changes save automatically

### Adding Your Data
1. **Client Sales** — Click "+ Add Row", fill in Date, Client Name, Project, DP, Full Payment
2. **Expenses** — Log every expense with date, supplier, description, amount
3. **Debts** — Track what you owe creditors
4. **Supplier Payments** — Log payments to suppliers; debt table updates automatically

### Data Persistence
- Everything saves to your browser's localStorage
- Clear browser data = clears dashboard data (export CSV first as backup)

## Keyboard Shortcuts & Tips

| Action | How To |
|--------|--------|
| Add row | Click "+ Add Row" button below each table |
| Edit cell | Click the cell, type new value, press Enter |
| Delete row | Click the 🗑️ delete button on the row |
| View client profile | Click "Profile" button on any client row |
| Export all data | Click "Export CSV" button at top |

## Loyalty Status Rules

| Status | Requirements | Badge Color |
|--------|--------------|-------------|
| New | 1 purchase | Gray |
| Returning | 2-3 purchases | Yellow |
| Loyal | 4-9 purchases | Blue |
| VIP | 10+ purchases OR total spent > $50,000 | Purple |

## File Structure
