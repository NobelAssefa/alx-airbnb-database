**How to Use**
Create your database (e.g., PostgreSQL):
createdb booking_db
Run the schema file to create tables:
psql -d booking_db -f schema.sql
Load sample data:
psql -d booking_db -f seed.sql
