# 🚲 Bike Rental Shop

Bike Rental System built using Bash and PostgreSQL.

This application allows customers to rent and return bikes while managing availability, customers, and rental history through a relational database.

---

## Technologies Used

- Bash (Shell scripting)
- PostgreSQL
- SQL 

---

## Project Structure

bike-shop.sh  
→ Main Bash application  

bikes.sql  
→ PostgreSQL database schema + seed data  

---

## Database Structure

The system is built using three relational tables:

1) bikes  
- bike_id → integer (Primary Key)  
- type → varchar(50)  
- size → integer  
- available → boolean (default true)  

Stores all bikes and their availability.

---

2) customers  
- customer_id → integer (Primary Key)  
- phone → varchar(15) (UNIQUE)  
- name → varchar(40)  

Stores customer information.  
Phone numbers must be unique.

---

3) rentals  
- rental_id → integer (Primary Key)  
- customer_id → integer (Foreign Key → customers)  
- bike_id → integer (Foreign Key → bikes)  
- date_rented → date (default NOW())  
- date_returned → date  

Stores rental history and tracks returns.

Relationships:
- rentals.customer_id → customers.customer_id  
- rentals.bike_id → bikes.bike_id  

---

## Features

✔ View available bikes  
✔ Rent a bike  
✔ Automatically create new customers  
✔ Return a bike  
✔ Prevent renting unavailable bikes  
✔ Validate numeric input using regex  
✔ Track rental history  

---

## ▶ How to Run

1) Create the database: createdb bikes

2) Import schema and data: psql -U freecodecamp -d bikes -f bikes.sql

3) Run the application: bash bike-shop.sh

---

## What This Project Demonstrates

- Bash functions and control flow
- Regular expression input validation
- SQL queries executed from shell
- INNER JOIN usage
- Foreign key relationships
- Data integrity constraints
- Command-line user interaction

---

Built as part of backend/database practice.
