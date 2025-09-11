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
🌸 ER Diagram 🌸

```mermaid
erDiagram
    Patients {
        int patient_id PK
        string first_name
        string last_name
        string email
        string phone
        date dob
        enum gender
        timestamp created_at
    }

    Departments {
        int department_id PK
        string department_name
    }

    Doctors {
        int doctor_id PK
        string first_name
        string last_name
        string specialization
        string email
        string phone
        int department_id FK
    }

    Appointments {
        int appointment_id PK
        int patient_id FK
        int doctor_id FK
        datetime appointment_date
        enum status
        timestamp created_at
    }

    Payments {
        int payment_id PK
        int appointment_id FK UNIQUE
        decimal amount
        timestamp payment_date
        enum payment_method
    }

    Medical_Records {
        int record_id PK
        int appointment_id FK UNIQUE
        text diagnosis
        text prescription
        text notes
        timestamp created_at
    }

    %% Relationships
    Patients ||--o{ Appointments : "books"
    Doctors  ||--o{ Appointments : "handles"
    Departments ||--o{ Doctors : "hosts"
    Appointments ||--|| Payments : "paid_by"
    Appointments ||--|| Medical_Records : "recorded_in"


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

        👩‍💻 Author   

      🗯️ Shalom🦋🎀
