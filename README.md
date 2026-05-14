# smart-parking-system
Smart Parking System is a MySQL-based DBMS project designed to manage parking operations efficiently. It includes user management, vehicle tracking, parking slot allocation, bookings, payments, monthly passes, SQL views, stored procedures, triggers, and automated billing features.

---

## Features

- User Management
- Vehicle Registration
- Parking Slot Allocation
- Booking System
- Auto Billing System
- Payment Tracking
- Monthly Pass Management
- Staff Management
- Fine Calculation
- SQL Views
- Stored Procedures
- SQL Triggers

---

## Database Tables

### Users
Stores user information.

### Vehicles
Stores registered vehicle details.

### ParkingSlots
Manages parking slot availability.

### Bookings
Handles vehicle parking entries and exits.

### Payments
Stores payment records.

### MonthlyPass
Manages monthly parking subscriptions.

### Staff
Stores parking staff information.

---

## SQL Concepts Used

- Primary Keys
- Foreign Keys
- JOIN Queries
- Aggregate Functions
- CASE Statements
- SQL Views
- Stored Procedures
- Triggers
- AUTO_INCREMENT
- ENUM
- Constraints

---

## Technologies Used

- MySQL
- SQL

---

## Project Structure

```bash
smart-parking-system/
│
├── smart_parking_system.sql
├── README.md
└── screenshots/
```

---

## How to Run

### 1. Create Database

```sql
CREATE DATABASE smart_parking_system;
USE smart_parking_system;
```

### 2. Import SQL File

Run the SQL file:

```sql
SOURCE smart_parking_system.sql;
```

Or import directly using MySQL Workbench / phpMyAdmin.

---

## Example Queries

### Available Parking Slots

```sql
SELECT * FROM ParkingSlots
WHERE status='Available';
```

### Active Bookings

```sql
SELECT v.vehicle_no, p.slot_number
FROM Bookings b
JOIN Vehicles v ON b.vehicle_id=v.vehicle_id
JOIN ParkingSlots p ON b.slot_id=p.slot_id
WHERE b.booking_status='Active';
```

### Daily Income

```sql
SELECT SUM(amount) AS total_income
FROM Payments
WHERE payment_date=CURDATE();
```

---

## Advanced Features

### Stored Procedure

```sql
CALL GetUserBookings(1);
```

### Trigger

Automatically generates parking bills after vehicle exit.

### View

```sql
SELECT * FROM FreeSlots;
```

---

## Future Improvements

- Web Dashboard
- QR Code Entry
- RFID Integration
- Online Payments
- Real-Time Slot Monitoring
- Mobile Application
- Parking Analytics

---

## Author

Hindtech

---

## License

This project is open-source and free to use for educational purposes.
