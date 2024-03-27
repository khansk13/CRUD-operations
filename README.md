# CRUD-operations

# Node.js Express Data Pusher Web Application

This is a Node.js Express web application designed to receive data into the app server for an account and send it across different platforms (destinations) from that particular account using webhook URLs.

## Installation and Usage

1. Clone the repository.
2. Install dependencies using `npm install`.
3. Run the application using `node app.js <path_to_database>`.
   Example: `node app.js <C:\Users\Praveen\OneDrive\Desktop\DB\sample.sqlite>`.

## Usage

### CRUD Operations for Accounts

- **Create Account**: POST `/api/accounts/`
- **Read Account**: GET `/api/accounts/:accountId`
- **Update Account**: PUT `/api/accounts/:accountId`
- **Delete Account**: DELETE `/api/accounts/:accountId`

### CRUD Operations for Destinations

- **Create Destination**: POST `/api/accounts/:accountId/destinations`
- **Read Destination**: GET `/api/accounts/:accountId/destinations`
- **Update Destination**: PUT `/api/accounts/:accountId/destinations/:destinationId`
- **Delete Destination**: DELETE `/api/accounts/:accountId/destinations/:destinationId`

### Receiving Data

- Endpoint: POST `/api/data`
- Header: `JWT Token` - Use the provided secret token for authentication.
- JSON Data: Should be sent in the POST body.

### Sample CURL for Account Creation

```bash
curl --location 'http://localhost:3000/api/accounts/' \
--header 'token: Bearer <your_secret_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "accountId": 1007,
    "email": "raina@gmail.com",
    "accountName": "Praveen",
    "website": "https://twitter.com/"
}'

