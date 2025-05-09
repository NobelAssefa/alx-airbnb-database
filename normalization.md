**Step 1: First Normal Form (1NF) — Eliminate Repeating Groups**
A table is in 1NF if:
Each column contains only atomic (indivisible) values.
Each row is unique.
There are no repeating groups.
All fields like first_name, email, phone_number, etc., contain only atomic values.
Tables have a primary key that uniquely identifies each row.
No lists or arrays in a single field (e.g., no "multiple emails" in one field).
design satisfies 1NF.
**Step 2: Second Normal Form (2NF) — Eliminate Partial Dependencies**
A table is in 2NF if:
It is already in 1NF.
All non-key attributes are fully dependent on the entire primary key (not part of it).
All tables use a single-column primary key (UUID).
No table has a composite key, so partial dependencies are not an issue.
Your design satisfies 2NF.
**Step 3: Third Normal Form (3NF) — Eliminate Transitive Dependencies**
A table is in 3NF if:
It is in 2NF.
No non-key column depends on another non-key column (i.e., no transitive dependency).
Applied to your design:
For  examine:
 **User Table**
Attributes like first_name, last_name, email, etc. depend only on user_id.
No field depends on another non-key field (e.g., phone_number doesn’t depend on email).
 **Property Table**
All attributes depend on property_id, which is the primary key.
host_id is a foreign key that properly links to User (no transitive issues).
No transitive dependencies exist in any of the tables.



**normalized database design!**
![alx-airbnb-database drawio](https://github.com/user-attachments/assets/bacf4fe9-906e-4f3f-9d92-269b1410c270)
