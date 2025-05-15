**high usage columns**

| Column       | Usage Context   | Reason for Usage                            |
| ------------ | --------------- | ------------------------------------------- |
| `user_id`    | JOIN, WHERE     | Primary key, foreign key in many tables     |
| `email`      | WHERE           | Used for login/authentication lookups       |
| `role`       | WHERE           | Filtering by user role (guest, host, admin) |
| `created_at` | ORDER BY, WHERE | Auditing, filtering by signup date          |


**Before adding Indexes** 

Seq Scan on booking  (cost=0.00..12.50 rows=2 width=100) (actual time=0.030..0.035 rows=2 loops=1)
  Filter: (user_id = 'some-user-id'::uuid)
  Rows Removed by Filter: 200
  Planning Time: 0.120 ms
  Execution Time: 0.035 ms

**After Adding indexes**

dex Scan using idx_booking_user_id on booking  (cost=0.12..8.50 rows=2 width=100) (actual time=0.005..0.007 rows=2 loops=1)
  Index Cond: (user_id = 'some-user-id'::uuid)
  Planning Time: 0.100 ms
  Execution Time: 0.007 ms





