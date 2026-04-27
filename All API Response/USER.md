
## User Management

### 1. Get All Users

**Access:** Admin  
**Description:** Retrieve a list of all registered users

#### Endpoint

```
GET /api/v1/auth
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Users retrieved successfully",
    "data": [
        {
            "id": "c68cb6ae-244d-4c0e-83bd-339cef029b52",
            "name": "Robiul Hossain",
            "email": "robiulhossain@outlook.com",
            "password": "$2b$10$xBT7GjSYOLdCVgiiAhj1d.N/lV1fdS0GfnrXLicz/Kk84xNrnZg1y",
            "emailVerified": false,
            "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
            "role": "USER",
            "status": "active",
            "contactNumber": "+8801512345679",
            "address": "Chittagong, Bangladesh",
            "generatedAt": "2026-04-26T15:49:23.571Z",
            "updatedAt": "2026-04-26T15:49:23.571Z"
        },
        {
            "id": "e5592ed8-103a-407e-960b-28594e85cfff",
            "name": "Abdul Hannan",
            "email": "abdul.hannan@example.com",
            "password": "hannan123456",
            "emailVerified": false,
            "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
            "role": "ADMIN",
            "status": "active",
            "contactNumber": "+8801812345678",
            "address": "Chittagong, Bangladesh",
            "generatedAt": "2026-03-25T14:17:43.469Z",
            "updatedAt": "2026-03-25T14:17:43.469Z"
        },
        {
            "id": "e09213da-bab4-4f99-9c46-324c329db9f0",
            "name": "Shaiful Islam",
            "email": "shaifulislam@gmail.com",
            "password": "shaiful123456",
            "emailVerified": false,
            "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
            "role": "AGENT",
            "status": "active",
            "contactNumber": "+8801512345678",
            "address": "Chattogram, Bangladesh",
            "generatedAt": "2026-03-25T15:01:51.530Z",
            "updatedAt": "2026-03-25T15:01:51.530Z"
        }
    ]
}

```

### 2. Get User Details

**Access:** User / Admin  
**Description:** Retrieve detailed information about a specific user

#### Endpoint

```
GET /api/v1/auth/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "User details retrieved successfully",
    "data": {
            "id": "c68cb6ae-244d-4c0e-83bd-339cef029b52",
            "name": "Robiul Hossain",
            "email": "robiulhossain@outlook.com",
            "password": "$2b$10$xBT7GjSYOLdCVgiiAhj1d.N/lV1fdS0GfnrXLicz/Kk84xNrnZg1y",
            "emailVerified": false,
            "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
            "role": "USER",
            "status": "active",
            "contactNumber": "+8801512345679",
            "address": "Chittagong, Bangladesh",
            "generatedAt": "2026-04-26T15:49:23.571Z",
            "updatedAt": "2026-04-26T15:49:23.571Z"
        }
}

```

---

### 3. Update User Details

**Access:** User / Admin  
**Description:** Update information for a specific user

#### Endpoint

```
PUT /api/v1/auth/update-profile/:id
```

#### Request Body

```json

{
    "name": "Akash Chowdhury",
    "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
    "contactNumber": "+8801812345678",
    "address": "Chittagong, Bangladesh"
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Profile updated successfully",
    "data": {
        "id": "b2eed1d3-5e87-448f-862d-b581b9a52296",
        "name": "Akash Chowdhury",
        "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
        "contactNumber": "+8801812345678",
        "address": "Chittagong, Bangladesh"
    }
}

```

### 4. Delete User

**Access:** Admin  
**Description:** Delete a user account from the system

#### Endpoint

```
DELETE /api/v1/auth/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "User deleted successfully",
    "data": {
        "id": "72dbd17d-0679-4322-94f3-4636787ed67e",
        "name": "Al Ehsan Foundation",
        "email": "alehsanfoundation21@gmail.com",
        "password": "$2b$10$dZLBgAOanN5/6i634h2/cuxPzAa.GcLfIlHS4YLt5StY5F4JbTN/K",
        "emailVerified": false,
        "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
        "role": "USER",
        "status": "active",
        "contactNumber": "+8801512345679",
        "address": "Chittagong, Bangladesh",
        "generatedAt": "2026-04-27T08:49:20.356Z",
        "updatedAt": "2026-04-27T08:49:20.356Z"
    }
}

```

### Note :

*In Admin Dashboard, in Manage Users Section, here must be update and delete button for each user card. Admin can update and delete any user.he can also visit a specific user details*

*In User Dashboard Profile, here must be update button. User can update own profile and he can view his own profile details*
