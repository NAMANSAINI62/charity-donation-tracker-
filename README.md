# Charity Donation Tracker

A robust and scalable **Database Management System (DBMS)** project developed for managing and streamlining charity donations, campaigns, beneficiaries, and donor interactions.

> 📌 Developed as part of the **BCA - Database Management System (23CAT-251)** course at **Chandigarh University**.

---

## 📖 Table of Contents

- [Introduction](#introduction)
- [Key Features](#key-features)
- [Database Design](#database-design)
- [Technologies Used](#technologies-used)
- [Schema Overview](#schema-overview)
- [SQL Highlights](#sql-highlights)
- [System Configuration](#system-configuration)
- [How to Use](#how-to-use)
- [ER Diagram](#er-diagram)
- [Conclusion](#conclusion)
- [Author](#author)

---

## 📌 Introduction

**Charity Donation Tracker** is a comprehensive relational database solution designed for NGOs and charitable organizations to efficiently manage:

- Donors and their profiles
- Campaigns and donations
- Fund allocation to beneficiaries
- Recurring and in-kind donations
- Campaign updates, testimonials, and refunds

This project showcases practical use of ER modeling, normalization, primary/foreign key constraints, stored procedures, views, triggers, and advanced SQL queries.

---

## ✨ Key Features

- 🔐 Multi-role admin accounts (`Manager`, `Clerk`, `Auditor`)
- 👤 Donor segmentation and profiling
- 💳 Tracking of one-time and recurring donations
- 🗏️ Automatic generation of donation receipts
- 📊 Reports on donor behavior and campaign performance
- 📣 Campaign updates and social media tracking
- 📩 Thank-you notes and donor communication tracking
- ⚙️ Stored procedures for recommendations and statistics
- 🔄 Refund and tax deduction tracking
- 🏰 Gift donation management (non-monetary support)

---

## 🧱 Database Design

- All tables normalized to **Third Normal Form (3NF)**
- Secure relational structure using **primary and foreign keys**
- Many-to-many relationships managed using junction tables
- Performance optimized via **indexes**, **views**, and **procedures**
- Data integrity maintained using **CHECK**, **NOT NULL**, **UNIQUE**, and **ON DELETE** constraints

---

## 🛠️ Technologies Used

- **MySQL / MariaDB**
- SQL (DDL, DML, DCL, Views, Triggers, Procedures)
- ER Modeling Tools (for schema design)

---

## 🗃️ Schema Overview

The system is divided into several modules:

| Module | Description |
|--------|-------------|
| **User & Admin Management** | Tracks users, profiles, and admin roles |
| **Campaign & Donation** | Handles donors, campaigns, and monetary gifts |
| **Fund Distribution** | Allocation of funds to beneficiaries |
| **Engagement** | Feedback, testimonials, thank-you notes |
| **Finance** | Payments, receipts, refunds, tax tracking |
| **Analytics** | Reports on donor/campaign impact |
| **Security** | Roles, permissions, audit logs |

---

## 🧠 SQL Highlights

Here are some sample SQL operations included in the project:

- **Donors with donation > ₹500**
```sql
SELECT donor_id, donation_amount
FROM donations
WHERE donation_amount > 500
ORDER BY donation_amount DESC;
```

- **Top 5 campaigns by funds**
```sql
SELECT campaign_id, SUM(donation_amount) AS total
FROM donations
GROUP BY campaign_id
ORDER BY total DESC
LIMIT 5;
```

- **Recurring monthly donors**
```sql
SELECT donor_id, amount
FROM recurring_donations
WHERE donation_frequency = 'monthly';
```

- **Campaigns with updates**
```sql
SELECT c.campaign_name, u.update_title, u.update_date  
FROM campaign_updates u
JOIN campaigns c ON u.campaign_id = c.campaign_id;
```

> ⚡ Full query list with outputs available in the `/docs/SQL_QUERIES.sql` file.


## 🖥️ System Configuration

| Component | Recommended |
|-----------|-------------|
| DB Engine | MySQL 8+ / MariaDB 10+ |
| Storage | 10GB minimum, scalable |
| RAM | 8–16 GB (for concurrent reporting) |
| Access | Role-based permissions via views |


## 🚀 How to Use

1. **Clone the repo**
```bash
git clone https://github.com/yourusername/charity-donation-tracker.git
```

2. **Import database**
   - Open MySQL Workbench or your SQL terminal
   - Run the `charity_donation_tracker.sql` script

3. **Populate with sample data**
   - Run the insert script provided in the `/sample_data.sql` file

4. **Run analytics or test queries**
   - Execute queries from `/docs/SQL_QUERIES.sql`



## 📜 ER Diagram

A high-level Entity-Relationship diagram is available in the `/assets/er_diagram.png` file (or replace this with the actual file if uploaded). It maps entities like:

- Donors ↔ Donations ↔ Campaigns
- Donations ↔ Beneficiaries ↔ Allocations
- Admins, Feedback, Testimonials, Events, Gift Donations


## ✅ Conclusion

This project demonstrates the power of relational databases in real-world social applications. It supports data integrity, transparency, and effective reporting—all vital to the success of charitable organizations.

Whether you're managing 100 or 1 million donors, **Charity Donation Tracker** can scale to meet your needs with reliable, secure, and efficient database structures.


## 👤 Author

**Naman Saini**  
🎓 BCA, Chandigarh University  
🏥 UID: 23BCA10698  
📚 Subject: Database Management System (23CAT-251)  
👨‍🏫 Guided by: Arvinder Singh
