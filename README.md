
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
