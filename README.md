Backend Ledger Service

A secure and scalable ledger system built with Node.js, Express, and
MongoDB, designed for immutable financial record-keeping and
transactional integrity.

OVERVIEW

This backend service implements a banking-style ledger architecture
where all financial records are immutable. It ensures accurate balance
computation using dual-entry accounting principles.

CORE FEATURES

Immutable Ledger: - Ledger entries cannot be modified or deleted once
created. - Protected via middleware to preserve financial integrity.

10-Step Transaction Flow: - Input validation - Idempotency check -
Transaction creation (PENDING state) - Debit entry creation - Credit
entry creation - Status update (COMPLETED/FAILED) - Atomic consistency
handling

Idempotency Protection: - Each transaction uses a unique
idempotencyKey - Prevents duplicate transfers in case of retries

Security: - JWT-based authentication - Token blacklist for
logout/session invalidation - Password hashing using bcrypt

Automated Email Notifications: - Registration success emails -
Transaction success/failure notifications - Implemented using Nodemailer
with Gmail OAuth2

API ENDPOINTS

Authentication: POST /api/auth/register POST /api/auth/login POST
/api/auth/logout

Accounts: POST /api/accounts/create GET /api/accounts GET
/api/accounts/balance/:accountId

Transactions: POST /api/transactions/transfer POST
/api/transactions/system/initial-funds

SETUP REQUIREMENTS

Database: - MongoDB (connection string required)

Environment Variables: MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key EMAIL_USER=your_email
CLIENT_ID=your_google_client_id CLIENT_SECRET=your_google_client_secret
REFRESH_TOKEN=your_google_refresh_token

INSTALLATION

npm install npm run dev

TECH STACK

-   Node.js
-   Express.js
-   MongoDB
-   Mongoose
-   JWT
-   bcryptjs
-   Nodemailer

Author: Himanshu Kumar
