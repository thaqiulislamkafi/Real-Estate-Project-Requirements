
## Property Management

### 1. Get All Properties

**Access:** Public  
**Description:** Retrieve a list of all available properties

#### Endpoint

```
GET /api/v1/property
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
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": false
            }
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
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": false
            }
        }
    ]
}
        
```

---

### 2. Get Property Details

**Access:** Public  
**Description:** Retrieve detailed information about a specific property

#### Endpoint

```
GET /api/v1/property/:id
```
#### Success Response (201 Created)
```json
{
    "success": true,
    "message": "Property details retrieved successfully",
    "data": {
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
        "agent": {
            "id": "508f7879-e762-4666-869f-539c017df80a",
            "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
            "isVerified": false,
            "isFraud": false
        }
    }
}
        
```

### 3. Add Property

**Access:** Agent  
**Description:** Add a new property to the system

#### Form Fields

| Field        | Type   | Description                                         | Required                            |
| ------------ | ------ | --------------------------------------------------- | ----------------------------------- |
| agentId      | UUID   | ID of the agent adding the property                 | Yes                                 |
| title        | String | Title of the property                               | Min 3 Characters                    |
| description  | String | Detailed description of the property                | Min 10 Characters                   |
| imageUrl     | String | URL of the property image                           | Must be a valid URL                 |
| location     | String | Location of the property                            | Min 3 Characters                    |
| priceRange   | String | Price range for the property                        | Min 3 Characters                    |
| propertyType | Enum   | Type of the property (HOUSE, APARTMENT, COMMERCIAL) | Must be one of the specified values |


#### Endpoint

```
POST /api/v1/property
```

#### Request Body

```json
{
    "agentId": "508f7879-e762-4666-869f-539c017df80a",
    "title": "Retail Shop in New Market",
    "description": "Busy retail location with high foot traffic.",
    "imageUrl": "https://example.com/images/newmarket-shop.jpg",
    "location": "New Market, Dhaka",
    "priceRange": "$2500-$3500",
    "propertyType": "COMMERCIAL"
}
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Property added successfully",
    "data": {
    "id": 1,
    "agentId": "508f7879-e762-4666-869f-539c017df80a",
    "title": "Retail Shop in New Market",
    "description": "Busy retail location with high foot traffic.",
    "imageUrl": "https://example.com/images/newmarket-shop.jpg",
    "location": "New Market, Dhaka",
    "priceRange": "$2500-$3500",
    "propertyType": "COMMERCIAL",
    "isVerified": false,
    "isAdvertised": false,
    "isBought": false,
    "generatedAt": "2026-03-25T15:27:11.923Z",
    "updatedAt": "2026-03-25T15:27:11.923Z"
    }
}
        
```

---

### 3. Update Property

**Access:** Agent  
**Description:** Update details of an existing property

#### Form Fields

| Field        | Type   | Description                                         | Required                            |
| ------------ | ------ | --------------------------------------------------- | ----------------------------------- |
| title        | String | Title of the property                               | Min 3 Characters                    |
| description  | String | Detailed description of the property                | Min 10 Characters                   |
| imageUrl     | String | URL of the property image                           | Must be a valid URL                 |
| location     | String | Location of the property                            | Min 3 Characters                    |
| priceRange   | String | Price range for the property                        | Min 3 Characters                    |
| propertyType | Enum   | Type of the property (HOUSE, APARTMENT, COMMERCIAL) | Must be one of the specified values |

#### Endpoint

```
PUT /api/v1/property/:id
```
#### Request Body

```json

{
    "title": "Updated Retail Shop in New Market",
    "description": "Updated description for the retail shop.",
    "imageUrl": "https://example.com/images/newmarket-shop-updated.jpg",
    "location": "New Market, Dhaka",
    "priceRange": "$3000-$4000",
    "propertyType": "COMMERCIAL"
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Property updated successfully",
    "data": {
        "id": 3,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "title": "Family House",
        "description": "Cozy family house with garden, parking, and easy highway access.",
        "imageUrl": "https://example.com/images/family-house.jpg",
        "location": "Purbachal, Dhaka",
        "priceRange": "$2000-$2500",
        "propertyType": "HOUSE",
        "isVerified": false,
        "isAdvertised": false,
        "isBought": false,
        "generatedAt": "2026-03-25T15:29:13.081Z",
        "updatedAt": "2026-04-03T04:22:56.900Z"
    }
}
        
```

---

### 4. Delete Property

**Access:** Agent / Admin  
**Description:** Delete a property from the system

#### Endpoint

```
DELETE /api/v1/property/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Property deleted successfully",
    "data": {
        "id": 3,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "title": "Family House",
        "description": "Cozy family house with garden, parking, and easy highway access.",
        "imageUrl": "https://example.com/images/family-house.jpg",
        "location": "Purbachal, Dhaka",
        "priceRange": "$2000-$2500",
        "propertyType": "HOUSE",
        "isVerified": false,
        "isAdvertised": false,
        "isBought": false,
        "generatedAt": "2026-03-25T15:29:13.081Z",
        "updatedAt": "2026-04-03T04:22:56.900Z",
    }
}
        
```

---

### 5. Get Properties by Agent

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

← [Back to Main Documentation](./../README.md)
