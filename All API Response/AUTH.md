
## Auth Management

### 1. User Sign Up

**Access:** Public  
**Description:** Register a new user account

#### Endpoint

```
POST /api/v1/auth/signup
```

Form Fields:

| Field Name    | Type   | Description                       | Required              |
| ------------- | ------ | --------------------------------- | --------------------- |
| name          | String | The full name of the user         | At lest 3 characters  |
| email         | String | The email address of the user     | Valid email format    |
| password      | String | The password for the account      | At least 6 characters |
| image         | String | Base64 encoded profile image      | Optional              |
| contactNumber | String | The contact number of the user    | Optional              |
| address       | String | The address of the user           | Optional              |
| role          | String | The role of the user (USER/AGENT) | Required              |

### Note :
*Here roll field will be a dropdown box, here two options USER or AGENT*

#### Request Body

```json

{
  "name": "Mohammad Thaqi Ul Islam",
  "email": "thaqiulislamkafi@outlook.com",
  "password": "thaqi123456",
  "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
  "contactNumber": "+8801512345679",
  "address": "Chittagong, Bangladesh",
  "role": "USER"
}

```

#### Response

```json
{
    "success": true,
    "message": "User generated successfully",
    "data": {
        "id": "3f6301a7-5e89-4fb1-a507-629190ec620c",
        "name": "Mohammad Thaqi Ul Islam",
        "email": "thaqiulislamkafi@outlook.com",
        "password": "$2b$10$NCPNHxV7yz6Atm/o4hdmAOClP.Zdo1CRX1uNssdNGUECsoHAxMhA6",
        "emailVerified": false,
        "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
        "role": "USER",
        "status": "active",
        "contactNumber": "+8801512345679",
        "address": "Chittagong, Bangladesh",
        "generatedAt": "2026-04-28T07:40:26.564Z",
        "updatedAt": "2026-04-28T07:40:26.564Z"
    }
}

```

### 2. Email Verification

**Access:** Public  
**Description:** Verify a user's email address using a token

#### Endpoint

```
GET /api/v1/verification/verify-user/:userId
```

#### Request

```json
{
    "otp" : "455493"
}

```

#### Response

```json
{
    "success": true,
    "message": "User verified successfully",
    "data": true
}

```
### Bad Response

```json
{
    "success": false,
    "message": "Internal Server Error",
    "data": {}
}

```

### 3. User Sign In

**Access:** Public  
**Description:** Authenticate a user and obtain an access token

#### Endpoint

```
POST /api/v1/auth/signin
```

#### Request Body

```json
{
  "email": "thaqiulislamkafi@outlook.com",
  "password": "thaqi123456"
}

```

#### Response

```json
{
    "success": true,
    "message": "User signed in successfully",
    "data": {
        "id": "3f6301a7-5e89-4fb1-a507-629190ec620c",
        "name": "Mohammad Thaqi Ul Islam",
        "email": "thaqiulislamkafi@outlook.com",
        "password": "$2b$10$NCPNHxV7yz6Atm/o4hdmAOClP.Zdo1CRX1uNssdNGUECsoHAxMhA6",
        "emailVerified": true,
        "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
        "role": "USER",
        "status": "active",
        "contactNumber": "+8801512345679",
        "address": "Chittagong, Bangladesh",
        "generatedAt": "2026-04-28T07:40:26.564Z",
        "updatedAt": "2026-04-28T07:40:26.564Z"
    }
}

```

### Note :

*Here a signup pages in app, in sign up pages sign up all fields must be existed,When user sign up then he can see a OTP Email Verification Window, here only feild, if email verification success then he go to his own dashboard(USER|AGENT) according to his role and show fresh data according to his userId in everywhere in his dashboard*

*In login page, here would be a linkup text named Create new accout?, when user clicked this linked text, user will be gone in SignUp Pages,when he signed in, then he go to his own dashboard(USER|AGENT|ADMIN) according to his role and show fresh data according to his userId in everywhere in his dashboard*




