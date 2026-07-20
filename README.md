# Megadhoodh Cable & Internet Billing

A simple, single-file billing app for a Cable TV / Internet (LCO/ISP) business —
built for a non-technical operator, with a Tamil/English language switch.

## Features

- **Customers** — name, phone, address, area, package, STB/connection number, balance due
- **Bulk Add** — paste or upload a list to add many customers, packages, or employees at once
- **Collect Payment** — pick a customer, enter the amount, choose Cash or UPI
- **UPI QR codes** — generates a scannable payment QR for your bank account, per payment
- **Tickets / Complaints** — log and track customer issues (No Signal, Internet Down, Billing, STB) through Open → In Progress → Resolved
- **WhatsApp / SMS sharing** — send a payment receipt or a customer's balance statement directly via WhatsApp
- **Reports** — filter collections by date range, employee, or area
- **Areas, Packages, Employees** — manage all of these from the Manage tab
- **Tamil / English** — switch the whole interface with one tap
- **Google Drive backup** (when used inside Claude) — export/restore your data

## Running it

This is a single self-contained HTML file — no build step, no server required.

- **Locally:** just open `index.html` in any browser.
- **GitHub Pages:** enable Pages on this repo (Settings → Pages → Deploy from branch → `main` → `/root`), then visit the generated URL.

## Data & privacy

All customer, payment, and employee data lives in **browser storage on the device
you're using** — nothing is sent to a server, and nothing is stored in this repository.

⚠️ **Do not commit real customer data into this repo.** `index.html` in this repository
intentionally ships empty — no pre-loaded customers, packages, or employees. Add your
data after opening the app, using **Customers → Bulk Add**, **Manage → Packages → Bulk Add**,
and **Manage → Employees → Bulk Add** (or manual entry).

If you keep any exported backup files (`.json`, `.txt`, `.csv`) for your own reference,
keep them **outside this repo** or in a private repo only — see `.gitignore`.

## Tech notes

- Plain HTML/CSS/JavaScript, no framework, no build tools
- QR codes via [qrcodejs](https://github.com/davidshimjs/qrcodejs) (loaded from cdnjs)
- Fonts: Space Grotesk, Inter, Noto Sans Tamil (Google Fonts)
- WhatsApp/SMS sharing uses standard `wa.me` and `sms:` links — nothing is sent automatically, you still tap Send yourself
