high usage columns

| Column       | Usage Context   | Reason for Usage                            |
| ------------ | --------------- | ------------------------------------------- |
| `user_id`    | JOIN, WHERE     | Primary key, foreign key in many tables     |
| `email`      | WHERE           | Used for login/authentication lookups       |
| `role`       | WHERE           | Filtering by user role (guest, host, admin) |
| `created_at` | ORDER BY, WHERE | Auditing, filtering by signup date          |






