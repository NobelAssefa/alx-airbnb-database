
Nested Loop Left Join  (cost=0.84..312.75 rows=50 width=224) (actual time=0.034..1.204 rows=50 loops=1)
  Join Filter: (b.booking_id = pay.booking_id)
  -> Nested Loop  (cost=0.56..285.40 rows=50 width=200) (actual time=0.027..0.912 rows=50 loops=1)
        -> Hash Join  (cost=0.28..142.30 rows=50 width=168) (actual time=0.018..0.507 rows=50 loops=1)
             Hash Cond: (b.property_id = p.property_id)
             -> Seq Scan on booking b  (cost=0.00..52.00 rows=2000 width=104) (actual time=0.005..0.159 rows=2000 loops=1)
             -> Hash  (cost=0.17..0.17 rows=10 width=64) (actual time=0.012..0.012 rows=10 loops=1)
                  Buckets: 1024  Batches: 1  Memory Usage: 9kB
                  -> Seq Scan on property p  (cost=0.00..0.17 rows=10 width=64) (actual time=0.004..0.007 rows=10 loops=1)
        -> Index Scan using idx_user_id on "user" u  (cost=0.28..2.86 rows=1 width=32) (actual time=0.004..0.006 rows=1 loops=50)
              Index Cond: (user_id = b.user_id)
  -> Index Scan using idx_payment_booking_id on payment pay  (cost=0.28..0.54 rows=1 width=24) (actual time=0.003..0.004 rows=1 loops=50)

Planning Time: 0.520 ms
Execution Time: 1.347 ms
