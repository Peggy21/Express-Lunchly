# Express-Lunchly
Lunchly is an Express app that is not an API server, nor is it RESTful.
Instead, it’s a server-side templated application with custom URLs.
We should be able to see the list of customers, view a customer detail page, and add a customer. Adding a reservation is not yet complete, so expect errors if we try to create a new reservation.

### Languages, Frameworks and Application Platform:

- HTML5
- CSS
- Postgres database
- Bootstrap v5.1
- JavaScript
- Express.js

<p>&nbsp;</p>

**Example of tables:**
```
CREATE TABLE customers (
    id integer PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
    first_name text NOT NULL,
    last_name text NOT NULL,
    phone text,
    notes text DEFAULT '' NOT NULL
);

CREATE TABLE reservations (
    id integer PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
    customer_id integer NOT NULL REFERENCES customers,
    start_at timestamp without time zone NOT NULL,
    num_guests integer NOT NULL,
    notes text DEFAULT '' NOT NULL,
    CONSTRAINT reservations_num_guests_check CHECK ((num_guests > 0))
);

```
