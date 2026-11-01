# Wrench+ — Garage Profit Planner

A standalone, responsive Dutch car-repair garage profitability calculator. No build step, dependencies, login or backend required.

## Features

- Editable numeric steppers for working days, jobs/day, average repair invoice, VAT, parts, consumables, rent and optional owner-compensation target.
- Editable monthly expenses for energy, water, telecom, garage insurance, accounting, tools, diagnostics software, marketing, waste, banking, **transport**, and compliance.
- Instantly recalculates repair revenue excluding VAT, monthly fixed/variable costs, operating surplus and required jobs to break even.
- Monthly/annual view, cost-allocation bar and CSV export.
- Automatically saves values to the current browser's `localStorage`.
- Save/load portable JSON scenarios; change values offline.
- Accessible responsive layout for desktop and mobile.

## Use

Open `index.html` in any modern browser. All calculations run locally.

Default assumptions are illustrative, not verified supplier quotes or a forecast. Customer invoice includes VAT, revenue excludes VAT, and expense fields are entered **net of any recoverable VAT**. The model does not calculate income tax or actual net take-home income.

## Publish on GitHub Pages

1. Create a public repository named `wrenchplus`.
2. Add `index.html` and `README.md` to the repository's root.
3. Open repository **Settings → Pages → Build and deployment**.
4. Select **Deploy from a branch**, `main`, `/ (root)`, and save.
5. The site should become available at `https://YOUR_USERNAME.github.io/wrenchplus/` once deployed.

To upload with git from this folder:

```bash
git init
git add index.html README.md
git commit -m "Add Wrench+ garage profit planner"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/wrenchplus.git
git push -u origin main
```

## Calculation

- Jobs/month = working days × completed jobs/day
- Monthly revenue ex VAT = jobs × invoice / (1 + VAT% / 100)
- Variable costs = jobs × (parts + consumables)
- Fixed costs = rent + monthly overhead
- Operating surplus = revenue ex VAT − variable costs − fixed costs
- Contribution per job = invoice ex VAT − parts − consumables
- Break-even jobs = ceiling(fixed costs / contribution per job), provided contribution is positive

All amounts are in euros. This is a planning tool, not legal, tax or accounting advice.
