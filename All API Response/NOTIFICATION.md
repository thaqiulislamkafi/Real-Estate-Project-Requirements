
## Notification Management

### 1. Get All Notifications

**Access:** Admin  
**Description:** Retrieve a list of all notifications

#### Endpoint

```
GET /api/v1/notification
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Notifications retrieved successfully",
    "data": [
        {
            "id": "9352da86-1bf8-4cc2-b3f2-0e6567fb0fb8",
            "title": "New Agent Registrated",
            "message": "Mohammad Thaqi Ul Islam is new registrated as agent in our app",
            "receiverId": null,
            "receiverRole": "ADMIN",
            "generatedAt": "2026-05-07T06:31:41.814Z"
        },
        {
            "id": "f81c68f2-6db8-47d9-92fa-a30da40591af",
            "title": "User Deleted",
            "message": "Mohammad Thaqi Ul Islam deleted by Admin",
            "receiverId": null,
            "receiverRole": "ADMIN",
            "generatedAt": "2026-05-07T06:34:42.887Z"
        },
        {
            "id": "087e3ed7-f0a9-4ce3-b588-d511afad89b8",
            "title": "New User Registrated",
            "message": "Mohammad Thaqi Ul Islam is new user registrated in our app",
            "receiverId": null,
            "receiverRole": "ADMIN",
            "generatedAt": "2026-05-07T06:35:04.641Z"
        },
        {
            "id": "d3c68112-3da6-4137-a4b3-15dbc02dcdf7",
            "title": "Changing Password",
            "message": "Mohammad Thaqi Ul Islam changed his password",
            "receiverId": null,
            "receiverRole": "ADMIN",
            "generatedAt": "2026-05-07T06:36:51.755Z"
        },
        {
            "id": "5329eae4-53bb-44f5-afdd-5f7486e78b24",
            "title": "New Property Booked",
            "message": "Check your property list",
            "receiverId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
            "receiverRole": "AGENT",
            "generatedAt": "2026-05-07T07:56:46.816Z"
        },
        {
            "id": "6b263d32-5160-408e-9e43-83ab47c86978",
            "title": "New Property Sold",
            "message": "Check your property list",
            "receiverId": "508f7879-e762-4666-869f-539c017df80a",
            "receiverRole": "AGENT",
            "generatedAt": "2026-05-07T07:59:21.724Z"
        }
    ]
}

```

---

### 2. Get Notifications by ReceiverId

**Access:** User / Agent 
**Description:** Retrieve notifications for a specific user or agent

#### Endpoint

```
GET /api/v1/notification/user/:userId
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Notification fetched Successfuly for 913fc870-beba-44de-9a0d-98b3c79ddb2c id",
    "data": [
        {
            "id": "5329eae4-53bb-44f5-afdd-5f7486e78b24",
            "title": "New Property Booked",
            "message": "Check your property list",
            "receiverId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
            "receiverRole": "AGENT",
            "generatedAt": "2026-05-07T07:56:46.816Z"
        }
    ]
}

```

---

### 3. Delete Notification 

**Access:** Admin
**Description:** Delete a specific notification

#### Endpoint

```
DELETE /api/v1/notification/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Notification deleted successfully",
    "data": {
        "id": "0f0096b7-8859-4f67-8888-9ceb6882d194",
        "title": "New Review Added",
        "message": "Mohammad Thaqi Ul Islam reviewed in Smart House property",
        "receiverId": null,
        "receiverRole": "ADMIN",
        "generatedAt": "2026-05-07T08:06:10.981Z"
    }
}

```

---