high usage columns

| Column       | Usage Context   | Reason for Usage                            |
| ------------ | --------------- | ------------------------------------------- |
| `user_id`    | JOIN, WHERE     | Primary key, foreign key in many tables     |
| `email`      | WHERE           | Used for login/authentication lookups       |
| `role`       | WHERE           | Filtering by user role (guest, host, admin) |
| `created_at` | ORDER BY, WHERE | Auditing, filtering by signup date          |






CREATE INDEX idx_user_email ON User(email);
CREATE INDEX idx_user_id ON User(user_id);
CREATE INDEX idx_user_role ON User(role);
CREATE INDEX idx_user_created_at ON User(created_at);

CREATE INDEX idx_booking_user_id ON Booking(user_id);
CREATE INDEX idx_booking_property_id ON Booking(property_id);
CREATE INDEX idx_booking_status ON Booking(status);
CREATE INDEX idx_booking_start_date ON Booking(start_date);
CREATE INDEX idx_booking_end_date ON Booking(end_date);
CREATE INDEX idx_booking_created_at ON Booking(created_at);


CREATE INDEX idx_property_host_id ON Property(host_id);
CREATE INDEX idx_property_location ON Property(location);
CREATE INDEX idx_property_pricepernight ON Property(pricepernight);
CREATE INDEX idx_property_created_at ON Property(created_at);
