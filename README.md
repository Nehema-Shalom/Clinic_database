## 🏥 Clinic Booking System – Colorful ER Diagram

```mermaid
%% Set theme (light or dark)
%% GitHub currently ignores theme in ER diagrams, but classes still work

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

    %% Relationships
    Patients ||--o{ Appointments : "books"
    Doctors  ||--o{ Appointments : "handles"
    Departments ||--o{ Doctors : "hosts"
    Appointments ||--|| Payments : "paid_by"
    Appointments ||--|| MedicalRecords : "recorded_in"

    %% Classes for colors
    class Patients,Doctors,Departments,Appointments,Payments,MedicalRecords pinkClass;

    %% Class definitions
    classDef pinkClass fill:#ffe4e1,stroke:#ff69b4,stroke-width:2px,color:#800080,font-size:12px;
