🌸 Clinic Booking System Database 🌸

Welcome to the Clinic Booking System! This database helps manage patients, doctors, appointments, payments, and medical records efficiently, all in one place. 💖

💾 Database Name

  clinic_db

📋 Tables & Purpose
1️⃣ Patients

Stores patient info: name, contact, DOB, gender

Keeps track of when each patient was added

2️⃣ Departments

Stores all clinic departments

Department names are unique

3️⃣ Doctors

Stores doctor details: name, specialization, contact info

Linked to a department

Can be assigned multiple appointments

4️⃣ Appointments

Tracks appointments between patients & doctors

Stores date, status (Scheduled, Completed, Cancelled)

Auto timestamps when appointment is created

5️⃣ Payments

One-to-one with appointments 💸

Tracks payment amount, date, and method (Cash, Credit Card, Insurance, Mobile Money)

6️⃣ Medical Records

One-to-one with appointments 📝

Stores diagnosis, prescription, and notes

-------- Key Features -----------

🗯️ Foreign keys for data integrity

🗯️Cascading deletes to keep database clean

🗯️ Auto timestamps for tracking creation dates

🗯️ Enums for consistent values (gender, status, payment method)

🗯️One-to-one relationships for payments & medical records

--------🤍 How to Use -------

Open MySQL Workbench (or any MySQL client)

Run the clinic_db.sql script

Start adding patients, doctors, appointments, payments, and medical records 💖



## 📊 Clinic Booking System ER Diagram (Mermaid)

```mermaid
erDiagram
    Patients {
        int patient_id PK
        string first_name
        string last_name
        date dob
        string gender
        string phone
        string email
    }

    Doctors {
        int doctor_id PK
        string first_name
        string last_name
        string specialty
        string phone
        string email
    }

    Appointments {
        int appointment_id PK
        int patient_id FK
        int doctor_id FK
        date appointment_date
        string appointment_time
        string status
    }

    Services {
        int service_id PK
        string service_name
        string description
        decimal fee
    }

    Payments {
        int payment_id PK
        int appointment_id FK
        decimal amount
        date payment_date
        string payment_method
    }

    Appointment_Services {
        int appointment_id FK
        int service_id FK
    }

    Patients ||--o{ Appointments : "books"
    Doctors  ||--o{ Appointments : "handles"
    Appointments ||--|| Payments : "paid_by"
    Appointments ||--o{ Appointment_Services : "includes"
    Services ||--o{ Appointment_Services : "part_of"


        👩‍💻 Author   

      🗯️ Shalom🦋🎀
