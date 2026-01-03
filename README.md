# 🏦 ShihabTaxEngine.bd
**A Professional, Future-Ready Income Tax Calculation Engine for Bangladesh.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Year: 2025-2026](https://img.shields.io/badge/Compliant-FY_2025--26-indigo)](https://nbr.gov.bd)

TaxEngine.bd is a high-performance, client-side web utility designed for the evolving tax landscape of Bangladesh. Unlike static calculators, this app features a **Decoupled Law Engine**, allowing users to modify tax slabs, thresholds, and rebate logic directly from the UI without touching the source code.

## 🚀 Key Features
- **Dynamic Law Configuration:** Toggle "Admin Mode" to update slabs (5%, 10%, 15% etc.) as per new Finance Acts.
- **Three-Way Rebate Logic:** Complies with Section 78 of the Income Tax Act 2023 (Lowest of 15% investment, 3% income, or 10L BDT).
- **Wealth Surcharge System:** Automatically triggers surcharges for assets exceeding 4 Crore BDT.
- **Local Persistence:** Your tax laws and personal data are saved in `localStorage`—no database required.
- **Mobile-First UI:** Built with Tailwind CSS for a premium, responsive experience.

## 🛠️ Tech Stack
- **Frontend:** HTML5, Tailwind CSS (Styling)
- **Reactivity:** [Alpine.js](https://alpinejs.dev/) (Lightweight, declarative state management)
- **Formatting:** `Intl.NumberFormat('en-IN')` for Laks/Crore comma placement.

## 📊 Code Analysis: The Tax Engine
The core of the application lies in the `taxEngine()` function. It separates **User Data** from **Legal Rules**.

### The Rule Schema
The law is modeled as a JSON object, making it "Future-Ready":
```javascript
law: {
    thresholds: { general: 350000, female: 400000 },
    slabs: [
        { limit: 100000, rate: 5 }, 
        { limit: 400000, rate: 10 },
        // ... more slabs
    ],
    rebateIncomeRate: 3, 
    minTax: 5000
}
