#  🎀Clinic Booking System 

This project allows managing patients, doctors, appointments, departments, payments, and medical records in a clean and organized way. It provides a centralized system where clinic staff can easily keep track of patient information, schedule appointments, manage doctors and their departments, and ensure that all payments and medical records are properly recorded. With this system, administrative tasks become faster, more accurate, and less stressful, while giving staff a clear overview of the clinic’s operations. It’s designed to be intuitive, efficient, and scalable, making it perfect for clinics of any size that want to stay organized and provide better care to their patients.

---

##  ER Diagram 

```mermaid
erDiagram
    Patients {
        int patient_id PK
        string first_name
        string last_name
        string email
        string phone
        date dob
        string gender
        date created_at
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
        date appointment_date
        string status
        date created_at
    }

    Payments {
        int payment_id PK
        int appointment_id FK
        float amount
        date payment_date
        string payment_method
    }

    MedicalRecords {
        int record_id PK
        int appointment_id FK
        string diagnosis
        string prescription
        string notes
        date created_at
    }

    Patients ||--o{ Appointments : "books"
    Doctors  ||--o{ Appointments : "handles"
    Departments ||--o{ Doctors : "hosts"
    Appointments ||--|| Payments : "paid_by"
    Appointments ||--|| MedicalRecords : "recorded_in"
