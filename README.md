Clinic Booking System Database

This repository contains the SQL script to create a Clinic Booking System database. It includes tables for patients, doctors, departments, appointments, payments, and medical records. The database is designed to manage clinic operations efficiently while maintaining data integrity.

Database Name

clinic_db

Tables

Patients
Stores patient information such as name, contact details, date of birth, gender, and creation timestamp.

Departments
Stores clinic departments with unique names.

Doctors
Stores doctor details including specialization, contact information, and associated department.

Appointments
Tracks patient appointments with doctors, including date, status, and creation timestamp.

Payments
Records payments for appointments. Each appointment has a one-to-one relationship with payments.

Medical_Records
Stores medical records for appointments, including diagnosis, prescription, and notes. Each appointment has a one-to-one relationship with medical records.

Key Features

Referential integrity enforced via foreign keys

One-to-one relationships between Appointments ↔ Payments and Appointments ↔ Medical_Records

Auto-generated timestamps for creation and payments

Enum fields for standardized values (e.g., gender, appointment status, payment method)

Cascading deletes to maintain data consistency

Usage

Open MySQL Workbench or your preferred MySQL client.

Execute the clinic_db.sql script to create the database and tables.

Start inserting data and running queries to manage clinic operations.

Author

Shal – aspiring tech queen 💖
