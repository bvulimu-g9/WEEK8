# WEEK8
 Start MySQL server.
2. Run the SQL file `ecommerce_db.sql` in MySQL Workbench or:
   `mysql -u root -p < ecommerce_db.sql`
   This creates database `ecommerceDB` and sample data.

## Setup Node app
1. Copy project files to a folder `ecommerce-crud`.
2. Create a `.env` file with DB credentials (see .env.example).
3. Install dependencies:
   ```
   npm install
   ```
4. Start the server:
   ```
   npm run dev
   ```
   or
   ```
   npm start
   ```
5. Server runs at `http://localhost:3000`.

## API Endpoints

### Products
- `POST /products` — create product  
  Body JSON: `{ sku, name, description, price, quantity_in_stock, category_id }`
- `GET /products` — list products
- `GET /products/:id` — get product
- `PUT /products/:id` — update product
- `DELETE /products/:id` — delete product

### Orders
- `POST /orders` — create order (body: `{ customer_id, shipping_address_id, billing_address_id, items: [ {product_id, quantity} ] }`)
- `GET /orders` — list orders
- `GET /orders/:id` — get order with items
- `PATCH /orders/:id/status` — update order status (body: `{ status }`)
- `DELETE /orders/:id` — delete order

## Notes & Security
- This example stores `password_hash` placeholder only — do not store plaintext passwords.
- In production add authentication, input validation, prepared statements (we already use parameterized queries), and more robust error handling.
- Add migrations and proper schema versioning for real projects.
