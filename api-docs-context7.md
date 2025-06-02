# Semify Enterprise REST APIs

**Version:** 2.0.0  
**Contact:** [API Support](mailto:developers@semify.com)  
**Website:** [https://www.semify.com](https://www.semify.com)  
**License:** [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0.html)  
**Docs:** [Swagger](http://swagger.io)  
**External Docs:** [ReadMe Blog](https://blog.readme.io/an-example-filled-guide-to-swagger-3-2/)

---

## Security

- **JWTAuth**: HTTP Bearer (JWT)
  - A JWT token is required to access this API. Obtain a token via the Authorization API.

---

## Servers

- **Sandbox:** `https://uat.services.semify.com`
- **Production:** `https://services.semify.com`

---

## Tags

- **accounts**: Operations related to accounts.
- **keywords**: Operations related to keywords.
- **reports**: Reporting endpoints.
- **products**: Product management endpoints.
- **authentication**: Authentication/authorization endpoints.
- **campaigns**: Campaigns and related operations.
- **google gbp accounts**: Google GBP account endpoints.

---

## Endpoints (Summary)

### `/api/v1/accounts`
- **POST**: Create a new account (JWT required)
- **PUT**: Update an existing account (JWT required)
- **GET**: Retrieve all accounts (JWT required)

### `/api/v1/accounts/{account_id}`
- **GET**: Retrieve account details by ID (JWT required)

### `/api/v2/accounts`
- **POST**: Create a new account v2 (JWT required)
- **PUT**: Update an existing account v2 (JWT required)
- **GET**: Retrieve all accounts v2 (JWT required)

### `/api/v2/accounts/{account_id}`
- **GET**: Retrieve account details by ID v2 (JWT required)

### `/api/v1/accounts/iam/credentials`
- **POST**: Create account/campaign level IAM credentials (JWT required)

### `/api/v1/accounts/status`
- **PUT**: Deactivate or reactivate an account (JWT required)

### `/api/v1/keywords`
- **POST**: Create new keywords (JWT required)
- **PUT**: Update keywords (JWT required)
- **GET**: Retrieve all keywords (JWT required)

### `/api/v1/keywords/{rank_id}`
- **GET**: Get keyword by rank_id (JWT required)

### `/api/v1/campaigns`
- **GET**: Get all campaigns (JWT required)

### `/api/v2/campaigns/notes`
- **GET**: Get campaign notes (JWT required)
- **PUT**: Update campaign notes (JWT required)

### `/api/v1/authentication/login`
- **POST**: Authenticate a user (returns JWT)

### `/api/v1/reports/keywords/accounts/{account_id}/campaigns/{campaign_id}`
- **GET**: Get keyword reports (JWT required)

### `/api/v1/reports/google/analytics/traffic/accounts/{account_id}/campaigns/{campaign_id}/date_from/{date_from}/date_to/{date_to}`
- **GET**: Get Google Analytics traffic reports (JWT required)

### `/api/v1/reports/backlinks/accounts/{account_id}/campaigns/{campaign_id}`
- **GET**: Get backlink reports (JWT required)

### `/api/v1/reports/backlinks/lost/accounts/{account_id}/campaigns/{campaign_id}/date_from/{date_from}/date_to/{date_to}`
- **GET**: Get lost backlink reports (JWT required)

### `/api/v1/reports/backlinks/referring/accounts/{account_id}/campaigns/{campaign_id}/date_from/{date_from}/date_to/{date_to}`
- **GET**: Get referring backlinks (JWT required)

### `/api/v1/reports/backlinks/provisioned/accounts/{account_id}/campaigns/{campaign_id}/date_from/{date_from}/date_to/{date_to}`
- **GET**: Get backlinks provisioned by Semify (JWT required)

### `/api/v1/products/plans/campaigns`
- **POST**: Attach a service/product plan to an account (JWT required)

### `/api/v1/products/plans/campaigns/{campaign_id}/accounts/{account_id}`
- **GET**: Get service plans for campaign and account (JWT required)

---

## Example: Create Account (v2)

**POST** `/api/v2/accounts`

**Request Body Example:**
```json
{
  "account_name": "Semify",
  "phone": "3361231234",
  "email": "business@business.com",
  "first_name": "First",
  "last_name": "Last",
  "address_1": "2307 West Cone Blvd.",
  "address_2": "Suite 200",
  "city": "Greensboro",
  "state": "NC",
  "postal": "27410",
  "country_code": "US",
  "website_url": "https://www.semify.com",
  "external_account_identifier": "TestAccount5555",
  "external_account_manager": {
    "name": "Fnu Lnu",
    "email": "fnulnu@yourdomain.com"
  },
  "external_campaign_manager": {
    "name": "Fnu Lnu",
    "email": "fnulnu@yourdomain.com"
  },
  "attributes": [
    { "field_name": "Approval Type", "field_value": "Full" },
    { "field_name": "Another Field", "field_value": "Partial" }
  ]
}
```

**Response Example:**
```json
{
  "data": {
    "account_id": "123456",
    "campaign_id": "987654"
  },
  "error": false,
  "pagination": {
    "totalPages": 1,
    "maxRows": 0,
    "offset": 0,
    "page": 1,
    "totalRecords": 1
  },
  "messages": ["Account created successfully."]
}
```

---

**For more details, refer to the full OpenAPI YAML or the [Swagger documentation](http://swagger.io).** 
