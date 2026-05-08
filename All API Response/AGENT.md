
## Agent Management

### 1. Get All Agents
**Access:** Admin  
**Description:** Retrieve a list of all registered agents

#### Endpoint

```
GET /api/v1/agent
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Agents retrieved successfully",
    "data": [
        {
            "id": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
            "userId": "e09213da-bab4-4f99-9c46-324c329db9f0",
            "isVerified": false,
            "isFraud": false,
            "user": {
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
        },
        {
            "id": "508f7879-e762-4666-869f-539c017df80a",
            "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
            "isVerified": false,
            "isFraud": false,
            "user": {
                "id": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "name": "Rashed Hossain",
                "email": "rashed.hossain@gmail.com",
                "password": "$2b$10$6nbKZfQXAor.c4qQr53qGeW0cRtO0Wd5tG.CNwaOa4do/VSL.jOLy",
                "emailVerified": false,
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
                "role": "AGENT",
                "status": "active",
                "contactNumber": "+8801812345678",
                "address": "Khulna, Bangladesh",
                "generatedAt": "2026-03-25T15:06:09.054Z",
                "updatedAt": "2026-04-25T13:29:03.391Z"
            }
        }
    ]
}

```

### 2. Get Agent Details

**Access:** Admin  
**Description:** Retrieve detailed information about a specific agent

#### Endpoint

```
GET /api/v1/agent/:id
```

#### Success Response (200 OK)

```json

{
            "id": "508f7879-e762-4666-869f-539c017df80a",
            "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
            "isVerified": false,
            "isFraud": false,
            "user": {
                "id": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "name": "Rashed Hossain",
                "email": "rashed.hossain@gmail.com",
                "password": "$2b$10$6nbKZfQXAor.c4qQr53qGeW0cRtO0Wd5tG.CNwaOa4do/VSL.jOLy",
                "emailVerified": false,
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
                "role": "AGENT",
                "status": "active",
                "contactNumber": "+8801812345678",
                "address": "Khulna, Bangladesh",
                "generatedAt": "2026-03-25T15:06:09.054Z",
                "updatedAt": "2026-04-25T13:29:03.391Z"
            }
        }

```

---

### 3. Get Properties by Agent

**Access:** Agent  
**Description:** Retrieve all properties listed by a specific agent

#### Endpoint

```
GET /api/v1/property/agent/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Properties retrieved successfully",
    "data": [
        {
            "id": 1,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "title": "Commercial Shop Space",
            "description": "Street-facing commercial space suitable for retail or small office setup.",
            "imageUrl": "https://example.com/images/commercial-shop.jpg",
            "location": "GEC Circle, Chattogram",
            "priceRange": "$1500-$1900",
            "propertyType": "COMMERCIAL",
            "isVerified": false,
            "isAdvertised": false,
            "isBought": false,
            "generatedAt": "2026-03-25T15:27:11.923Z",
            "updatedAt": "2026-03-25T15:27:11.923Z",
        },
        {
            "id": 2,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "title": "Luxury Apartment in Gulshan",
            "description": "Modern fully furnished apartment with rooftop access and 24/7 security in the heart of Gulshan.",
            "imageUrl": "https://example.com/images/gulshan-apartment.jpg",
            "location": "Gulshan-2, Dhaka",
            "priceRange": "$2000-$2500",
            "propertyType": "COMMERCIAL",
            "isVerified": false,
            "isAdvertised": false,
            "isBought": false,
            "generatedAt": "2026-03-25T15:27:57.790Z",
            "updatedAt": "2026-03-25T15:27:57.790Z",
        }
    ]
}
        
```

---

### 4. Make Agent verified

**Access:** Admin
**Description:** Mark an agent as verified

#### Endpoint

```
PUT /api/v1/agent/verify-agent/:id
```

#### Request Body

```json

{
    "isVerified" : true
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Agent verified successfully",
    "data": {
        "id": "7ff640de-a091-41d9-af5e-1a727674e398",
        "userId": "3b95b14d-d66e-43f1-ba3c-96318dc3fea4",
        "isVerified": true,
        "isFraud": false
    }
}

```

### 5. Mark Agent as Fraud

**Access:** Admin
**Description:** Mark an agent as fraudulent

#### Endpoint

```
PUT /api/v1/agent/fraud-agent/:id
```

#### Request Body

```json

{
    "isFraud" : true
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Agent marked as fraud successfully and unverified",
    "data": {
        "id": "7ff640de-a091-41d9-af5e-1a727674e398",
        "userId": "3b95b14d-d66e-43f1-ba3c-96318dc3fea4",
        "isVerified": true,
        "isFraud": true
    }
}

```

### 6. Mark Agent as Not Fraud

**Access:** Admin
**Description:** Mark an agent as not fraudulent

#### Endpoint

```
PUT /api/v1/agent/fraud-agent/:id
```

#### Request Body

```json

{
    "isFraud" : false
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Agent marked as UnFraud successfully",
    "data": {
        "id": "7ff640de-a091-41d9-af5e-1a727674e398",
        "userId": "3b95b14d-d66e-43f1-ba3c-96318dc3fea4",
        "isVerified": true,
        "isFraud": false
    }
}

```

### 7. Delete Agent

**Access:** Admin
**Description:** Delete an agent from the system

#### Endpoint

```
DELETE /api/v1/agent/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Agent deleted successfully",
    "data": {
        "id": "7ff640de-a091-41d9-af5e-1a727674e398",
        "userId": "3b95b14d-d66e-43f1-ba3c-96318dc3fea4",
        "isVerified": false,
        "isFraud": false
    }
}

```

---

### Note :

* *In Admin Dashboard, in Manage Agents Section, here must be Make Fraud and Make Verified buttons for each agent card. Admin can delete any agent.So, here must be delete icon in agent card.he can also visit a specific agent details*

### Update :

* *In Admin Dashboard, in Manage Agents Section, we bring out UnFraud system, so implement it into Manage agents in admin dashboard.So, it can be added another icon or linked text for the UnFraud functionality in each agent card item.*