# Assignment 2

```mermaid
    erDiagram

    1NF
        STUDENT {
            int SSN
            string lastName
            string firstName
            string birthDate
            int age

            string advisName
            string advisPhone

            int act1code
            string act1desc
            string act1start
            int act1years

            int act2code
            string act2desc
            string act2start
            int act2years

            int act3code
            string act3desc
            string act3start
            int act3years
        }

    2NF
        STUDENT ||--o{ ADVISOR : has
        STUDENT {
            int SSN
            string lastName
            string firstName
            string birthDate
            int age
            int advisCode
            int actCode
        }

        ADVISDOR {
            int advisCode
            string advisName
            string advisPhone
        }

        STUDENT }|..|{ ACTIVITY : does
        ACTIVITY {
            int actCode
            string actDesc
        }

    3NF

        STUDENT ||--o{ ADVISOR : has
        STUDENT ||--o{ STUDENT_ACTIVITY : does
        STUDENT {
            int SSN
            string lastName
            string firstName
            string birthDate
            int age
            int advisCode
        }

        ADVISDOR {
            int advisCode
            string advisName
            string advisPhone
        }

        ACTIVITY {
            int actCode
            string actDesc
        }

        STUDENT_ACTIVITY }|..|{ ACTIVITY : participates in
        STUDENT_ACTIVITY {
            int SSN
            int actCode
            string actStart
            int actYears
        }


