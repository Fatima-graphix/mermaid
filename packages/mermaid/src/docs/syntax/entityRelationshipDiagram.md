erDiagram
    %% Define all entities and their attributes
    FACULTY {
        number F_id PK
        string Name
        number Salary
        string Mobile_no
    }

    STUDENT {
        number S_id PK
        string F_Name
        string L_Name
        string Phone_no
        date DOB
        number Age
    }

    SUBJECTS {
        number Subject_id PK
        string Subject_name
    }

    COURSE {
        number Course_id PK
        string Course_name
        string Duration
    }

    DEPARTMENT {
        number Department_id PK
        string D_name
    }

    HOSTEL {
        number Hostel_id PK
        string Hostel_name
        number No_of_seats
        string City
        string State
        string Address
        string Pin_code
    }

    EXAMS {
        number Exam_code PK
        date Date
        time Time
        string Room
    }

    %% Define the relationships
    FACULTY ||--o{ STUDENT : teaches
    FACULTY ||--o{ SUBJECTS : takes
    HOSTEL ||--o{ STUDENT : living
    STUDENT }|--|{ COURSE : enrols
    STUDENT ||--|| EXAMS : belongs
    EXAMS ||--|| DEPARTMENT : conducts
    COURSE ||--|| DEPARTMENT : handles
