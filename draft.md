 psql --username=freecodecamp --dbname=postgres
CREATE DATABASE salon;
\c salon;
CREATE TABLE customers();
CREATE TABLE appointments();
CREATE TABLE services();

ALTER TABLE customers ADD COLUMN customer_id SERIAL PRIMARY KEY;
ALTER TABLE customers ADD COLUMN phone VARCHAR(30) UNIQUE;
ALTER TABLE customers ADD COLUMN name VARCHAR(255);
ALTER TABLE appointments ADD COLUMN appointment_id SERIAL PRIMARY KEY;
ALTER TABLE appointments ADD COLUMN time VARCHAR(255);
ALTER TABLE appointments ADD COLUMN service_id INT;
ALTER TABLE appointments ADD COLUMN customer_id INT;
ALTER TABLE services ADD COLUMN service_id SERIAL PRIMARY KEY;
ALTER TABLE services ADD COLUMN name VARCHAR(255);
ALTER TABLE appointments ADD CONSTRAINT appointment_service FOREIGN KEY (service_id) REFERENCES services (service_id);
ALTER TABLE appointments ADD CONSTRAINT appointment_customer FOREIGN KEY (customer_id) REFERENCES customers (customer_id);

INSERT INTO services (name) VALUES (‘Haircut’);
INSERT INTO services (name) VALUES (‘Shave’);
INSERT INTO services (name) VALUES (‘Pedicure’);
