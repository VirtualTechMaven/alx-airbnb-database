# Database Normalization – Airbnb Clone Project

This document explains how the Airbnb database schema was normalized to **Third Normal Form (3NF)** to ensure efficient data structure and minimal redundancy.

---

## First Normal Form (1NF)

- All columns contain atomic values.
- No repeating groups.
- Each record is unique.

✔ Example:
- User table stores each phone number in a single field (no multiple numbers in one column).
- Bookings are listed one per row — not grouped.

---

## Second Normal Form (2NF)

- Must be in 1NF.
- All **non-key attributes are fully functionally dependent** on the **entire primary key**.

✔ Example:
- The `booking` table uses a single-column primary key (`booking_id`) instead of combining `user_id + property_id`.
- Attributes like `start_date`, `end_date`, and `total_price` depend on the booking ID alone.

---

## Third Normal Form (3NF)

- Must be in 2NF.
- **No transitive dependencies** (non-key → non-key).

 Example:
- `User` role (guest, host, admin) is stored directly — not in another table.
- Payment method (credit_card, paypal) is stored as an ENUM in the `payment` table.

---

## Summary of Normalized Tables

### User Table
- Atomic fields (first_name, last_name, email)
- No duplicate or repeating groups

### Property Table
- Foreign key to `host_id`
- Independent attributes like name, location, price

### Booking Table
- Connected only by `property_id` and `user_id`
- No redundant property/user info inside

### Payment Table
- Linked to `booking_id`
- Includes only payment-specific data

### Review & Message Tables
- Each tied directly to their respective foreign keys

---

 This normalization ensures our Airbnb database is efficient, scalable, and clean.
