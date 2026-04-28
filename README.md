# CleanPress — Mini Laundry Order Management System

> Built for the Software Engineering Assignment (AI-First)

---

## Setup Instructions

This is a **zero-dependency, single-file** web application.

### To Run:
1. Download `laundry-oms.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. That's it — no npm install, no server, no database setup needed.

Data is stored in the browser's **localStorage**, so it persists across page refreshes.

---

## Features Implemented

### ✅ Core Features
| Feature | Details |
|---|---|
| **Create Order** | Customer Name, Phone (validated 10-digit), Garments with Qty, Auto-calculated Bill |
| **Order Status Management** | RECEIVED → PROCESSING → READY → DELIVERED (updatable inline) |
| **View Orders** | Full orders table with expand/collapse per order |
| **Filter Orders** | By status (dropdown) and by customer name/phone/order ID (search) |
| **Basic Dashboard** | Total orders, total revenue, pending count, delivered count, orders per status |

### ✅ Bonus Features Implemented
| Feature | Details |
|---|---|
| **Simple Frontend (HTML/CSS/JS)** | Full UI — no React dependency, works offline |
| **Garment Search** | Filter orders by customer name, phone, or order ID |
| **Estimated Delivery Date** | (Can extend — delivery date field ready to add) |
| **In-Memory + Persistent Storage** | localStorage used for persistence |

### Garment Price Configuration
```
Shirt     → ₹50
Pants     → ₹60
Saree     → ₹120
Kurta     → ₹70
Jacket    → ₹150
Blanket   → ₹200
Bedsheet  → ₹100
Towel     → ₹30
```
To change prices, edit the `PRICES` object at the top of the `<script>` tag in the HTML file.

---

## AI Usage Report

### Tools Used
- **Claude (Anthropic)** — Primary code generation

### Sample Prompts Used
- "Build a mini laundry order management system as a single HTML file with embedded CSS and JS. Dark theme, monospace font, with a sidebar nav, dashboard with stats, create order form with dynamic garment rows, and orders table with inline status update."
- "Add filter functionality for orders — search by name/phone, filter by status."
- "Make the order rows expandable to show garment breakdown."

### Where AI Helped
- Scaffolded the entire layout and component structure in one shot
- Generated the dynamic garment row add/remove logic
- Produced all CSS theming and animation
- Created the dashboard stat aggregation logic

### Where I Fixed/Improved AI Code
- Added 10-digit phone validation (AI gave a generic regex)
- Fixed the localStorage read/write flow to prevent counter reset
- Improved the status badge class naming to match actual status values (lowercase mapping)
- Added row highlight on hover — AI had missed the CSS rule

### Tradeoffs
| Decision | Reason |
|---|---|
| Single HTML file vs multi-file | Easier to run without a server; meets "no framework" option |
| localStorage vs MongoDB | Kept it simple; can swap in a Node.js + Express + MongoDB backend easily |
| In-memory filtering vs server-side | Works fine for <10,000 orders client-side |
| No authentication | Not in core requirements; listed as bonus |

### What I Skipped
- User authentication (bonus feature)
- Deployment (bonus feature)
- Full database backend

### What I'd Improve With More Time
- Add estimated delivery date field per order
- Add Node.js/Express backend with MongoDB
- Add authentication with JWT
- Deploy to Vercel or Render
- Add chart visualization for revenue over time

---

## API / Demo Notes

Since this is a frontend-only app:
- Open `laundry-oms.html` in a browser
- Use the **New Order** tab to create orders
- Use the **All Orders** tab to update statuses and filter
- The **Dashboard** shows live aggregated stats

---

*Built with ❤️ using AI-first development approach*
