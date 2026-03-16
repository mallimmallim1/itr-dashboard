# 🇮🇳 ITR Dashboard — India Income Tax Return

> A fully client-side, browser-based Income Tax Return preparation and calculation tool for Indian taxpayers. Supports FY 2024–25 / AY 2025–26 with Old & New tax regime comparison, capital gains computation, loss set-off, PDF export and more.

![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-Web%20%7C%20Mobile-blue)
![Tax Year](https://img.shields.io/badge/AY-2025--26-orange)
![No Backend](https://img.shields.io/badge/backend-none%20required-brightgreen)

---

## 🖥️ Live Demo

> **[Launch ITR Dashboard →](https://mallimmallim1.github.io/itr-dashboard)**
>
> **[Launch ITR Portal (Login + Admin) →](https://mallimmallim1.github.io/itr-dashboard/itr-portal.html)**

---

## ✨ Features

### 🧮 Tax Calculation
- **Old Regime vs New Regime** side-by-side comparison with auto-recommendation
- Correct **tax slabs** for FY 2024–25 (including senior / super senior citizen slabs)
- **Rebate u/s 87A** automatically applied (₹25,000 New / ₹12,500 Old)
- **Surcharge** calculation for income above ₹50L, ₹1Cr, ₹2Cr, ₹5Cr
- **Health & Education Cess** @ 4%
- Net tax payable or refund computation after TDS

### 💼 Income Tab
- **Gross Salary Breakup** — Basic, HRA, DA, Conveyance, Medical, Special Allowance, LTA, Bonus
- **Allowances Exempt u/s 10** — HRA (auto-calculated), LTA, Education, Hostel, Gratuity, Leave Encashment, VRS
- **Standard Deduction u/s 16(ia)**, Entertainment Allowance u/s 16(ii), Professional Tax u/s 16(iii)
- **HRA Exemption** auto-computed from Basic+DA, HRA received, rent paid, metro/non-metro
- **Capital Gains** — Full Section 48 breakdown (FVC, Cost of Acquisition, Cost of Improvement, Transfer expenses)
  - STCG Equity @ 15% u/s 111A
  - LTCG Equity @ 10% above ₹1L
  - STCG Other Assets (at slab rate)
  - LTCG Other Assets @ 20% with indexation
- **Income from Other Sources** — Savings interest, FD/RD interest, ITR refund interest, dividends, gifts
- **Income from House Property** — Rental income with 30% standard deduction u/s 24(a)

### 🧾 Deductions Tab (Old Regime)
- 80C — EPF, PPF, ELSS, LIC, NSC, Tuition (max ₹1,50,000) with live progress bar
- 80D — Health Insurance (self + parents)
- 80E — Education Loan Interest
- 80G — Donations (50% / 100% eligible)
- 80TTA — Savings Account Interest (max ₹10,000)
- 80CCD(1B) — NPS Self Contribution (max ₹50,000)
- 24(b) — Home Loan Interest (max ₹2,00,000)

### 📉 Losses Tab
- **Current Year Losses** — auto-populated from Capital Gains and House Property sections
  - STCL / LTCL on Equity and Other Assets (computed when FVC < Cost)
  - House Property loss (when home loan interest > net rental income)
- **Brought Forward Losses** — STCL, LTCL, House Property Loss, Business Loss (manual entry)
- Correct set-off rules: STCL vs STCG first, then vs LTCG; LTCL only vs LTCG

### 💳 TDS Tab
- TDS on Salary — Form 16 (u/s 192)
- TDS on Non-Salary — Form 16A / 16B / 26AS
- Auto-subtracted from tax liability to arrive at net payable / refund

### 📊 Results Tab
- Summary cards — Gross Income, Tax (Old), Tax (New), Recommended Regime, Savings, TDS
- **Full Old vs New Regime Comparison Table** with Section 48 breakdown
- **Detailed Tax Breakdown** — per regime, with TDS clearly separated from tax liability
- **Tax Slab Table** — showing which slabs are applied and tax at each slab

### 📄 Summary Tab
- Complete ITR summary with personal details (Name, PAN, DOB, Mobile, Email, Address)
- **Download PDF** — opens a clean, print-ready tax summary in a new window
- **Export JSON** — structured data file for the IT Dept's Offline Utility
- **Export XML** — ITR schema format for offline utility import

### 🔐 ITR Portal (`itr-portal.html`)
- **Login page** — Sign In / Register with PAN and email
- **User Dashboard** — returns history, stats, quick actions
- **Admin Console** with 4 tabs:
  - 📊 Analytics — KPI cards, bar chart (registrations), donut chart (regime preference)
  - 👥 Users — Search, Add, Edit, Delete users
  - 📋 Returns — All filed returns across all users
  - 🕐 Activity — Live log of logins, filings, registrations

### 📋 Other Features
- **Form 16 Upload** — drag & drop PDF upload (guidance mode)
- **Financial Year / Assessment Year** dropdowns that sync with each other
- **Live header badge** updates with selected FY/AY
- Date of Birth → auto-sets Age Group (Senior / Super Senior Citizen)
- HRA Exemption u/s 10(13A) auto-populated from HRA Details inputs
- All data stays in-browser — **no server, no backend, no API calls**
- **Print / PDF** support with clean print stylesheet

---

## 📁 File Structure

```
itr-dashboard/
│
├── index.html              ← ITR Dashboard (rename from india-itr-dashboard.html)
├── itr-portal.html         ← Portal with Login & Admin Panel
└── README.md               ← This file
```

---

## 🚀 Getting Started

### Option A — Use directly in browser (no setup)
1. Download both HTML files
2. Double-click `index.html` to open in your browser
3. No server, npm, or installation required

### Option B — Serve locally
```bash
# Python
python -m http.server 8080

# Node.js
npx serve .

# Then open http://localhost:8080
```

### Option C — Deploy to GitHub Pages
1. Fork this repository
2. Go to **Settings → Pages → Source → main branch / root**
3. Access at `https://yourusername.github.io/itr-dashboard`

---

## 🧪 Test Data (Demo Login)

Use these credentials to explore the ITR Portal:

| Role | Email | Password |
|------|-------|----------|
| 👑 Admin | `admin@itr.gov.in` | `Admin@123` |
| 👤 User 1 | `rahul@email.com` | `User@123` |
| 👤 User 2 | `priya@email.com` | `User@123` |

---

## 🗺️ Roadmap

- [ ] Auto-fill from Form 16 PDF parsing (using pdf.js)
- [ ] Advance Tax calculation
- [ ] ITR-2 / ITR-3 form support (currently ITR-1 focused)
- [ ] 26AS / AIS data import
- [ ] Multi-property House Property support
- [ ] Carry forward loss tracking across years
- [ ] Dark / Light mode toggle
- [ ] Backend integration (Node.js / Supabase) for persistent user data

---

## ⚠️ Disclaimer

This tool is built for **educational and informational purposes only**. It is not a substitute for professional tax advice. Always verify computed figures with a Chartered Accountant or on the official [Income Tax e-Filing Portal](https://www.incometax.gov.in) before filing your return.

Tax laws change every year. Always verify the latest slabs, limits, and rules for the relevant Assessment Year.

---

## 📜 License

MIT License — free to use, modify and distribute with attribution.

---

## 🙏 Acknowledgements

- [Income Tax Department of India](https://www.incometax.gov.in)
- [Sora Font](https://fonts.google.com/specimen/Sora) — UI typography
- [JetBrains Mono](https://www.jetbrains.com/legalnotices/jetbrains-mono/) — numbers & code

---

*Built with ❤️ for Indian taxpayers*
