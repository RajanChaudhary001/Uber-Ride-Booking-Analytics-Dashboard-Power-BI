# 🚖 Uber Ride Booking Analytics Dashboard | Power BI

An end-to-end Power BI dashboard analyzing **150,000 Uber ride bookings** to uncover patterns in completion rates, cancellations, revenue, vehicle performance, and customer behavior.

![Dashboard Preview](images/dashboard_preview.png)

---

## 📌 Project Overview

This project analyzes a full year (Jan–Dec 2025) of Uber ride booking data to answer key business questions:

- What % of rides actually complete, and where are we losing bookings?
- Which vehicle type drives the most revenue and demand?
- When is ride demand highest during the day?
- Why do customers and drivers cancel rides?
- How is revenue trending month over month?

---

## 📊 Dashboard KPIs

| Metric | Value |
|---|---|
| Completed Rides | 93,000 |
| Lost Bookings (Cancelled/Incomplete/No Driver) | 57,000 |
| Total Revenue | ₹52M |
| Total Distance Covered | 2.51M km |
| Average Ride Distance | 24.64 km |
| Average Driver Rating | 4.23 / 5 |

---

## 🔍 Key Insights

- **Only 62% of bookings complete.** Driver-side cancellations (27K) are the single biggest cause of lost bookings — bigger than "No Driver Found" and customer cancellations combined.
- **Auto is the top-performing vehicle type** — 37,419 rides (25% of all bookings) and the highest revenue contributor, though average trip distance is nearly identical (~24.6 km) across all vehicle types.
- **UPI is the dominant payment method**, used in 31% of all rides — more than double Cash transactions.
- **Demand peaks in the evening** — rides between 5–8 PM run 8–9x higher than the 12 AM–4 AM window, useful for driver incentive scheduling.
- **Driver cancellation reasons skew personal** — "customer sick" and "personal/car issues" are nearly as common as genuine customer-related complaints, pointing to a potential training/support fix.
- **Revenue is stable, not seasonal** — monthly revenue stays within a narrow ₹3.97M–₹4.57M band all year, with no major festive spike.

---

## 🛠️ Tools & Skills Used

- **Power BI Desktop** — data modeling, DAX measures, interactive visuals
- **DAX** — custom measures for rides count, cancellation rate, revenue aggregation
- **Data Cleaning** — handling blanks/nulls in cancellation reason columns
- **Data Visualization** — KPI cards, gauge chart, line chart, bar chart, donut/pie chart

### Sample DAX Measures
```DAX
Total Rides = COUNTROWS('Sheet1')

Completed Rides = CALCULATE(COUNTROWS('Sheet1'), 'Sheet1'[Booking Status] = "Completed")

Cancellation Rate = DIVIDE([Total Rides] - [Completed Rides], [Total Rides])

Avg Distance = AVERAGE('Sheet1'[Ride Distance])
```

---

## 📁 Repository Structure

```
uber-booking-analytics/
│
├── README.md
├── dashboard/
│   └── uber_dashboard.pbix
├── data/
│   └── uber_bookings_sample.csv        # sample rows only (see note below)
├── images/
│   └── dashboard_preview.png
└── insights.md
```

> ⚠️ **Note on data:** The full dataset (150,000 rows) is not uploaded due to size/privacy. Only a sample is included for reference. The `.pbix` file contains the complete data model.

---

## 📈 Dataset Description

| Column | Description |
|---|---|
| Date, Time | Booking timestamp |
| Booking ID, Customer ID | Unique identifiers |
| Booking Status | Completed / Cancelled by Driver / Cancelled by Customer / No Driver Found / Incomplete |
| Vehicle Type | Auto, Bike, Go Mini, Go Sedan, Premier Sedan, eBike, Uber XL |
| Booking Value, Ride Distance | Revenue and trip distance |
| Driver/Customer Rating | Feedback scores |
| Cancellation Reasons | Reasons logged by customer/driver |
| Payment Method | UPI, Cash, Card, Wallet |

---

## 🚀 How to View

1. Clone this repo
2. Open `dashboard/uber_dashboard.pbix` in **Power BI Desktop**
3. Explore filters by vehicle type, month, and booking status

---

## 👤 Author

Built by [Rajan Chaudhary] — connect on [ linkedin.com/in/rajan-chaudhary-7089482b2 ](#) | [Portfolio](#)

⭐ If you found this useful, consider starring the repo!
