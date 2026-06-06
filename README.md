# HyperLocal Delivery — Database Project

A relational database for a hyperlocal grocery delivery platform, built using **Microsoft SQL Server (T-SQL)**.

---

## Database: `hyperlocaldb`

**Tables:** Users, Addresses, Vendors, ProductCategories, Products, Inventory, Orders, OrderItems, Payments, DeliveryPartners, Status, DeliveryStatus, Reviews, Notification

---

## Project Phases

**Phase 1 — Schema**
Created 14 tables with primary keys, foreign keys, and constraints.

**Phase 2 — Seed Data**
Inserted 10 users, 5 vendors, 5 categories, 100 products, inventory, orders, payments, and delivery records.

**Phase 3 — Queries**
10 business queries: revenue per vendor, popular products, pending payments, low stock alerts, top customers, keyword search, and more.

**Phase 4 — Views, Trigger, Stored Procedure, Indexes**
- `vw_OrderSummary` — order details with customer, vendor, and status
- `vw_ProductSalesSummary` — total units sold per product
- `trg_UpdateInventoryOnOrder` — auto-decrements stock on order placement
- `sp_PlaceOrder` — places an order with multiple items atomically
- `sp_SendNotificationTem` — returns today's scheduled promo notifications
- Indexes on `Products(Name)` and `OrderItems(OrderID, ProductID)`

**Phase 5 — Performance & Security**
- Query benchmarking with `SET STATISTICS TIME/IO ON`
- Role-based access: `AdminRole` (full access) and `VendorRole` (inventory only)

---

## Setup

1. Open `dba.sql` in SSMS
2. Create and select the database:
   ```sql
   CREATE DATABASE hyperlocaldb;
   USE hyperlocaldb;
   ```
3. Run the script top to bottom
