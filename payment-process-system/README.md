## Planer - Payment Processing Microservice

Planer will be the new Payment Processing Microservice for our furniture ecommerce platform. It serves as an interface between the platform and the payment processor API, enabling seamless and secure handling of purchase transactions. This microservice will ensure reliable and efficient payment processing, enhancing the overall user experience and facilitating successful furniture sales.

In order to integrate this microservice and interface with the following API, we need to have a clean and reusable way.

### API Documentation

#### Endpoint: /api/payment
**Method:** POST

**Description:** Process a payment

**Request body:**
```json
{
  "amount": 100.0,
  "currency": "USD",
  "card_number": "1234567890123456",
  "expiry_month": "12",
  "expiry_year": "2024",
  "cvv": "123"
}```

**Response body:**
```json
{
  "success": true,
  "transaction_id": "1234567890",
  "message": "Payment processed successfully"
}```

-----------
#### Endpoint: /api/transaction/{transaction_id}
**Method: GET**

**Description: Get transaction details**

**Response body:**
```json
{
  "transaction_id": "1234567890",
  "amount": 100.0,
  "currency": "USD",
  "status": "completed",
  "timestamp": "2023-06-06T12:34:56Z"
}```

----------
#### Endpoint: /api/refund
**Method: POST**

**Description: Initiate a refund**

**Request body:**
```json
{
  "transaction_id": "1234567890",
  "amount": 50.0
}```

**Response body:**
```json
{
  "success": true,
  "refund_id": "9876543210",
  "message": "Refund processed successfully"
}```

-----------
#### Endpoint: /api/refund/{refund_id}
**Method: GET**

**Description: Get refund details**

**Response body:**
```json
{
  "refund_id": "9876543210",
  "transaction_id": "1234567890",
  "amount": 50.0,
  "status": "completed",
  "timestamp": "2023-06-06T13:45:12Z"
}```

