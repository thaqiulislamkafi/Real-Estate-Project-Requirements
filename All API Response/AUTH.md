
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
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJkYXRhIjp7ImlkIjoiYWRmM2FhYmQtOTcyMC00NDFlLWEzNTYtZGUxYTA3MjI4YjBmIiwibmFtZSI6Ik1vaGFtbWFkIFRoYXFpIFVsIElzbGFtIiwiZW1haWwiOiJ0aGFxaXVsaXNsYW1rYWZpQG91dGxvb2suY29tIiwicGFzc3dvcmQiOiIkMmIkMTAkQmpITlc0UkhaaGlHOG90RjNBSTFUT1cvR24wNWJETVZ2eHhPeEI3bnZLQTQ4NFhpc2g1SmUiLCJlbWFpbFZlcmlmaWVkIjpmYWxzZSwiaW1hZ2UiOiJkYXRhOmltYWdlL3BuZztiYXNlNjQsaVZCT1J3MEtHZ29BQUFBTlNVaEVVZ0FBQUFVQS4uLiIsInJvbGUiOiJVU0VSIiwic3RhdHVzIjoiYWN0aXZlIiwiY29udGFjdE51bWJlciI6Iis4ODAxNTEyMzQ1Njc5IiwiYWRkcmVzcyI6IkNoaXR0YWdvbmcsIEJhbmdsYWRlc2giLCJnZW5lcmF0ZWRBdCI6IjIwMjYtMDQtMjlUMDY6MDE6NDMuMDQ3WiIsInVwZGF0ZWRBdCI6IjIwMjYtMDQtMjlUMDY6MDE6NDMuMDQ3WiJ9LCJpYXQiOjE3Nzc0NDI1MDUsImV4cCI6MTc3ODA0NzMwNX0.XTOd_GznxgTSfbwFjD-KvOXA-SwY542C-Sk5_WXP0S0",
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
POST /api/v1/verification/verify-user/:userId
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
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJkYXRhIjp7ImlkIjoiYWRmM2FhYmQtOTcyMC00NDFlLWEzNTYtZGUxYTA3MjI4YjBmIiwibmFtZSI6Ik1vaGFtbWFkIFRoYXFpIFVsIElzbGFtIiwiZW1haWwiOiJ0aGFxaXVsaXNsYW1rYWZpQG91dGxvb2suY29tIiwicGFzc3dvcmQiOiIkMmIkMTAkQmpITlc0UkhaaGlHOG90RjNBSTFUT1cvR24wNWJETVZ2eHhPeEI3bnZLQTQ4NFhpc2g1SmUiLCJlbWFpbFZlcmlmaWVkIjpmYWxzZSwiaW1hZ2UiOiJkYXRhOmltYWdlL3BuZztiYXNlNjQsaVZCT1J3MEtHZ29BQUFBTlNVaEVVZ0FBQUFVQS4uLiIsInJvbGUiOiJVU0VSIiwic3RhdHVzIjoiYWN0aXZlIiwiY29udGFjdE51bWJlciI6Iis4ODAxNTEyMzQ1Njc5IiwiYWRkcmVzcyI6IkNoaXR0YWdvbmcsIEJhbmdsYWRlc2giLCJnZW5lcmF0ZWRBdCI6IjIwMjYtMDQtMjlUMDY6MDE6NDMuMDQ3WiIsInVwZGF0ZWRBdCI6IjIwMjYtMDQtMjlUMDY6MDE6NDMuMDQ3WiJ9LCJpYXQiOjE3Nzc0NDI1MDUsImV4cCI6MTc3ODA0NzMwNX0.XTOd_GznxgTSfbwFjD-KvOXA-SwY542C-Sk5_WXP0S0",
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

### 4. Change Email 

**Access** :  Public
**Description** : An specific user(USER|Agent) can change his email

#### Endpoint

```json
PUT /api/v1/auth/user/change-email/:id
```

#### Request Body

```json

{
   "email":"thaqiulislamkafi@outlook.com"
}

```

#### Response Body

```json

{
    "success": true,
    "message": "Email Changed Successfully and otp send",
    "data": {
        "id": "fe5cdcd5-4db8-42a0-9dea-1612aac98526",
        "name": "Mohammad Thaqi Ul Islam",
        "email": "thaqiulislamkafi@outlook.com",
        "password": "$2b$10$ZqKZPTlEMM91PARZLjV0CuCoECCqOBya0zL6VTJ7OurEwtvSb0Q6K",
        "emailVerified": false,
        "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
        "role": "USER",
        "status": "active",
        "contactNumber": "+8801512345679",
        "address": "Chittagong, Bangladesh",
        "generatedAt": "2026-04-30T05:48:06.253Z",
        "updatedAt": "2026-05-02T05:40:58.460Z"
    }
}


```

---


### Note : 

*Here a signup pages in app, in sign up pages sign up all fields must be existed,When user sign up then he can see a OTP Email Verification Window, here only feild, if email verification success then he go to his own dashboard(USER|AGENT) according to his role and show fresh data according to his userId in everywhere in his dashboard*

*In login page, here would be a linkup text named Create new accout?, when user clicked this linked text, user will be gone in SignUp Pages,when he signed in, then he go to his own dashboard(USER|AGENT|ADMIN) according to his role and show fresh data according to his userId in everywhere in his dashboard*

### Updated Notes : 

* *Now we update our auth process convert into token based system.Token can stored by using SharedPreferences*
* *When user sign up or sign in successfully then user get a token, this token is used for authentication and authorization in subsequent API requests. User can store this token in SharedPreferences for future use. When user log out then we can remove this token from SharedPreferences*
* *Token will be sent to backend in every request, in this case, here can be used interceptor like Okhttp*


