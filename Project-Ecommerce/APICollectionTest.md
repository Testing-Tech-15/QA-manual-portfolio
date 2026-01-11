📁 API Testing Portfolio (Postman)
🔗 Project: Authentication API – Test Collection (Anonymized)

This project demonstrates hands-on API testing skills using Postman, focused on authentication-related endpoints.
All endpoints, request data, and identifiers are fully anonymized in compliance with NDA requirements.

---


🧪 Scope of Testing

The collection covers positive and negative test cases for the Login functionality:

✅ Covered HTTP Methods

* GET

* POST

* PUT

* DELETE

(Displayed for testing methodology purposes only)

---

| Test Case ID | Scenario                        |
| ------------ | ------------------------------- |
| TC01         | Login with valid credentials    |
| TC02         | Login with missing password     |
| TC03         | Login with invalid email format |
| TC04         | Login with empty request body   |
| TC05         | Login with invalid password     |


---


🧩 Example Test Case (API)
TC01 – Login with Valid Data

Method: POST

Endpoint: /api/v1/auth/login (anonymized)

Preconditions:

* API is available

* User exists in the system

* Request Body (Anonymized)


---

{
  "email": "user@example.com",
  "password": "ValidPassword123"
}

Expected Result

* Status code: 200 OK

* Authentication token returned

* User session created successfully

  ---

  ❌ Negative Testing Examples

* Missing required fields

* Invalid email format

* Incorrect password

* Empty request body

    🧩 These tests ensure:

* Proper validation

* Clear error responses

* Secure authentication handling

  ---

  🛠 Tools & Techniques Used

* Postman – request execution and validation

* Collections & folders – structured test organization

* Environment variables – token & base URL handling

* Status code & response validation

* Positive / Negative / Edge case testing

  --- 

🔒 NDA Notice

All API endpoints, request payloads, response data, and identifiers have been anonymized.
Real URLs, tokens, credentials, and business logic details were removed or replaced.

This portfolio demonstrates testing approach, structure, and QA methodology only.

---








