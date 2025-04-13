# API Documentation Prompts

This guide provides structured templates for generating clear, comprehensive API documentation. Use these templates to ensure consistent and thorough documentation.

## 📝 Endpoint Documentation Template

```
As a technical writer specializing in API documentation, please document this endpoint:

1. Basic Information:
- Endpoint: [HTTP method + path]
- Purpose: [What this endpoint does]
- Authentication: [Required auth methods]

2. Request Details:
- Headers: [Required/optional headers]
- Query Parameters: [URL parameters]
- Request Body: [JSON structure]
- Example Request: [Curl command or code snippet]

3. Response Details:
- Success Response: [200 structure]
- Error Responses: [Common error codes]
- Response Examples: [JSON examples]

4. Usage Notes:
- Rate Limits: [If applicable]
- Permissions: [Required roles/scopes]
- Caching: [Cache behavior]
```

Example:
```
As a technical writer specializing in API documentation, please document this endpoint:

1. Basic Information:
- Endpoint: POST /api/v1/users
- Purpose: Creates a new user account in the system
- Authentication: Bearer token required

2. Request Details:
- Headers:
  - Authorization: Bearer {token}
  - Content-Type: application/json
- Query Parameters: None
- Request Body:
  ```json
  {
    "username": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "role": "user|admin"
  }
  ```
- Example Request:
  ```bash
  curl -X POST https://api.example.com/api/v1/users \
    -H "Authorization: Bearer {token}" \
    -H "Content-Type: application/json" \
    -d '{
      "username": "johndoe",
      "email": "john@example.com",
      "firstName": "John",
      "lastName": "Doe",
      "role": "user"
    }'
  ```

3. Response Details:
- Success Response (200):
  ```json
  {
    "id": "uuid",
    "username": "string",
    "email": "string",
    "firstName": "string",
    "lastName": "string",
    "role": "string",
    "createdAt": "ISO8601 datetime"
  }
  ```
- Error Responses:
  - 400: Invalid request body
  - 401: Unauthorized
  - 409: Username/email already exists
  - 422: Validation error

4. Usage Notes:
- Rate Limits: 10 requests per minute per API key
- Permissions: Requires 'create:users' scope
- Caching: Responses are not cached
```

## 🔄 API Change Documentation Template

```
Please help document these API changes:

1. Change Overview:
- Type: [Breaking/Non-breaking]
- Version: [New version number]
- Affected Endpoints: [List]

2. Changes Per Endpoint:
- Before: [Old behavior/structure]
- After: [New behavior/structure]
- Migration Steps: [How to update]

3. Migration Timeline:
- Deprecation Date: [When old version stops]
- Support Window: [How long both versions run]
- Important Dates: [Key migration milestones]
```

## 💡 API Usage Examples Template

```
Please provide comprehensive examples for this API:

1. Use Case:
[Describe the scenario]

2. Example Implementation:
- Language: [Programming language]
- Dependencies: [Required libraries]
- Authentication Setup: [Auth steps]
- Code Example: [Working implementation]

3. Common Patterns:
- Error Handling: [How to handle errors]
- Rate Limiting: [How to handle limits]
- Pagination: [If applicable]

4. Best Practices:
- Performance Tips: [Optimization advice]
- Security Considerations: [Security best practices]
```

## 📚 API Overview Template

```
Please create an overview of this API:

1. API Introduction:
- Purpose: [What the API does]
- Core Features: [Key capabilities]
- Target Users: [Who should use it]

2. Getting Started:
- Prerequisites: [What's needed]
- Authentication: [How to get access]
- Quick Start: [First API call]

3. Key Concepts:
- Data Models: [Core objects]
- Workflows: [Common processes]
- Limitations: [Important constraints]

4. Resources:
- Documentation: [Where to find more]
- Support: [How to get help]
- SDKs/Tools: [Available tools]
```

## 🔍 API Testing Documentation Template

```
Please document the testing approach for this API:

1. Test Scenarios:
- Happy Path: [Expected usage]
- Edge Cases: [Corner cases]
- Error Cases: [Expected failures]

2. Test Environment:
- Endpoints: [Test URLs]
- Auth: [Test credentials]
- Data: [Test datasets]

3. Testing Tools:
- Recommended Tools: [Tool list]
- Setup Instructions: [How to configure]
- Example Tests: [Sample test code]
```

## Tips for Better Documentation Prompts

1. Always specify:
   - Target audience (developers, admins, etc.)
   - Required technical knowledge
   - Documentation format preferences

2. Include examples for:
   - Success and error scenarios
   - Different programming languages
   - Common use cases

3. Request validation:
   - Accuracy check
   - Completeness check
   - Technical review suggestions