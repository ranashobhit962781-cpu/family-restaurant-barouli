# Family Restaurant Barouli

A starter full-stack restaurant website with:
- Customer menu, signup/login, cart and online order placement
- Customer phone number, delivery address and optional GPS coordinates
- Owner dashboard for orders and order-status updates
- Menu item creation, photos, prices and categories
- Editable restaurant details, free-delivery radius and delivery fee
- Map link for customer coordinates

## Run locally
1. Install Node.js 18 or newer.
2. Copy `.env.example` to `.env`.
3. Change `SESSION_SECRET`, `ADMIN_USERNAME`, and `ADMIN_PASSWORD` in `.env`.
4. In this folder run:
   ```bash
   npm install
   npm start
   ```
5. Open `http://localhost:3000`.
6. Owner dashboard: visit `http://localhost:3000/#owner`, then sign in with the admin credentials.

## Delivery-radius setup
In Owner dashboard → Website & delivery settings:
- Set restaurant latitude and longitude (use the location button while physically at the restaurant).
- Set free delivery radius in kilometres.
- Set the delivery fee outside that radius.

Customer GPS is optional. If a customer does not share GPS, the standard delivery fee is used. Browser GPS generally requires HTTPS when deployed publicly (localhost is also allowed).

## Important before going live
This is a starter project, not yet connected to a hosting provider, SMS/WhatsApp notifications, payment gateway, or production database service. Orders are stored in a local SQLite database on the server. Deploy it to a Node.js host with persistent disk storage and HTTPS before accepting real customer orders. Set strong environment secrets and back up the database. Add a privacy notice and obtain customer consent before collecting location. Do not expose the owner password or `.env` file.

For production, configure a persistent session store (the default Express memory session store is only suitable for local testing), HTTPS, backups, and an order notification workflow. Test checkout and delivery-radius calculations before launch.
