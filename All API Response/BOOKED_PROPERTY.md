
## Booked Property Management

### 1. Get All Booked Properties

**Access:** Admin  
**Description:** Retrieve a list of all booked properties in the app

#### Endpoint

```
GET /api/v1/booked-property
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Booked properties retrieved successfully",
    "data": [
        {
            "id": 2,
            "propertyId": 2,
            "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
            "agentId": "7ff640de-a091-41d9-af5e-1a727674e398",
            "proposedAmount": "$1200",
            "isPropAmountAccepted": false,
            "isSold": false,
            "bookedAt": "2026-03-27T13:05:48.978Z",
            "updatedAt": "2026-03-27T13:05:48.978Z",
            "property": {
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
                "updatedAt": "2026-03-25T15:27:57.790Z"
            },
            "agent": {
                "id": "7ff640de-a091-41d9-af5e-1a727674e398",
                "userId": "3b95b14d-d66e-43f1-ba3c-96318dc3fea4",
                "isVerified": false,
                "isFraud": false
            },
            "user": {
                "id": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
                "name": "Mehedi Hasan",
                "email": "mehedi.hasan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        },
        {
            "id": 3,
            "propertyId": 3,
            "userId": "a80ecf75-dac4-4850-bb37-462bdcf9e726",
            "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
            "proposedAmount": "$5000",
            "isPropAmountAccepted": false,
            "isSold": false,
            "bookedAt": "2026-03-27T13:06:05.746Z",
            "updatedAt": "2026-03-27T13:06:05.746Z",
            "property": {
                "id": 3,
                "agentId": "508f7879-e762-4666-869f-539c017df80a",
                "title": "Family House",
                "description": "Amazing family house with garden, parking, and easy highway access.",
                "imageUrl": "https://example.com/images/family-house.jpg",
                "location": "Purbachal,Dhaka",
                "priceRange": "$2000-$2500",
                "propertyType": "HOUSE",
                "isVerified": false,
                "isAdvertised": false,
                "isBought": false,
                "generatedAt": "2026-03-25T15:29:13.081Z",
                "updatedAt": "2026-04-03T05:44:52.281Z"
            },
            "agent": {
                "id": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
                "userId": "e09213da-bab4-4f99-9c46-324c329db9f0",
                "isVerified": false,
                "isFraud": false
            },
            "user": {
                "id": "a80ecf75-dac4-4850-bb37-462bdcf9e726",
                "name": "Fatema Begum",
                "email": "fatema.begum@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        }
    ]
}
        
```

### 2. Get Booked Property Details  

**Access:** User / Admin  
**Description:** Retrieve detailed information about a specific booked property

#### Endpoint

```
GET /api/v1/booked-property/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Booked property details retrieved successfully",
    "data": {
        "id": 2,
        "propertyId": 2,
        "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
        "agentId": "7ff640de-a091-41d9-af5e-1a727674e398",
        "proposedAmount": "$1200",
        "isPropAmountAccepted": false,
        "isSold": false,
        "bookedAt": "2026-03-27T13:05:48.978Z",
        "updatedAt": "2026-03-27T13:05:48.978Z",
        "property": {
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
            "updatedAt": "2026-03-25T15:27:57.790Z"
        },
        "agent": {
            "id": "7ff640de-a091-41d9-af5e-1a727674e398",
            "userId": "3b95b14d-d66e-43f1-ba3c-96318dc3fea4",
            "isVerified": false,
            "isFraud": false
        },
        "user": {
            "id": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
            "name": "Mehedi Hasan",
            "email": "mehedi.hasan@example.com",
            "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
        }
    }
}

        
```

### 3. Post Booked Property

**Access:** User  
**Description:** Book a property by proposing an amount to the agent

#### Endpoint

```
POST /api/v1/booked-property
```

#### Request Body

```json

{
    "propertyId": 7,
    "userId": "a80ecf75-dac4-4850-bb37-462bdcf9e726",
    "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
    "proposedAmount": "$3500",
    "isPropAmountAccepted": false,
    "isSold": false
}

```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Property booked successfully",
    "data": {
        "id": 4,
        "propertyId": 7,
        "userId": "a80ecf75-dac4-4850-bb37-462bdcf9e726",
        "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
        "proposedAmount": "$3500",
        "isPropAmountAccepted": false,
        "isSold": false,
        "bookedAt": "2026-04-03T18:25:30.123Z",
        "updatedAt": "2026-04-03T18:25:30.123Z"
    }
}
        
```

<!-- here property data can updated as isPropAmountAccepted field update or proposedAmount field update or isSold field update -->

### 4. Update Booked Property Status

**Access:** Agent / Admin  
**Description:** Update the status of a booked property (accept/reject proposed amount, mark as sold)

#### Endpoint

```
PUT /api/v1/booked-property/:id
```

#### Request Body

```json

{
    "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
    "agentId": "508f7879-e762-4666-869f-539c017df80a",
    "isPropAmountAccepted" : true
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Booked property status updated successfully",
    "data": {
        "id": 2,
        "propertyId": 2,
        "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
        "agentId": "7ff640de-a091-41d9-af5e-1a727674e398",
        "proposedAmount": "$1200",
        "isPropAmountAccepted": true,
        "isSold": false,
        "bookedAt": "2026-03-27T13:05:48.978Z",
        "updatedAt": "2026-04-03T18:30:45.456Z"
    }
}
        
```

### 5. Get Booked Properties by UserId

**Access:** User / Admin  
**Description:** Retrieve all booked properties for a specific user

#### Endpoint

```
GET /api/v1/booked-property/user/:userId
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Booked properties retrieved successfully",
    "data": [
        {
            "id": 2,
            "propertyId": 2,
            "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
            "agentId": "7ff640de-a091-41d9-af5e-1a727674e398",
            "proposedAmount": "$1200",
            "isPropAmountAccepted": false,
            "isSold": false,
            "bookedAt": "2026-03-27T13:05:48.978Z",
            "updatedAt": "2026-03-27T13:05:48.978Z",
            "property": {
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
                "updatedAt": "2026-03-25T15:27:57.790Z"
            },
            "agent": {
                "id": "7ff640de-a091-41d9-af5e-1a727674e398",
                "userId": "3b95b14d-d66e-43f1-ba3c-96318dc3fea4",
                "isVerified": false,
                "isFraud": false
            },
            "user": {
                "id": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
                "name": "Mehedi Hasan",
                "email": "meheedi.hasan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        }
    ]
}

        
```

